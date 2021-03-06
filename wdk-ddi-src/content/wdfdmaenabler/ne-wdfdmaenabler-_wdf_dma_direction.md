---
UID: NE:wdfdmaenabler._WDF_DMA_DIRECTION
title: "_WDF_DMA_DIRECTION"
author: windows-driver-content
description: The WDF_DMA_DIRECTION enumeration defines the direction of a DMA transfer.
old-location: wdf\wdf_dma_direction.htm
old-project: wdf
ms.assetid: 813414fa-17b6-4b69-a3dd-f3a2e5190305
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFDmaObjectRef_e790f51f-b8cb-4e04-a5f3-49f24fabf5b8.xml, WDF_DMA_DIRECTION, WDF_DMA_DIRECTION enumeration, WdfDmaDirectionReadFromDevice, WdfDmaDirectionWriteToDevice, _WDF_DMA_DIRECTION, kmdf.wdf_dma_direction, wdf.wdf_dma_direction, wdfdmaenabler/WDF_DMA_DIRECTION, wdfdmaenabler/WdfDmaDirectionReadFromDevice, wdfdmaenabler/WdfDmaDirectionWriteToDevice
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wdfdmaenabler.h
req.include-header: Wdf.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
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
-	HeaderDef
api_location:
-	wdfdmaenabler.h
api_name:
-	WDF_DMA_DIRECTION
product: Windows
targetos: Windows
req.typenames: WDF_DMA_DIRECTION
req.product: Windows 10 or later.
---

# _WDF_DMA_DIRECTION enumeration


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WDF_DMA_DIRECTION</b> enumeration defines the direction of a DMA transfer.


## -syntax


````
typedef enum _WDF_DMA_DIRECTION { 
  WdfDmaDirectionReadFromDevice  = FALSE,
  WdfDmaDirectionWriteToDevice   = TRUE
} WDF_DMA_DIRECTION;
````


## -enum-fields




### -field WdfDmaDirectionReadFromDevice

The DMA transfer direction is from the device (read).


### -field WdfDmaDirectionWriteToDevice

The DMA transfer direction is to the device (write).


## -remarks



The <b>WDF_DMA_DIRECTION</b> enumeration is used as input to the <a href="https://msdn.microsoft.com/c01b94b2-aabf-47dd-952a-06e481579614">EvtProgramDma</a> callback function and the <a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactioninitialize.md">WdfDmaTransactionInitialize</a> and <a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactioninitializeusingrequest.md">WdfDmaTransactionInitializeUsingRequest</a> methods.




## -see-also

<a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactioninitialize.md">WdfDmaTransactionInitialize</a>



<a href="https://msdn.microsoft.com/c01b94b2-aabf-47dd-952a-06e481579614">EvtProgramDma</a>



<a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactioninitializeusingrequest.md">WdfDmaTransactionInitializeUsingRequest</a>



 

 


