---
UID: NI:ntddsysenv.IOCTL_SYSENV_SET_VARIABLE
title: IOCTL_SYSENV_SET_VARIABLE
author: windows-driver-content
description: Sets the value of the specified system environment variables using SysEnv device.
old-location: kernel\ioctl_ioctl_sysenv_set_variable.htm
old-project: kernel
ms.assetid: 2BA555D8-CFD3-4D27-BC38-3B261D2F95EF
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: IOCTL_SYSENV_SET_VARIABLE, IOCTL_SYSENV_SET_VARIABLE control code [Kernel-Mode Driver Architecture], kernel.ioctl_ioctl_sysenv_set_variable, ntddsysenv/IOCTL_SYSENV_SET_VARIABLE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ntddsysenv.h
req.include-header: 
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
-	Ntddsysenv.h
api_name:
-	IOCTL_SYSENV_SET_VARIABLE
product: Windows
targetos: Windows
req.typenames: STORAGE_ZONE_GROUP, *PSTORAGE_ZONE_GROUP
---

# IOCTL_SYSENV_SET_VARIABLE IOCTL


## -description



Sets the value of the specified system environment variables using
    SysEnv device.





## -ioctlparameters




### -input-buffer

A pointer to a  <a href="..\ntddsysenv\ns-ntddsysenv-_xvariable_name_and_value.md">XVARIABLE_NAME_AND_VALUE</a> structure that contains the information to set.


### -input-buffer-length

The size of the <a href="..\ntddsysenv\ns-ntddsysenv-_xvariable_name_and_value.md">XVARIABLE_NAME_AND_VALUE</a> structure.


### -output-buffer



<text></text>




### -output-buffer-length



<text></text>




### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

<b>Irp-&gt;IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> code. 


## -see-also

<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendioctlsynchronously.md">WdfIoTargetSendIoctlSynchronously</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542894">Creating IOCTL Requests in Drivers</a>



<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendinternalioctlotherssynchronously.md">WdfIoTargetSendInternalIoctlOthersSynchronously</a>



<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendinternalioctlsynchronously.md">WdfIoTargetSendInternalIoctlSynchronously</a>



 

 


