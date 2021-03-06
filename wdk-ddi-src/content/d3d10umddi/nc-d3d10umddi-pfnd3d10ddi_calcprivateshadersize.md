---
UID: NC:d3d10umddi.PFND3D10DDI_CALCPRIVATESHADERSIZE
title: PFND3D10DDI_CALCPRIVATESHADERSIZE
author: windows-driver-content
description: The CalcPrivateShaderSize function determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory) for a shader.
old-location: display\calcprivateshadersize.htm
old-project: display
ms.assetid: 76cdddb0-b927-4547-ae1d-f5105905633b
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: CalcPrivateShaderSize, CalcPrivateShaderSize callback function [Display Devices], PFND3D10DDI_CALCPRIVATESHADERSIZE, UserModeDisplayDriverDx10_Functions_32a6a3cc-1a0d-4a20-a985-0e0e50daa914.xml, d3d10umddi/CalcPrivateShaderSize, display.calcprivateshadersize
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	d3d10umddi.h
api_name:
-	CalcPrivateShaderSize
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---

# PFND3D10DDI_CALCPRIVATESHADERSIZE callback


## -description


The <b>CalcPrivateShaderSize</b> function determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory) for a shader.


## -prototype


````
PFND3D10DDI_CALCPRIVATESHADERSIZE CalcPrivateShaderSize;

SIZE_T APIENTRY CalcPrivateShaderSize(
   D3D10DDI_HDEVICE                           hDevice,
   __in_ecount(pCode[1]) CONST UINT           *pCode,
   __in CONST D3D10DDIARG_STAGE_IO_SIGNATURES *pSignatures
)
{ ... }
````


## -parameters




### -param D3D10DDI_HDEVICE


### -param *pShaderCode


### -param *








#### - hDevice

 [in] A handle to the display device (graphics context).


#### - pCode


      [in] An array of CONST UINT tokens that make up the shader code.
     


#### - pSignatures

 [in] A pointer to a <a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg_stage_io_signatures.md">D3D10DDIARG_STAGE_IO_SIGNATURES</a> structure that makes up the shader's signature.


## -returns



<i>CalcPrivateShaderSize</i> returns the size of the memory region that the driver requires for creating a shader.




## -see-also

<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg_stage_io_signatures.md">D3D10DDIARG_STAGE_IO_SIGNATURES</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddi_devicefuncs.md">D3D10DDI_DEVICEFUNCS</a>



 

 


