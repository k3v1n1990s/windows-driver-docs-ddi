---
UID: NF:rilapi.RIL_WritePhonebookEntry
title: RIL_WritePhonebookEntry function
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\ril_writephonebookentry.htm
old-project: netvista
ms.assetid: 03fc6240-ccc8-48de-87e0-b1ee5db3bac8
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: RIL_WritePhonebookEntry, RIL_WritePhonebookEntry method [Network Drivers Starting with Windows Vista], netvista.ril_writephonebookentry, rilapi/RIL_WritePhonebookEntry
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: rilapi.h
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
-	HeaderDef
api_location:
-	rilapi.h
api_name:
-	RIL_WritePhonebookEntry
product: Windows
targetos: Windows
req.typenames: RH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER, *PRH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER
req.product: Windows 10 or later.
---

# RIL_WritePhonebookEntry function


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 

            


## -syntax


````
HRESULT  RIL_WritePhonebookEntry(
   HRIL                         hRil,
   LPVOID                       lpContext,
   HUICCAPP                     hUiccApp,
   RILPHONEENTRYSTORELOCATION   dwStoreLocation,
   const RILPHONEBOOKENTRY      lpEntry,
   const RILUICCLOCKCREDENTIAL  lpLockVerification
);
````


## -parameters




### -param hRil


### -param lpContext


### -param hUiccApp


### -param dwStoreLocation


### -param lpEntry


### -param lpLockVerification


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.



