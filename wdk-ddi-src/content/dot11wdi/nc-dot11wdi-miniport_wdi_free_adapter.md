---
UID: NC:dot11wdi.MINIPORT_WDI_FREE_ADAPTER
title: MINIPORT_WDI_FREE_ADAPTER
author: windows-driver-content
description: The MiniportWdiFreeAdapter handler function requests that the IHV driver deletes its software state.
old-location: netvista\miniportwdifreeadapter.htm
old-project: netvista
ms.assetid: 7D88B513-5289-4347-BD25-BDFEB86CE62F
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: MINIPORT_WDI_FREE_ADAPTER, MiniportWdiFreeAdapter, MiniportWdiFreeAdapter callback function [Network Drivers Starting with Windows Vista], dot11wdi/MiniportWdiFreeAdapter, netvista.miniportwdifreeadapter
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
-	MiniportWdiFreeAdapter
product: Windows
targetos: Windows
req.typenames: SYNTH_STATS, *PSYNTH_STATS
---

# MINIPORT_WDI_FREE_ADAPTER callback


## -description


The MiniportWdiFreeAdapter handler function requests that the IHV driver deletes its software state.

This is a WDI miniport handler inside <a href="..\dot11wdi\ns-dot11wdi-_ndis_miniport_driver_wdi_characteristics.md">NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS</a>.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>MINIPORT_WDI_FREE_ADAPTER</b> type. For more
   information, see the following Examples section.</div><div> </div>

## -prototype


````
MINIPORT_WDI_FREE_ADAPTER MiniportWdiFreeAdapter;

VOID MiniportWdiFreeAdapter(
  _In_ NDIS_HANDLE MiniportAdapterContext
)
{ ... }
````


## -parameters




### -param MiniportAdapterContext [in]

The handle to the context area that the miniport driver allocated.


## -returns



This callback function does not return a value.




## -see-also

<a href="..\dot11wdi\ns-dot11wdi-_ndis_miniport_driver_wdi_characteristics.md">NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS</a>



 

 


