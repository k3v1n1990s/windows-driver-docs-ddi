---
UID: NC:d3d10umddi.PFND3D11_1DDI_CREATEVIDEODECODER
title: PFND3D11_1DDI_CREATEVIDEODECODER
author: windows-driver-content
description: Creates a video decoder object.
old-location: display\createvideodecoder.htm
old-project: display
ms.assetid: 41254f99-1806-428c-8bf3-7e736dbeec84
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: CreateVideoDecoder, CreateVideoDecoder callback function [Display Devices], PFND3D11_1DDI_CREATEVIDEODECODER, d3d10umddi/CreateVideoDecoder, display.createvideodecoder
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
-	CreateVideoDecoder
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---

# PFND3D11_1DDI_CREATEVIDEODECODER callback


## -description


Creates a video decoder object.


## -prototype


````
PFND3D11_1DDI_CREATEVIDEODECODER CreateVideoDecoder;

HRESULT APIENTRY* CreateVideoDecoder(
  _In_       D3D10DDI_HDEVICE                 hDevice,
  _In_ const D3D11_1DDIARG_CREATEVIDEODECODER *pCreateData,
  _In_       D3D11_1DDI_HDECODE               hDecoder,
  _In_       D3D11_1DDI_HRTDECODE             hRTDecode
)
{ ... }
````


## -parameters




### -param D3D10DDI_HDEVICE


### -param *


### -param D3D11_1DDI_HDECODE


### -param D3D11_1DDI_HRTDECODE








#### - hDecoder [in]

A handle to the driver's private data for the video decoder object. For more information, see the Remarks section.


#### - hDevice [in]

A handle to the display device (graphics context).




#### - hRTDecode [in]

A handle to the video decoder object that the driver should use when it calls back into the runtime.


#### - pCreateData [in]

A pointer to a <a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddiarg_createvideodecoder.md">D3D11_1DDIARG_CREATEVIDEODECODER</a> structure. This structure specifies the attributes of the video decoder object to be created.


## -returns



<b>CreateVideoDecoder</b> returns one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The video decoder object was created successfully.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>D3DDDIERR_DEVICEREMOVED</b></dt>
</dl>
</td>
<td width="60%">
The graphics adapter was removed.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
</td>
<td width="60%">

        Memory was not available to complete the operation.

</td>
</tr>
</table>
 




## -remarks



The Microsoft Direct3D runtime calls <i>CreateVideoDecoder</i> after it has called the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_calcprivatevideodecodersize.md">CalcPrivateVideoDecoderSize</a> to determine the size in bytes for the private data that the driver requires for the video decoder object. The runtime allocates the memory for this private data for the driver. The driver uses this memory to store private data that is related to the video decoder object.

When the runtime  calls <i>CreateVideoDecoder</i>, it passes the handle to the private data memory in the <i>hDecoder</i> parameter. This handle is actually a pointer to the memory. 

The driver must keep track of the handle to the display device that was used to create the cryptographic session. The driver should fail all subsequent calls that use this created cryptographic session, such as <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_videodecoderbeginframe.md">VideoDecoderBeginFrame</a>, if the display device that is specified in those calls is different from the display device that was used to create the video decoder. 






## -see-also

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_negotiatecryptosessionkeyeschange.md">NegotiateCryptoSessionKeyExchange</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_calcprivatevideodecodersize.md">CalcPrivateVideoDecoderSize</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddiarg_createvideodecoder.md">D3D11_1DDIARG_CREATEVIDEODECODER</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_videodecoderbeginframe.md">VideoDecoderBeginFrame</a>



 

 


