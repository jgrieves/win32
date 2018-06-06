---
Description: Rotates a quaternion about an arbitrary axis.
ms.assetid: 9673ef89-458f-4a25-960e-8f03179e78ba
title: D3DXQuaternionRotationAxis function
ms.technology: desktop
ms.prod: windows
ms.author: windowssdkdev
ms.topic: article
ms.date: 05/31/2018
---

# D3DXQuaternionRotationAxis function

Rotates a quaternion about an arbitrary axis.

## Syntax


```C++
D3DXQUATERNION* D3DXQuaternionRotationAxis(
  _Inout_       D3DXQUATERNION *pOut,
  _In_    const D3DXVECTOR3    *pV,
  _In_          FLOAT          Angle
);
```



## Parameters

<dl> <dt>

*pOut* \[in, out\]
</dt> <dd>

Type: **[**D3DXQUATERNION**](https://msdn.microsoft.com/VS|directx_sdk|~\d3dxquaternion.htm)\***

Pointer to the [**D3DXQUATERNION**](d3d10-d3dxquaternion.md) that is the result of the operation.

</dd> <dt>

*pV* \[in\]
</dt> <dd>

Type: **const [**D3DXVECTOR3**](https://msdn.microsoft.com/VS|directx_sdk|~\d3dxvector3.htm)\***

Pointer to the [**D3DXVECTOR3**](d3d10-d3dxvector3.md) that identifies the axis about which to rotate the quaternion.

</dd> <dt>

*Angle* \[in\]
</dt> <dd>

Type: **[**FLOAT**](https://msdn.microsoft.com/4553cafc-450e-4493-a4d4-cb6e2f274d46)**

Angle of rotation, in radians. Angles are measured clockwise when looking along the rotation axis toward the origin.

</dd> </dl>

## Return value

Type: **[**D3DXQUATERNION**](https://msdn.microsoft.com/VS|directx_sdk|~\d3dxquaternion.htm)\***

Pointer to a D3DXQUATERNION structure rotated around the specified axis.

## Remarks

The return value for this function is the same value returned in the pOut parameter. In this way, the D3DXQuaternionRotationAxis function can be used as a parameter for another function.

Use [**D3DXQuaternionNormalize**](d3d10-d3dxquaternionnormalize.md) for any quaternion input that is not already normalized.

## Requirements



|                    |                                                                                         |
|--------------------|-----------------------------------------------------------------------------------------|
| Header<br/>  | <dl> <dt>D3DX10Math.h</dt> </dl> |
| Library<br/> | <dl> <dt>D3DX10.lib</dt> </dl>   |



## See also

<dl> <dt>

[Math Functions](d3d10-graphics-reference-d3dx10-functions-math.md)
</dt> </dl>

 

 



