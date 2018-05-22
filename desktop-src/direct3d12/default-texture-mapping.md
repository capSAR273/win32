---
title: UMA Optimizations CPU Accessible Textures and Standard Swizzle
description: Universal Memory Architecture (UMA) GPUs offer some efficiency advantages over discrete GPUs, especially when optimizing for mobile devices.
ms.assetid: '26C41948-9625-4786-BBDF-552D1F8A2437'
---

# UMA Optimizations: CPU Accessible Textures and Standard Swizzle

Universal Memory Architecture (UMA) GPUs offer some efficiency advantages over discrete GPUs, especially when optimizing for mobile devices. Giving resources CPU access when the GPU is UMA can reduce the amount of copying that occurs between CPU and GPU. While we don’t recommend applications blindly give CPU access to all resources on UMA designs, there are opportunities to improve efficiencies by giving the right resources CPU access. Unlike discrete GPUs, the CPU can technically have a pointer to all resources that the GPU can access.

-   [Overview of CPU accessible textures](#overview-of-cpu-accessible-textures)
-   [Overview of Standard Swizzle](#overview-of-standard-swizzle)
-   [APIs](#apis)
-   [Related topics](#related-topics)

## Overview of CPU accessible textures

CPU accessible textures, in the graphics pipeline, are a feature of UMA architecture, enabling CPUs read and write access to textures. On the more common discreet GPUs, the CPU does not have access to textures in the graphics pipeline.

The general best practice advice for textures is to accommodate discrete GPUs, which typically involves following the processes in [Uploading Texture Data Through Buffers](upload-and-readback-of-texture-data.md), summarized as:

-   Not having any CPU access for the majority of textures.
-   Setting the texture layout to D3D12\_TEXTURE\_LAYOUT\_UNKNOWN.
-   Uploading the textures to the GPU with [**CopyTextureRegion**](id3d12graphicscommandlist-copytextureregion.md).

However, for certain cases, the CPU and GPU may interact so frequently on the same data, that mapping textures becomes helpful to save power, or to speed up a particular design on particular adapters or architectures. Applications should detect these cases and optimize out the unnecessary copies. In this case, for best performance consider the following:

-   Only start entertaining the better performance of mapping textures when [**D3D12\_FEATURE\_DATA\_ARCHITECTURE**](d3d12-feature-data-architecture.md)::UMA is TRUE. Then pay attention to *CacheCoherentUMA* if deciding which CPU cache properties to choose on the heap.

-   Leveraging CPU access for textures is more complicated than for buffers. The most efficient texture layouts for GPUs are rarely row\_major. In fact, some GPUs can only support row\_major textures when copying texture data around.

-   UMA GPUs should universally benefit from a simple optimization to reduce level-load times. After recognizing UMA, the application can optimize out the initial [**CopyTextureRegion**](id3d12graphicscommandlist-copytextureregion.md) to populate textures that the GPU will not modify. Instead of creating the texture in a heap with D3D12\_HEAP\_TYPE\_DEFAULT, and marshalling the texture data through, the application can use [**WriteToSubresource**](id3d12resource-writetosubresource.md) to avoid understanding the actual texture layout.

-   In D3D12, textures created with D3D12\_TEXTURE\_LAYOUT\_UNKNOWN and no CPU access are the most efficient for frequent GPU rendering and sampling. When performance testing, those textures should be compared against D3D12\_TEXTURE\_LAYOUT\_UNKNOWN with CPU access, and D3D12\_TEXTURE\_LAYOUT\_STANDARD\_SWIZZLE with CPU access, and D3D12\_TEXTURE\_LAYOUT\_ROW\_MAJOR for cross-adapter support.

-   Using D3D12\_TEXTURE\_LAYOUT\_UNKNOWN with CPU access enables the methods [**WriteToSubresource**](id3d12resource-writetosubresource.md), [**ReadFromSubresource**](id3d12resource-readfromsubresource.md), [**Map**](id3d12resource-map.md) (precluding application access to pointer), and [**Unmap**](id3d12resource-unmap.md); but can sacrifice efficiency of GPU access.

-   Using D3D12\_TEXTURE\_LAYOUT\_STANDARD\_SWIZZLE with CPU access enables [**WriteToSubresource**](id3d12resource-writetosubresource.md), [**ReadFromSubresource**](id3d12resource-readfromsubresource.md), [**Map**](id3d12resource-map.md) (which returns a valid pointer to application), and [**Unmap**](id3d12resource-unmap.md). It can also sacrifice the efficiency of GPU access more than D3D12\_TEXTURE\_LAYOUT\_UNKNOWN with CPU access.

## Overview of Standard Swizzle

D3D12 (and D3D11.3) introduce a standard multi-dimensional data layout. This is done to enable multiple processing units to operate on the same data without copying the data or swizzling the data between multiple layouts. A standardized layout enables efficiency gains through network effects and allows algorithms to make short-cuts assuming a particular pattern.

For a detailed description of the texture layouts, refer to [**D3D12\_TEXTURE\_LAYOUT**](d3d12-texture-layout.md).

Note though that this standard swizzle is a hardware feature, and may not be supported by all GPUs.

For background information on swizzling, refer to [Z-order curve](https://en.wikipedia.org/wiki/Z-order_curve).

## APIs

Unlike D3D11.3, D3D12 supports texture mapping by default, so there is no need to query [**D3D12\_FEATURE\_DATA\_D3D12\_OPTIONS**](d3d12-feature-data-d3d12-options.md). However D3D12 does not always support standard swizzle - this feature will need to be queried for with a call to [**CheckFeatureSupport**](id3d12device-checkfeaturesupport.md) and checking the *StandardSwizzle64KBSupported* field of **D3D12\_FEATURE\_DATA\_D3D12\_OPTIONS**.

The following APIs reference texture mapping:

Enums

-   [**D3D12\_TEXTURE\_LAYOUT**](d3d12-texture-layout.md) : controls the swizzle pattern of default textures and enable map support on CPU accessible textures.

Structures

-   [**D3D12\_RESOURCE\_DESC**](d3d12-resource-desc.md) : describes a resource, such as a texture, this is an extensively used structure.
-   [**D3D12\_HEAP\_DESC**](d3d12-heap-desc.md) : describes a heap.

Methods

-   [**ID3D12Device::CreateCommittedResource**](id3d12device-createcommittedresource.md) : creates a single resource and backing heap of the right size and alignment.
-   [**ID3D12Device::CreateHeap**](id3d12device-createheap.md) : creates a heap for a buffer or texture.
-   [**ID3D12Device::CreatePlacedResource**](id3d12device-createplacedresource.md) : creates a resource that is placed in a specific heap, usually a faster method of creating a resource than [**CreateHeap**](id3d12device-createheap.md).
-   [**ID3D12Device::CreateReservedResource**](id3d12device-createreservedresource.md) : creates a resource that is reserved but not yet committed or placed in a heap.
-   [**ID3D12CommandQueue::UpdateTileMappings**](id3d12commandqueue-updatetilemappings.md) : updates mappings of tile locations in tiled resources to memory locations in a resource heap.
-   [**ID3D12Resource::Map**](id3d12resource-map.md) : gets a pointer to the specified data in the resource, and denies the GPU access to the subresource.
-   [**ID3D12Resource::GetDesc**](id3d12resource-getdesc.md) : gets the resource properties.
-   [**ID3D12Heap::GetDesc**](id3d12heap-getdesc.md) gets the heap properties.
-   [**ReadFromSubresource**](id3d12resource-readfromsubresource.md) : copies data from a texture which was mapped using [**Map**](id3d12resource-map.md).
-   [**WriteToSubresource**](id3d12resource-writetosubresource.md) : copies data into a texture which was mapped using [**Map**](id3d12resource-map.md).

Resources and parent heaps have alignment requirements:

-   D3D12\_DEFAULT\_MSAA\_RESOURCE\_PLACEMENT\_ALIGNMENT (4MB) for multi-sample textures.
-   D3D12\_DEFAULT\_RESOURCE\_PLACEMENT\_ALIGNMENT (64KB) for single sample textures and buffers.
-   Linear subresource copying must be aligned to D3D12\_TEXTURE\_DATA\_PLACEMENT\_ALIGNMENT (512 bytes), with row pitch being aligned to D3D12\_TEXTURE\_DATA\_PITCH\_ALIGNMENT (256 bytes).
-   Constant buffer views must be aligned to D3D12\_CONSTANT\_BUFFER\_DATA\_PLACEMENT\_ALIGNMENT (256 bytes).

Textures smaller than 64KB should be processed through [**CreateCommittedResource**](id3d12device-createcommittedresource.md).

With dynamic textures (textures that change every frame) the CPU will write linearly to the upload heap, followed by a GPU copy operation.

Typically to create dynamic resources create a large buffer in an upload heap (refer to [Suballocation Within Buffers](large-buffers.md)). To create staging resources, create a large buffer in a readback heap. To create default static resources, create adjacent resources in a default heap. To create default aliased resources, create overlapping resources in a default heap.

[**WriteToSubresource**](id3d12resource-writetosubresource.md) and [**ReadFromSubresource**](id3d12resource-readfromsubresource.md) rearrange texture data between a row-major layout and an undefined resource layout. The operation is synchronous, so the application should keep CPU scheduling in mind. The application can always break up the copying into smaller regions or schedule this operation in another task. MSAA resources and depth-stencil resources with opaque resource layouts are not supported by these CPU copy operations, and will cause a failure. Formats which don’t have a power-of-two element size are also not supported and will also cause a failure. Out of memory return codes can occur.

## Related topics

<dl> <dt>

[**Core Constants**](constants.md)
</dt> <dt>

[**ID3D12Heap**](id3d12heap.md)
</dt> <dt>

[Resource Binding](resource-binding.md)
</dt> </dl>

 

 



