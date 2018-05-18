---
title: CLUSCTL\_RESOURCE\_TYPE\_VALIDATE\_PRIVATE\_PROPERTIES control code
description: Verifies that a property list contains valid resource type property names and values and that the list is properly formatted.
audience: developer
author: REDMOND\\markl
manager: REDMOND\\markl
ms.assetid: '4d509cad-9fc8-40c4-a557-2ebb65855f78'
ms.prod: 'windows-server-dev'
ms.technology: 'failover-clustering'
ms.tgt_platform: multiple
keywords: ["CLUSCTL_RESOURCE_TYPE_VALIDATE_PRIVATE_PROPERTIES control code Failover Cluster"]
topic_type:
- apiref
api_name:
- CLUSCTL_RESOURCE_TYPE_VALIDATE_PRIVATE_PROPERTIES
api_location:
- ClusAPI.h
api_type:
- HeaderDef
---

# CLUSCTL\_RESOURCE\_TYPE\_VALIDATE\_PRIVATE\_PROPERTIES control code

Verifies that a [property list](property-lists.md) contains valid [resource type](resource-types.md) property names and values and that the list is properly formatted. Applications use this [control code](about-control-codes.md) as a [**ClusterResourceTypeControl**](clusterresourcetypecontrol.md) parameter, and [resource DLLs](resource-dlls.md) receive the control code as a [**ResourceTypeControl**](resourcetypecontrol.md) parameter.


```C++
ClusterResourceTypeControl( hCluster,                                          // cluster handle
                            lpszResTypeName,                                   // resource type name
                            hHostNode,                                         // optional host node
                            CLUSCTL_RESOURCE_TYPE_VALIDATE_PRIVATE_PROPERTIES, // this control code
                            lpInBuffer,                                        // input buffer: property list
                            cbInBufferSize,                                    // allocated buffer size (bytes)
                            NULL,                                              // output buffer: (not used)
                            0,                                                 // output buffer size (not used)
                            NULL );                                            // actual size of resulting data (not used)
```



## Parameters

The following control code function and DLL support parameters are specific to this control code. For complete parameter descriptions, see [**ClusterResourceTypeControl**](clusterresourcetypecontrol.md) or [**ResourceTypeControl**](resourcetypecontrol.md).

<dl> <dt>

*lpInBuffer* 
</dt> <dd>

Points to a [property list](property-lists.md) containing one or more read/write private resource type properties.

</dd> </dl>

## Return value

[**ClusterResourceTypeControl**](clusterresourcetypecontrol.md) returns one of the following values.

<dl> <dt>

**ERROR\_SUCCESS**
</dt> <dd>

0

The operation completed successfully. The property list is correctly formatted and contains valid data values.

</dd> <dt>

**ERROR\_INSUFFICIENT\_BUFFER**
</dt> <dd>

122 (0x7A)

The data area passed to a system call is too small. The actual size of the property list buffer as determined by the [Cluster service](cluster-service.md) is larger than the size specified in the *cbInBufferSize* parameter.

</dd> <dt>

**ERROR\_INVALID\_DATA**
</dt> <dd>

13 (0xD)

The data is invalid. The property list is either formatted incorrectly or contains invalid data, such as an out-of-range value.

</dd> <dt>

**ERROR\_INVALID\_PARAMETER**
</dt> <dd>

87 (0x57)

The parameter is incorrect.

</dd> <dt>

**RPC\_X\_BAD\_STUB\_DATA**
</dt> <dd>

1783 (0x6F7)

The stub received bad data. The *lpInBuffer* parameter is **NULL**.

</dd> <dt>

**[System error code](https://msdn.microsoft.com/library/windows/desktop/ms681381)**
</dt> <dd>

If any value is returned, then the operation failed.

</dd> </dl>

## Remarks

For information on working with property lists, see [Using Property Lists](using-property-lists.md).

ClusAPI.h defines the 32 bits of CLUSCTL\_RESOURCE\_TYPE\_VALIDATE\_PRIVATE\_PROPERTIES as follows (for more information, see [Control Code Architecture](control-code-architecture.md)).



| Component                 | Bit location     | Value                                                      |
|---------------------------|------------------|------------------------------------------------------------|
| Object code<br/>    | 24�31<br/> | **CLUS\_OBJECT\_RESOURCE\_TYPE** (0x2)<br/>          |
| Global bit<br/>     | 23<br/>    | **CLUS\_NOT\_GLOBAL** (0x0)<br/>                     |
| Modify bit<br/>     | 22<br/>    | **CLUS\_NO\_MODIFY** (0x0)<br/>                      |
| User bit<br/>       | 21<br/>    | **CLCTL\_CLUSTER\_BASE** (0x0)<br/>                  |
| Type bit<br/>       | 20<br/>    | External (0x0)<br/>                                  |
| Operation code<br/> | 0�23<br/>  | **CLCTL\_VALIDATE\_PRIVATE\_PROPERTIES** (0x89)<br/> |
| Access code<br/>    | 0�1<br/>   | **CLUS\_ACCESS\_READ** (0x1)<br/>                    |



�

### Resource DLL Support

Required. Always support the CLUSCTL\_RESOURCE\_TYPE\_VALIDATE\_PRIVATE\_PROPERTIES control code. Your implementation should parse the property list passed in the *InBuffer* parameter, verifying that each property value is valid for the resource type.

If you do not support this control code, the [Resource Monitor](resource-monitor.md) verifies that the property list is formatted correctly but does not actually validate the data. This can result in the assignment of invalid property values.

As a general guideline, the Resource Monitor should handle all of the control codes for common properties, while your DLL should handle all control codes for private properties.

For more information on the [**ResourceTypeControl**](resourcetypecontrol.md) entry point, see [Implementing ResourceTypeControl](implementing-resourcetypecontrol.md).

## Requirements



|                                     |                                                                                      |
|-------------------------------------|--------------------------------------------------------------------------------------|
| Minimum supported client<br/> | None supported<br/>                                                            |
| Minimum supported server<br/> | Windows Server�2008 Enterprise, Windows Server�2008 Datacenter<br/>            |
| Header<br/>                   | <dl> <dt>ClusAPI.h</dt> </dl> |



## See also

<dl> <dt>

[External Resource Type Control Codes](external-resource-type-control-codes.md)
</dt> <dt>

[**ClusterResourceTypeControl**](clusterresourcetypecontrol.md)
</dt> <dt>

[**ResourceTypeControl**](resourcetypecontrol.md)
</dt> </dl>

�

�




