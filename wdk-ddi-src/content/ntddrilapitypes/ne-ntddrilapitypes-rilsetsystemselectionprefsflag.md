---
UID: NE:ntddrilapitypes.RILSETSYSTEMSELECTIONPREFSFLAG
title: RILSETSYSTEMSELECTIONPREFSFLAG
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsetsystemselectionprefsflag.htm
old-project: netvista
ms.assetid: 081f4a23-43d8-4ad4-806c-1b6322e057d5
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: RILSETSYSTEMSELECTIONPREFSFLAG, RILSETSYSTEMSELECTIONPREFSFLAG enumeration [Network Drivers Starting with Windows Vista], RIL_SSSPFLAG_ALL, RIL_SSSPFLAG_APPLYIMMEDIATELY, RIL_SSSPFLAG_ENFORCESCAN, netvista.rilsetsystemselectionprefsflag, ntddrilapitypes/RILSETSYSTEMSELECTIONPREFSFLAG, ntddrilapitypes/RIL_SSSPFLAG_ALL, ntddrilapitypes/RIL_SSSPFLAG_APPLYIMMEDIATELY, ntddrilapitypes/RIL_SSSPFLAG_ENFORCESCAN
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
-	RILSETSYSTEMSELECTIONPREFSFLAG
product: Windows
targetos: Windows
req.typenames: RILSETSYSTEMSELECTIONPREFSFLAG
---

# RILSETSYSTEMSELECTIONPREFSFLAG enumeration


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


````
typedef enum _RILSETSYSTEMSELECTIONPREFSFLAG { 
  RIL_SSSPFLAG_APPLYIMMEDIATELY,
  RIL_SSSPFLAG_ENFORCESCAN,
  RIL_SSSPFLAG_ALL
} RILSETSYSTEMSELECTIONPREFSFLAG;
````


## -enum-fields




### -field RIL_SSSPFLAG_NONE


### -field RIL_SSSPFLAG_APPLYIMMEDIATELY


### -field RIL_SSSPFLAG_ENFORCESCAN


### -field RIL_SSSPFLAG_ALL

