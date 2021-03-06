---
UID: NF:ksproxy.IKsClockPropertySet.KsSetPhysicalTime
title: IKsClockPropertySet::KsSetPhysicalTime method
author: windows-driver-content
description: The KsSetPhysicalTime method sets the physical time on the underlying clock.
old-location: stream\iksclockpropertyset_kssetphysicaltime.htm
old-project: stream
ms.assetid: 2f8eb011-1fe1-40f6-b833-50d3e853bffd
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: IKsClockPropertySet, IKsClockPropertySet interface [Streaming Media Devices], KsSetPhysicalTime method, IKsClockPropertySet::KsSetPhysicalTime, KsSetPhysicalTime method [Streaming Media Devices], KsSetPhysicalTime method [Streaming Media Devices], IKsClockPropertySet interface, KsSetPhysicalTime,IKsClockPropertySet.KsSetPhysicalTime, ksproxy/IKsClockPropertySet::KsSetPhysicalTime, ksproxy_1cebc4eb-efb8-4ec6-97f4-e34fc978fb2f.xml, stream.iksclockpropertyset_kssetphysicaltime
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: ksproxy.h
req.include-header: Ksproxy.h
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	ksproxy.h
api_name:
-	IKsClockPropertySet.KsSetPhysicalTime
product: Windows
targetos: Windows
req.typenames: PIPE_STATE
---

# IKsClockPropertySet::KsSetPhysicalTime method


## -description


The <b>KsSetPhysicalTime</b> method sets the physical time on the underlying clock. 


## -syntax


````
HRESULT KsSetPhysicalTime(
  [in] LONGLONG Time
);
````


## -parameters




### -param Time [in]

Physical time to which to set the underlying clock.


## -returns



Returns NOERROR if successful; otherwise, returns an error code.




## -remarks



The physical time is based on some underlying physical clock that always progresses, even if the physical type of clock must be changed on the fly. Other physical clocks use an underlying clock's physical time for rate matching.

The proxy uses the <a href="https://msdn.microsoft.com/library/windows/hardware/ff565088">KSPROPERTY_CLOCK_PHYSICALTIME</a> property to set the physical time. 




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff565088">KSPROPERTY_CLOCK_PHYSICALTIME</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559742">IKsClockPropertySet::KsGetPhysicalTime</a>



 

 


