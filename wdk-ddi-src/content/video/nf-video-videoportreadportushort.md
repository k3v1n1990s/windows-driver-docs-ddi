---
UID: NF:video.VideoPortReadPortUshort
title: VideoPortReadPortUshort function
author: windows-driver-content
description: The VideoPortReadPortUshort function reads a USHORT value from a mapped I/O port.
old-location: display\videoportreadportushort.htm
old-project: display
ms.assetid: a5277cee-40e8-4c87-8521-8ae59c9b33a3
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: VideoPortReadPortUshort, VideoPortReadPortUshort function [Display Devices], VideoPort_Functions_cb14aa82-3092-4982-83c5-4682d7a487c0.xml, display.videoportreadportushort, video/VideoPortReadPortUshort
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
req.irql: See Remarks section.
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Videoprt.sys
api_name:
-	VideoPortReadPortUshort
product: Windows
targetos: Windows
req.typenames: VIDEO_PORT_SERVICES
req.product: Windows 10 or later.
---

# VideoPortReadPortUshort function


## -description


The <b>VideoPortReadPortUshort</b> function reads a USHORT value from a mapped I/O port.


## -syntax


````
USHORT VideoPortReadPortUshort(
   PUSHORT Port
);
````


## -parameters




### -param Port

Pointer to the port. The given <i>Port</i> must be in a mapped I/O-space range returned by <a href="..\video\nf-video-videoportgetdevicebase.md">VideoPortGetDeviceBase</a>.


## -returns



<b>VideoPortReadPortUshort</b> returns the USHORT value read from the adapter.




## -remarks



A miniport driver's <a href="..\video\nc-video-pvideo_hw_interrupt.md">HwVidInterrupt</a> or <a href="..\video\nc-video-pminiport_synchronize_routine.md">HwVidSynchronizeExecutionCallback</a> function can call <b>VideoPortReadPortUshort</b>.

Callers of <b>VideoPortReadPortUshort</b> can be running at any IRQL, provided that the memory pointed to by the <i>Port</i> parameter is resident, mapped device memory.




## -see-also

<a href="..\video\nf-video-videoportgetdevicebase.md">VideoPortGetDeviceBase</a>



<a href="..\video\nc-video-pvideo_hw_interrupt.md">HwVidInterrupt</a>



<a href="..\video\nc-video-pminiport_synchronize_routine.md">HwVidSynchronizeExecutionCallback</a>



 

 


