---
UID: NF:vmbuskernelmodeclientlibapi.VmbServerChannelInitSetSaveRestorePacketCallbacks
title: VmbServerChannelInitSetSaveRestorePacketCallbacks function
author: windows-driver-content
description: The VmbServerChannelInitSetSaveRestorePacketCallbacks function sets the save and restore callback functions that are called for each packet when the driver calls a save function, such as VmbChannelSaveBegin, VmbChannelSaveContinue, and VmbChannelSaveEnd, or the VmbChannelRestoreFromBuffer function.
old-location: netvista\vmbserverchannelinitsetsaverestorepacketcallbacks.htm
old-project: netvista
ms.assetid: 2E704BF1-21E2-498E-82C2-2B55BF44D044
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: VmbServerChannelInitSetSaveRestorePacketCallbacks, VmbServerChannelInitSetSaveRestorePacketCallbacks function [Network Drivers Starting with Windows Vista], netvista.vmbserverchannelinitsetsaverestorepacketcallbacks, vmbuskernelmodeclientlibapi/VmbServerChannelInitSetSaveRestorePacketCallbacks
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: vmbuskernelmodeclientlibapi.h
req.include-header: VmbusKernelModeClientLibApi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
req.kmdf-ver: 1.13
req.umdf-ver: 2.0
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
-	VmbusKernelModeClientLibApi.h
api_name:
-	VmbServerChannelInitSetSaveRestorePacketCallbacks
product: Windows
targetos: Windows
req.typenames: VIDEO_PORT_AGP_SERVICES, *PVIDEO_PORT_AGP_SERVICES
req.product: Windows 10 or later.
---

# VmbServerChannelInitSetSaveRestorePacketCallbacks function


## -description


<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>VmbServerChannelInitSetSaveRestorePacketCallbacks</b> function sets the save and restore callback functions that are called for each packet when the
driver calls a save function, such as <a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmbchannelsavebegin.md">VmbChannelSaveBegin</a>, <a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmbchannelsavecontinue.md">VmbChannelSaveContinue</a>, and <a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmbchannelsaveend.md">VmbChannelSaveEnd</a>, or the <a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmbchannelrestorefrombuffer.md">VmbChannelRestoreFromBuffer</a> function.


## -syntax


````
NTSTATUS
 VmbServerChannelInitSetSaveRestorePacketCallbacks(
  _In_ VMBCHANNEL                     Channel,
  _In_ PFN_VMB_CHANNEL_SAVE_PACKET    SavePacketCallback,
  _In_ PFN_VMB_CHANNEL_RESTORE_PACKET RestorePacketCallback
);
````


## -parameters




### -param Channel [in]

 A handle for a channel.  


### -param SavePacketCallback [in]

A callback function to call during channel
save. 


### -param RestorePacketCallback [in]

A callback function to call during channel     restore.


## -returns



<b>VmbServerChannelInitSetSaveRestorePacketCallbacks</b> returns the following status values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER_1</b></dt>
</dl>
</td>
<td width="60%">
The <i>Channel</i> value was invalid or in an invalid state, such as Disabled.

</td>
</tr>
</table>
 




## -see-also

<a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmbchannelsavebegin.md">VmbChannelSaveBegin</a>



<a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmbchannelsaveend.md">VmbChannelSaveEnd</a>



<a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmbchannelrestorefrombuffer.md">VmbChannelRestoreFromBuffer</a>



<a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmbchannelsavecontinue.md">VmbChannelSaveContinue</a>



 

 


