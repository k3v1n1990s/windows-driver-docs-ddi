---
UID: NF:video.VideoPortCompareMemory
title: VideoPortCompareMemory function
author: windows-driver-content
description: The VideoPortCompareMemory function compares two blocks of system memory, byte-by-byte, and returns the number of compared bytes that are equivalent.
old-location: display\videoportcomparememory.htm
old-project: display
ms.assetid: 89528b31-4d81-4612-92d7-5f64bdca8108
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: VideoPortCompareMemory, VideoPortCompareMemory function [Display Devices], VideoPort_Functions_87b1236e-d77b-4930-897f-d5b33b1130aa.xml, display.videoportcomparememory, video/VideoPortCompareMemory
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: video.h
req.include-header: Video.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows 2000 and later versions of the Windows operating systems.
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
req.lib: Videoprt.lib
req.dll: Videoprt.sys
req.irql: Any level (see Remarks section)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Videoprt.sys
api_name:
-	VideoPortCompareMemory
product: Windows
targetos: Windows
req.typenames: VIDEO_PORT_SERVICES
req.product: Windows 10 or later.
---

# VideoPortCompareMemory function


## -description


The <b>VideoPortCompareMemory</b> function compares two blocks of system memory, byte-by-byte, and returns the number of compared bytes that are equivalent.


## -syntax


````
ULONG VideoPortCompareMemory(
   PVOID  Source1,
   PVOID  Source2,
   SIZE_T Length
);
````


## -parameters




### -param Source1

Pointer to the first block of memory to compare.


### -param Source2

Pointer to the second block of memory to compare.


### -param Length

Specifies the number of bytes to be compared.


## -returns



<b>VideoPortCompareMemory</b> returns the number of bytes that are equivalent. If both blocks are equivalent, it returns the <i>Length</i> parameter.




## -remarks



The values in the <i>Source1</i> and <i>Source2</i> parameters must be in a mapped logical range returned by <a href="..\video\nf-video-videoportgetdevicebase.md">VideoPortGetDeviceBase</a> and/or a <a href="https://msdn.microsoft.com/5f6fec1a-1134-4765-81be-9b50939e5e66">system space</a> RAM address, such as an address on the stack.

Callers of <b>VideoPortCompareMemory</b> can be running at any IRQL if both blocks of memory are resident.




## -see-also

<a href="..\video\nf-video-videoportzeromemory.md">VideoPortZeroMemory</a>



<a href="..\video\nf-video-videoportgetdevicebase.md">VideoPortGetDeviceBase</a>



<a href="..\video\nf-video-videoportzerodevicememory.md">VideoPortZeroDeviceMemory</a>



<a href="..\video\nf-video-videoportscanrom.md">VideoPortScanRom</a>



<a href="..\video\nf-video-videoportmovememory.md">VideoPortMoveMemory</a>



 

 


