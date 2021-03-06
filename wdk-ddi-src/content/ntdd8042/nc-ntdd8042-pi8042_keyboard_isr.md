---
UID: NC:ntdd8042.PI8042_KEYBOARD_ISR
title: PI8042_KEYBOARD_ISR
author: windows-driver-content
description: A PI8042_KEYBOARD_ISR-typed callback routine customizes the operation of the I8042prt keyboard ISR.
old-location: hid\pi8042_keyboard_isr.htm
old-project: hid
ms.assetid: e21fa089-0650-4a3f-96f9-f479d36ef080
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: KeyboardIsr, KeyboardIsr callback function [Human Input Devices], PI8042_KEYBOARD_ISR, hid.pi8042_keyboard_isr, i8042ref_34293f47-3e6c-4721-ab58-8ac531543c8e.xml, ntdd8042/KeyboardIsr
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ntdd8042.h
req.include-header: Ntdd8042.h
req.target-type: Desktop
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
req.irql: See Remarks section.
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	ntdd8042.h
api_name:
-	KeyboardIsr
product: Windows
targetos: Windows
req.typenames: MSFC_VirtualFibrePortAttributes, *PMSFC_VirtualFibrePortAttributes
---

# PI8042_KEYBOARD_ISR callback


## -description


A PI8042_KEYBOARD_ISR-typed callback routine customizes the operation of the I8042prt keyboard ISR.


## -prototype


````
PI8042_KEYBOARD_ISR KeyboardIsr;

BOOLEAN KeyboardIsr(
  _In_  PVOID                IsrContext,
  _In_  PKEYBOARD_INPUT_DATA CurrentInput,
  _In_  POUTPUT_PACKET       CurrentOutput,
  _In_  UCHAR                StatusByte,
  _In_  PUCHAR               Byte,
  _Out_ PBOOLEAN             ContinueProcessing,
  _In_  PKEYBOARD_SCAN_STATE ScanState
)
{ ... }
````


## -parameters




### -param IsrContext [in]

Pointer to the filter device object of the driver that supplies a callback.


### -param CurrentInput [in]

Pointer to the input <a href="https://msdn.microsoft.com/library/windows/hardware/ff542337">KEYBOARD_INPUT_DATA</a> structure that is being constructed by the ISR.


### -param CurrentOutput [in]

Pointer to an <a href="..\ntdd8042\ns-ntdd8042-_output_packet.md">OUTPUT_PACKET</a> structure, which specifies an array of bytes that is being written to the hardware device.


### -param StatusByte [in]

Specifies the status byte that is read from I/O port 60 when an interrupt occurs.


### -param Byte [in]

Specifies the data byte that is read  from I/O port 64 when an interrupt occurs.


### -param ContinueProcessing [out]

Specifies, if <b>TRUE</b>, that processing in the I8042prt keyboard ISR will continue after this callback completes. Otherwise, processing does not continue.


### -param ScanState [in]

Pointer to a <a href="..\ntdd8042\ne-ntdd8042-_keyboard_scan_state.md">KEYBOARD_SCAN_STATE</a> enumeration value, which identifies the keyboard scan state.


## -returns



A PI8042_KEYBOARD_ISR callback returns <b>TRUE</b> if the I8042prt keyboard ISR should continue; otherwise it returns <b>FALSE</b>.




## -remarks



A PI8042_KEYBOARD_ISR callback is not needed if the default operation of the I8042prt keyboard ISR is sufficient. 

An optional, vendor-supplied, upper-level keyboard filter driver can provide a PI8042_KEYBOARD_ISR callback. The I8042prt ISR calls the callback after it validates the interrupt and reads the scan code. 

The PI8042_KEYBOARD_ISR callback runs in kernel mode at the IRQL of the I8042prt keyboard ISR.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff542337">KEYBOARD_INPUT_DATA</a>



<a href="..\ntdd8042\nc-ntdd8042-pi8042_keyboard_isr.md">PI8042_KEYBOARD_ISR</a>



<a href="https://msdn.microsoft.com/0feca7de-aa80-4d1e-a5fc-901c18169649">KbFilter_IsrHook</a>



<a href="..\ntdd8042\ns-ntdd8042-_output_packet.md">OUTPUT_PACKET</a>



<a href="..\ntdd8042\ne-ntdd8042-_keyboard_scan_state.md">KEYBOARD_SCAN_STATE</a>



 

 


