---
UID: NC:d3d10umddi.PFND3D11_1DDI_CREATEHULLSHADER
title: PFND3D11_1DDI_CREATEHULLSHADER
author: windows-driver-content
description: Creates a hull shader.
old-location: display\createhullshader_d3d11_1_.htm
old-project: display
ms.assetid: 5461f9d4-5eff-4ff7-9eeb-cf94bc243dba
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: CreateHullShader(D3D11_1), CreateHullShader(D3D11_1) callback function [Display Devices], PFND3D11_1DDI_CREATEHULLSHADER, d3d10umddi/CreateHullShader(D3D11_1), display.createhullshader_d3d11_1_, display.pfncreatehullshader
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
-	CreateHullShader(D3D11_1)
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---

# PFND3D11_1DDI_CREATEHULLSHADER callback


## -description


Creates a hull shader.


## -prototype


````
PFND3D11_1DDI_CREATEHULLSHADER CreateHullShader(D3D11_1);

VOID APIENTRY* CreateHullShader(D3D11_1)(
             D3D10DDI_HDEVICE                         hDevice,
  _In_ const UINT                                     *pShaderCode,
             D3D10DDI_HSHADER                         hShader,
             D3D10DDI_HRTSHADER                       hRTShader,
  _In_ const D3D11_1DDIARG_TESSELLATION_IO_SIGNATURES *pSignatures
)
{ ... }
````


## -parameters




### -param D3D10DDI_HDEVICE


### -param *pShaderCode [in]

 A pointer to an array of CONST UINT tokens that form the shader code. The first token in the shader code stream is always the version token. The next token in the stream is the length token that determines the end of the shader code stream. For more information about the format of Direct3D version 11.1 shader code, see the comments inside the D3d11tokenizedprogramformat.hpp header file that is included with the WDK.


### -param D3D10DDI_HSHADER


### -param D3D10DDI_HRTSHADER


### -param *








#### - hDevice

A handle to the display device (graphics context).


#### - hRTShader

 A handle to the hull shader that the driver should use when it calls back into the Direct3D runtime. 


#### - hShader

 A handle to the driver's private data for the hull shader. The driver returns the size, in bytes, of the memory region that the Microsoft Direct3D runtime must allocate for the private data from a call to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_calcprivatetessellationshadersize.md">CalcPrivateTessellationShaderSize(D3D11_1)</a>  function. The handle is just a pointer to a region of memory, the size of which the driver requested. The driver uses this region of memory to store internal data structures that are related to its tessellation-shader object. 


#### - pSignatures [in]

 A pointer to a <a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddiarg_tessellation_io_signatures.md">D3D11_1DDIARG_TESSELLATION_IO_SIGNATURES</a> structure that forms the tessellation-shader's signature.


## -returns



This callback function does not return a value.




## -see-also

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_calcprivatetessellationshadersize.md">CalcPrivateTessellationShaderSize(D3D11_1)</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddiarg_tessellation_io_signatures.md">D3D11_1DDIARG_TESSELLATION_IO_SIGNATURES</a>



 

 


