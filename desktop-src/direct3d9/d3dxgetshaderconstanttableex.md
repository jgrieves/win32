---
Description: Gets the shader-constant table embedded inside a shader.
ms.assetid: f7e846e4-9cb4-4634-95e3-4b2a752978a8
title: D3DXGetShaderConstantTableEx function (D3DX9Shader.h)
ms.topic: reference
ms.date: 05/31/2018
topic_type: 
- APIRef
- kbSyntax
api_name: 
- D3DXGetShaderConstantTableEx
api_type: 
- LibDef
api_location: 
- d3dx9.lib
- d3dx9.dll
---

# D3DXGetShaderConstantTableEx function

Gets the shader-constant table embedded inside a shader.

## Syntax


```C++
HRESULT D3DXGetShaderConstantTableEx(
  _In_  const DWORD               *pFunction,
  _In_        DWORD               Flags,
  _Out_       LPD3DXCONSTANTTABLE * ppConstantTable
);
```



## Parameters

<dl> <dt>

*pFunction* \[in\]
</dt> <dd>

Type: **const [**DWORD**](https://msdn.microsoft.com/en-us/library/Aa383751(v=VS.85).aspx)\***

Pointer to the function DWORD stream.

</dd> <dt>

*Flags* \[in\]
</dt> <dd>

Type: **[**DWORD**](https://msdn.microsoft.com/en-us/library/Aa383751(v=VS.85).aspx)**

Use the D3DXCONSTTABLE\_LARGEADDRESSAWARE flag to access up to 4 GB of virtual address space (instead of the default of 2 GB). If you do not need the additional virtual address space, use [**D3DXGetShaderConstantTable**](d3dxgetshaderconstanttable.md).

</dd> <dt>

 *ppConstantTable* \[out\]
</dt> <dd>

Type: **[**LPD3DXCONSTANTTABLE**](id3dxconstanttable.md)\***

Returns the constant table interface (see [**ID3DXConstantTable**](id3dxconstanttable.md)) that manages the constant table.

</dd> </dl>

## Return value

Type: **[**HRESULT**](https://msdn.microsoft.com/en-us/library/Bb401631(v=MSDN.10).aspx)**

If the function succeeds, the return value is D3D\_OK. If the function fails, the return value can be one of the following: D3DERR\_INVALIDCALL, D3DXERR\_INVALIDDATA, E\_OUTOFMEMORY.

## Remarks

A constant table is generated by [**D3DXCompileShader**](d3dxcompileshader.md) and embedded in the shader body.

## Requirements



|                    |                                                                                          |
|--------------------|------------------------------------------------------------------------------------------|
| Header<br/>  | <dl> <dt>D3DX9Shader.h</dt> </dl> |
| Library<br/> | <dl> <dt>D3dx9.lib</dt> </dl>     |



## See also

<dl> <dt>

[Shader Functions](dx9-graphics-reference-d3dx-functions-shader.md)
</dt> </dl>

 

 




