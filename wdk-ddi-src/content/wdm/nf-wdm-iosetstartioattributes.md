---
UID: NF:wdm.IoSetStartIoAttributes
title: IoSetStartIoAttributes function
author: windows-driver-content
description: The IoSetStartIoAttributes routine sets attributes for the driver's StartIo routine.
old-location: kernel\iosetstartioattributes.htm
old-project: kernel
ms.assetid: 47ae3578-231c-49c8-a851-9f165db27fb1
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: IoSetStartIoAttributes, IoSetStartIoAttributes routine [Kernel-Mode Driver Architecture], k104_cf8613cc-f891-45f7-816c-224b3294f8dd.xml, kernel.iosetstartioattributes, wdm/IoSetStartIoAttributes
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available for Microsoft Windows XP and later versions of the Windows operating system.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: StartIoCancel, StartIoRecursion, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: Any level
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	IoSetStartIoAttributes
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# IoSetStartIoAttributes function


## -description


The <b>IoSetStartIoAttributes</b> routine sets attributes for the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff563858">StartIo</a> routine.


## -syntax


````
VOID IoSetStartIoAttributes(
  _In_ PDEVICE_OBJECT DeviceObject,
  _In_ BOOLEAN        DeferredStartIo,
  _In_ BOOLEAN        NonCancelable
);
````


## -parameters




### -param DeviceObject [in]

Pointer to the device object for the driver's device.


### -param DeferredStartIo [in]

If <b>TRUE</b>, the I/O manager will defer any call to the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff563858">StartIo</a> routine while the driver is already inside the routine. In particular, if the <i>StartIo</i> routine calls <a href="..\wdm\nf-wdm-iostartnextpacket.md">IoStartNextPacket</a>, the <i>StartIo</i> routine will not be called again until the current invocation completes. The default is <b>FALSE</b>.


### -param NonCancelable [in]

If <b>TRUE</b>, the IRP cannot be canceled once it has been dequeued by a call to <b>IoStartNextPacket</b>. The default is <b>FALSE</b>. Drivers that set this member to <b>FALSE</b> must synchronize their IRP handling with the cancel spin lock.


## -returns



None




## -see-also

<a href="..\wdm\nf-wdm-iostartnextpacket.md">IoStartNextPacket</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563858">StartIo</a>



 

 


