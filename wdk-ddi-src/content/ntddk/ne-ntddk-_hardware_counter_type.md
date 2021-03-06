---
UID: NE:ntddk._HARDWARE_COUNTER_TYPE
title: "_HARDWARE_COUNTER_TYPE"
author: windows-driver-content
description: The HARDWARE_COUNTER_TYPE enumeration specifies the type of a hardware counter.
old-location: kernel\hardware_counter_type.htm
old-project: kernel
ms.assetid: 837f5a55-ca07-4462-85d7-203d02df168c
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: "*PHARDWARE_COUNTER_TYPE, HARDWARE_COUNTER_TYPE, HARDWARE_COUNTER_TYPE enumeration [Kernel-Mode Driver Architecture], MaxHardwareCounterType, PHARDWARE_COUNTER_TYPE, PHARDWARE_COUNTER_TYPE enumeration pointer [Kernel-Mode Driver Architecture], PMCCounter, _HARDWARE_COUNTER_TYPE, kernel.hardware_counter_type, ntddk/HARDWARE_COUNTER_TYPE, ntddk/MaxHardwareCounterType, ntddk/PHARDWARE_COUNTER_TYPE, ntddk/PMCCounter, sysenum_861db9b8-cd2d-4cfe-ae99-5c292f28c420.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntddk.h
req.include-header: Winnt.h, Ntddk.h
req.target-type: Windows
req.target-min-winverclnt: Supported in Windows 7 and later versions of Windows.
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
-	ntddk.h
api_name:
-	HARDWARE_COUNTER_TYPE
product: Windows
targetos: Windows
req.typenames: HARDWARE_COUNTER_TYPE, *PHARDWARE_COUNTER_TYPE
---

# _HARDWARE_COUNTER_TYPE enumeration


## -description


The <b>HARDWARE_COUNTER_TYPE</b> enumeration specifies the type of a hardware counter.


## -syntax


````
typedef enum _HARDWARE_COUNTER_TYPE { 
  PMCCounter              = 0,
  MaxHardwareCounterType  = 1
} HARDWARE_COUNTER_TYPE, *PHARDWARE_COUNTER_TYPE;
````


## -enum-fields




### -field PMCCounter

Performance monitor counter. This type of counter is used by thread-profiling applications. 


### -field MaxHardwareCounterType

The maximum value in this enumeration type.


## -remarks



The <b>Type</b> member of the <a href="..\ntddk\ns-ntddk-_hardware_counter.md">HARDWARE_COUNTER</a> structure contains a <b>HARDWARE_COUNTER_TYPE</b> enumeration value. 




## -see-also

<a href="..\ntddk\ns-ntddk-_hardware_counter.md">HARDWARE_COUNTER</a>



 

 


