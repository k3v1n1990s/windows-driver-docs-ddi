---
UID: NF:wdfdevice.WdfDeviceInitRegisterPnpStateChangeCallback
title: WdfDeviceInitRegisterPnpStateChangeCallback function
author: windows-driver-content
description: The WdfDeviceInitRegisterPnpStateChangeCallback method registers a driver-supplied event callback function that the framework calls when a device's Plug and Play state machine changes state.
old-location: wdf\wdfdeviceinitregisterpnpstatechangecallback.htm
old-project: wdf
ms.assetid: a14b790a-28d7-4fb8-823f-f37f05e7529f
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFDeviceObjectGeneralRef_51127783-092b-409d-85ad-e502760b62e7.xml, WdfDeviceInitRegisterPnpStateChangeCallback, WdfDeviceInitRegisterPnpStateChangeCallback method, kmdf.wdfdeviceinitregisterpnpstatechangecallback, wdf.wdfdeviceinitregisterpnpstatechangecallback, wdfdevice/WdfDeviceInitRegisterPnpStateChangeCallback
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.ddi-compliance: ChildDeviceInitAPI, DeviceInitAPI, DriverCreate, InitFreeDeviceCallback, InitFreeDeviceCreate, InitFreeNull, KmdfIrql, KmdfIrql2, PdoDeviceInitAPI, PdoInitFreeDeviceCallback, PdoInitFreeDeviceCreate
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Wdf01000.sys
-	Wdf01000.sys.dll
api_name:
-	WdfDeviceInitRegisterPnpStateChangeCallback
product: Windows
targetos: Windows
req.typenames: WDF_STATE_NOTIFICATION_TYPE
req.product: Windows 10 or later.
---

# WdfDeviceInitRegisterPnpStateChangeCallback function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfDeviceInitRegisterPnpStateChangeCallback</b> method registers a driver-supplied event callback function that the framework calls when a device's Plug and Play state machine changes state.


## -syntax


````
NTSTATUS WdfDeviceInitRegisterPnpStateChangeCallback(
  _In_ PWDFDEVICE_INIT                              DeviceInit,
  _In_ WDF_DEVICE_PNP_STATE                         PnpState,
  _In_ PFN_WDF_DEVICE_PNP_STATE_CHANGE_NOTIFICATION EvtDevicePnpStateChange,
  _In_ ULONG                                        CallbackTypes
);
````


## -parameters




### -param DeviceInit [in]

A caller-supplied pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff546951">WDFDEVICE_INIT</a> structure.


### -param PnpState [in]

A <a href="..\wdfdevice\ne-wdfdevice-_wdf_device_pnp_state.md">WDF_DEVICE_PNP_STATE</a> enumerator that identifies the Plug and Play machine state for which the driver is requesting notification.


### -param EvtDevicePnpStateChange [in]

A caller-supplied pointer to the driver's <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_pnp_state_change_notification.md">EvtDevicePnpStateChange</a> event callback function.


### -param CallbackTypes [in]

An ORed combination of <a href="..\wdfdevice\ne-wdfdevice-_wdf_state_notification_type.md">WDF_STATE_NOTIFICATION_TYPE</a>-typed enumerators.


## -returns



If the operation succeeds, <b>WdfDeviceInitRegisterPnpStateChangeCallback</b> returns STATUS_SUCCESS. Additional return values include:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
An invalid parameter was detected.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
There is insufficient memory to complete the operation.

</td>
</tr>
</table>
 




## -remarks



If your driver calls <b>WdfDeviceInitRegisterPnpStateChangeCallback</b>, it must do so before it calls <a href="..\wdfdevice\nf-wdfdevice-wdfdevicecreate.md">WdfDeviceCreate</a>.

For more information about <b>WdfDeviceInitRegisterPnpStateChangeCallback</b>, see <a href="https://msdn.microsoft.com/5ef307c6-0310-4a83-a63f-3a6d96782013">State Machines in the Framework</a>.


#### Examples

The following code example registers an event callback function that the framework will call when the device's Plug and Play state machine changes state.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>status = WdfDeviceInitRegisterPnpStateChangeCallback(
                                                     DeviceInit,
                                                     WdfDevStatePnpEjectFailed,
                                                     MyDrvPnPStateChangeCallback,
                                                     StateNotificationAllStates
                                                     );</pre>
</td>
</tr>
</table></span></div>



## -see-also

<a href="..\wdfdevice\ne-wdfdevice-_wdf_state_notification_type.md">WDF_STATE_NOTIFICATION_TYPE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546951">WDFDEVICE_INIT</a>



<a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_pnp_state_change_notification.md">EvtDevicePnpStateChange</a>



<a href="..\wdfdevice\ne-wdfdevice-_wdf_device_pnp_state.md">WDF_DEVICE_PNP_STATE</a>



 

 


