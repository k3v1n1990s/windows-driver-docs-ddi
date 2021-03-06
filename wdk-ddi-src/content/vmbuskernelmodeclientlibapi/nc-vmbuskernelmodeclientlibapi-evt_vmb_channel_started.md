---
UID: NC:vmbuskernelmodeclientlibapi.EVT_VMB_CHANNEL_STARTED
title: EVT_VMB_CHANNEL_STARTED
author: windows-driver-content
description: The EvtVmbChannelStarted callback function is invoked at either endpoint when a channel is fully configured but before any packets have been delivered. This occurs when the opposite endpoint opened the channel or reopened it after closing it.
old-location: netvista\evt_vmb_channel_started.htm
old-project: netvista
ms.assetid: C4F35016-3F93-4258-A42F-D692AF690020
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: EVT_VMB_CHANNEL_STARTED, EvtVmbChannelStarted, EvtVmbChannelStarted callback function [Network Drivers Starting with Windows Vista], PFN_VMB_CHANNEL_STARTED, PFN_VMB_CHANNEL_STARTED callback function pointer [Network Drivers Starting with Windows Vista], netvista.evt_vmb_channel_started, vmbuskernelmodeclientlibapi/EvtVmbChannelStarted
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: vmbuskernelmodeclientlibapi.h
req.include-header: VmbusKernelModeClientLibApi.h
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	VmbusKernelModeClientLibApi.h
api_name:
-	PFN_VMB_CHANNEL_STARTED
product: Windows
targetos: Windows
req.typenames: VIDEO_PORT_AGP_SERVICES, *PVIDEO_PORT_AGP_SERVICES
req.product: Windows 10 or later.
---

# EVT_VMB_CHANNEL_STARTED callback


## -description


<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <i>EvtVmbChannelStarted</i> callback function is invoked at either endpoint when a channel is
fully configured but before any packets have been delivered.  This occurs when the opposite endpoint opened the channel or reopened it after closing it.  


## -prototype


````
EVT_VMB_CHANNEL_STARTED EvtVmbChannelStarted;

VOID EvtVmbChannelStarted(
  _In_ VMBCHANNEL Channel
)
{ ... }

typedef EVT_VMB_CHANNEL_STARTED PFN_VMB_CHANNEL_STARTED;
````


## -parameters




### -param Channel [in]

The channel which is started.


## -returns



This callback function does not return a value.




## -remarks



After a channel is created, a client driver can specify callback functions for state changes, including  <i>EvtVmbChannelStarted</i>, by using the <a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmb_channel_state_change_callbacks_init.md">VMB_CHANNEL_STATE_CHANGE_CALLBACKS_INIT</a> function.

If a paused channel is opened or an opened channel is started, Kernel Mode Client Library (KMCL) calls <i>EvtVmbChannelStarted</i> after it calls the <a href="..\vmbuskernelmodeclientlibapi\nc-vmbuskernelmodeclientlibapi-evt_vmb_channel_opened.md">EvtVmbChannelOpened</a> callback.  <i>EvtVmbChannelStarted</i> can call the <a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmbpacketsend.md">VmbPacketSend</a>, <a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmbpacketsendwithexternalmdl.md">VmbPacketSendWithExternalMdl</a>, and <a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmbpacketsendwithexternalpfns.md">VmbPacketSendWithExternalPfns</a> functions 
to queue up outgoing packets. Because the incoming queue is not running at this point, this callback must not block on incoming packets or 
completions.  

Most drivers using KMCL do not implement
this callback. An alternative is the <a href="..\vmbuskernelmodeclientlibapi\nc-vmbuskernelmodeclientlibapi-evt_vmb_channel_post_started.md">EvtVmbChannelPostStarted</a> callback function.

Waiting for a sent packet to complete, such as by the <a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmbchannelsendsynchronousrequest.md">VmbChannelSendSynchronousRequest</a> function, never returns because packets are not flowing when this callback is invoked.




## -see-also

<a href="..\vmbuskernelmodeclientlibapi\nc-vmbuskernelmodeclientlibapi-evt_vmb_channel_post_started.md">EvtVmbChannelPostStarted</a>



<a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmbpacketsendwithexternalpfns.md">VmbPacketSendWithExternalPfns</a>



<a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmbpacketsend.md">VmbPacketSend</a>



<a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmbchannelsendsynchronousrequest.md">VmbChannelSendSynchronousRequest</a>



<a href="..\vmbuskernelmodeclientlibapi\nc-vmbuskernelmodeclientlibapi-evt_vmb_channel_opened.md">EvtVmbChannelOpened</a>



<a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmbpacketsendwithexternalmdl.md">VmbPacketSendWithExternalMdl</a>



<a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmb_channel_state_change_callbacks_init.md">VMB_CHANNEL_STATE_CHANGE_CALLBACKS_INIT</a>



 

 


