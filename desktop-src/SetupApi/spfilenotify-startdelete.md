---
Description: 'The SPFILENOTIFY\_STARTDELETE notification is sent to the callback function when the queue starts a file delete operation.'
ms.assetid: '244714ad-dde7-4b5a-b3f3-78aa4cc901f5'
title: 'SPFILENOTIFY\_STARTDELETE message'
---

# SPFILENOTIFY\_STARTDELETE message

The **SPFILENOTIFY\_STARTDELETE** notification is sent to the callback function when the queue starts a file delete operation.


```C++
SPFILENOTIFY_STARTDELETE
  Param1 = (UINT) FilePathInfo;
  Param2 = (UINT) Operation;
            
```



## Parameters

<dl> <dt>

*Param1* 
</dt> <dd>

Pointer to a [**FILEPATHS**](filepaths-str.md) structure.

</dd> <dt>

*Param2* 
</dt> <dd>

Always has the value FILEOP\_DELETE.

</dd> </dl>

## Return value

The callback routine should return one of the following values.



| Return code                                                                                  | Description                                                                                                                                                                                                                                                                                                                                                                  |
|----------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <dl> <dt>**FILEOP\_ABORT**</dt> </dl> | Abort the queue commit. The callback routine should call [**SetLastError**](https://msdn.microsoft.com/library/windows/desktop/ms680627) to indicate the reason for aborting. [**SetupCommitFileQueue**](setupcommitfilequeue.md) returns **FALSE** and a subsequent call to [**GetLastError**](https://msdn.microsoft.com/library/windows/desktop/ms679360) returns the error code set by the callback routine during the call to **SetLastError**.<br/> |
| <dl> <dt>**FILEOP\_DOIT**</dt> </dl>  | Perform the file copy operation.<br/>                                                                                                                                                                                                                                                                                                                                  |
| <dl> <dt>**FILEOP\_SKIP**</dt> </dl>  | Skip the current copy operation.<br/>                                                                                                                                                                                                                                                                                                                                  |



�

## Requirements



|                                     |                                                                                       |
|-------------------------------------|---------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows�XP \[desktop apps only\]<br/>                                           |
| Minimum supported server<br/> | Windows Server�2003 \[desktop apps only\]<br/>                                  |
| Header<br/>                   | <dl> <dt>Setupapi.h</dt> </dl> |



## See also

<dl> <dt>

[Overview](overview.md)
</dt> <dt>

[Notifications](notifications.md)
</dt> <dt>

[**FILEPATHS**](filepaths-str.md)
</dt> <dt>

[**SetupCommitFileQueue**](setupcommitfilequeue.md)
</dt> <dt>

[**SetupDefaultQueueCallback**](setupdefaultqueuecallback.md)
</dt> </dl>

�

�



