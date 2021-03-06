---
UID: NC:dot11wdi.NDIS_WDI_IDLE_NOTIFICATION_COMPLETE
title: NDIS_WDI_IDLE_NOTIFICATION_COMPLETE
author: windows-driver-content
description: Miniport drivers call NdisWdiIdleNotificationComplete callback function to complete a pending idle notification for an NDIS selective suspend operation. NDIS begins the operation when it calls the driver's MiniportWdiIdleNotification handler function.
old-location: netvista\ndiswdiidlenotificationcomplete.htm
old-project: netvista
ms.assetid: 22622545-F92E-4FEE-8F5D-64EC792490C7
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: NDIS_WDI_IDLE_NOTIFICATION_COMPLETE, NdisWdiIdleNotificationComplete, NdisWdiIdleNotificationComplete callback function [Network Drivers Starting with Windows Vista], dot11wdi/NdisWdiIdleNotificationComplete, netvista.ndiswdiidlenotificationcomplete
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	dot11wdi.h
api_name:
-	NdisWdiIdleNotificationComplete
product: Windows
targetos: Windows
req.typenames: SYNTH_STATS, *PSYNTH_STATS
---

# NDIS_WDI_IDLE_NOTIFICATION_COMPLETE callback


## -description


Miniport drivers call NdisWdiIdleNotificationComplete callback function to complete a pending idle notification for an NDIS selective suspend operation. NDIS begins the operation when it calls the driver's <a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_idle_notification.md">MiniportWdiIdleNotification</a> handler function.

This is a control path callback inside <a href="..\dot11wdi\ns-dot11wdi-_ndis_wdi_init_parameters.md">NDIS_WDI_INIT_PARAMETERS</a>.


## -prototype


````
NDIS_WDI_IDLE_NOTIFICATION_COMPLETE NdisWdiIdleNotificationComplete;

VOID NdisWdiIdleNotificationComplete(
  _In_ NDIS_HANDLE MiniportAdapterHandle
)
{ ... }
````


## -parameters




### -param MiniportAdapterHandle [in]

The miniport handle.


## -returns



This callback function does not return a value.




## -see-also

<a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_idle_notification.md">MiniportWdiIdleNotification</a>



<a href="..\dot11wdi\ns-dot11wdi-_ndis_wdi_init_parameters.md">NDIS_WDI_INIT_PARAMETERS</a>



<a href="https://msdn.microsoft.com/2330A8EE-DC8B-4244-935C-DEF20A6EB5E7">Completing the NDIS Selective Suspend Idle Notification</a>



 

 


