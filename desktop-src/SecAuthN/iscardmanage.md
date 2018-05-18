﻿---
Description: 'Used for attaching to a specific smart card or reader, for creating other optional interfaces to perform specific smart card functions, for locking a specific smart card for exclusive use, and for getting the status of a smart card or reader.'
ms.assetid: '67077034-5bd0-4176-9dc7-774caba3d427'
title: ISCardManage interface
---

# ISCardManage interface

\[The **ISCardManage** interface no longer available for use as of Windows Server 2008, Windows Vista, and Windows Server 2003 with Service Pack 1 (SP1) and later. The [Smart Card Modules](secsmart.smart_card_modules) provide similar functionality.\]

The following interface definition is provided as a standard that can be followed when developing a [*smart card*](security.s_gly#-security-smart-card-gly) [*service provider*](security.c_gly#-security-cryptographic-service-provider-gly).

The **ISCardManage** interface must be provided. It is used for attaching to a specific [*smart card*](security.s_gly#-security-smart-card-gly) or [*reader*](security.r_gly#-security-reader-gly), for creating other optional interfaces to perform specific smart card functions, for locking a specific smart card for exclusive use, and for getting the status of a smart card or reader. As a set, these services can be responsible for maintaining a well-defined context within which an application can communicate with a [*smart card*](security.s_gly#-security-smart-card-gly) or [*reader*](security.r_gly#-security-reader-gly).

Following is a typical use of **ISCardManage** interface.

**To connect to a smart card**

1.  Create the **ISCardManage** interface associated with the card.
2.  Connect to a smart card by attaching to a specific smart card reader ([**AttachByIFD**](iscardmanage-attachbyifd.md)) or by using a previously acquired handle ([**AttachByHandle**](iscardmanage-attachbyhandle.md)).
3.  Create other interfaces to perform smart card operations ([**CreateCardAuth**](iscardmanage-createcardauth.md), [**CreateFileAccess**](iscardmanage-createfileaccess.md), [**CreateCHVerification**](iscardmanage-createchverification.md), or [**CreateInterface**](iscardmanage-createinterface.md)).
4.  Release the card ([**Detach**](iscardmanage-detach.md)).
5.  Release the **ISCardManage** interface and others as required.

## Members

The **ISCardManage** interface inherits from the [**IDispatch**](ebbff4bc-36b2-4861-9efa-ffa45e013eb5) interface. **ISCardManage** also has these types of members:

-   [Methods](#methods)

### Methods

The **ISCardManage** interface has these methods.



| Method                                                            | Description                                                                                                                                                                                                                                                                |
|:------------------------------------------------------------------|:---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [**AttachByHandle**](iscardmanage-attachbyhandle.md)             | Allows an application to create a communication link to a smart card using a handle returned by the smart card [*resource manager*](security.r_gly#-security-resource-manager-gly).<br/>                                              |
| [**AttachByIFD**](iscardmanage-attachbyifd.md)                   | Allows an application to request establishment of a context for a specific reader referenced with a display name.<br/>                                                                                                                                               |
| [**CreateCardAuth**](iscardmanage-createcardauth.md)             | Allows the creation of a [**ISCardAuth**](iscardauth.md) interface.<br/>                                                                                                                                                                                            |
| [**CreateCHVerification**](iscardmanage-createchverification.md) | Allows the creation of a [**ISCardVerify**](iscardverify.md) interface.<br/>                                                                                                                                                                                        |
| [**CreateFileAccess**](iscardmanage-createfileaccess.md)         | Allows the creation of a [**ISCardFileAccess**](iscardfileaccess.md) interface.<br/>                                                                                                                                                                                |
| [**CreateInterface**](iscardmanage-createinterface.md)           | Allows the creation of an interface.<br/>                                                                                                                                                                                                                            |
| [**Detach**](iscardmanage-detach.md)                             | Releases the attachment to a particular smart card or reader allocated by [**AttachByHandle**](iscardmanage-attachbyhandle.md) or [**AttachByIFD**](iscardmanage-attachbyifd.md) respectively.<br/>                                                                |
| [**Reconnect**](iscardmanage-reconnect.md)                       | Allows an application to reconnect to a smart card or reader without having to issue a [**Detach**](iscardmanage-detach.md) followed by [**AttachByHandle**](iscardmanage-attachbyhandle.md) or [**AttachByIFD**](iscardmanage-attachbyifd.md) respectively.<br/> |
| [**SCardLock**](iscardmanage-scardlock.md)                       | Locks a connected smart card or reader for exclusive use.<br/>                                                                                                                                                                                                       |
| [**SCardUnlock**](iscardmanage-scardunlock.md)                   | Releases exclusive use of the connected smart card or reader.<br/>                                                                                                                                                                                                   |
| [**Status**](iscardmanage-status.md)                             | Allows an application to get the current status of the smart card or reader.<br/>                                                                                                                                                                                    |



 

## Requirements



|                                     |                                                      |
|-------------------------------------|------------------------------------------------------|
| Minimum supported client<br/> | Windows XP \[desktop apps only\]<br/>          |
| Minimum supported server<br/> | Windows Server 2003 \[desktop apps only\]<br/> |
| End of client support<br/>    | Windows XP<br/>                                |
| End of server support<br/>    | Windows Server 2003<br/>                       |



 

 



