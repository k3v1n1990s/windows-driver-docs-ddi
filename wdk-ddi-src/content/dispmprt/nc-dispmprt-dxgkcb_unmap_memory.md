---
UID: NC:dispmprt.DXGKCB_UNMAP_MEMORY
title: DXGKCB_UNMAP_MEMORY
author: windows-driver-content
description: The DxgkCbUnmapMemory function unmaps a range of addresses previously mapped by DxgkCbMapMemory.
old-location: display\dxgkcbunmapmemory.htm
old-project: display
ms.assetid: 71e8eb0e-599b-44cf-955b-828f6667edf6
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DXGKCB_UNMAP_MEMORY, DpFunctions_d0ba5b02-22ab-4fad-a54a-1e402f538456.xml, DxgkCbUnmapMemory, DxgkCbUnmapMemory callback function [Display Devices], display.dxgkcbunmapmemory, dispmprt/DxgkCbUnmapMemory
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: dispmprt.h
req.include-header: Dispmprt.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	dispmprt.h
api_name:
-	DxgkCbUnmapMemory
product: Windows
targetos: Windows
req.typenames: SYMBOL_INFO_EX, *PSYMBOL_INFO_EX
---

# DXGKCB_UNMAP_MEMORY callback


## -description


The <b>DxgkCbUnmapMemory</b> function unmaps a range of addresses previously mapped by <a href="..\dispmprt\nc-dispmprt-dxgkcb_map_memory.md">DxgkCbMapMemory</a>.


## -prototype


````
DXGKCB_UNMAP_MEMORY DxgkCbUnmapMemory;

NTSTATUS DxgkCbUnmapMemory(
  _In_ HANDLE DeviceHandle,
  _In_ PVOID  VirtualAddress
)
{ ... }
````


## -parameters




### -param DeviceHandle [in]

A handle that represents a display adapter. The display miniport driver previously obtained this handle in the <b>DeviceHandle</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560942">DXGKRNL_INTERFACE</a> structure that was passed to <a href="..\dispmprt\nc-dispmprt-dxgkddi_start_device.md">DxgkDdiStartDevice</a>.


### -param VirtualAddress [in]

The beginning address of the range to be unmapped. This address can be a virtual address in system space, a virtual address in the address space of a user-mode process, or an address in I/O space.


## -returns



<b>DxgkCbUnmapMemory</b> returns STATUS_SUCCESS if it succeeds. Otherwise, it returns one of the error codes defined in <i>Ntstatus.h</i>.




## -see-also

<a href="..\dispmprt\nc-dispmprt-dxgkcb_map_memory.md">DxgkCbMapMemory</a>



 

 


