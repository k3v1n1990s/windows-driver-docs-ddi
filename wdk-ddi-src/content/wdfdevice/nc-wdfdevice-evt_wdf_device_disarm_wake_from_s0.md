---
UID: NC:wdfdevice.EVT_WDF_DEVICE_DISARM_WAKE_FROM_S0
title: EVT_WDF_DEVICE_DISARM_WAKE_FROM_S0
author: windows-driver-content
description: A driver's EvtDeviceDisarmWakeFromS0 event callback function disarms (that is, disables) a device's ability to trigger a wake signal while in a low-power device state, if the system remains in the system working state (S0).
old-location: wdf\evtdevicedisarmwakefroms0.htm
old-project: wdf
ms.assetid: e944c299-d0b4-4ee3-8f46-0458807e4cee
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFDeviceObjectGeneralRef_75c64592-ec2c-471f-9f9d-484ab181e432.xml, EVT_WDF_DEVICE_DISARM_WAKE_FROM_S0, EvtDeviceDisarmWakeFromS0, EvtDeviceDisarmWakeFromS0 callback function, kmdf.evtdevicedisarmwakefroms0, wdf.evtdevicedisarmwakefroms0, wdfdevice/EvtDeviceDisarmWakeFromS0
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL (see Remarks section)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Wdfdevice.h
api_name:
-	EvtDeviceDisarmWakeFromS0
product: Windows
targetos: Windows
req.typenames: WDF_DEVICE_SHUTDOWN_FLAGS
req.product: Windows 10 or later.
---

# EVT_WDF_DEVICE_DISARM_WAKE_FROM_S0 callback


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

A driver's <i>EvtDeviceDisarmWakeFromS0</i> event callback function disarms (that is, disables) a device's ability to trigger a wake signal while in a low-power device state, if the system remains in the <a href="https://msdn.microsoft.com/93ab0943-a4cc-4ef0-a250-1c63b2c915d5">system working state</a> (S0). 


## -prototype


````
EVT_WDF_DEVICE_DISARM_WAKE_FROM_S0 EvtDeviceDisarmWakeFromS0;

VOID EvtDeviceDisarmWakeFromS0(
  _In_ WDFDEVICE Device
)
{ ... }
````


## -parameters




### -param Device [in]

A handle to a framework device object.


## -returns



None




## -remarks



To register an <i>EvtDeviceDisarmWakeFromS0</i> callback function, a driver must call <a href="..\wdfdevice\nf-wdfdevice-wdfdeviceinitsetpowerpolicyeventcallbacks.md">WdfDeviceInitSetPowerPolicyEventCallbacks</a>. The driver must also set <b>IdleCanWakeFromS0</b> in the <b>IdleCaps</b> member of its <a href="..\wdfdevice\ns-wdfdevice-_wdf_device_power_policy_idle_settings.md">WDF_DEVICE_POWER_POLICY_IDLE_SETTINGS</a> structure.

If the driver has registered an <i>EvtDeviceDisarmWakeFromS0</i> callback function, the framework calls it after the bus driver determines that an event has awakened the device, and after the bus driver subsequently completes the <a href="https://msdn.microsoft.com/ed582644-af51-4841-be59-6a3deb6d9de5">wait/wake IRP</a>. Before calling the driver's <i>EvtDeviceDisarmWakeFromS0</i><i>EvtDeviceDisarmWakeFromS0</i> callback function, the framework calls the driver's <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_d0_entry.md">EvtDeviceD0Entry</a>, <a href="..\wdfinterrupt\nc-wdfinterrupt-evt_wdf_interrupt_enable.md">EvtInterruptEnable</a>, and <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_wake_from_s0_triggered.md">EvtDeviceWakeFromS0Triggered</a> callback functions.

The <i>EvtDeviceDisarmWakeFromS0</i> callback function must perform any hardware operations that are needed to disable the device's ability to trigger a wake signal after the power has been lowered.

For more information about when the framework calls this callback function, see <a href="https://msdn.microsoft.com/9175ce95-196d-44bd-b31c-88386fa0d3d3">PnP and Power Management Scenarios</a>.

For more information about this callback function, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/supporting-idle-power-down">Supporting Idle Power-Down</a>.

The <i>EvtDeviceDisarmWakeFromS0</i> callback function is called at IRQL = PASSIVE_LEVEL. You should not make this callback function <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/creating-pageable-code-in-a-kmdf-driver">pageable</a>.


#### Examples

To define an <i>EvtDeviceDisarmWakeFromS0</i> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtDeviceDisarmWakeFromS0</i> callback function that is named <i>MyDeviceDisarmWakeFromS0</i>, use the <b>EVT_WDF_DEVICE_DISARM_WAKE_FROM_S0</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_WDF_DEVICE_DISARM_WAKE_FROM_S0  MyDeviceDisarmWakeFromS0;</pre>
</td>
</tr>
</table></span></div>
Then, implement your callback function as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>_Use_decl_annotations_
VOID
 MyDeviceDisarmWakeFromS0 (
    WDFDEVICE  Device
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>EVT_WDF_DEVICE_DISARM_WAKE_FROM_S0</b> function type is defined in the Wdfdevice.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_WDF_DEVICE_DISARM_WAKE_FROM_S0</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/73a408ba-0219-4fde-8dad-ca330e4e67c3">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://msdn.microsoft.com/en-US/library/c0aa268d-6fa3-4ced-a8c6-f7652b152e61">Annotating Function Behavior</a>.




## -see-also

<a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_disarm_wake_from_sx.md">EvtDeviceDisarmWakeFromSx</a>



<a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_arm_wake_from_s0.md">EvtDeviceArmWakeFromS0</a>



 

 


