---
UID: NS:ksmedia.tagKS_DATARANGE_ANALOGVIDEO
title: tagKS_DATARANGE_ANALOGVIDEO
author: windows-driver-content
description: The KS_DATARANGE_ANALOGVIDEO structure describes an analog video stream.
old-location: stream\ks_datarange_analogvideo.htm
old-project: stream
ms.assetid: e89e9108-28a1-46ac-8694-047a656dcb74
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: "*PKS_DATARANGE_ANALOGVIDEO, KS_DATARANGE_ANALOGVIDEO, KS_DATARANGE_ANALOGVIDEO structure [Streaming Media Devices], PKS_DATARANGE_ANALOGVIDEO, PKS_DATARANGE_ANALOGVIDEO structure pointer [Streaming Media Devices], ksmedia/KS_DATARANGE_ANALOGVIDEO, ksmedia/PKS_DATARANGE_ANALOGVIDEO, stream.ks_datarange_analogvideo, tagKS_DATARANGE_ANALOGVIDEO, vidcapstruct_43f72b11-2ac7-4b68-b595-c37022d956c7.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ksmedia.h
req.include-header: Ksmedia.h
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
-	ksmedia.h
api_name:
-	KS_DATARANGE_ANALOGVIDEO
product: Windows
targetos: Windows
req.typenames: KS_DATARANGE_ANALOGVIDEO, *PKS_DATARANGE_ANALOGVIDEO
---

# tagKS_DATARANGE_ANALOGVIDEO structure


## -description


The KS_DATARANGE_ANALOGVIDEO structure describes an analog video stream.


## -syntax


````
typedef struct tagKS_DATARANGE_ANALOGVIDEO {
  KSDATARANGE        DataRange;
  KS_ANALOGVIDEOINFO AnalogVideoInfo;
} KS_DATARANGE_ANALOGVIDEO, *PKS_DATARANGE_ANALOGVIDEO;
````


## -struct-fields




### -field DataRange

Specifies the major identifier for the format.


### -field AnalogVideoInfo

Specifies the details of the analog video stream. 


## -see-also

<a href="..\ksmedia\ns-ksmedia-tagks_analogvideoinfo.md">KS_ANALOGVIDEOINFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561658">KSDATARANGE</a>



 

 


