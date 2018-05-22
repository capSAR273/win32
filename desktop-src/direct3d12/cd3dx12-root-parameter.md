---
title: CD3DX12\_ROOT\_PARAMETER structure
description: A helper structure to enable easy initialization of a D3D12\_ROOT\_PARAMETER structure.
ms.assetid: 'CDDF84D0-4E66-4CF2-999B-3F401E8DD17F'
keywords: ["CD3DX12_ROOT_PARAMETER structure"]
topic_type:
- apiref
api_name:
- CD3DX12_ROOT_PARAMETER
api_location:
- d3dx12.h
api_type:
- HeaderDef
---

# CD3DX12\_ROOT\_PARAMETER structure

A helper structure to enable easy initialization of a [**D3D12\_ROOT\_PARAMETER**](d3d12-root-parameter.md) structure.

## Syntax


```C++
struct CD3DX12_ROOT_PARAMETER  : public D3D12_ROOT_PARAMETER{
   ����CD3DX12_ROOT_PARAMETER();
   ����explicit CD3DX12_ROOT_PARAMETER(const D3D12_ROOT_PARAMETER &amp;o);
  void static inline InitAsDescriptorTable(D3D12_ROOT_PARAMETER &amp;rootParam, UINT numDescriptorRanges, const D3D12_DESCRIPTOR_RANGE* pDescriptorRanges, D3D12_SHADER_VISIBILITY visibility = D3D12_SHADER_VISIBILITY_ALL);
  void static inline InitAsConstants(D3D12_ROOT_PARAMETER &amp;rootParam, UINT num32BitValues, UINT shaderRegister, UINT registerSpace = 0, D3D12_SHADER_VISIBILITY visibility = D3D12_SHADER_VISIBILITY_ALL);
  void static inline InitAsConstantBufferView(D3D12_ROOT_PARAMETER &amp;rootParam, UINT shaderRegister, UINT registerSpace = 0, D3D12_SHADER_VISIBILITY visibility = D3D12_SHADER_VISIBILITY_ALL);
  void static inline InitAsShaderResourceView(D3D12_ROOT_PARAMETER &amp;rootParam, UINT shaderRegister, UINT registerSpace = 0, D3D12_SHADER_VISIBILITY visibility = D3D12_SHADER_VISIBILITY_ALL);
  void static inline InitAsUnorderedAccessView(D3D12_ROOT_PARAMETER &amp;rootParam, UINT shaderRegister, UINT registerSpace = 0, D3D12_SHADER_VISIBILITY visibility = D3D12_SHADER_VISIBILITY_ALL);
  void inline InitAsDescriptorTable(UINT numDescriptorRanges, const D3D12_DESCRIPTOR_RANGE* pDescriptorRanges, D3D12_SHADER_VISIBILITY visibility = D3D12_SHADER_VISIBILITY_ALL);
  void inline InitAsConstants(UINT num32BitValues, UINT shaderRegister, UINT registerSpace = 0, D3D12_SHADER_VISIBILITY visibility = D3D12_SHADER_VISIBILITY_ALL);
  void inline InitAsConstantBufferView(UINT shaderRegister, UINT registerSpace = 0, D3D12_SHADER_VISIBILITY visibility = D3D12_SHADER_VISIBILITY_ALL);
  void inline InitAsShaderResourceView(UINT shaderRegister, UINT registerSpace = 0, D3D12_SHADER_VISIBILITY visibility = D3D12_SHADER_VISIBILITY_ALL);
  void inline InitAsUnorderedAccessView(UINT shaderRegister, UINT registerSpace = 0, D3D12_SHADER_VISIBILITY visibility = D3D12_SHADER_VISIBILITY_ALL);
};
```



## Members

<dl> <dt>

**CD3DX12\_ROOT\_PARAMETER()**
</dt> <dd>

Creates a new, uninitialized, instance of a CD3DX12\_ROOT\_PARAMETER.

</dd> <dt>

**explicit CD3DX12\_ROOT\_PARAMETER(const D3D12\_ROOT\_PARAMETER &o)**
</dt> <dd>

Creates a new instance of a CD3DX12\_ROOT\_PARAMETER, initialized with the contents of another [**D3D12\_ROOT\_PARAMETER**](d3d12-root-parameter.md) structure.

</dd> <dt>

**static inline InitAsDescriptorTable(D3D12\_ROOT\_PARAMETER &rootParam, UINT numDescriptorRanges, const D3D12\_DESCRIPTOR\_RANGE\* pDescriptorRanges, D3D12\_SHADER\_VISIBILITY visibility = D3D12\_SHADER\_VISIBILITY\_ALL)**
</dt> <dd>

Specifies a function that initializes the following parameters:

[**D3D12\_ROOT\_PARAMETER**](d3d12-root-parameter.md) &rootParam

UINT numDescriptorRanges

[**D3D12\_DESCRIPTOR\_RANGE**](d3d12-descriptor-range.md)\* pDescriptorRanges

(opt) [**D3D12\_SHADER\_VISIBILITY**](d3d12-shader-visibility.md) visibility = D3D12\_SHADER\_VISIBILITY\_ALL

</dd> <dt>

**static inline InitAsConstants(D3D12\_ROOT\_PARAMETER &rootParam, UINT num32BitValues, UINT shaderRegister, UINT registerSpace = 0, D3D12\_SHADER\_VISIBILITY visibility = D3D12\_SHADER\_VISIBILITY\_ALL)**
</dt> <dd>

Specifies a function that initializes the following parameters:

[**D3D12\_ROOT\_PARAMETER**](d3d12-root-parameter.md) &rootParam

UINT num32BitValues

UINT shaderRegister

(opt) UINT registerSpace = 0

(opt) [**D3D12\_SHADER\_VISIBILITY**](d3d12-shader-visibility.md) visibility = D3D12\_SHADER\_VISIBILITY\_ALL

</dd> <dt>

**static inline InitAsConstantBufferView(D3D12\_ROOT\_PARAMETER &rootParam, UINT shaderRegister, UINT registerSpace = 0, D3D12\_SHADER\_VISIBILITY visibility = D3D12\_SHADER\_VISIBILITY\_ALL)**
</dt> <dd>

Specifies a function that initializes the following parameters:

[**D3D12\_ROOT\_PARAMETER**](d3d12-root-parameter.md) &rootParam

UINT shaderRegister

(opt) UINT registerSpace = 0

(opt) [**D3D12\_SHADER\_VISIBILITY**](d3d12-shader-visibility.md) visibility = D3D12\_SHADER\_VISIBILITY\_ALL

</dd> <dt>

**static inline InitAsShaderResourceView(D3D12\_ROOT\_PARAMETER &rootParam, UINT shaderRegister, UINT registerSpace = 0, D3D12\_SHADER\_VISIBILITY visibility = D3D12\_SHADER\_VISIBILITY\_ALL)**
</dt> <dd>

Specifies a function that initializes the following parameters:

[**D3D12\_ROOT\_PARAMETER**](d3d12-root-parameter.md) &rootParam

UINT shaderRegister

(opt) UINT registerSpace = 0

(opt) [**D3D12\_SHADER\_VISIBILITY**](d3d12-shader-visibility.md) visibility = D3D12\_SHADER\_VISIBILITY\_ALL

</dd> <dt>

**static inline InitAsUnorderedAccessView(D3D12\_ROOT\_PARAMETER &rootParam, UINT shaderRegister, UINT registerSpace = 0, D3D12\_SHADER\_VISIBILITY visibility = D3D12\_SHADER\_VISIBILITY\_ALL)**
</dt> <dd>

Specifies a function that initializes the following parameters:

[**D3D12\_ROOT\_PARAMETER**](d3d12-root-parameter.md) &rootParam

UINT shaderRegister

(opt) UINT registerSpace = 0

(opt) [**D3D12\_SHADER\_VISIBILITY**](d3d12-shader-visibility.md) visibility = D3D12\_SHADER\_VISIBILITY\_ALL

</dd> <dt>

**inline InitAsDescriptorTable(UINT numDescriptorRanges, const D3D12\_DESCRIPTOR\_RANGE\* pDescriptorRanges, D3D12\_SHADER\_VISIBILITY visibility = D3D12\_SHADER\_VISIBILITY\_ALL)**
</dt> <dd>

Specifies a function that initializes the following parameters:

UINT numDescriptorRanges

[**D3D12\_DESCRIPTOR\_RANGE**](d3d12-descriptor-range.md)\* pDescriptorRanges

(opt) [**D3D12\_SHADER\_VISIBILITY**](d3d12-shader-visibility.md) visibility = D3D12\_SHADER\_VISIBILITY\_ALL

</dd> <dt>

**inline InitAsConstants(UINT num32BitValues, UINT shaderRegister, UINT registerSpace = 0, D3D12\_SHADER\_VISIBILITY visibility = D3D12\_SHADER\_VISIBILITY\_ALL)**
</dt> <dd>

Specifies a function that initializes the following parameters:

UINT num32BitValues

UINT shaderRegister

(opt) UINT registerSpace = 0

(opt) [**D3D12\_SHADER\_VISIBILITY**](d3d12-shader-visibility.md) visibility = D3D12\_SHADER\_VISIBILITY\_ALL

</dd> <dt>

**inline InitAsConstantBufferView(UINT shaderRegister, UINT registerSpace = 0, D3D12\_SHADER\_VISIBILITY visibility = D3D12\_SHADER\_VISIBILITY\_ALL)**
</dt> <dd>

Specifies a function that initializes the following parameters:

UINT shaderRegister

(opt) UINT registerSpace = 0

(opt) [**D3D12\_SHADER\_VISIBILITY**](d3d12-shader-visibility.md) visibility = D3D12\_SHADER\_VISIBILITY\_ALL

</dd> <dt>

**inline InitAsShaderResourceView(UINT shaderRegister, UINT registerSpace = 0, D3D12\_SHADER\_VISIBILITY visibility = D3D12\_SHADER\_VISIBILITY\_ALL)**
</dt> <dd>

Specifies a function that initializes the following parameters:

UINT shaderRegister

(opt) UINT registerSpace = 0

(opt) [**D3D12\_SHADER\_VISIBILITY**](d3d12-shader-visibility.md) visibility = D3D12\_SHADER\_VISIBILITY\_ALL

</dd> <dt>

**inline InitAsUnorderedAccessView(UINT shaderRegister, UINT registerSpace = 0, D3D12\_SHADER\_VISIBILITY visibility = D3D12\_SHADER\_VISIBILITY\_ALL)**
</dt> <dd>

Specifies a function that initializes the following parameters:

UINT shaderRegister

(opt) UINT registerSpace = 0

(opt) [**D3D12\_SHADER\_VISIBILITY**](d3d12-shader-visibility.md) visibility = D3D12\_SHADER\_VISIBILITY\_ALL

</dd> </dl>

## Requirements



|                   |                                                                                     |
|-------------------|-------------------------------------------------------------------------------------|
| Header<br/> | <dl> <dt>D3dx12.h</dt> </dl> |



## See also

<dl> <dt>

[**D3D12\_ROOT\_PARAMETER**](d3d12-root-parameter.md)
</dt> <dt>

[Helper Structures for D3D12](helper-structures-for-d3d12.md)
</dt> </dl>

�

�




