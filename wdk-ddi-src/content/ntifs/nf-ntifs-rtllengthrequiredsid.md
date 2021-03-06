---
UID: NF:ntifs.RtlLengthRequiredSid
title: RtlLengthRequiredSid function
author: windows-driver-content
description: The RtlLengthRequiredSid routine returns the length, in bytes, of the buffer required to store a security identifier (SID) with a specified number of subauthorities.
old-location: ifsk\rtllengthrequiredsid.htm
old-project: ifsk
ms.assetid: 1d6aa888-8e61-4a0e-88ea-13842fc2fff2
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RtlLengthRequiredSid, RtlLengthRequiredSid routine [Installable File System Drivers], ifsk.rtllengthrequiredsid, ntifs/RtlLengthRequiredSid, rtlref_78e8a660-8510-40bc-b221-747538423488.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe (kernel mode); Ntdll.dll (user mode)
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
-	Ntdll.dll
api_name:
-	RtlLengthRequiredSid
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# RtlLengthRequiredSid function


## -description


The <b>RtlLengthRequiredSid</b> routine returns the length, in bytes, of the buffer required to store a security identifier (SID) with a specified number of subauthorities. 


## -syntax


````
ULONG RtlLengthRequiredSid(
  _In_ ULONG SubAuthorityCount
);
````


## -parameters




### -param SubAuthorityCount [in]

The number of subauthorities to be stored in the SID. 


## -returns



<b>RtlLengthRequiredSid</b> returns the length, in bytes, of the buffer required to store the SID structure. 




## -remarks



For more information about security and access control, see the documentation on these topics in the Microsoft Windows SDK.




## -see-also

<a href="..\ntifs\nf-ntifs-rtllengthsid.md">RtlLengthSid</a>



<a href="..\ntifs\nf-ntifs-rtlequalsid.md">RtlEqualSid</a>



<a href="..\ntifs\nf-ntifs-rtlvalidsid.md">RtlValidSid</a>



<a href="..\ntifs\nf-ntifs-rtlequalprefixsid.md">RtlEqualPrefixSid</a>



<a href="..\ntifs\nf-ntifs-rtlsubauthoritysid.md">RtlSubAuthoritySid</a>



<a href="..\ntifs\nf-ntifs-rtlinitializesid.md">RtlInitializeSid</a>



<a href="..\ntifs\ns-ntifs-_sid.md">SID</a>



 

 


