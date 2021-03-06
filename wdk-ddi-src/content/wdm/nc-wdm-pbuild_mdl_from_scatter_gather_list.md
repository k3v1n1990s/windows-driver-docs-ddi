---
UID: NC:wdm.PBUILD_MDL_FROM_SCATTER_GATHER_LIST
title: PBUILD_MDL_FROM_SCATTER_GATHER_LIST
author: windows-driver-content
description: The BuildMdlFromScatterGatherList routine builds an MDL from a scatter/gather list allocated by the system.Note  This routine is reserved for system use.
old-location: kernel\buildmdlfromscattergatherlist.htm
old-project: kernel
ms.assetid: 2bf190a3-cc42-42b4-b687-cd66021e66c2
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: BuildMdlFromScatterGatherList, BuildMdlFromScatterGatherList callback function [Kernel-Mode Driver Architecture], PBUILD_MDL_FROM_SCATTER_GATHER_LIST, kdma_8a1b5bc2-b0ff-41ca-b352-647a0e7b4a79.xml, kernel.buildmdlfromscattergatherlist, wdm/BuildMdlFromScatterGatherList
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wdm.h
req.include-header: Wdm.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows XP and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlDispatch
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	wdm.h
api_name:
-	BuildMdlFromScatterGatherList
product: Windows
targetos: Windows
req.typenames: WDI_TYPE_PMK_NAME, *PWDI_TYPE_PMK_NAME
req.product: Windows 10 or later.
---

# PBUILD_MDL_FROM_SCATTER_GATHER_LIST callback


## -description


The <b>BuildMdlFromScatterGatherList</b> routine builds an MDL from a scatter/gather list allocated by the system.
<div class="alert"><b>Note</b>  This routine is reserved for system use.</div><div> </div>

## -prototype


````
PBUILD_MDL_FROM_SCATTER_GATHER_LIST BuildMdlFromScatterGatherList;

NTSTATUS BuildMdlFromScatterGatherList(
  _In_  PADAPTER_OBJECT      DmaAdapter,
  _In_  PSCATTER_GATHER_LIST ScatterGather,
  _In_  PMDL                 OriginalMdl,
  _Out_ PMDL                 *TargetMdl
)
{ ... }
````


## -parameters




### -param DmaAdapter [in]

Pointer to the <a href="..\wdm\ns-wdm-_dma_adapter.md">DMA_ADAPTER</a> structure returned by <a href="..\wdm\nf-wdm-iogetdmaadapter.md">IoGetDmaAdapter</a> that represents the bus-master adapter or DMA controller.


### -param ScatterGather [in]

Pointer to the <a href="..\wdm\ns-wdm-_scatter_gather_list.md">SCATTER_GATHER_LIST</a> structure passed to the driver's <a href="..\wdm\nc-wdm-driver_list_control.md">AdapterListControl</a> routine.


### -param OriginalMdl [in]

Pointer to the original MDL that the driver used to build the scatter/gather list.


### -param *TargetMdl [out]

Pointer to a variable the routine uses to return the MDL created to hold the buffer described by the scatter/gather list. The value returned can be the same as <i>OriginalMdl</i>.


## -returns



<b>BuildMdlFromScatterGatherList</b> returns one of the following status codes:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The operation succeeded.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The <i>OriginalMdl</i> parameter is <b>NULL</b>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
There is not enough memory available to allocate a new MDL.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NONE_MAPPED</b></dt>
</dl>
</td>
<td width="60%">
The system has already created a new MDL for the memory locations in the scatter/gather list. (This only happens if the routine is called twice on the same scatter/gather list.)

</td>
</tr>
</table>
 




## -remarks



<b>BuildMdlFromScatterGatherList</b>
           is not a system routine that can be called directly by name. This routine can be called only by pointer from the address returned in a 
          <a href="..\wdm\ns-wdm-_dma_operations.md">DMA_OPERATIONS</a>
           structure. Drivers obtain the address of this routine by calling <a href="..\wdm\nf-wdm-iogetdmaadapter.md">IoGetDmaAdapter</a> with the <b>Version</b> member of the <i>DeviceDescription</i> parameter set to DEVICE_DESCRIPTION_VERSION2. If <b>IoGetDmaAdapter</b> returns <b>NULL</b>, the routine is not available on your platform.

When a driver creates a scatter/gather list to write to a device, the system can make a copy of the data to be written, and use that copy to perform the DMA operation. Use this routine to access the memory locations in the scatter/gather list, regardless of whether those locations are a copy.




## -see-also

<a href="..\wdm\ns-wdm-_dma_operations.md">DMA_OPERATIONS</a>



<a href="..\wdm\ns-wdm-_dma_adapter.md">DMA_ADAPTER</a>



<a href="..\wdm\nf-wdm-iogetdmaadapter.md">IoGetDmaAdapter</a>



<a href="..\wdm\ns-wdm-_device_description.md">DEVICE_DESCRIPTION</a>



<a href="..\wdm\nc-wdm-pbuild_scatter_gather_list.md">BuildScatterGatherList</a>



<a href="..\wdm\ns-wdm-_scatter_gather_list.md">SCATTER_GATHER_LIST</a>



 

 


