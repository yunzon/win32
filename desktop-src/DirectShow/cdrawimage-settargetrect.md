---
Description: 'The SetTargetRect method sets the target rectangle.'
ms.assetid: '033f8bae-e63d-4be0-8dd0-715cc1229392'
title: 'CDrawImage.SetTargetRect method'
---

# CDrawImage.SetTargetRect method

The `SetTargetRect` method sets the target rectangle.

## Syntax


```C++
void SetTargetRect(
  �RECT *pTargetRect
);
```



## Parameters

<dl> <dt>

*pTargetRect* 
</dt> <dd>

Pointer to a **RECT** structure that defines the new target rectangle.

</dd> </dl>

## Return value

This method does not return a value.

## Remarks

The owning filter should call this method if the source rectangle changes; for example, in response to an [**IBasicVideo::SetDestinationPosition**](ibasicvideo-setdestinationposition.md) call.

Before calling this method, validate the rectangle given in *pTargetRect*, relative to the video window.

## Requirements



|                    |                                                                                                                                                                                            |
|--------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Header<br/>  | <dl> <dt>Winutil.h (include Streams.h)</dt> </dl>                                                                                   |
| Library<br/> | <dl> <dt>Strmbase.lib (retail builds); </dt> <dt>Strmbasd.lib (debug builds)</dt> </dl> |



## See also

<dl> <dt>

[**CDrawImage Class**](cdrawimage.md)
</dt> </dl>

�

�



