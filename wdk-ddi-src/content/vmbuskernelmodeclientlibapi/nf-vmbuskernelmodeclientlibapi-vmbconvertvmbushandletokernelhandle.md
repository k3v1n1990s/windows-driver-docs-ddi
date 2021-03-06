---
UID: NF:vmbuskernelmodeclientlibapi.VmbConvertVmbusHandleToKernelHandle
title: VmbConvertVmbusHandleToKernelHandle function
author: windows-driver-content
description: The VmbConvertVmbusHandleToKernelHandle function converts the user mode VMBus handle to kernel mode handle.
old-location: netvista\vmbconvertvmbushandletokernelhandle.htm
old-project: netvista
ms.assetid: C549B9C7-221D-4DD8-9D8D-24BC729099C7
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: VmbConvertVmbusHandleToKernelHandle, VmbConvertVmbusHandleToKernelHandle function [Network Drivers Starting with Windows Vista], netvista.vmbconvertvmbushandletokernelhandle, vmbuskernelmodeclientlibapi/VmbConvertVmbusHandleToKernelHandle
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: vmbuskernelmodeclientlibapi.h
req.include-header: VmbusKernelModeClientLibApi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
req.kmdf-ver: 1.13
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	VmbusKernelModeClientLibApi.h
api_name:
-	VmbConvertVmbusHandleToKernelHandle
product: Windows
targetos: Windows
req.typenames: VIDEO_PORT_AGP_SERVICES, *PVIDEO_PORT_AGP_SERVICES
req.product: Windows 10 or later.
---

# VmbConvertVmbusHandleToKernelHandle function


## -description


<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>VmbConvertVmbusHandleToKernelHandle</b> function converts the user mode VMBus handle to kernel mode handle. 


## -syntax


````
NTSTATUS VmbConvertVmbusHandleToKernelHandle(
  _In_  HANDLE  VmbusHandle,
  _Out_ PHANDLE KernelHandle
);
````


## -parameters




### -param VmbusHandle [in]

The user-mode handle to convert. This must have been was opened in the virtual machine worker process.



### -param KernelHandle [out]

The kernel handle that references the same object as the <i>VmbusHandle</i> value.


## -remarks



The
caller is responsible to close the kernel handle.


Because the <i>VmbusHandle</i> parameter is a user-mode
handle, this function must be called in the context of the user-mode process which
opened the VMBus handle.

  Calling this function is often immediately followed by calling
the <a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmbserverchannelinitsetvmbushandle.md">VmbServerChannelInitSetVmbusHandle</a> function.




## -see-also

<a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmbserverchannelinitsetvmbushandle.md">VmbServerChannelInitSetVmbusHandle</a>



 

 


