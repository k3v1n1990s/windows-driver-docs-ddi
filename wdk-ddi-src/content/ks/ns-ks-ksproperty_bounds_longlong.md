---
UID: NS:ks.KSPROPERTY_BOUNDS_LONGLONG
title: KSPROPERTY_BOUNDS_LONGLONG
author: windows-driver-content
description: The KSPROPERTY_BOUNDS_LONGLONG structure defines the bounds for a 64-bit property.
old-location: stream\ksproperty_bounds_longlong.htm
old-project: stream
ms.assetid: 25e3e430-abce-4d14-a336-4cb32a4fe5df
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: "*PKSPROPERTY_BOUNDS_LONGLONG, KSPROPERTY_BOUNDS_LONGLONG, KSPROPERTY_BOUNDS_LONGLONG union [Streaming Media Devices], PKSPROPERTY_BOUNDS_LONGLONG, PKSPROPERTY_BOUNDS_LONGLONG union pointer [Streaming Media Devices], ks-struct_553b35b1-55c4-404d-af6b-a9fb2bbfb6b9.xml, ks/KSPROPERTY_BOUNDS_LONGLONG, ks/PKSPROPERTY_BOUNDS_LONGLONG, stream.ksproperty_bounds_longlong"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ks.h
req.include-header: Ks.h
req.target-type: Windows
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
-	HeaderDef
api_location:
-	ks.h
api_name:
-	KSPROPERTY_BOUNDS_LONGLONG
product: Windows
targetos: Windows
req.typenames: KSPROPERTY_BOUNDS_LONGLONG, *PKSPROPERTY_BOUNDS_LONGLONG
---

# KSPROPERTY_BOUNDS_LONGLONG structure


## -description


The KSPROPERTY_BOUNDS_LONGLONG structure defines the bounds for a 64-bit property.


## -syntax


````
typedef union {
  struct {
    LONGLONG SignedMinimum;
    LONGLONG SignedMaximum;
  };
  struct {
    ULONGLONG UnsignedMinimum;
    ULONGLONG UnsignedMaximum;
  };
} KSPROPERTY_BOUNDS_LONGLONG, *PKSPROPERTY_BOUNDS_LONGLONG;
````


## -struct-fields




### -field _SIGNED64

 


### -field _UNSIGNED64

 




#### - SignedMaximum

Specifies a maximum bound as a signed 64-bit value.


#### - SignedMinimum

Specifies a minimum bound as a signed 64-bit value.


#### - UnsignedMaximum

Specifies a maximum bound as an unsigned 64-bit value.


#### - UnsignedMinimum

Specifies a minimum bound as an unsigned 64-bit value.


## -remarks



This structure specifies a range of 64-bit values for a property. Use only when the <b>MembersFlags</b> member of the relevant <a href="..\ks\ns-ks-ksproperty_membersheader.md">KSPROPERTY_MEMBERSHEADER</a> is set to KSPROPERTY_MEMBER_RANGES. Use this structure in the <b>Members</b> array in the relevant <a href="..\ks\ns-ks-ksproperty_memberslist.md">KSPROPERTY_MEMBERSLIST</a> structure.

See the Testcap sample in the Windows Driver Kit (WDK) for examples of usage.

Also see related information in <a href="https://msdn.microsoft.com/a385929e-1934-4d88-aaf9-ff1ddbfd30f7">KS Properties</a>.




## -see-also

<a href="..\ks\ns-ks-ksproperty_memberslist.md">KSPROPERTY_MEMBERSLIST</a>



<a href="..\ks\ns-ks-ksproperty_values.md">KSPROPERTY_VALUES</a>



<a href="..\ks\ns-ks-ksproperty_membersheader.md">KSPROPERTY_MEMBERSHEADER</a>



 

 


