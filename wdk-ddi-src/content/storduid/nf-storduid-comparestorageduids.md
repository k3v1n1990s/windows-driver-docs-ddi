---
UID: NF:storduid.CompareStorageDuids
title: CompareStorageDuids function
author: windows-driver-content
description: The CompareStorageDuids routine compares two device unique identifiers (DUIDs) and reports whether they match or not.
old-location: storage\comparestorageduids.htm
old-project: storage
ms.assetid: bf66a04d-0892-4813-9615-845054526125
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: CompareStorageDuids, CompareStorageDuids routine [Storage Devices], storage.comparestorageduids, storduid/CompareStorageDuids, storertns-general_86f18b5a-ed33-48e8-b13c-76bd2422418d.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: storduid.h
req.include-header: Storduid.h
req.target-type: Desktop
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
-	storduid.h
api_name:
-	CompareStorageDuids
product: Windows
targetos: Windows
req.typenames: DUID_MATCH_STATUS
req.product: Windows 10 or later.
---

# CompareStorageDuids function


## -description


The <b>CompareStorageDuids</b> routine compares two device unique identifiers (DUIDs) and reports whether they match or not.


## -syntax


````
__inline DUID_MATCH_STATUS CompareStorageDuids(
  _In_ PSTORAGE_DEVICE_UNIQUE_IDENTIFIER Duid1,
  _In_ PSTORAGE_DEVICE_UNIQUE_IDENTIFIER Duid2
);
````


## -parameters




### -param Duid1 [in]

A pointer to a DUID to compare with the DUID that <i>Duid2</i> points to.


### -param Duid2 [in]

A pointer to a DUID to compare with the DUID that <i>Duid1</i> points to.


## -returns



<b>CompareStorageDuids</b> returns a <a href="..\storduid\ne-storduid-_duid_match_status.md">DUID_MATCH_STATUS</a> value that indicates whether the two DUIDs matched or not, if the operation succeeds. Otherwise, this routine returns a DUID_MATCH_STATUS value that indicates the error status.




## -see-also

<a href="..\storduid\ne-storduid-_duid_match_status.md">DUID_MATCH_STATUS</a>



 

 


