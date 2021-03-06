---
UID: NF:portcls.IMiniportStreamAudioEngineNode.GetLfxState
title: IMiniportStreamAudioEngineNode::GetLfxState method
author: windows-driver-content
description: Gets the state of the local effects (LFX) node that is in the path of the audio stream.
old-location: audio\iminiportstreamaudioenginenode_getlfxstate.htm
old-project: audio
ms.assetid: 2810D8B3-DDB7-4B55-839B-B2D079BDC0FC
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: GetLfxState method [Audio Devices], GetLfxState method [Audio Devices], IMiniportStreamAudioEngineNode interface, GetLfxState,IMiniportStreamAudioEngineNode.GetLfxState, IMiniportStreamAudioEngineNode, IMiniportStreamAudioEngineNode interface [Audio Devices], GetLfxState method, IMiniportStreamAudioEngineNode::GetLfxState, audio.iminiportstreamaudioenginenode_getlfxstate, portcls/IMiniportStreamAudioEngineNode::GetLfxState
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
-	IMiniportStreamAudioEngineNode.GetLfxState
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---

# IMiniportStreamAudioEngineNode::GetLfxState method


## -description


Gets the state of the local effects (LFX) node that is in the path of the audio stream.


## -syntax


````
NTSTATUS GetLfxState(
  [out] BOOL *pbEnable
);
````


## -parameters




### -param pbEnable [out]

The current state of the LFX node.


## -returns



<b>GetLfxState</b> returns S_OK, if the call was successful. Otherwise, the method returns an appropriate error 

code.




## -see-also

<a href="..\portcls\nn-portcls-iminiportstreamaudioenginenode.md">IMiniportStreamAudioEngineNode</a>



 

 


