---
UID: NS:dot11wdi._WDI_TX_METADATA
title: "_WDI_TX_METADATA"
author: windows-driver-content
description: The WDI_TX_METADATA structure defines the TX metadata.
old-location: netvista\wdi_tx_metadata.htm
old-project: netvista
ms.assetid: 21833980-0098-43c2-822c-9d8292f7120a
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*PWDI_TX_METADATA, PWDI_TX_METADATA, PWDI_TX_METADATA structure pointer [Network Drivers Starting with Windows Vista], WDI_TX_METADATA, WDI_TX_METADATA structure [Network Drivers Starting with Windows Vista], _WDI_TX_METADATA, dot11wdi/PWDI_TX_METADATA, dot11wdi/WDI_TX_METADATA, netvista.wdi_tx_metadata, netvista.wifi_tx_metadata"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: dot11wdi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
-	dot11wdi.h
api_name:
-	WDI_TX_METADATA
product: Windows
targetos: Windows
req.typenames: WDI_TX_METADATA, *PWDI_TX_METADATA
---

# _WDI_TX_METADATA structure


## -description


The 
  WDI_TX_METADATA structure defines the TX metadata.


## -syntax


````
typedef struct _WDI_TX_METADATA {
  WDI_PORT_ID               PortID;
  WDI_PEER_ID               PeerID;
  WDI_EXTENDED_TID          ExTID;
  BOOLEAN                   IsUnicast;
  BOOLEAN                   bAllowLegacyRates;
  UINT16                    Ethertype;
  BOOLEAN                   bTxCompleteRequired;
  UINT8                     PnLength;
  UINT16                    TxCost;
  WDI_EXEMPTION_ACTION_TYPE ExemptionAction;
  WDI_TXRX_MPDU_PN          MpduPn;
  UINT64                    ReplayIHVReserved0;
  UINT64                    ReplayIHVReserved1;
  UINT16                    SeqCtl;
  UINT16                    wPad;
} WDI_TX_METADATA, *PWDI_TX_METADATA;
````


## -struct-fields




### -field PortID

Port ID of the frame.


### -field PeerID

Peer ID of the frame (only if <b>TargetPriorityQueueing</b> is false).


### -field ExTID

Extended TID of the frame (only if <b>TargetPriorityQueueing</b> is false).


### -field IsUnicast

Specifies if the frame is for a unicast recipient address.


### -field bAllowLegacyRates

Specifies if legacy rates should be used for transmitting the frame.


### -field Ethertype

Specifies the Ethertype of the frame.


### -field bTxCompleteRequired

Specifies if an <a href="..\dot11wdi\nc-dot11wdi-ndis_wdi_tx_send_complete_ind.md">NdisWdiTxSendCompleteIndication</a> is required for this frame.


### -field PnLength

Specifies the PnLength for the frame. This is only applicable to Requeued/Replayed TX frames.  Otherwise, set to zero.


### -field TxCost

Specifies the number of credits required to dequeue the frame.


### -field ExemptionAction

Specifies the <a href="..\dot11wdi\ne-dot11wdi-_wdi_exemption_action_type.md">WDI_EXEMPTION_ACTION_TYPE</a> value for this frame.


### -field MpduPn

Specifies the MpduPn for the frame. This is only applicable to Requeued/Replayed TX frames.  Otherwise, set to zero.


### -field ReplayIHVReserved0

Reserved for use by the IHV miniport for Requeued/Replayed TX frames. This is only applicable to Requeued/Replayed TX frames.  Otherwise, set to zero.  


### -field ReplayIHVReserved1

Reserved for use by the IHV miniport for Requeued/Replayed TX frames. This is only applicable to Requeued/Replayed TX frames.  Otherwise, set to zero.  


### -field SeqCtl

Specifies the SeqCtl (if necessary). This is only applicable to Requeued/Replayed TX frames.  Otherwise, set to zero.


### -field wPad

Reserved.


## -see-also

<a href="..\dot11wdi\ne-dot11wdi-_wdi_exemption_action_type.md">WDI_EXEMPTION_ACTION_TYPE</a>



<a href="..\dot11wdi\ns-dot11wdi-_wdi_txrx_target_capabilities.md">WDI_TXRX_CAPABILITIES</a>



 

 


