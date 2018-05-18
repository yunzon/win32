---
title: IGPMBackupDirEx Property Methods
description: The property method of the IGPMBackupDirEx interface gets the property that is described in the following table. For a general discussion of property methods, see Interface Property Methods in the ADSI documentation.
audience: developer
author: REDMOND\\markl
manager: REDMOND\\markl
ms.assetid: 'd2f9609d-2e77-4dcb-a23b-eedd18ff0965'
ms.prod: 'windows-server-dev'
ms.technology: 'group-policy'
ms.tgt_platform: multiple
keywords: ["IGPMBackupDirEx Property Methods GPMC"]
topic_type:
- apiref
api_name:
- IGPMBackupDirEx Property Methods
- IGPMBackupDirEx.BackupDirectory
- IGPMBackupDirEx.get_BackupDirectory
- IGPMBackupDirEx.BackupType
- IGPMBackupDirEx.get_BackupType
api_location:
- Gpmgmt.dll
api_type:
- COM
---

# IGPMBackupDirEx Property Methods

The property method of the [**IGPMBackupDirEx**](igpmbackupdirex.md) interface gets the property that is described in the following table. For a general discussion of property methods, see [**Interface Property Methods**](https://msdn.microsoft.com/library/aa746378) in the ADSI documentation.

## Properties

<dl> <dt>

**BackupDirectory**
</dt> <dd> <dl>

The full path of the file system directory for Group Policy object (GPO) backups or for Starter GPO backups.

<dt>

Access type: Read-only
</dt> <dt>

Scripting data type: **String**
</dt> <dt>



``` syntax
// C++ method syntax
HRESULT get_BackupDirectory(
  [out] BSTR* pbstrBackupDir
);
```


</dt> </dl> </dd> <dt>

**BackupType**
</dt> <dd> <dl>

The value that specifies whether the specified backup is a GPO backup [**GPMBackup**](igpmbackup.md) or a Starter GPO backup **GPMStarterGPOBackup**.

<dt>

Access type: Read-only
</dt> <dt>

Scripting data type: **enum**
</dt> <dt>



``` syntax
// C++ method syntax
HRESULT get_BackupType(
  [out] GPMBackupType* pgpmBackupType
);
```


</dt> </dl> </dd> </dl>

�

## Requirements



|                                     |                                                                                       |
|-------------------------------------|---------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows�Vista<br/>                                                              |
| Minimum supported server<br/> | Windows Server�2008<br/>                                                        |
| Header<br/>                   | <dl> <dt>Gpmgmt.h</dt> </dl>   |
| IDL<br/>                      | <dl> <dt>Gpmgmt.idl</dt> </dl> |
| DLL<br/>                      | <dl> <dt>Gpmgmt.dll</dt> </dl> |
| IID<br/>                      | IGPMBackupDirEx is defined as F8DC55ED-3BA0-4864-AAD4-D365189EE1D5<br/>         |



## See also

<dl> <dt>

[**IGPMBackupDirEx**](igpmbackupdirex.md)
</dt> <dt>

[**IGPMBackup**](igpmbackup.md)
</dt> <dt>

[**IGPMBackupCollection**](igpmbackupcollection.md)
</dt> <dt>

[**IGPMBackupDir**](igpmbackupdir.md)
</dt> </dl>

�

�




