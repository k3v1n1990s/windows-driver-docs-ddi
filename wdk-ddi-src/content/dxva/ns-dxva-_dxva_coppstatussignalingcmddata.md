---
UID: NS:dxva._DXVA_COPPStatusSignalingCmdData
title: "_DXVA_COPPStatusSignalingCmdData"
author: windows-driver-content
description: The DXVA_COPPStatusSignalingCmdData structure describes how the signal that goes through the physical connector associated with the DirectX VA COPP device is protected.
old-location: display\dxva_coppstatussignalingcmddata.htm
old-project: display
ms.assetid: 3065dddc-e084-4273-93eb-62a51763e213
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DXVA_COPPStatusSignalingCmdData, DXVA_COPPStatusSignalingCmdData structure [Display Devices], _DXVA_COPPStatusSignalingCmdData, display.dxva_coppstatussignalingcmddata, dxva/DXVA_COPPStatusSignalingCmdData, dxvaref_6a90a0a1-2173-4698-9e3d-83db1d5062f2.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: dxva.h
req.include-header: Dxva.h
req.target-type: Windows
req.target-min-winverclnt: This structure applies only to Windows Server 2003 with SP1 and later, and Windows XP with SP2 and later.
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
-	dxva.h
api_name:
-	DXVA_COPPStatusSignalingCmdData
product: Windows
targetos: Windows
req.typenames: DXVA_COPPStatusSignalingCmdData
---

# _DXVA_COPPStatusSignalingCmdData structure


## -description


The DXVA_COPPStatusSignalingCmdData structure describes how the signal that goes through the physical connector associated with the DirectX VA COPP device is protected.


## -syntax


````
typedef struct _DXVA_COPPStatusSignalingCmdData {
  GUID  rApp;
  ULONG dwFlags;
  ULONG AvailableTVProtectionStandards;
  ULONG ActiveTVProtectionStandard;
  ULONG TVType;
  ULONG AspectRatioValidMask1;
  ULONG AspectRatioData1;
  ULONG AspectRatioValidMask2;
  ULONG AspectRatioData2;
  ULONG AspectRatioValidMask3;
  ULONG AspectRatioData3;
  ULONG ExtendedInfoValidMask[4];
  ULONG ExtendedInfoData[4];
} DXVA_COPPStatusSignalingCmdData;
````


## -struct-fields




### -field rApp

Specifies a 128-bit random number, used once. This random number is generated by the requesting application and supplied to the display driver in the <b>rApp</b> member of the <a href="..\dxva\ns-dxva-_dxva_coppstatusinput.md">DXVA_COPPStatusInput</a> structure.


### -field dwFlags

Specifies additional status information that might be relevant to the calling application. The display driver should set <b>dwFlags</b> to the COPP_StatusNormal (0x00) value from the <b>COPP_StatusFlags</b> enumeration type or to a valid ORed combination of the following COPP_StatusFlags:

<ul>
<li>
COPP_LinkLost (0x01)

</li>
<li>
COPP_RenegotiationRequired (0x02)

</li>
</ul>

### -field AvailableTVProtectionStandards

Specifies a valid ORed combination of values from the <b>COPP_TVProtectionStandard</b> enumeration type that indicates the types of television signals that the physical connector associated with the DirectX VA COPP device can carry. For the list of signal types, see the <b>ActiveTVProtectionStandard</b> member of the <a href="..\dxva\ns-dxva-_dxva_coppsetsignalingcmddata.md">DXVA_COPPSetSignalingCmdData</a> structure.


### -field ActiveTVProtectionStandard

Specifies a valid ORed combination of values from the <b>COPP_TVProtectionStandard</b> enumeration type that indicates the types of television signals that the physical connector associated with the DirectX VA COPP device currently carries. For the list of signal types, see the <b>ActiveTVProtectionStandard</b> member of the <a href="..\dxva\ns-dxva-_dxva_coppsetsignalingcmddata.md">DXVA_COPPSetSignalingCmdData</a> structure.


### -field TVType

Specifies a value that indicates attributes of the connected display monitor that the driver is aware of. Not currently used.


### -field AspectRatioValidMask1

Specifies the COPP_ImageAspectRatio_EN300294_Mask (0x00000007) constant that indicates that only the first three bits in the following <b>AspectRatioData1</b> member are valid.


### -field AspectRatioData1

Specifies one of the values from the <b>COPP_ImageAspectRatio_EN300294</b> enumeration type to indicate an ETSI EN 300 294 value. For the list of values, see the <b>AspectRatioData1</b> member of the <a href="..\dxva\ns-dxva-_dxva_coppsetsignalingcmddata.md">DXVA_COPPSetSignalingCmdData</a> structure.


### -field AspectRatioValidMask2

Specifies a value that indicates the valid bitfields in the following <b>AspectRatioData2</b> member.


### -field AspectRatioData2

Specifies 32-bit data for additional aspect ratio-related data for specific protection standards. This data can be used to read End and Q0 values for EIA-608-B, or active format description for CEA-805-A Type B packets.


### -field AspectRatioValidMask3

Specifies a value that indicates the valid bitfields in the following <b>AspectRatioData3</b> member.


### -field AspectRatioData3

Specifies 32-bit data for additional aspect ratio-related data for specific protection standards. This data can be used to read End and Q0 values for EIA-608-B, or active format description for CEA-805-A Type B packets.


### -field ExtendedInfoValidMask

Specifies an array of values that indicate the valid bitfields in the respective elements of the following <b>ExtendedInfoData</b> array member.


### -field ExtendedInfoData

Specifies an array of additional 32-bit data. Not currently used.


## -see-also

<a href="..\dxva\ns-dxva-_dxva_coppstatusinput.md">DXVA_COPPStatusInput</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539652">COPPQueryStatus</a>



<a href="..\dxva\ns-dxva-_dxva_coppstatusoutput.md">DXVA_COPPStatusOutput</a>



<a href="..\dxva\ns-dxva-_dxva_coppsetprotectionlevelcmddata.md">DXVA_COPPSetProtectionLevelCmdData</a>



 

 


