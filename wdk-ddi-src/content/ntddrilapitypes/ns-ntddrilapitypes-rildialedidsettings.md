---
UID: NS:ntddrilapitypes.RILDIALEDIDSETTINGS
title: RILDIALEDIDSETTINGS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rildialedidsettings.htm
old-project: netvista
ms.assetid: e68ed118-76c7-44ff-a10f-dc64f1ce2d0e
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*LPRILDIALEDIDSETTINGS, RILDIALEDIDSETTINGS, RILDIALEDIDSETTINGS structure [Network Drivers Starting with Windows Vista], netvista.rildialedidsettings, ntddrilapitypes/RILDIALEDIDSETTINGS"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddrilapitypes.h
req.include-header: Rilapitypes.h
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
-	ntddrilapitypes.h
api_name:
-	RILDIALEDIDSETTINGS
product: Windows
targetos: Windows
req.typenames: RILDIALEDIDSETTINGS, *LPRILDIALEDIDSETTINGS
---

# RILDIALEDIDSETTINGS structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


````
typedef struct _RILDIALEDIDSETTINGS {
  DWORD                         cbSize;
  DWORD                         dwParams;
  DWORD                         dwExecutor;
  RILSERVICESETTINGSSTATUS      dwStatus;
  RILSERVICEPROVISIONINGSTATUS  dwProvisioning;
} RILDIALEDIDSETTINGS, RILDIALEDIDSETTINGS;
````


## -struct-fields




### -field cbSize


### -field dwParams


### -field dwExecutor


### -field dwStatus


### -field dwProvisioning

