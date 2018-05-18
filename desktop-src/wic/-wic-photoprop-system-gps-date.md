---
Description: 'The photo metadata policy for the System.GPS.Date property.'
ms.assetid: '75047658-b6f3-454e-961a-89016c244bf6'
title: 'System.GPS.Date Photo Metadata Policy'
---

# System.GPS.Date Photo Metadata Policy

The photo metadata policy for the [System.GPS.Date](http://msdn.microsoft.com/en-us/library/bb787482(VS.85).aspx) property.

### PKEY

PKEY\_GPS\_Date

### Containers

JPEG, TIFF

### Read-Only

No

### Input Type

String.

### Conflict Resolution Policy

Values from different schemas are reconciled.

### JPEG Policies

### Read Paths



| Order | Path                      | Disk Format |
|-------|---------------------------|-------------|
| 1     | /app1/ifd/gps/{ushort=29} | ascii       |
| 2     | /xmp/exif:GPSTimeStamp    | unicode     |



 

### Write Paths



| Order | Path                      | Disk Format |
|-------|---------------------------|-------------|
| 1     | /app1/ifd/gps/{ushort=29} | ascii       |
| 2     | /xmp/exif:GPSTimeStamp    | unicode     |



 

### Remove Paths



| Order | Path                      |
|-------|---------------------------|
| 1     | /app1/ifd/gps/{ushort=29} |
| 2     | /xmp/exif:GPSTimeStamp    |



 

### TIFF Policies

### Read Paths



| Order | Path                       | Disk Format |
|-------|----------------------------|-------------|
| 1     | /ifd/gps/{ushort=29}       | ascii       |
| 2     | /ifd/xmp/exif:GPSTimeStamp | unicode     |



 

### Write Paths



| Order | Path                       | Disk Format |
|-------|----------------------------|-------------|
| 1     | /ifd/gps/{ushort=29}       | ascii       |
| 2     | /ifd/xmp/exif:GPSTimeStamp | unicode     |



 

### Remove Paths



| Order | Path                       |
|-------|----------------------------|
| 1     | /ifd/gps/{ushort=29}       |
| 2     | /ifd/xmp/exif:GPSTimeStamp |



 

## Remarks

## Related topics

<dl> <dt>

[System.GPS.Date](http://msdn.microsoft.com/en-us/library/bb787482(VS.85).aspx)
</dt> </dl>

 

 


