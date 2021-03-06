---
UID: NC:d3d10umddi.PFND3D10DDI_SETCONSTANTBUFFERS
title: PFND3D10DDI_SETCONSTANTBUFFERS
author: windows-driver-content
description: The CsSetConstantBuffers function sets constant buffers for a compute shader.
old-location: display\cssetconstantbuffers.htm
old-project: display
ms.assetid: 159ee0ac-7ddf-4ffd-a07f-3d58130b90e8
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: CsSetConstantBuffers, CsSetConstantBuffers callback function [Display Devices], PFND3D10DDI_SETCONSTANTBUFFERS, UserModeDisplayDriverDx11_Functions_ae0b7e35-f8c5-428d-97d0-e22d5b609c72.xml, d3d10umddi/CsSetConstantBuffers, display.cssetconstantbuffers
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: CsSetConstantBuffers is supported beginning with the Windows 7 operating system.
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
-	CsSetConstantBuffers
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---

# PFND3D10DDI_SETCONSTANTBUFFERS callback


## -description


The <b>CsSetConstantBuffers</b> function sets constant buffers for a compute shader. 


## -prototype


````
PFND3D10DDI_SETCONSTANTBUFFERS CsSetConstantBuffers;

VOID APIENTRY CsSetConstantBuffers(
  _In_       D3D10DDI_HDEVICE   hDevice,
  _In_       UINT               StartBuffer,
  _In_       UINT               NumBuffers,
  _In_ const D3D10DDI_HRESOURCE *phBuffers
)
{ ... }
````


## -parameters




### -param D3D10DDI_HDEVICE


### -param StartSlot


### -param NumBuffers [in]

 The total number of buffers to set. 


### -param *








#### - StartBuffer [in]

 The starting constant buffer to set. 


#### - hDevice [in]

 A handle to the display device (graphics context).


#### - phBuffers [in]

 An array of handles to the constant buffers, beginning with the buffer that <b>StartBuffer</b> specifies.


## -returns



None

The driver can use the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> callback function to set an error code. For more information about setting error codes, see the following Remarks section.




## -remarks



Buffers that the <b>CsSetConstantBuffers</b> function specifies are created with the D3D10_BIND_CONSTANT_BUFFER flag. 

The driver should not encounter any error, except for D3DDDIERR_DEVICEREMOVED. Therefore, if the driver passes any error, except for D3DDDIERR_DEVICEREMOVED, in a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> function, the Direct3D runtime determines that the error is critical. Even if the device is removed, the driver is not required to return D3DDDIERR_DEVICEREMOVED; however, if device removal interferes with the operation of <b>CsSetConstantBuffers</b> (which typically should not happen), the driver can return D3DDDIERR_DEVICEREMOVED.




## -see-also

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d11ddi_devicefuncs.md">D3D11DDI_DEVICEFUNCS</a>



 

 


