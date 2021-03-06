---
UID: NF:storport.StorPortEnablePassiveInitialization
title: StorPortEnablePassiveInitialization function
author: windows-driver-content
description: The StorPortEnablePassiveInitialization routine enables the miniport's HwStorPassiveInitializeRoutine callback routine to execute at PASSIVE_LEVEL during miniport initialization.
old-location: storage\storportenablepassiveinitialization.htm
old-project: storage
ms.assetid: 881253d2-b44d-4c41-ad72-b0143dc50803
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: StorPortEnablePassiveInitialization, StorPortEnablePassiveInitialization routine [Storage Devices], storage.storportenablepassiveinitialization, storport/StorPortEnablePassiveInitialization, storprt_faea18e4-c684-4010-aca4-177132c011c5.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: StorPortEnablePassive, StorPortPassiveFromHwInit
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: DIRQL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	storport.h
api_name:
-	StorPortEnablePassiveInitialization
product: Windows
targetos: Windows
req.typenames: STOR_SPINLOCK
req.product: Windows 10 or later.
---

# StorPortEnablePassiveInitialization function


## -description


The <b>StorPortEnablePassiveInitialization</b> routine enables  the miniport's <a href="..\storport\nc-storport-hw_passive_initialize_routine.md">HwStorPassiveInitializeRoutine</a> callback routine to execute at PASSIVE_LEVEL during miniport initialization.


## -syntax


````
BOOLEAN StorPortEnablePassiveInitialization(
  _In_ PVOID                          HwDeviceExtension,
  _In_ PHW_PASSIVE_INITIALIZE_ROUTINE HwPassiveInitialization
);
````


## -parameters




### -param DeviceExtension

TBD


### -param HwPassiveInitializeRoutine

TBD




#### - HwDeviceExtension [in]

Pointer to the per-adapter device extension. 


#### - HwPassiveInitialization [in]

Pointer to a callback routine that the port driver calls at PASSIVE_LEVEL to initialize the DPCs that the miniport driver will use. For a description of this callback routine, see <a href="..\storport\nc-storport-hw_passive_initialize_routine.md">HwStorPassiveInitializeRoutine</a>. 


## -returns



The <b>StorPortEnablePassiveInitialization</b> routine returns <b>TRUE</b> if the operating system supports DPCs, and <b>FALSE</b> if not. 




## -remarks



A miniport must call the <b>StorPortEnablePassiveInitialization</b> routine only from within <a href="..\storport\nc-storport-hw_initialize.md">HwStorInitialize</a>. Otherwise, <b>StorPortEnablePassiveInitialization</b> will return <b>FALSE</b> and the <a href="..\storport\nc-storport-hw_passive_initialize_routine.md">HwStorPassiveInitializeRoutine</a> routine will not execute.

This routine is implemented using inline function definitions, so that miniport drivers that use this routine will not have to link to libraries that are dependent on the version of the operating system. Miniport drivers can use this routine without sacrificing backward compatibility with versions of the operating system that do not support DPCs in storage miniport drivers. 




## -see-also

<a href="..\storport\nc-storport-hw_passive_initialize_routine.md">HwStorPassiveInitializeRoutine</a>



 

 


