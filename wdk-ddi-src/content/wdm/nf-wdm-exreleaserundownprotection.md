---
UID: NF:wdm.ExReleaseRundownProtection
title: ExReleaseRundownProtection function
author: windows-driver-content
description: The ExReleaseRundownProtection routine releases run-down protection that the caller previously acquired by calling the ExAcquireRundownProtection routine.
old-location: kernel\exreleaserundownprotection.htm
old-project: kernel
ms.assetid: 442FD107-04D4-4194-B64A-21699A70B4B6
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: ExReleaseRundownProtection, ExReleaseRundownProtection routine [Kernel-Mode Driver Architecture], kernel.exreleaserundownprotection, wdm/ExReleaseRundownProtection
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	ExReleaseRundownProtection
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# ExReleaseRundownProtection function


## -description


The <b>ExReleaseRundownProtection</b> routine releases run-down protection that the caller previously acquired by calling the <a href="..\wdm\nf-wdm-exacquirerundownprotection.md">ExAcquireRundownProtection</a> routine.


## -syntax


````
VOID ExReleaseRundownProtection(
  _Inout_ PEX_RUNDOWN_REF RunRef
);
````


## -parameters




### -param RunRef [in, out]

A pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/jj569379">EX_RUNDOWN_REF</a> structure that was initialized by a previous call to the  <a href="..\wdm\nf-wdm-exinitializerundownprotection.md">ExInitializeRundownProtection</a> routine. The run-down protection routines use this structure to track the run-down status of the associated shared object. This structure is opaque to drivers.


## -returns



None.




## -remarks



A driver that calls <a href="..\wdm\nf-wdm-exacquirerundownprotection.md">ExAcquireRundownProtection</a> to acquire run-time protection for an object access is responsible for calling <b>ExReleaseRundownProtection</b> to release the run-time protection when the access is finished.

For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/jj569382">Run-Down Protection</a>.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/jj569379">EX_RUNDOWN_REF</a>



<a href="..\wdm\nf-wdm-exacquirerundownprotection.md">ExAcquireRundownProtection</a>



<a href="..\wdm\nf-wdm-exinitializerundownprotection.md">ExInitializeRundownProtection</a>



 

 


