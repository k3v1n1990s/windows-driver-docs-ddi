---
UID: NF:wdm.IoFreeErrorLogEntry
title: IoFreeErrorLogEntry function
author: windows-driver-content
description: The IoFreeErrorLogEntry routine frees an unused error log entry.
old-location: kernel\iofreeerrorlogentry.htm
old-project: kernel
ms.assetid: 7244a63b-404f-45e0-b2f7-6c4ea70e4a21
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: IoFreeErrorLogEntry, IoFreeErrorLogEntry routine [Kernel-Mode Driver Architecture], k104_33f7cbb2-e145-46f1-99a0-b53381704aad.xml, kernel.iofreeerrorlogentry, wdm/IoFreeErrorLogEntry
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows XP and later versions of the Windows operating system.
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	IoFreeErrorLogEntry
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# IoFreeErrorLogEntry function


## -description


The <b>IoFreeErrorLogEntry</b> routine frees an unused error log entry. 


## -syntax


````
VOID IoFreeErrorLogEntry(
  _In_ PVOID ElEntry
);
````


## -parameters




### -param ElEntry [in]

Pointer to an error log packet allocated by <a href="..\wdm\nf-wdm-ioallocateerrorlogentry.md">IoAllocateErrorLogEntry</a>. 


## -returns



None




## -remarks



Drivers use <b>IoFreeErrorLogEntry</b> to free an error log entry allocated by <a href="..\wdm\nf-wdm-ioallocateerrorlogentry.md">IoAllocateErrorLogEntry</a>. <a href="..\wdm\nf-wdm-iowriteerrorlogentry.md">IoWriteErrorLogEntry</a> also frees any error log entries passed to it, so drivers must not call both on the same log entry.




## -see-also

<a href="..\wdm\nf-wdm-iowriteerrorlogentry.md">IoWriteErrorLogEntry</a>



<a href="..\wdm\nf-wdm-ioallocateerrorlogentry.md">IoAllocateErrorLogEntry</a>



<a href="..\wdm\ns-wdm-_io_error_log_packet.md">IO_ERROR_LOG_PACKET</a>



 

 


