---
UID: NF:portcls.IMiniportStreamAudioEngineNode.GetStreamChannelMute
title: IMiniportStreamAudioEngineNode::GetStreamChannelMute method
author: windows-driver-content
description: Gets the state of the Mute node in the path of the audio stream.
old-location: audio\iminiportstreamaudioenginenode_getstreamchannelmute.htm
old-project: audio
ms.assetid: 16010297-5B08-466C-AB79-4ED12A9539D9
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: GetStreamChannelMute method [Audio Devices], GetStreamChannelMute method [Audio Devices], IMiniportStreamAudioEngineNode interface, GetStreamChannelMute,IMiniportStreamAudioEngineNode.GetStreamChannelMute, IMiniportStreamAudioEngineNode, IMiniportStreamAudioEngineNode interface [Audio Devices], GetStreamChannelMute method, IMiniportStreamAudioEngineNode::GetStreamChannelMute, audio.iminiportstreamaudioenginenode_getstreamchannelmute, portcls/IMiniportStreamAudioEngineNode::GetStreamChannelMute
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: portcls.h
req.include-header: 
req.target-type: Universal
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	Portcls.h
api_name:
-	IMiniportStreamAudioEngineNode.GetStreamChannelMute
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---

# IMiniportStreamAudioEngineNode::GetStreamChannelMute method


## -description


Gets the state of the Mute node in the path of the audio stream.


## -syntax


````
NTSTATUS GetStreamChannelMute(
  [in]  UINT32 ulChannel,
  [out] BOOL   *pbMute
);
````


## -parameters




### -param ulChannel [in]

The audio stream channel.


### -param pbMute [out]

The state of the Mute node.


## -returns



<b>GetStreamChannelMute</b> returns S_OK, if the call was successful. Otherwise, the method returns an appropriate error 

code.




## -see-also

<a href="..\portcls\nn-portcls-iminiportstreamaudioenginenode.md">IMiniportStreamAudioEngineNode</a>



 

 


