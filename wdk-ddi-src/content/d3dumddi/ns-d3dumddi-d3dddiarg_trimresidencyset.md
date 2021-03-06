---
UID: NS:d3dumddi.D3DDDIARG_TRIMRESIDENCYSET
title: D3DDDIARG_TRIMRESIDENCYSET
author: windows-driver-content
description: D3DDDIARG_TRIMRESIDENCYSET is used with pfnTrimResidencySet by a user mode driver to trim the residency list for a given device.
old-location: display\d3dddiarg_trimresidencyset.htm
old-project: display
ms.assetid: DEF219B9-115A-4B61-8014-266730CEBD30
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3DDDIARG_TRIMRESIDENCYSET, D3DDDIARG_TRIMRESIDENCYSET structure [Display Devices], d3dumddi/D3DDDIARG_TRIMRESIDENCYSET, display.d3dddiarg_trimresidencyset
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
-	HeaderDef
api_location:
-	d3dumddi.h
api_name:
-	D3DDDIARG_TRIMRESIDENCYSET
product: Windows
targetos: Windows
req.typenames: D3DDDIARG_TRIMRESIDENCYSET
---

# D3DDDIARG_TRIMRESIDENCYSET structure


## -description


<b>D3DDDIARG_TRIMRESIDENCYSET</b> is used with <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_trimresidencyset.md">pfnTrimResidencySet</a> by a user mode driver to trim the residency list for a given device.


## -syntax


````
typedef struct D3DDDIARG_TRIMRESIDENCYSET {
  D3DDDI_TRIMRESIDENCYSET_FLAGS TrimFlags;
  UINT64                        NumBytesToTrim;
} D3DDDIARG_TRIMRESIDENCYSET;
````


## -struct-fields




### -field TrimFlags

The trimming behavior flags.


### -field NumBytesToTrim

When <b>TrimToBudget</b> is set, this value specifies how much the application should evict in order to meet its current memory budget.


## -see-also

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_trimresidencyset.md">pfnTrimResidencySet</a>



 

 


