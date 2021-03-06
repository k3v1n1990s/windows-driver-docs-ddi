---
UID: NF:udecxusbdevice.UdecxUsbDeviceSignalFunctionWake
title: UdecxUsbDeviceSignalFunctionWake function
author: windows-driver-content
description: Initiates wake up of the specified function from a low power state. This applies to virtual USB 3.0 devices.
old-location: buses\udecxusbdevicesignalfunctionwake.htm
old-project: usbref
ms.assetid: 82B3B3BD-CEAC-427E-A89E-84CBE85BDBE7
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: UdecxUsbDeviceSignalFunctionWake, UdecxUsbDeviceSignalFunctionWake function [Buses], buses.udecxusbdevicesignalfunctionwake, udecxusbdevice/UdecxUsbDeviceSignalFunctionWake
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: udecxusbdevice.h
req.include-header: Udecx.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 1.15
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Udecxstub.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Udecxstub.lib
-	Udecxstub.dll
api_name:
-	UdecxUsbDeviceSignalFunctionWake
product: Windows
targetos: Windows
req.typenames: UDECX_USB_DEVICE_WAKE_SETTING, *PUDECX_USB_DEVICE_WAKE_SETTING
req.product: Windows 10 or later.
---

# UdecxUsbDeviceSignalFunctionWake function


## -description


Initiates wake up of the specified function from a low power state. This applies to virtual USB 3.0 devices.


## -syntax


````
void UdecxUsbDeviceSignalFunctionWake(
  _In_ UDECXUSBDEVICE UdecxUsbDevice,
  _In_ ULONG          Interface
);
````


## -parameters




### -param UdecxUsbDevice [in]

A handle to UDE device object. The client driver retrieved this pointer in the previous call to <a href="..\udecxusbdevice\nf-udecxusbdevice-udecxusbdevicecreate.md">UdecxUsbDeviceCreate</a>.


### -param Interface [in]

This value is the <b>bInterfaceNumber</b> of the interface that is waking up. 


## -returns



This function does not return a value.




## -remarks



The client driver for the device must have enabled wake capability in the most recent <a href="..\udecxusbdevice\nc-udecxusbdevice-evt_udecx_usb_device_set_function_suspend_and_wake.md">EVT_UDECX_USB_DEVICE_SET_FUNCTION_SUSPEND_AND_WAKE</a> call.


If the device is in a low power state, or going to such a state, this call also wakes up  the entire device.





## -see-also

<a href="..\udecxusbdevice\nc-udecxusbdevice-evt_udecx_usb_device_set_function_suspend_and_wake.md">EVT_UDECX_USB_DEVICE_SET_FUNCTION_SUSPEND_AND_WAKE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt595939">Write a UDE client driver</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt595932">Architecture: USB Device Emulation (UDE)</a>



 

 


