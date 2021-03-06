---
UID: NF:dmusicks.IAllocatorMXF.GetMessage
title: IAllocatorMXF::GetMessage method
author: windows-driver-content
description: The GetMessage method serves as the retrieval point for any DirectMusic kernel-mode component that utilizes the port driver's allocator to reuse DMUS_KERNEL_EVENT structures.
old-location: audio\iallocatormxf_getmessage.htm
old-project: audio
ms.assetid: d5b56926-bcfb-4411-b24d-cc0758852510
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: GetMessage method [Audio Devices], GetMessage method [Audio Devices], IAllocatorMXF interface, GetMessage,IAllocatorMXF.GetMessage, IAllocatorMXF, IAllocatorMXF interface [Audio Devices], GetMessage method, IAllocatorMXF::GetMessage, audio.iallocatormxf_getmessage, audmp-routines_24207ff5-69a9-47bd-a756-78c2a218080e.xml, dmusicks/IAllocatorMXF::GetMessage
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: dmusicks.h
req.include-header: Dmusicks.h
req.target-type: Desktop
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
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	dmusicks.h
api_name:
-	IAllocatorMXF.GetMessage
product: Windows
targetos: Windows
req.typenames: DMUS_STREAM_TYPE
---

# IAllocatorMXF::GetMessage method


## -description


The <code>GetMessage</code> method serves as the retrieval point for any DirectMusic kernel-mode component that utilizes the port driver's allocator to reuse <a href="..\dmusicks\ns-dmusicks-_dmus_kernel_event.md">DMUS_KERNEL_EVENT</a> structures.


## -syntax


````
NTSTATUS GetMessage(
  [out] PDMUS_KERNEL_EVENT *ppDMKEvt
);
````


## -parameters




### -param ppDMKEvt [out]

Output pointer for the MIDI event. This parameter points to a caller-allocated pointer variable into which the method writes a pointer to the event structure being retrieved from the allocator. The structure itself is empty (zeroed by the allocator).


## -returns



<code>GetMessage</code> returns S_OK if the call was successful. Otherwise, the method returns an appropriate error code.




## -remarks



The miniport driver uses the <code>GetMessage</code> method to retrieve event structures for MIDI rendering and capture. This method retrieves <a href="..\dmusicks\ns-dmusicks-_dmus_kernel_event.md">DMUS_KERNEL_EVENT</a> structures from the same pool that <a href="https://msdn.microsoft.com/library/windows/hardware/ff536791">IMXF::PutMessage</a> puts them into when it discards them to the allocator.

In the case of a MIDI capture stream, the port driver retrieves capture events from the miniport driver when prompted by the usual Service DPC.

For more information about the allocator, see <a href="https://msdn.microsoft.com/8f263288-2f79-4f1d-b740-d78d40f47b32">Allocator</a>.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff536791">IMXF::PutMessage</a>



<a href="..\dmusicks\ns-dmusicks-_dmus_kernel_event.md">DMUS_KERNEL_EVENT</a>



<a href="..\dmusicks\nn-dmusicks-iallocatormxf.md">IAllocatorMXF</a>



 

 


