---
UID: NF:ks.KsInitializeDriver
title: KsInitializeDriver function
author: windows-driver-content
description: The KsInitializeDriver function initializes the driver object of an AVStream minidriver.
old-location: stream\ksinitializedriver.htm
old-project: stream
ms.assetid: 5a77e59f-ce64-4ff2-ac95-c9062cef20d2
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: KsInitializeDriver, KsInitializeDriver function [Streaming Media Devices], avfunc_2a16bc8c-a92a-4792-8007-29735a19f806.xml, ks/KsInitializeDriver, stream.ksinitializedriver
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
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
req.lib: Ks.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Ks.lib
-	Ks.dll
api_name:
-	KsInitializeDriver
product: Windows
targetos: Windows
req.typenames: 
---

# KsInitializeDriver function


## -description


The<b> KsInitializeDriver </b>function initializes the driver object of an AVStream minidriver.


## -syntax


````
NTSTATUS KsInitializeDriver(
  _In_           PDRIVER_OBJECT      DriverObject,
  _In_           PUNICODE_STRING     RegistryPath,
  _In_opt_ const KSDEVICE_DESCRIPTOR *Descriptor
);
````


## -parameters




### -param DriverObject [in]

A pointer to the <a href="..\wdm\ns-wdm-_driver_object.md">DRIVER_OBJECT</a> structure for the AVStream driver being initialized. Minidrivers that call <b>KsInitializeDriver</b> should use the driver object passed to <b>DriverEntry</b> by the operating system.


### -param RegistryPathName

A pointer to a Unicode string containing the registry path string passed into the minidriver's **DriverEntry** function by the operating system.


### -param Descriptor [in, optional]

A pointer to a <a href="..\ks\ns-ks-_ksdevice_descriptor.md">KSDEVICE_DESCRIPTOR</a> structure that specifies the characteristics of the device being initialized. If this pointer is <b>NULL</b>, a device is created with default characteristics and no associated filter factories.


#### - RegistryPath [in]

A pointer to a Unicode string containing the registry path string passed into the minidriver's <b>DriverEntry</b> function by the operating system.


## -returns



<b>KsInitializeDriver</b> returns STATUS_SUCCESS or an appropriate error code as returned by <a href="..\wdm\nf-wdm-iocreatedevice.md">IoCreateDevice</a> or internal AVStream device initialization routines.  




## -remarks



This function is typically called from <b>DriverEntry</b>. If the minidriver passes in a device descriptor, AVStream creates a device with the specified characteristics at <b>AddDevice</b> time. Minidrivers that perform device initialization themselves do not necessarily need to call <b>KsInitializeDriver</b>.  For more information, see <a href="https://msdn.microsoft.com/666d6efb-93ec-43f3-87c5-ea1a3983bfd0">Initializing an AVStream Minidriver</a>.




## -see-also

<a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a>



<a href="..\ks\nf-ks-ksinitializedevice.md">KsInitializeDevice</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff558721">DriverEntry of AVStream</a>



<a href="..\wdm\ns-wdm-_driver_object.md">DRIVER_OBJECT</a>



<a href="..\ks\ns-ks-_ksfilter_descriptor.md">KSFILTER_DESCRIPTOR</a>



<a href="..\ks\ns-ks-_ksdevice_dispatch.md">KSDEVICE_DISPATCH</a>



<a href="..\ks\ns-ks-_ksdevice_descriptor.md">KSDEVICE_DESCRIPTOR</a>



<a href="..\wdm\nf-wdm-iocreatedevice.md">IoCreateDevice</a>



 

 


