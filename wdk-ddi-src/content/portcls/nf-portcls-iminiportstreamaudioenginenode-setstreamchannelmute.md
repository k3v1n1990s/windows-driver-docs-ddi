---
UID: NF:portcls.IMiniportStreamAudioEngineNode.SetStreamChannelMute
title: IMiniportStreamAudioEngineNode::SetStreamChannelMute method
author: windows-driver-content
description: Sets the state of the Mute node in the path of the audio stream.
old-location: audio\iminiportstreamaudioenginenode_setstreamchannelmute.htm
old-project: audio
ms.assetid: AAD0101E-13FB-48A2-8834-799472B93931
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: IMiniportStreamAudioEngineNode, IMiniportStreamAudioEngineNode interface [Audio Devices], SetStreamChannelMute method, IMiniportStreamAudioEngineNode::SetStreamChannelMute, SetStreamChannelMute method [Audio Devices], SetStreamChannelMute method [Audio Devices], IMiniportStreamAudioEngineNode interface, SetStreamChannelMute,IMiniportStreamAudioEngineNode.SetStreamChannelMute, audio.iminiportstreamaudioenginenode_setstreamchannelmute, portcls/IMiniportStreamAudioEngineNode::SetStreamChannelMute
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
-	IMiniportStreamAudioEngineNode.SetStreamChannelMute
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---

# IMiniportStreamAudioEngineNode::SetStreamChannelMute method


## -description


Sets the state of the Mute node in the path of the audio stream.


## -syntax


````
NTSTATUS SetStreamChannelMute(
  [in] UINT32 ulChannel,
  [in] BOOL   bMute
);
````


## -parameters




### -param ulChannel [in]

The channel for the audio stream.


### -param bMute [in]

The state to which the Mute node will be set.


## -returns



<b>SetStreamChannelMute</b> returns S_OK, if the call was successful. Otherwise, the method returns an appropriate error 

code.




## -see-also

<a href="..\portcls\nn-portcls-iminiportstreamaudioenginenode.md">IMiniportStreamAudioEngineNode</a>



 

 


