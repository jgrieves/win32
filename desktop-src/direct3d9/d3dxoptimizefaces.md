---
Description: Generates an optimized face remapping for a triangle list.
ms.assetid: 428c2af8-43e7-4cf7-8b9b-04ba5cff82c8
title: D3DXOptimizeFaces function
ms.technology: desktop
ms.prod: windows
ms.author: windowssdkdev
ms.topic: article
ms.date: 05/31/2018
---

# D3DXOptimizeFaces function

Generates an optimized face remapping for a triangle list.

## Syntax


```C++
HRESULT D3DXOptimizeFaces(
  _In_    LPCVOID pIndices,
  _In_    UINT    NumFaces,
  _In_    UINT    NumVertices,
  _In_    BOOL    Indices32Bit,
  _Inout_ DWORD   *pFaceRemap
);
```



## Parameters

<dl> <dt>

*pIndices* \[in\]
</dt> <dd>

Type: **[**LPCVOID**](https://msdn.microsoft.com/4553cafc-450e-4493-a4d4-cb6e2f274d46)**

Pointer to triangle list indices to use for ordering vertices.

</dd> <dt>

*NumFaces* \[in\]
</dt> <dd>

Type: **[**UINT**](https://msdn.microsoft.com/4553cafc-450e-4493-a4d4-cb6e2f274d46)**

Number of faces in the triangle list. For 16-bit meshes, this is limited to 2^16 - 1 (65535) or fewer faces.

</dd> <dt>

*NumVertices* \[in\]
</dt> <dd>

Type: **[**UINT**](https://msdn.microsoft.com/4553cafc-450e-4493-a4d4-cb6e2f274d46)**

Number of vertices referenced by the triangle list.

</dd> <dt>

*Indices32Bit* \[in\]
</dt> <dd>

Type: **[**BOOL**](https://msdn.microsoft.com/4553cafc-450e-4493-a4d4-cb6e2f274d46)**

Flag indicating index type: **TRUE** if indices are 32-bit (more than 65535 indices), **FALSE** if indices are 16-bit (65535 or fewer indices).

</dd> <dt>

*pFaceRemap* \[in, out\]
</dt> <dd>

Type: **[**DWORD**](https://msdn.microsoft.com/4553cafc-450e-4493-a4d4-cb6e2f274d46)\***

Pointer to the original mesh face that was split to generate the current face.

</dd> </dl>

## Return value

Type: **[**HRESULT**](https://msdn.microsoft.com/windows/desktop/455d07e9-52c3-4efb-a9dc-2955cbfd38cc)**

If the function succeeds, the return value is D3D\_OK. If the function fails, the return value can be one of the following: D3DERR\_INVALIDCALL, E\_OUTOFMEMORY.

## Remarks

This function's optimization procedure is functionally equivalent to calling [**ID3DXMesh::Optimize**](id3dxmesh--optimize.md) with the D3DXMESHOPT\_DEVICEINDEPENDENT flag, but this function makes more efficient use of vertex caches.

## Requirements



|                    |                                                                                        |
|--------------------|----------------------------------------------------------------------------------------|
| Header<br/>  | <dl> <dt>D3DX9Mesh.h</dt> </dl> |
| Library<br/> | <dl> <dt>D3dx9.lib</dt> </dl>   |



## See also

<dl> <dt>

[Mesh Functions](dx9-graphics-reference-d3dx-functions-mesh.md)
</dt> </dl>

 

 



