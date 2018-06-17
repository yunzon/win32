---
Description: Contains red, green, and blue ramp data.
ms.assetid: c596f47a-6c09-4b97-ab2f-b1da3d851aa4
title: D3DGAMMARAMP structure
ms.technology: desktop
ms.prod: windows
ms.author: windowssdkdev
ms.topic: structure
ms.date: 05/31/2018
---

# D3DGAMMARAMP structure

Contains red, green, and blue ramp data.

## Syntax


```C++
typedef struct D3DGAMMARAMP {
  WORD red[256];
  WORD green[256];
  WORD blue[256];
} D3DGAMMARAMP, *LPD3DGAMMARAMP;
```



## Members

<dl> <dt>

**red**
</dt> <dd>

Type: **[**WORD**](https://msdn.microsoft.com/en-us/library/Aa383751(v=VS.85).aspx)**

</dd> <dd>

Array of 256 WORD element that describes the red gamma ramp.

</dd> <dt>

**green**
</dt> <dd>

Type: **[**WORD**](https://msdn.microsoft.com/en-us/library/Aa383751(v=VS.85).aspx)**

</dd> <dd>

Array of 256 WORD element that describes the green gamma ramp.

</dd> <dt>

**blue**
</dt> <dd>

Type: **[**WORD**](https://msdn.microsoft.com/en-us/library/Aa383751(v=VS.85).aspx)**

</dd> <dd>

Array of 256 WORD element that describes the blue gamma ramp.

</dd> </dl>

## Requirements



|                   |                                                                                        |
|-------------------|----------------------------------------------------------------------------------------|
| Header<br/> | <dl> <dt>D3D9Types.h</dt> </dl> |



## See also

<dl> <dt>

[Direct3D Structures](dx9-graphics-reference-d3d-structures.md)
</dt> <dt>

[**GetGammaRamp**](/windows/desktop/api)
</dt> <dt>

[**SetGammaRamp**](/windows/desktop/api)
</dt> </dl>

 

 



