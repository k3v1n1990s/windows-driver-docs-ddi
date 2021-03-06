---
UID: NS:ntddvol._VOLUME_DISK_EXTENTS
title: "_VOLUME_DISK_EXTENTS"
author: windows-driver-content
description: The VOLUME_DISK_EXTENTS structure is used in conjunction with the IOCTL_VOLUME_GET_VOLUME_DISK_EXTENTS request to retrieve information about all the extents on a given volume.
old-location: storage\volume_disk_extents.htm
old-project: storage
ms.assetid: 227846c2-8794-4859-89af-c139ead32143
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PVOLUME_DISK_EXTENTS, PVOLUME_DISK_EXTENTS, PVOLUME_DISK_EXTENTS structure pointer [Storage Devices], VOLUME_DISK_EXTENTS, VOLUME_DISK_EXTENTS structure [Storage Devices], _VOLUME_DISK_EXTENTS, ntddvol/PVOLUME_DISK_EXTENTS, ntddvol/VOLUME_DISK_EXTENTS, storage.volume_disk_extents, structs-volumemgr_148847d4-324c-4767-8247-7d286e496d42.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddvol.h
req.include-header: Ntddvol.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntddvol.h
api_name:
-	VOLUME_DISK_EXTENTS
product: Windows
targetos: Windows
req.typenames: VOLUME_DISK_EXTENTS, *PVOLUME_DISK_EXTENTS
---

# _VOLUME_DISK_EXTENTS structure


## -description


The VOLUME_DISK_EXTENTS structure is used in conjunction with the <a href="..\ntddvol\ni-ntddvol-ioctl_volume_get_volume_disk_extents.md">IOCTL_VOLUME_GET_VOLUME_DISK_EXTENTS</a> request to retrieve information about all the extents on a given volume.


## -syntax


````
typedef struct _VOLUME_DISK_EXTENTS {
  ULONG       NumberOfDiskExtents;
  DISK_EXTENT Extents[ANYSIZE_ARRAY];
} VOLUME_DISK_EXTENTS, *PVOLUME_DISK_EXTENTS;
````


## -struct-fields




### -field NumberOfDiskExtents

Indicates the number of extents that comprise the volume, which can span multiple disks. 


### -field Extents

Indicates the number of extents that comprise the volume, which can span multiple disks. 


## -see-also

disk extent



<a href="..\ntddvol\ns-ntddvol-_disk_extent.md">DISK_EXTENT</a>



<a href="..\ntddvol\ni-ntddvol-ioctl_volume_get_volume_disk_extents.md">IOCTL_VOLUME_GET_VOLUME_DISK_EXTENTS</a>



 

 


