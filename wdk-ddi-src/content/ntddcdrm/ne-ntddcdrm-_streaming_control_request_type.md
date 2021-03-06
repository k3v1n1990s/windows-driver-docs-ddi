---
UID: NE:ntddcdrm._STREAMING_CONTROL_REQUEST_TYPE
title: "_STREAMING_CONTROL_REQUEST_TYPE"
author: windows-driver-content
description: The STREAMING_CONTROL_REQUEST_TYPE enumeration defines the CDROM streaming modes.
old-location: storage\streaming_control_request_type.htm
old-project: storage
ms.assetid: A17F0E3C-402B-4484-B4AE-0583773AEDA8
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PSTREAMING_CONTROL_REQUEST_TYPE, CdromStreamingDisable, CdromStreamingEnableForReadOnly, CdromStreamingEnableForReadWrite, CdromStreamingEnableForWriteOnly, PSTREAMING_CONTROL_REQUEST_TYPE, PSTREAMING_CONTROL_REQUEST_TYPE enumeration pointer [Storage Devices], STREAMING_CONTROL_REQUEST_TYPE, STREAMING_CONTROL_REQUEST_TYPE enumeration [Storage Devices], _STREAMING_CONTROL_REQUEST_TYPE, ntddcdrm/ CdromStreamingEnableForWriteOnly, ntddcdrm/CdromStreamingDisable, ntddcdrm/CdromStreamingEnableForReadOnly, ntddcdrm/CdromStreamingEnableForReadWrite, ntddcdrm/PSTREAMING_CONTROL_REQUEST_TYPE, ntddcdrm/STREAMING_CONTROL_REQUEST_TYPE, storage.streaming_control_request_type"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntddcdrm.h
req.include-header: Ntddcdrm.h
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
-	Ntddcdrm.h
api_name:
-	STREAMING_CONTROL_REQUEST_TYPE
product: Windows
targetos: Windows
req.typenames: STREAMING_CONTROL_REQUEST_TYPE, *PSTREAMING_CONTROL_REQUEST_TYPE
---

# _STREAMING_CONTROL_REQUEST_TYPE enumeration


## -description


The STREAMING_CONTROL_REQUEST_TYPE enumeration defines the CDROM streaming modes. This enumeration is a member of the <a href="..\ntddcdrm\ns-ntddcdrm-_cdrom_streaming_control.md">CDROM_STREAMING_CONTROL</a> structure, the input parameter to the <a href="..\ntddcdrm\ni-ntddcdrm-ioctl_cdrom_enable_streaming.md">IOCTL_CDROM_ENABLE_STREAMING</a> I/O control code, which is used to enable or disable CDROM streaming. 


## -syntax


````
typedef enum _STREAMING_CONTROL_REQUEST_TYPE { 
  CdromStreamingDisable                  = 1,
  CdromStreamingEnableForReadOnly        = 2,
      CdromStreamingEnableForWriteOnly   = 3,
  CdromStreamingEnableForReadWrite       = 4
} STREAMING_CONTROL_REQUEST_TYPE, *PSTREAMING_CONTROL_REQUEST_TYPE;
````


## -enum-fields




### -field CdromStreamingDisable

Streaming read and streaming write requests will be disabled for the requested file handle.


### -field CdromStreamingEnableForReadOnly

Streaming read requests will be enabled, and streaming write requests will be disabled, for the requested file handle.


### -field CdromStreamingEnableForWriteOnly

Streaming read requests will be disabled, and streaming write requests will be enabled, for the requested file handle.


### -field CdromStreamingEnableForReadWrite

Streaming read and streaming write requests will be enabled for the requested file handle.


## -see-also

<a href="..\ntddcdrm\ns-ntddcdrm-_cdrom_streaming_control.md">CDROM_STREAMING_CONTROL</a>



<a href="..\ntddcdrm\ni-ntddcdrm-ioctl_cdrom_enable_streaming.md">IOCTL_CDROM_ENABLE_STREAMING</a>



 

 


