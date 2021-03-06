---
UID: NF:portcls.IPortEvents.AddEventToEventList
title: IPortEvents::AddEventToEventList method
author: windows-driver-content
description: The AddEventToEventList method adds an event to the port driver's event list.
old-location: audio\iportevents_addeventtoeventlist.htm
old-project: audio
ms.assetid: 49b01942-3562-4fb2-907b-8863b2f09f8e
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: AddEventToEventList method [Audio Devices], AddEventToEventList method [Audio Devices], IPortEvents interface, AddEventToEventList,IPortEvents.AddEventToEventList, IPortEvents, IPortEvents interface [Audio Devices], AddEventToEventList method, IPortEvents::AddEventToEventList, audio.iportevents_addeventtoeventlist, audmp-routines_13ea6aa7-0f65-43d4-b80c-4aa46102c43e.xml, portcls/IPortEvents::AddEventToEventList
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Universal
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	portcls.h
api_name:
-	IPortEvents.AddEventToEventList
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---

# IPortEvents::AddEventToEventList method


## -description


The <code>AddEventToEventList</code> method adds an event to the port driver's event list.


## -syntax


````
void AddEventToEventList(
  [in] PKSEVENT_ENTRY EventEntry
);
````


## -parameters




### -param EventEntry [in]

Pointer to the event entry that describes the event. This is an opaque system structure of type <a href="..\ks\ns-ks-_ksevent_entry.md">KSEVENT_ENTRY</a>.


## -returns



None




## -remarks



This method is used by a miniport driver's to add events to the event list that is maintained by the associated port object. The miniport driver's event handler typically calls this method in response to a PCEVENT_VERB_ADD request after the handler has validated support for the event being requested.




## -see-also

<a href="..\portcls\nn-portcls-iportevents.md">IPortEvents</a>



<a href="..\portcls\nc-portcls-pcpfnevent_handler.md">EventHandler</a>



<a href="..\ks\ns-ks-_ksevent_entry.md">KSEVENT_ENTRY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536889">IPortEvents::GenerateEventList</a>



 

 


