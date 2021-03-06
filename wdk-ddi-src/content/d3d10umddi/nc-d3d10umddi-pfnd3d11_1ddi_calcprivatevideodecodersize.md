---
UID: NC:d3d10umddi.PFND3D11_1DDI_CALCPRIVATEVIDEODECODERSIZE
title: PFND3D11_1DDI_CALCPRIVATEVIDEODECODERSIZE
author: windows-driver-content
description: Returns the number of bytes that the driver requires to store private data for the video decoder state.
old-location: display\calcprivatevideodecodersize.htm
old-project: display
ms.assetid: a878cba1-589e-4932-9d2b-1abab417660f
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: CalcPrivateVideoDecoderSize, CalcPrivateVideoDecoderSize callback function [Display Devices], FND3D11_1DDI_CALCPRIVATEVIDEODECODERSIZE, d3d10umddi/CalcPrivateVideoDecoderSize, display.calcprivatevideodecodersize
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
-	D3d10umddi.h
api_name:
-	CalcPrivateVideoDecoderSize
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---

# PFND3D11_1DDI_CALCPRIVATEVIDEODECODERSIZE callback


## -description


Returns the number of bytes that the driver requires to store private data for the video decoder state.


## -prototype


````
FND3D11_1DDI_CALCPRIVATEVIDEODECODERSIZE CalcPrivateVideoDecoderSize;

SIZE_T APIENTRY* CalcPrivateVideoDecoderSize(
  _In_       D3D10DDI_HDEVICE                 hDevice,
  _In_ const D3D11_1DDIARG_CREATEVIDEODECODER *pDecoder
)
{ ... }
````


## -parameters




### -param D3D10DDI_HDEVICE


### -param *








#### - hDevice [in]

A handle to the display device (graphics context).




#### - pDecoder [in]

A pointer to a <a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddiarg_createvideodecoder.md">D3D11_1DDIARG_CREATEVIDEODECODER</a> structure that describes the video decoder.


## -returns



The required number of bytes for the video decoder state.




## -remarks



The runtime will validate the members of the <a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddiarg_createvideodecoder.md">D3D11_1DDIARG_CREATEVIDEODECODER</a> structure before it calls this function.

This function is not expected to fail.




## -see-also

<a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddiarg_createvideodecoder.md">D3D11_1DDIARG_CREATEVIDEODECODER</a>



 

 


