---
UID: NS:d3dhal._D3DHAL_CLIPPEDTRIANGLEFAN
title: "_D3DHAL_CLIPPEDTRIANGLEFAN"
author: windows-driver-content
description: DirectX 8.0 and later versions only.
old-location: display\d3dhal_clippedtrianglefan.htm
old-project: display
ms.assetid: c169c483-ffad-470c-9adb-397e275341e3
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*LPD3DHAL_CLIPPEDTRIANGLEFAN, D3DHAL_CLIPPEDTRIANGLEFAN, D3DHAL_CLIPPEDTRIANGLEFAN structure [Display Devices], LPD3DHAL_CLIPPEDTRIANGLEFAN, LPD3DHAL_CLIPPEDTRIANGLEFAN structure pointer [Display Devices], _D3DHAL_CLIPPEDTRIANGLEFAN, d3dhal/D3DHAL_CLIPPEDTRIANGLEFAN, d3dhal/LPD3DHAL_CLIPPEDTRIANGLEFAN, d3dstrct_443edf3e-a245-41c3-ba98-2ee9634363b9.xml, display.d3dhal_clippedtrianglefan"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dhal.h
req.include-header: D3dhal.h
req.target-type: Windows
req.target-min-winverclnt: 
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
-	HeaderDef
api_location:
-	d3dhal.h
api_name:
-	D3DHAL_CLIPPEDTRIANGLEFAN
product: Windows
targetos: Windows
req.typenames: D3DHAL_CLIPPEDTRIANGLEFAN
---

# _D3DHAL_CLIPPEDTRIANGLEFAN structure


## -description



   DirectX 8.0 and later versions only.
   

One or more D3DHAL_CLIPPEDTRIANGLEFAN structures are parsed from the command buffer by the <a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a> callback when the <a href="..\d3dhal\ns-d3dhal-_d3dhal_dp2command.md">D3DHAL_DP2COMMAND</a> structure's <b>bCommand</b> member is set to D3DDP2OP_CLIPPEDTRIANGLEFAN, and are used to render clipped triangle fans.


## -syntax


````
typedef struct _D3DHAL_CLIPPEDTRIANGLEFAN {
  DWORD FirstVertexOffset;
  DWORD dwEdgeFlags;
  DWORD PrimitiveCount;
} D3DHAL_CLIPPEDTRIANGLEFAN, *LPD3DHAL_CLIPPEDTRIANGLEFAN;
````


## -struct-fields




### -field FirstVertexOffset

Specifies the byte offset into stream 0 of the start of the vertex data (not the index of the vertex).


### -field dwEdgeFlags

Specifies a bitmask that identifies what edges are to be drawn when rendering wire frame (to prevent the drawing of edges introduced by clipping). For more information about this bitmask, see the Remarks section of the <a href="..\d3dhal\ns-d3dhal-_d3dhal_dp2trianglefan_imm.md">D3DHAL_DP2TRIANGLEFAN_IMM</a> structure.


### -field PrimitiveCount

Specifies the number of triangles in the given triangle fan.


## -see-also

<a href="..\d3dhal\ns-d3dhal-_d3dhal_dp2command.md">D3DHAL_DP2COMMAND</a>



D3DDP2OP_CLIPPEDTRIANGLEFAN



<a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a>



 

 


