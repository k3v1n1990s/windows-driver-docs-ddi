---
UID: NS:dispmprt._DXGK_CHILD_DESCRIPTOR
title: "_DXGK_CHILD_DESCRIPTOR"
author: windows-driver-content
description: The DXGK_CHILD_DESCRIPTOR structure holds identification and capability information for an individual child device of the display adapter.
old-location: display\dxgk_child_descriptor.htm
old-project: display
ms.assetid: a814da0c-3712-4e7b-9349-a446d7b32c90
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PDXGK_CHILD_DESCRIPTOR, DXGK_CHILD_DESCRIPTOR, DXGK_CHILD_DESCRIPTOR structure [Display Devices], DmStructs_711f63dc-7ad9-49d8-b83b-5e375764a762.xml, PDXGK_CHILD_DESCRIPTOR, PDXGK_CHILD_DESCRIPTOR structure pointer [Display Devices], _DXGK_CHILD_DESCRIPTOR, display.dxgk_child_descriptor, dispmprt/DXGK_CHILD_DESCRIPTOR, dispmprt/PDXGK_CHILD_DESCRIPTOR"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: dispmprt.h
req.include-header: Dispmprt.h
req.target-type: Windows
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Dispmprt.h
api_name:
-	DXGK_CHILD_DESCRIPTOR
product: Windows
targetos: Windows
req.typenames: DXGK_CHILD_DESCRIPTOR, *PDXGK_CHILD_DESCRIPTOR
---

# _DXGK_CHILD_DESCRIPTOR structure


## -description


The DXGK_CHILD_DESCRIPTOR structure holds identification and capability information for an individual child device of the display adapter.


## -syntax


````
typedef struct _DXGK_CHILD_DESCRIPTOR {
  DXGK_CHILD_DEVICE_TYPE  ChildDeviceType;
  DXGK_CHILD_CAPABILITIES ChildCapabilities;
  ULONG                   AcpiUid;
  ULONG                   ChildUid;
} DXGK_CHILD_DESCRIPTOR, *PDXGK_CHILD_DESCRIPTOR;
````


## -struct-fields




### -field ChildDeviceType

A member of the <a href="..\dispmprt\ne-dispmprt-_dxgk_child_device_type.md">DXGK_CHILD_DEVICE_TYPE</a> enumeration that indicates the type of the child device.


### -field ChildCapabilities

A <a href="..\dispmprt\ns-dispmprt-_dxgk_child_capabilities.md">DXGK_CHILD_CAPABILITIES</a> structure that describes the capabilities of the child device.


### -field AcpiUid

If the child device is an ACPI device, this member contains the unique ACPI identifier of the child device.


### -field ChildUid

A unique identifier, created by the display miniport driver, that identifies the child device.


## -remarks



The <a href="..\dispmprt\nc-dispmprt-dxgkddi_query_child_relations.md">DxgkDdiQueryChildRelations</a> function, implemented by the display miniport driver, fills in an array of DXGK_CHILD_DESCRIPTOR structures, one for each child device of the display adapter.

Each child device of type <b>TypeVideoOutput</b> is associated with a video present target, and the <b>ChildUid</b> member of this structure is used as the identifier for that video present target. Several functions implemented by the video present network (VidPN) manager receive a video present target identifier. For an example, see the <i>VidPnTargetId</i> parameter of the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpn_acquiretargetmodeset.md">pfnAcquireTargetModeSet</a> function.




## -see-also

<a href="..\dispmprt\ne-dispmprt-_dxgk_child_device_type.md">DXGK_CHILD_DEVICE_TYPE</a>



<a href="..\dispmprt\ns-dispmprt-_dxgk_child_capabilities.md">DXGK_CHILD_CAPABILITIES</a>



<a href="..\dispmprt\nc-dispmprt-dxgkddi_query_child_status.md">DxgkDdiQueryChildStatus</a>



<a href="..\dispmprt\nc-dispmprt-dxgkddi_query_child_relations.md">DxgkDdiQueryChildRelations</a>



 

 


