---
UID: NF:sdplib.SdpCreateNodeInt8
title: SdpCreateNodeInt8 function
author: windows-driver-content
description: The Bluetooth SdpCreateNodeInt8 function is used to allocate and initialize an SDP_NODE structure to an 8-bit integer type.
old-location: bltooth\sdpcreatenodeint8.htm
old-project: bltooth
ms.assetid: 52829c1e-31df-4a53-8cd1-5050e564aa2e
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: SdpCreateNodeInt8, SdpCreateNodeInt8 function [Bluetooth Devices], bltooth.sdpcreatenodeint8, bth_funcs_445898ae-3a2a-49f7-bfff-30e8c0773227.xml, sdplib/SdpCreateNodeInt8
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: sdplib.h
req.include-header: BthSdpddi.h
req.target-type: Desktop
req.target-min-winverclnt: Versions:\_Supported in Windows Vista, and later.
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
req.irql: "<= PASSIVE_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	sdplib.h
api_name:
-	SdpCreateNodeInt8
product: Windows
targetos: Windows
req.typenames: SDCMD_DESCRIPTOR, *PSDCMD_DESCRIPTOR
req.product: Windows 10 or later.
---

# SdpCreateNodeInt8 function


## -description


The Bluetooth 
  <b>SdpCreateNodeInt8</b> function is used to allocate and initialize an 
  <a href="..\sdpnode\ns-sdpnode-_sdp_node.md">SDP_NODE</a> structure to an 8-bit integer type.


## -syntax


````
PSDP_NODE SdpCreateNodeInt8(
  _In_ CHAR  cVal,
  _In_ ULONG tag
);
````


## -parameters




### -param cVal [in]

The 8-bit integer value that is used to initialize the 
     <b>SDP_NODE</b> structure.


### -param tag [in]

A profile driver defined tag to associate with the node.


## -returns



If successful, this function returns a pointer to the newly allocated SDP_NODE structure. If not
     successful, this function returns <b>NULL</b>.




## -remarks



After the 
    <b>SdpCreateNodeInt8</b> function allocates an 
    <a href="..\sdpnode\ns-sdpnode-_sdp_node.md">SDP_NODE</a> structure, it initializes the structure in
    the following ways.

It ensures that the SDP_NODE structure's data type and data size fields are set appropriately.

It ensures that the pointer members of the associated 
      <a href="..\sdpnode\ns-sdpnode-_sdp_node_header.md">SDP_NODE_HEADER</a> structure are initialized
      to point to the node itself. This creates a valid list with only one element.

It ensures that the 
      <i>value</i> parameter passed to the function is copied to the appropriate element of the 
      <a href="..\sdpnode\ns-sdpnode-_sdp_node_data.md">SDP_NODE_DATA</a> union that is associated with
      the SDP_NODE structure.

The data associated with the 
    <b>SdpCreateNodeInt8</b> function is copied into the node, and the original data can be freed at any
    time.

Bluetooth profile drivers can obtain a pointer to this function through the 
    <a href="..\bthsdpddi\ns-bthsdpddi-_bthddi_sdp_node_interface.md">BTHDDI_SDP_NODE_INTERFACE</a>.




## -see-also

<a href="..\sdpnode\ns-sdpnode-_sdp_node.md">SDP_NODE</a>



<a href="..\sdpnode\ns-sdpnode-_sdp_node_data.md">SDP_NODE_DATA</a>



<a href="..\sdpnode\ns-sdpnode-_sdp_node_header.md">SDP_NODE_HEADER</a>



<a href="..\bthsdpddi\ns-bthsdpddi-_bthddi_sdp_node_interface.md">BTHDDI_SDP_NODE_INTERFACE</a>



 

 


