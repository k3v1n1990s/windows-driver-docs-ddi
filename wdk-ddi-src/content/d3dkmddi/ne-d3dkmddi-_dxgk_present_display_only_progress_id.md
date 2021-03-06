---
UID: NE:d3dkmddi._DXGK_PRESENT_DISPLAY_ONLY_PROGRESS_ID
title: "_DXGK_PRESENT_DISPLAY_ONLY_PROGRESS_ID"
author: windows-driver-content
description: Indicates the status of the current present operation.
old-location: display\dxgk_present_display_only_progress_id.htm
old-project: display
ms.assetid: 38023aaf-754a-4b16-96fc-6fd3d48233c3
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DXGK_PRESENT_DISPLAYONLY_PROGRESS_ID_COMPLETE, DXGK_PRESENT_DISPLAYONLY_PROGRESS_ID_FAILED, DXGK_PRESENT_DISPLAY_ONLY_PROGRESS_ID, DXGK_PRESENT_DISPLAY_ONLY_PROGRESS_ID enumeration [Display Devices], _DXGK_PRESENT_DISPLAY_ONLY_PROGRESS_ID, d3dkmddi/DXGK_PRESENT_DISPLAYONLY_PROGRESS_ID_COMPLETE, d3dkmddi/DXGK_PRESENT_DISPLAYONLY_PROGRESS_ID_FAILED, d3dkmddi/DXGK_PRESENT_DISPLAY_ONLY_PROGRESS_ID, display.dxgk_present_display_only_progress_id
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3dkmddi.h
req.include-header: 
req.target-type: Windows
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	D3dkmddi.h
api_name:
-	DXGK_PRESENT_DISPLAY_ONLY_PROGRESS_ID
product: Windows
targetos: Windows
req.typenames: DXGK_PRESENT_DISPLAY_ONLY_PROGRESS_ID
---

# _DXGK_PRESENT_DISPLAY_ONLY_PROGRESS_ID enumeration


## -description


Indicates the status of the current present operation.


## -syntax


````
typedef enum _DXGK_PRESENT_DISPLAY_ONLY_PROGRESS_ID { 
  DXGK_PRESENT_DISPLAYONLY_PROGRESS_ID_COMPLETE  = 0,
  DXGK_PRESENT_DISPLAYONLY_PROGRESS_ID_FAILED    = 1
} DXGK_PRESENT_DISPLAY_ONLY_PROGRESS_ID;
````


## -enum-fields




### -field DXGK_PRESENT_DISPLAYONLY_PROGRESS_ID_COMPLETE

The present operation has completed.


### -field DXGK_PRESENT_DISPLAYONLY_PROGRESS_ID_FAILED

An error occurred during the present operation.


## -see-also

<a href="..\d3dkmddi\ns-d3dkmddi-_dxgkargcb_present_displayonly_progress.md">DXGKARGCB_PRESENT_DISPLAYONLY_PROGRESS</a>



 

 


