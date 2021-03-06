---
UID: NF:ks.KsFilterRegisterAggregatedClientUnknown
title: KsFilterRegisterAggregatedClientUnknown function
author: windows-driver-content
description: This inline function is a wrapper for KsRegisterAggregatedClientUnknown.
old-location: stream\ksfilterregisteraggregatedclientunknown.htm
old-project: stream
ms.assetid: aac70408-83b8-4bfd-8ce9-9b74483f6282
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: KsFilterRegisterAggregatedClientUnknown, KsFilterRegisterAggregatedClientUnknown function [Streaming Media Devices], avfunc_c485334a-83bd-474e-abfc-ced331ca55db.xml, ks/KsFilterRegisterAggregatedClientUnknown, stream.ksfilterregisteraggregatedclientunknown
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ks.h
req.include-header: Ks.h
req.target-type: Desktop
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ks.h
api_name:
-	KsFilterRegisterAggregatedClientUnknown
product: Windows
targetos: Windows
req.typenames: 
---

# KsFilterRegisterAggregatedClientUnknown function


## -description


This inline function is a wrapper for <a href="..\ks\nf-ks-ksregisteraggregatedclientunknown.md">KsRegisterAggregatedClientUnknown</a>.


## -syntax


````
PUNKNOWN __inline KsFilterRegisterAggregatedClientUnknown(
  _In_ PKSFILTER Filter,
  _In_ PUNKNOWN  ClientUnknown
);
````


## -parameters




### -param Filter [in]

A pointer to the specified AVStream <a href="..\ks\ns-ks-_ksfilter.md">KSFILTER</a> structure.


### -param ClientUnknown [in]

The client <b>IUnknown</b> interface object.


## -returns



<b>KsFilterRegisterAggregatedClientUnknown</b> returns a pointer to an <b>IUnknown</b> interface representing the newly created aggregate object.




## -remarks



Note that this inline function only performs a typecast and then calls <a href="..\ks\nf-ks-ksregisteraggregatedclientunknown.md">KsRegisterAggregatedClientUnknown</a>.




## -see-also

<a href="..\ks\nf-ks-ksregisteraggregatedclientunknown.md">KsRegisterAggregatedClientUnknown</a>



 

 


