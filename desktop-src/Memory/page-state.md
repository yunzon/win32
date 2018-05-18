﻿---
Description: 'The pages of a process''s virtual address space can be in one of the following states.'
ms.assetid: 'a6faa901-2966-4556-90ef-c113b1ba6c6d'
title: Page State
---

# Page State

The pages of a process's virtual address space can be in one of the following states.



| State     | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
|-----------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Free      | The page is neither committed nor reserved. The page is not accessible to the process. It is available to be reserved, committed, or simultaneously reserved and committed. Attempting to read from or write to a free page results in an access violation exception. <br/> A process can use the [**VirtualFree**](virtualfree.md) or [**VirtualFreeEx**](virtualfreeex.md) function to release reserved or committed pages of its address space, returning them to the free state.<br/>                                                                                                                                                                                                                                                                                                                              |
| Reserved  | The page has been reserved for future use. The range of addresses cannot be used by other allocation functions. The page is not accessible and has no physical storage associated with it. It is available to be committed. <br/> A process can use the [**VirtualAlloc**](virtualalloc.md) or [**VirtualAllocEx**](virtualallocex.md) function to reserve pages of its address space and later to commit the reserved pages. It can use [**VirtualFree**](virtualfree.md) or [**VirtualFreeEx**](virtualfreeex.md) to decommit committed pages and return them to the reserved state.<br/>                                                                                                                                                                                                                          |
| Committed | Memory charges have been allocated from the overall size of RAM and paging files on disk. The page is accessible and access is controlled by one of the [memory protection constants](memory-protection-constants.md). The system initializes and loads each committed page into physical memory only during the first attempt to read or write to that page. When the process terminates, the system releases the storage for committed pages. <br/> A process can use [**VirtualAlloc**](virtualalloc.md) or [**VirtualAllocEx**](virtualallocex.md) to commit physical pages from a reserved region. They can also simultaneously reserve and commit pages.<br/> The [**GlobalAlloc**](globalalloc.md) and [**LocalAlloc**](localalloc.md) functions allocate committed pages with read/write access.<br/> |



 

 

 



