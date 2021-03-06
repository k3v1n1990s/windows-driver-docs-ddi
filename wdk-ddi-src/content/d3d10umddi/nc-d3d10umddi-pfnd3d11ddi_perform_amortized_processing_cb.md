---
UID: NC:d3d10umddi.PFND3D11DDI_PERFORM_AMORTIZED_PROCESSING_CB
title: PFND3D11DDI_PERFORM_AMORTIZED_PROCESSING_CB
author: windows-driver-content
description: The pfnPerformAmortizedProcessingCb function performs amortized processing.
old-location: display\pfnperformamortizedprocessingcb.htm
old-project: display
ms.assetid: 6b9fd47f-c6b6-4541-a014-0cd6604eb3b3
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: PFND3D11DDI_PERFORM_AMORTIZED_PROCESSING_CB, d3d10umddi/pfnPerformAmortizedProcessingCb, d3d11state_functions_7da0e622-fd33-44b6-a096-143ff6c47953.xml, display.pfnperformamortizedprocessingcb, pfnPerformAmortizedProcessingCb, pfnPerformAmortizedProcessingCb callback function [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: pfnPerformAmortizedProcessingCb is supported beginning with the Windows 7 operating system.
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	d3d10umddi.h
api_name:
-	pfnPerformAmortizedProcessingCb
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---

# PFND3D11DDI_PERFORM_AMORTIZED_PROCESSING_CB callback


## -description


The <b>pfnPerformAmortizedProcessingCb</b> function performs amortized processing. 


## -prototype


````
PFND3D11DDI_PERFORM_AMORTIZED_PROCESSING_CB pfnPerformAmortizedProcessingCb;

void APIENTRY pfnPerformAmortizedProcessingCb(
  _In_ D3D10DDI_HRTCORELAYER hRuntimeDevice
)
{ ... }
````


## -parameters




### -param D3D10DDI_HRTCORELAYER








#### - hRuntimeDevice [in]

 A handle to a context for the core Microsoft Direct3D runtime. This handle is supplied to the driver in a call to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createdevice.md">CreateDevice(D3D10)</a> function. 


## -returns



None




## -remarks



For more information about amortized processing, see <a href="https://msdn.microsoft.com/014a5e44-f8c4-45c0-96e8-d82f37b8b28d">Changes from Direct3D 10</a>.




## -see-also

<a href="..\d3d10umddi\ns-d3d10umddi-d3d11ddi_corelayer_devicecallbacks.md">D3D11DDI_CORELAYER_DEVICECALLBACKS</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createdevice.md">CreateDevice(D3D10)</a>



 

 


