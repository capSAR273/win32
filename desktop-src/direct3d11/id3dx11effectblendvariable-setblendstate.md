---
title: ID3DX11EffectBlendVariable SetBlendState method
description: Sets an effect's blend-state.
ms.assetid: '46100721-65a3-46de-aa22-3e7e2fb7b960'
keywords: ["SetBlendState method Direct3D 11", "SetBlendState method Direct3D 11 , ID3DX11EffectBlendVariable interface", "ID3DX11EffectBlendVariable interface Direct3D 11 , SetBlendState method"]
topic_type:
- apiref
api_name:
- ID3DX11EffectBlendVariable.SetBlendState
api_location:
- N/A
- N/A.dll
api_type:
- COM
---

# ID3DX11EffectBlendVariable::SetBlendState method

Sets an effect's blend-state.

## Syntax


```C++
HRESULT SetBlendState(
  �UINT ������������Index,
  �ID3D11BlendState *pBlendState
);
```



## Parameters

<dl> <dt>

*Index* 
</dt> <dd>

Type: **[**UINT**](https://msdn.microsoft.com/library/windows/desktop/aa383751)**

Index into an array of blend-state interfaces. If there is only one blend-state interface, use 0.

</dd> <dt>

*pBlendState* 
</dt> <dd>

Type: **[**ID3D11BlendState**](id3d11blendstate.md)\***

A pointer to an [**ID3D11BlendState**](id3d11blendstate.md) interface containing the blend-state to set.

</dd> </dl>

## Return value

Type: **[**HRESULT**](455d07e9-52c3-4efb-a9dc-2955cbfd38cc)**

Returns one of the following [Direct3D 11 Return Codes](d3d11-graphics-reference-returnvalues.md).

## Remarks

> [!Note]  
> The DirectX SDK does not supply any compiled binaries for effects. You must use Effects 11 source to build your effects-type application. For more information about using Effects 11 source, see [Differences Between Effects 10 and Effects 11](d3d11-graphics-programming-guide-effects-differences.md).

�

## Requirements



|                    |                                                                                                                                              |
|--------------------|----------------------------------------------------------------------------------------------------------------------------------------------|
| Header<br/>  | <dl> <dt>D3dx11effect.h</dt> </dl>                                                    |
| Library<br/> | <dl> <dt>N/A (An Effects 11 library is available online as shared source.)</dt> </dl> |



## See also

<dl> <dt>

[ID3DX11EffectBlendVariable](id3dx11effectblendvariable.md)
</dt> </dl>

�

�




