---
UID: NF:storport.StorPortReadRegisterUchar
title: StorPortReadRegisterUchar macro
author: windows-driver-content
description: The StorPortReadRegisterUchar routine reads a value from a specified register address.
old-location: storage\storportreadregisteruchar.htm
old-project: storage
ms.assetid: 1edf800d-f097-4d3f-ae89-1b11e4f82f2d
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: StorPortReadRegisterUchar, StorPortReadRegisterUchar routine [Storage Devices], storage.storportreadregisteruchar, storport/StorPortReadRegisterUchar, storprt_9f2898e2-6b5e-45ae-9162-57c58a3471f7.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: storport.h
req.include-header: Storport.h
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
req.lib: Storport.lib
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Storport.lib
-	Storport.dll
api_name:
-	StorPortReadRegisterUchar
product: Windows
targetos: Windows
req.typenames: STOR_SPINLOCK
req.product: Windows 10 or later.
---

# StorPortReadRegisterUchar macro


## -description


The <b>StorPortReadRegisterUchar</b> routine reads a value from a specified register address. 


## -syntax


````
STORPORT_API UCHAR StorPortReadRegisterUchar(
  _In_ PVOID  HwDeviceExtension,
  _In_ PUCHAR Register
);
````


## -parameters




### -param h

TBD


### -param r

TBD






#### - HwDeviceExtension [in]

Pointer to the hardware device extension.


#### - Register [in]

Pointer to the register where the data is to be read. 


## -remarks



For more information, see <a href="..\storport\nf-storport-scsiportreadregisteruchar.md">ScsiPortReadRegisterUchar</a>. For a buffered version of this routine, see <a href="..\storport\nf-storport-storportreadregisterbufferuchar.md">StorPortReadRegisterBufferUchar</a>.




## -see-also

<a href="..\storport\nf-storport-storportreadregisterbufferuchar.md">StorPortReadRegisterBufferUchar</a>



<a href="..\storport\nf-storport-scsiportreadregisteruchar.md">ScsiPortReadRegisterUchar</a>



 

 


