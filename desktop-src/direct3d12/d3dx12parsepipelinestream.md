---
title: D3DX12ParsePipelineStream function
description: Parses a pipeline state stream description, calling a user-defined callback for each subobject instance parsed.
ms.assetid: 'BE4E8CC4-1E1F-4FE8-B109-05FAF93EB620'
keywords: ["D3DX12ParsePipelineStream function"]
topic_type:
- apiref
api_name:
- D3DX12ParsePipelineStream
api_location:
- D3D12.dll
api_type:
- DllExport
---

# D3DX12ParsePipelineStream function

Parses a pipeline state stream description, calling a user-defined callback for each subobject instance parsed.

## Syntax


```C++
HRESULT inline D3DX12ParsePipelineStream(
  �const D3D12_PIPELINE_STATE_STREAM_DESC &amp;Desc,
  �������ID3DX12PipelineParserCallbacks ��*pCallbacks
);
```



## Parameters

<dl> <dt>

*Desc* \[ref\]
</dt> <dd>

Type: **const [**D3D12\_PIPELINE\_STATE\_STREAM\_DESC**](d3d12-pipeline-state-stream-desc.md)**

The pipeline state stream description to parse.

</dd> <dt>

*pCallbacks* 
</dt> <dd>

Type: **[**ID3DX12PipelineParserCallbacks**](id3dx12pipelineparsercallbacks.md)\***

A structure that specifies the callbacks to call for each subobject type and additional callbacks to call in the event of a parsing error.

</dd> </dl>

## Return value

Type: **[**HRESULT**](455d07e9-52c3-4efb-a9dc-2955cbfd38cc)**

This method returns an HRESULT success (**S\_OK** or **E\_INVALIDARG** error if an unknown subobject type is encountered, if the stream description is empty, null, or contains duplicate subobjects (including derived subobjects), or if *pCallbacks* is null. In each case that E\_INVALIDARG is returned, a corresponding callback is first called.

## Requirements



|                    |                                                                                      |
|--------------------|--------------------------------------------------------------------------------------|
| Header<br/>  | <dl> <dt>D3dx12.h</dt> </dl>  |
| Library<br/> | <dl> <dt>D3D12.lib</dt> </dl> |
| DLL<br/>     | <dl> <dt>D3D12.dll</dt> </dl> |



## See also

<dl> <dt>

[Helper Functions for D3D12](helper-functions-for-d3d12.md)
</dt> </dl>

�

�




