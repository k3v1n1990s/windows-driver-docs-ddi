---
UID: NF:wdfusb.WdfUsbTargetPipeSetNoMaximumPacketSizeCheck
title: WdfUsbTargetPipeSetNoMaximumPacketSizeCheck function
author: windows-driver-content
description: The WdfUsbTargetPipeSetNoMaximumPacketSizeCheck method disables the framework's test of whether the size of a driver's read buffer is a multiple of a USB pipe's maximum packet size.
old-location: wdf\wdfusbtargetpipesetnomaximumpacketsizecheck.htm
old-project: wdf
ms.assetid: 552eaf46-1710-4df5-bdc3-0fa7ce3adf54
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFUsbRef_e750d0d1-6d91-498d-8bb5-2eb9bab0149d.xml, WdfUsbTargetPipeSetNoMaximumPacketSizeCheck, WdfUsbTargetPipeSetNoMaximumPacketSizeCheck method, kmdf.wdfusbtargetpipesetnomaximumpacketsizecheck, wdf.wdfusbtargetpipesetnomaximumpacketsizecheck, wdfusb/WdfUsbTargetPipeSetNoMaximumPacketSizeCheck
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfusb.h
req.include-header: Wdfusb.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2, UsbKmdfIrql, UsbKmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Wdf01000.sys
-	Wdf01000.sys.dll
-	WUDFx02000.dll
-	WUDFx02000.dll.dll
api_name:
-	WdfUsbTargetPipeSetNoMaximumPacketSizeCheck
product: Windows
targetos: Windows
req.typenames: WDF_USB_REQUEST_TYPE, *PWDF_USB_REQUEST_TYPE
req.product: Windows 10 or later.
---

# WdfUsbTargetPipeSetNoMaximumPacketSizeCheck function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfUsbTargetPipeSetNoMaximumPacketSizeCheck</b> method disables the framework's test of whether the size of a driver's read buffer is a multiple of a USB pipe's maximum packet size.


## -syntax


````
VOID WdfUsbTargetPipeSetNoMaximumPacketSizeCheck(
  _In_ WDFUSBPIPE Pipe
);
````


## -parameters




### -param Pipe [in]

A handle to a framework pipe object that was obtained by calling <a href="..\wdfusb\nf-wdfusb-wdfusbinterfacegetconfiguredpipe.md">WdfUsbInterfaceGetConfiguredPipe</a>. 


## -returns



None.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



To avoid receiving extra data from unexpected bus activity, which is sometimes called <i>babble</i>, drivers usually specify read buffers that are a multiple of the pipe's maximum packet size. (Drivers receive a USB pipe's maximum packet size in a <a href="..\wdfusb\ns-wdfusb-_wdf_usb_pipe_information.md">WDF_USB_PIPE_INFORMATION</a> structure.) By default, the framework reports an error if a driver specifies a read buffer that is not a multiple of the pipe's maximum packet size. If the driver calls <b>WdfUsbTargetPipeSetNoMaximumPacketSizeCheck</b>, the framework does not report an error if a read buffer is not a multiple of the maximum packet size.

For more information about the <b>WdfUsbTargetPipeSetNoMaximumPacketSizeCheck</b> method and USB I/O targets, see <a href="https://msdn.microsoft.com/195c0f4b-7f33-428a-8de7-32643ad854c6">USB I/O Targets</a>.


#### Examples

The following code example disables the framework's test of whether the size of a buffer is a multiple of a USB pipe's maximum packet size.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WdfUsbTargetPipeSetNoMaximumPacketSizeCheck(pipe);
 </pre>
</td>
</tr>
</table></span></div>



## -see-also

<a href="..\wdfusb\ns-wdfusb-_wdf_usb_pipe_information.md">WDF_USB_PIPE_INFORMATION</a>



<a href="..\wdfusb\nf-wdfusb-wdfusbinterfacegetconfiguredpipe.md">WdfUsbInterfaceGetConfiguredPipe</a>



 

 


