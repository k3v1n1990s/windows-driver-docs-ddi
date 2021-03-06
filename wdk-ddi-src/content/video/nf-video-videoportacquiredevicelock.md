---
UID: NF:video.VideoPortAcquireDeviceLock
title: VideoPortAcquireDeviceLock function
author: windows-driver-content
description: The VideoPortAcquireDeviceLock function acquires the device lock maintained by the video port driver.
old-location: display\videoportacquiredevicelock.htm
old-project: display
ms.assetid: eeb2d1ad-ad99-4099-9560-8653a627aa08
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: VideoPortAcquireDeviceLock, VideoPortAcquireDeviceLock function [Display Devices], VideoPort_Functions_4c588378-53be-496c-93f0-0d285b8a1a05.xml, display.videoportacquiredevicelock, video/VideoPortAcquireDeviceLock
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Videoprt.sys
api_name:
-	VideoPortAcquireDeviceLock
product: Windows
targetos: Windows
req.typenames: VIDEO_PORT_SERVICES
req.product: Windows 10 or later.
---

# VideoPortAcquireDeviceLock function


## -description


The <b>VideoPortAcquireDeviceLock</b> function acquires the device lock maintained by the video port driver.


## -syntax


````
VOID VideoPortAcquireDeviceLock(
  _In_ PVOID HwDeviceExtension
);
````


## -parameters




### -param HwDeviceExtension [in]

Pointer to the miniport driver's device extension.


## -returns



None




## -remarks



Typically, the video port driver guarantees threaded synchronization into the miniport driver through the use of a device lock. However, a miniport driver must perform its own synchronization when being accessed by a child device. That is, a miniport driver must perform synchronization in routines that it exposes through <a href="..\video\nc-video-pvideo_hw_query_interface.md">HwVidQueryInterface</a> by acquiring the device lock maintained by the video port driver.

The miniport driver should release the device lock as quickly as possible by calling <a href="..\video\nf-video-videoportreleasedevicelock.md">VideoPortReleaseDeviceLock</a>.




## -see-also

<a href="..\video\nc-video-pvideo_hw_query_interface.md">HwVidQueryInterface</a>



<a href="..\video\nf-video-videoportreleasedevicelock.md">VideoPortReleaseDeviceLock</a>



 

 


