---
Description: Computes unit normals for each vertex in a mesh. Provided to support legacy applications. Use D3DXComputeTangentFrameEx for better results.
ms.assetid: 7c879149-2c4c-4824-9604-e88696cc6ddc
title: D3DXComputeNormals function (D3DX9Mesh.h)
ms.topic: reference
ms.date: 05/31/2018
topic_type: 
- APIRef
- kbSyntax
api_name: 
- D3DXComputeNormals
api_type: 
- LibDef
api_location: 
- d3dx9.lib
- d3dx9.dll
---

# D3DXComputeNormals function

Computes unit normals for each vertex in a mesh. Provided to support legacy applications. Use [**D3DXComputeTangentFrameEx**](d3dxcomputetangentframeex.md) for better results.

## Syntax


```C++
HRESULT D3DXComputeNormals(
  _Inout_       LPD3DXBASEMESH pMesh,
  _In_    const DWORD          *pAdjacency
);
```



## Parameters

<dl> <dt>

*pMesh* \[in, out\]
</dt> <dd>

Type: **[**LPD3DXBASEMESH**](id3dxbasemesh.md)**

Pointer to an [**ID3DXBaseMesh**](id3dxbasemesh.md) interface, representing the normalized mesh object.

</dd> <dt>

*pAdjacency* \[in\]
</dt> <dd>

Type: **const [**DWORD**](https://msdn.microsoft.com/en-us/library/Aa383751(v=VS.85).aspx)\***

Pointer to an array of three DWORDs per face that specify the three neighbors for each face in the created progressive mesh. This parameter is optional and should be set to **NULL** if it is unused.

</dd> </dl>

## Return value

Type: **[**HRESULT**](https://msdn.microsoft.com/en-us/library/Bb401631(v=MSDN.10).aspx)**

If the function succeeds, the return value is S\_OK. If the function fails, the return value can be one of the following: D3DERR\_INVALIDCALL, D3DXERR\_INVALIDDATA, E\_OUTOFMEMORY.

## Remarks

The input mesh must have the [D3DFVF\_NORMAL](d3dfvf.md) flag specified in its flexible vertex format (FVF).

A normal for a vertex is generated by averaging the normals of all faces that share that vertex.

If adjacency is provided, replicated vertices are ignored and "smoothed" over. If adjacency is not provided, replicated vertices will have normals averaged in from only the faces explicitly referencing them.

This function simply calls [**D3DXComputeTangentFrameEx**](d3dxcomputetangentframeex.md) with the following input parameters:


```
D3DXComputeTangentFrameEx( pMesh,
                           D3DX_DEFAULT,
                           0,
                           D3DX_DEFAULT,
                           0,
                           D3DX_DEFAULT,
                           0,
                           D3DDECLUSAGE_NORMAL,
                           0,
                           D3DXTANGENT_GENERATE_IN_PLACE | D3DXTANGENT_CALCULATE_NORMALS,
                           pAdjacency,
                           -1.01f,
                           -0.01f,
                           -1.01f,
                           NULL,
                           NULL);
```



## Requirements



|                    |                                                                                        |
|--------------------|----------------------------------------------------------------------------------------|
| Header<br/>  | <dl> <dt>D3DX9Mesh.h</dt> </dl> |
| Library<br/> | <dl> <dt>D3dx9.lib</dt> </dl>   |



## See also

<dl> <dt>

[Mesh Functions](dx9-graphics-reference-d3dx-functions-mesh.md)
</dt> </dl>

 

 




