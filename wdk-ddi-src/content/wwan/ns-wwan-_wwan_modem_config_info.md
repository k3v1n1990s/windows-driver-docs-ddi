---
UID: NS:wwan._WWAN_MODEM_CONFIG_INFO
title: "_WWAN_MODEM_CONFIG_INFO"
author: windows-driver-content
description: The WWAN_MODEM_CONFIG_INFO structure represents the modem's configuration information.
old-location: netvista\wwan_modem_config_info.htm
old-project: netvista
ms.assetid: 14FBFA51-F4A5-417A-8905-241CEA543774
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*PWWAN_MODEM_CONFIG_INFO, PWWAN_MODEM_CONFIG_INFO, PWWAN_MODEM_CONFIG_INFO structure pointer [Network Drivers Starting with Windows Vista], WWAN_MODEM_CONFIG_INFO, WWAN_MODEM_CONFIG_INFO structure [Network Drivers Starting with Windows Vista], _WWAN_MODEM_CONFIG_INFO, netvista.wwan_modem_config_info, wwan/PWWAN_MODEM_CONFIG_INFO, wwan/WWAN_MODEM_CONFIG_INFO"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wwan.h
req.include-header: Wwan.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709
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
-	wwan.h
api_name:
-	WWAN_MODEM_CONFIG_INFO
product: Windows
targetos: Windows
req.typenames: WWAN_MODEM_CONFIG_INFO, *PWWAN_MODEM_CONFIG_INFO
req.product: Windows 10 or later.
---

# _WWAN_MODEM_CONFIG_INFO structure


## -description


The <b>WWAN_MODEM_CONFIG_INFO</b> structure represents the modem's configuration information.


## -syntax


````
typedef struct _WWAN_MODEM_CONFIG_INFO {
  WWAN_MODEM_CONFIG_STATUS ConfigStatus;
  WWAN_MODEM_CONFIG_MODE   ConfigMode;
} WWAN_MODEM_CONFIG_INFO, *PWWAN_MODEM_CONFIG_INFO;
````


## -struct-fields




### -field ConfigStatus

A formatted <a href="..\wwan\ns-wwan-_wwan_modem_config_status.md">WWAN_MODEM_CONFIG_STATUS</a> structure containing the modem's configuration (config) status.


### -field ConfigMode

The modem's configuration mode. For a list of defined values, see <a href="..\wwan\ne-wwan-_wwan_modem_config_mode.md">WWAN_MODEM_CONFIG_MODE</a>.


## -see-also

<a href="..\wwan\ne-wwan-_wwan_modem_config_mode.md">WWAN_MODEM_CONFIG_MODE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-wwan-modem-config-info">OID_WWAN_MODEM_CONFIG_INFO</a>



<a href="..\ndiswwan\ns-ndiswwan-_ndis_wwan_modem_config_info.md">NDIS_WWAN_MODEM_CONFIG_INFO</a>



<a href="..\wwan\ns-wwan-_wwan_modem_config_status.md">WWAN_MODEM_CONFIG_STATUS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/ndis-status-wwan-modem-config-info">NDIS_STATUS_WWAN_MODEM_CONFIG_INFO</a>



 

 


