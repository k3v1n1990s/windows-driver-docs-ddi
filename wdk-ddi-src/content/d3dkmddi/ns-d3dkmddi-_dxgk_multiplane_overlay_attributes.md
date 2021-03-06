---
UID: NS:d3dkmddi._DXGK_MULTIPLANE_OVERLAY_ATTRIBUTES
title: "_DXGK_MULTIPLANE_OVERLAY_ATTRIBUTES"
author: windows-driver-content
description: Used by the display miniport driver to specify overlay plane attributes.
old-location: display\dxgk_multiplane_overlay_attributes.htm
old-project: display
ms.assetid: 1f48a08f-138c-44b4-b13f-efa9b448ce4f
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DXGK_MULTIPLANE_OVERLAY_ATTRIBUTES, DXGK_MULTIPLANE_OVERLAY_ATTRIBUTES structure [Display Devices], _DXGK_MULTIPLANE_OVERLAY_ATTRIBUTES, d3dkmddi/DXGK_MULTIPLANE_OVERLAY_ATTRIBUTES, display.dxgk_multiplane_overlay_attributes
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
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
-	DXGK_MULTIPLANE_OVERLAY_ATTRIBUTES
product: Windows
targetos: Windows
req.typenames: DXGK_MULTIPLANE_OVERLAY_ATTRIBUTES
---

# _DXGK_MULTIPLANE_OVERLAY_ATTRIBUTES structure


## -description


Used by the display miniport driver to specify overlay plane attributes.


## -syntax


````
typedef struct _DXGK_MULTIPLANE_OVERLAY_ATTRIBUTES {
  DXGK_MULTIPLANE_OVERLAY_FLAGS              Flags;
  RECT                                       SrcRect;
  RECT                                       DstRect;
#if (DXGKDDI_INTERFACE_VERSION >= DXGKDDI_INTERFACE_VERSION_WDDM1_3)
  RECT                                       ClipRect;
#endif 
  D3DDDI_ROTATION                            Rotation;
  DXGK_MULTIPLANE_OVERLAY_BLEND              Blend;
#if (DXGKDDI_INTERFACE_VERSION < DXGKDDI_INTERFACE_VERSION_WDDM1_3)
  UINT                                       NumFilters;
  void                                       *pFilters;
#endif 
  DXGK_MULTIPLANE_OVERLAY_VIDEO_FRAME_FORMAT VideoFrameFormat;
  DXGK_MULTIPLANE_OVERLAY_YCbCr_FLAGS        YCbCrFlags;
  DXGK_MULTIPLANE_OVERLAY_STEREO_FORMAT      StereoFormat;
  BOOL                                       StereoLeftViewFrame0;
  BOOL                                       StereoBaseViewFrame0;
  DXGK_MULTIPLANE_OVERLAY_STEREO_FLIP_MODE   StereoFlipMode;
#if (DXGKDDI_INTERFACE_VERSION >= DXGKDDI_INTERFACE_VERSION_WDDM1_3)
  DXGK_MULTIPLANE_OVERLAY_STRETCH_QUALITY    StretchQuality;
#endif 
} DXGK_MULTIPLANE_OVERLAY_ATTRIBUTES;
````


## -struct-fields




### -field Flags

Specifies a flip operation as one of the applicable constant values in the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_multiplane_overlay_flags.md">DXGK_MULTIPLANE_OVERLAY_FLAGS</a> enumeration.


### -field SrcRect

Specifies the source rectangle, of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff569234">RECT</a>, relative to the source resource.


### -field DstRect

Specifies the destination rectangle, of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff569234">RECT</a>, relative to the monitor resolution.


### -field ClipRect

Specifies any additional clipping, of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff569234">RECT</a>, relative to the <b>DstRect</b> rectangle, after the data has been stretched according to the values of <b>SrcRect</b> and <b>DstRect</b>.

The driver and hardware can use the <b>ClipRect</b> member to apply a common stretch factor as the clipping changes when an app occludes part of the <b>DstRect</b> destination rectangle.


### -field Rotation

Specifies the clockwise rotation of the overlay plane, given as a value from the <a href="..\d3dukmdt\ne-d3dukmdt-_d3dddi_rotation.md">D3DDDI_ROTATION</a> enumeration.


### -field Blend

Specifies the blend mode that applies to this overlay plane and the plane beneath it, given as a value from the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_multiplane_overlay_blend.md">DXGK_MULTIPLANE_OVERLAY_BLEND</a> enumeration.


### -field NumFilters

Optionally specifies the number of filters that the driver and hardware implement on the overlay plane. Note that the operating system ignores this member.


### -field pFilters

An optional pointer to a buffer that specifies the filters that the driver and hardware implement on the overlay plane. Note that the operating system ignores this member.


### -field VideoFrameFormat

Specifies the overlay plane's video frame format, given as a value from the <a href="..\d3dkmddi\ne-d3dkmddi-_dxgk_multiplane_overlay_video_frame_format.md">DXGK_MULTIPLANE_OVERLAY_VIDEO_FRAME_FORMAT</a> enumeration.

<div class="alert"><b>Note</b>  This value must always be <b>DXGK_MULTIPLANE_OVERLAY_VIDEO_FRAME_FORMAT_PROGRESSIVE</b>. The operating system does not support the other enumeration values.</div>
<div> </div>

### -field YCbCrFlags

Specifies YUV range and conversion info given as a value from the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_multiplane_overlay_ycbcr_flags.md">DXGK_MULTIPLANE_OVERLAY_YCbCr_FLAGS</a> enumeration.


### -field StereoFormat

Specifies the overlay plane's video frame format, given as a value from the <a href="..\d3dkmddi\ne-d3dkmddi-_dxgk_multiplane_overlay_stereo_format.md">DXGK_MULTIPLANE_OVERLAY_STEREO_FORMAT</a> enumeration.

<div class="alert"><b>Note</b>  This value must always be <b>DXGK_MULTIPLANE_OVERLAY_STEREO_FORMAT_MONO</b>. The operating system does not support the other enumeration values.</div>
<div> </div>

### -field StereoLeftViewFrame0

Reserved for system use. Must always be <b>FALSE</b>.


### -field StereoBaseViewFrame0

Reserved for system use. Must always be <b>FALSE</b>.


### -field StereoFlipMode

Specifies the overlay plane's stereo flip mode, given as a value from the <a href="..\d3dkmddi\ne-d3dkmddi-_dxgk_multiplane_overlay_stereo_flip_mode.md">DXGK_MULTIPLANE_OVERLAY_STEREO_FLIP_MODE</a> enumeration.

<div class="alert"><b>Note</b>  This value must always be <b>DXGK_MULTIPLANE_OVERLAY_STEREO_FLIP_NONE</b>. The operating system does not support the other enumeration values.</div>
<div> </div>

### -field StretchQuality

Specifies the overlay plane's stretch quality, given as a value from the <a href="..\d3dkmddi\ne-d3dkmddi-_dxgk_multiplane_overlay_stretch_quality.md">DXGK_MULTIPLANE_OVERLAY_STRETCH_QUALITY</a> enumeration.


## -see-also

<a href="..\d3dkmddi\ne-d3dkmddi-_dxgk_multiplane_overlay_stereo_format.md">DXGK_MULTIPLANE_OVERLAY_STEREO_FORMAT</a>



<a href="..\d3dkmddi\ne-d3dkmddi-_dxgk_multiplane_overlay_stretch_quality.md">DXGK_MULTIPLANE_OVERLAY_STRETCH_QUALITY</a>



<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_multiplane_overlay_blend.md">DXGK_MULTIPLANE_OVERLAY_BLEND</a>



<a href="..\d3dkmddi\ne-d3dkmddi-_dxgk_multiplane_overlay_video_frame_format.md">DXGK_MULTIPLANE_OVERLAY_VIDEO_FRAME_FORMAT</a>



<a href="..\d3dukmdt\ne-d3dukmdt-_d3dddi_rotation.md">D3DDDI_ROTATION</a>



<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_multiplane_overlay_ycbcr_flags.md">DXGK_MULTIPLANE_OVERLAY_YCbCr_FLAGS</a>



<a href="..\d3dkmddi\ne-d3dkmddi-_dxgk_multiplane_overlay_stereo_flip_mode.md">DXGK_MULTIPLANE_OVERLAY_STEREO_FLIP_MODE</a>



<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_multiplane_overlay_flags.md">DXGK_MULTIPLANE_OVERLAY_FLAGS</a>



 

 


