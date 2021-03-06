---
UID: NC:d3d10umddi.PFND3D11DDI_CREATEUNORDEREDACCESSVIEW
title: PFND3D11DDI_CREATEUNORDEREDACCESSVIEW
author: windows-driver-content
description: The CreateUnorderedAccessView function creates an unordered access view.
old-location: display\createunorderedaccessview.htm
old-project: display
ms.assetid: c5a258e7-6645-46bb-ab2c-a1c8f5e593b7
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: CreateUnorderedAccessView, CreateUnorderedAccessView callback function [Display Devices], PFND3D11DDI_CREATEUNORDEREDACCESSVIEW, UserModeDisplayDriverDx11_Functions_4b9c2d38-c780-47be-a5fa-dec2c860732b.xml, d3d10umddi/CreateUnorderedAccessView, display.createunorderedaccessview
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: CreateUnorderedAccessView is supported beginning with the Windows 7 operating system.
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
-	CreateUnorderedAccessView
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---

# PFND3D11DDI_CREATEUNORDEREDACCESSVIEW callback


## -description


The <b>CreateUnorderedAccessView</b> function creates an unordered access view.


## -prototype


````
PFND3D11DDI_CREATEUNORDEREDACCESSVIEW CreateUnorderedAccessView;

VOID APIENTRY CreateUnorderedAccessView(
  _In_       D3D10DDI_HDEVICE                      hDevice,
  _In_ const D3D11DDIARG_CREATEUNORDEREDACCESSVIEW *pCreateUnorderedAccessView,
  _In_       D3D11DDI_HUNORDEREDACCESSVIEW         hUnorderedAccessView,
  _In_       D3D11DDI_HRTUNORDEREDACCESSVIEW       hRTUnorderedAccessView
)
{ ... }
````


## -parameters




### -param D3D10DDI_HDEVICE


### -param *


### -param D3D11DDI_HUNORDEREDACCESSVIEW


### -param D3D11DDI_HRTUNORDEREDACCESSVIEW








#### - hDevice [in]

 A handle to the display device (graphics context).


#### - hRTUnorderedAccessView [in]

 A handle to the unordered access view that the driver should use when it calls back into the Direct3D runtime. 


#### - hUnorderedAccessView [in]

 A handle to the driver's private data for the unordered access view. The driver returns the size, in bytes, of the memory region that the Microsoft Direct3D runtime must allocate for the private data from a call to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_calcprivateunorderedaccessviewsize.md">CalcPrivateUnorderedAccessViewSize</a> function. The handle is  just a pointer to a region of memory, the size of which the driver requested. The driver uses this region of memory to store internal data structures that are related to its unordered access view object. 


#### - pCreateUnorderedAccessView [in]

 A pointer to a <a href="..\d3d10umddi\ns-d3d10umddi-d3d11ddiarg_createunorderedaccessview.md">D3D11DDIARG_CREATEUNORDEREDACCESSVIEW</a> structure that describes the parameters that the user-mode display driver uses to create an unordered access view. 


## -returns



None

The driver can use the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> callback function to set an error code. For more information about setting error codes, see the following Remarks section.




## -remarks



The driver might run out of memory. Therefore, the driver can pass E_OUTOFMEMORY or D3DDDIERR_DEVICEREMOVED in a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> function. The Direct3D runtime determines that any other errors are critical. If the driver passes any errors, which includes D3DDDIERR_DEVICEREMOVED, the Direct3D runtime determines that the handle is invalid; therefore, the runtime does not call the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_destroyunorderedaccessview.md">DestroyUnorderedAccessView</a> function to destroy the handle that the <i>hUnorderedAccessView</i> parameter specifies.




## -see-also

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d11ddi_devicefuncs.md">D3D11DDI_DEVICEFUNCS</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d11ddiarg_createunorderedaccessview.md">D3D11DDIARG_CREATEUNORDEREDACCESSVIEW</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_calcprivateunorderedaccessviewsize.md">CalcPrivateUnorderedAccessViewSize</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_destroyunorderedaccessview.md">DestroyUnorderedAccessView</a>



 

 


