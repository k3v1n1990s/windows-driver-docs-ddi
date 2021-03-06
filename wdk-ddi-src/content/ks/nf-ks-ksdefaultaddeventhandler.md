---
UID: NF:ks.KsDefaultAddEventHandler
title: KsDefaultAddEventHandler function
author: windows-driver-content
description: The KsDefaultAddEventHandler function is a default routine to handle event 'add' requests.
old-location: stream\ksdefaultaddeventhandler.htm
old-project: stream
ms.assetid: 8e429a48-4e86-4673-aa32-85b640e2f64f
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: KsDefaultAddEventHandler, KsDefaultAddEventHandler function [Streaming Media Devices], avfunc_7e4e393b-c3ab-4538-8790-9fe4c4f964cd.xml, ks/KsDefaultAddEventHandler, stream.ksdefaultaddeventhandler
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
req.target-min-winverclnt: Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.
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
req.lib: Ks.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Ks.lib
-	Ks.dll
api_name:
-	KsDefaultAddEventHandler
product: Windows
targetos: Windows
req.typenames: 
---

# KsDefaultAddEventHandler function


## -description


The<b> KsDefaultAddEventHandler </b>function is a default routine to handle event 'add' requests.


## -syntax


````
NTSTATUS KsDefaultAddEventHandler(
  _In_    PIRP           Irp,
  _In_    PKSEVENTDATA   EventData,
  _Inout_ PKSEVENT_ENTRY EventEntry
);
````


## -parameters




### -param Irp [in]

The event <a href="..\wdm\ns-wdm-_irp.md">IRP</a>. This contains the object into which the event is inserted.


### -param EventData [in]

A pointer to a <a href="..\ks\ns-ks-kseventdata.md">KSEVENTDATA</a> structure that describes an event notification method.


### -param EventEntry [in, out]

The event entry that is to be inserted into the object's event list. The object is determined by <i>Irp</i>.


## -returns



Returns the success or failure of adding the event into the object's event list.




## -remarks



<b>KsDefaultAddEventHandler</b> determines the relevant object from <i>Irp</i> and adds the specified event to the object's event list.

This is functionally equivalent to <a href="..\ks\nf-ks-ksaddevent.md">KsAddEvent</a> (or <b>Ks</b><i>Xxx</i><b>AddEvent</b>, see below) for the object that is associated with <i>Irp</i>. Use <b>KsDefaultAddEventHandler</b> from a minidriver-specified <i>AddEvent</i> handler to insert the event into the object's event list.




## -see-also

<a href="..\ks\nf-ks-ksfilteraddevent.md">KsFilterAddEvent</a>



<a href="..\ks\ns-ks-_ksevent_entry.md">KSEVENT_ENTRY</a>



<a href="..\ks\nf-ks-kspinaddevent.md">KsPinAddEvent</a>



<a href="..\ks\nf-ks-ksgenerateevents.md">KsGenerateEvents</a>



<a href="..\ks\nf-ks-ksaddevent.md">KsAddEvent</a>



 

 


