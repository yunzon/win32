---
title: IVMVirtualNetwork BytesDropped property
description: The BytesDropped property contains the current number of bytes dropped per second by this virtual network.
ms.assetid: '725adae4-50d7-4698-978d-a7c317d2e167'
keywords: ["BytesDropped property Virtual Server", "BytesDropped property Virtual Server , IVMVirtualNetwork interface", "IVMVirtualNetwork interface Virtual Server , BytesDropped property", "BytesDropped property Virtual Server , VMVirtualNetwork class", "VMVirtualNetwork class Virtual Server , BytesDropped property"]
topic_type:
- apiref
api_name:
- IVMVirtualNetwork.BytesDropped
- IVMVirtualNetwork.get_BytesDropped
- VMVirtualNetwork.BytesDropped
api_location:
- VsComInterfaces.h
api_type:
- COM
---

# IVMVirtualNetwork::BytesDropped property

The **BytesDropped** property contains the current number of bytes dropped per second by this virtual network.

This property is read-only.

## Syntax


```C++
HRESULT get_BytesDropped(
  [out]�long *bytesDropped
);
```

<span codelanguage="VisualBasic"></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th>VB</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><pre><code>VMVirtualNetwork.BytesDropped( _
  ByRef bytesDropped _
)</code></pre></td>
</tr>
</tbody>
</table>



## Property value

The number of bytes dropped per second by this virtual network.

This property value is read-only.

## Error codes



| Name                                                                                          | Meaning                                              |
|-----------------------------------------------------------------------------------------------|------------------------------------------------------|
| <dl> <dt> S\_OK</dt> </dl>             | The operation was successful.<br/>             |
| <dl> <dt>E\_POINTER</dt> </dl>         | The *bytesDropped* parameter is **NULL**.<br/> |
| <dl> <dt>DISP\_E\_EXCEPTION</dt> </dl> | An unexpected error occurred.<br/>             |



## Requirements



|                     |                                                                                                   |
|---------------------|---------------------------------------------------------------------------------------------------|
| Product<br/>  | Microsoft Virtual Server 2005 onWindows Server�2003<br/>                                    |
| Download<br/> | Microsoft Virtual Server 2005 R2 SP1 Update onWindows Server�2008orWindows Server�2003<br/> |
| Header<br/>   | <dl> <dt>VsComInterfaces.h</dt> </dl>      |



## See also

<dl> <dt>

[**IVMVirtualNetwork**](ivmvirtualnetwork.md)
</dt> </dl>

�

�




