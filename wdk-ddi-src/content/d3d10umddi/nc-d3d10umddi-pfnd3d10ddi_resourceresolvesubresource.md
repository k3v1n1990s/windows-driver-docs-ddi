---
UID: NC:d3d10umddi.PFND3D10DDI_RESOURCERESOLVESUBRESOURCE
title: PFND3D10DDI_RESOURCERESOLVESUBRESOURCE
author: windows-driver-content
description: The ResourceResolveSubresource function resolves multiple samples to one pixel.
old-location: display\resourceresolvesubresource.htm
old-project: display
ms.assetid: f9f4a6e2-bc01-477f-a919-ec71871f665b
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: PFND3D10DDI_RESOURCERESOLVESUBRESOURCE, ResourceResolveSubresource, ResourceResolveSubresource callback function [Display Devices], UserModeDisplayDriverDx10_Functions_bddd44ef-1872-4285-9b04-fdd509e84527.xml, d3d10umddi/ResourceResolveSubresource, display.resourceresolvesubresource
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
-	ResourceResolveSubresource
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---

# PFND3D10DDI_RESOURCERESOLVESUBRESOURCE callback


## -description


The <i>ResourceResolveSubresource</i> function resolves multiple samples to one pixel.


## -prototype


````
PFND3D10DDI_RESOURCERESOLVESUBRESOURCE ResourceResolveSubresource;

VOID APIENTRY ResourceResolveSubresource(
  _In_ D3D10DDI_HDEVICE   hDevice,
  _In_ D3D10DDI_HRESOURCE hDstResource,
  _In_ UINT               DstSubresource,
  _In_ D3D10DDI_HRESOURCE hSrcResource,
  _In_ UINT               SrcSubresource,
  _In_ DXGI_FORMAT        ResolveFormat
)
{ ... }
````


## -parameters




### -param D3D10DDI_HDEVICE


### -param D3D10DDI_HRESOURCE


### -param UINT


### -param DXGI_FORMAT








#### - DstSubresource [in]

 An index that indicates the destination subresource to resolve to. 


#### - ResolveFormat [in]

 A DXGI_FORMAT-typed value that indicates how to interpret the contents of the resolved resource.


#### - SrcSubresource [in]

 An index that indicates the source subresource to resolve from. 


#### - hDevice [in]

 A handle to the display device (graphics context).


#### - hDstResource [in]

 A handle to the destination resource to resolve to. This resource must have been created as D3D10_USAGE_DEFAULT and single sampled.


#### - hSrcResource [in]

 A handle to the source resource to resolve from.


## -returns



None

The driver can use the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> callback function to set an error code. 




## -remarks



The algorithm to resolve multiple samples to one pixel depends on the implementation. 

The resolve operation shares similar restrictions to copy operations that occur in calls to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_resourcecopy.md">ResourceCopy</a> and <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_resourcecopyregion.md">ResourceCopyRegion</a> functions. That is, both source and destination resources must be the same type (for example, Texture2D), and no stretching or format conversions can occur. The driver can resolve only a whole subresource; therefore, both the source and destination subresources must be equal in dimensions. Because of typeless resources, the following interactions can exist with either the source or destination resource format: 

<ul>
<li>
If each resource is prestructured plus typed, both resources must have the same format type, and that format type must match the format type that was passed in the <i>ResolveFormat</i> parameter (for example, all R32_FLOAT). 

</li>
<li>
If one resource is prestructured plus typeless, the prestructured-plus-typed resource's format must be compatible with the typeless format, and the format type that was passed in the <i>ResolveFormat</i> parameter must match the prestructured-plus-typed format (for example, if the source format is R32_TYPELESS, and the destination format and <i>ResolveFormat</i> are R32_FLOAT). 

</li>
<li>
If both resources are prestructured plus typeless, they must be equal formats, and the format type that was passed in the <i>ResolveFormat</i> parameter can be any format that is compatible with the typeless format. (for example, if the source and destination format are R32_TYPELESS, and <i>ResolveFormat</i> is R32_FLOAT or R32_UINT).

</li>
</ul>



## -see-also

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_resourcecopyregion.md">ResourceCopyRegion</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_resourcecopy.md">ResourceCopy</a>



 

 


