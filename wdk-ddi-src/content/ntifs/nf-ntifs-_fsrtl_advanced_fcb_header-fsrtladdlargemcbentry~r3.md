---
UID: NF:ntifs._FSRTL_ADVANCED_FCB_HEADER.FsRtlAddLargeMcbEntry~r3
title: FsRtlAddLargeMcbEntry function
author: windows-driver-content
description: The FsRtlAddLargeMcbEntry routine adds a new mapping to an existing map control block (MCB).
old-location: ifsk\fsrtladdlargemcbentry.htm
old-project: ifsk
ms.assetid: 7cab24f3-624f-4fd1-9f33-76042e5f16ed
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: FsRtlAddLargeMcbEntry, FsRtlAddLargeMcbEntry routine [Installable File System Drivers], fsrtlref_de8b7789-cdba-4535-b2b9-bbc29add7fc6.xml, ifsk.fsrtladdlargemcbentry, ntifs/FsRtlAddLargeMcbEntry
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
req.dll: NtosKrnl.exe
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	FsRtlAddLargeMcbEntry
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# FsRtlAddLargeMcbEntry function


## -description


The <b>FsRtlAddLargeMcbEntry</b> routine adds a new mapping to an existing map control block (MCB). 


## -syntax


````
BOOLEAN FsRtlAddLargeMcbEntry(
  _In_ PLARGE_MCB OpaqueMcb,
  _In_ LONGLONG   LargeVbn,
  _In_ LONGLONG   LargeLbn,
  _In_ LONGLONG   LargeSectorCount
);
````


## -parameters




### -param Mcb

TBD


### -param Vbn

TBD


### -param Lbn

TBD


### -param SectorCount

TBD




#### - LargeLbn [in]

Logical block number (LBN) to which <i>LargeVbn</i> is to be mapped.


#### - LargeSectorCount [in]

Number of sectors in the new mapping run. 


#### - LargeVbn [in]

Starting virtual block number (VBN) of the new mapping run to be added to the MCB. 


#### - OpaqueMcb [in]

Pointer to an initialized MCB structure. 


## -returns



<b>FsRtlAddLargeMcbEntry</b> returns <b>TRUE</b> if the new mapping was successfully added to the MCB, <b>FALSE</b> otherwise. 




## -remarks



<b>FsRtlAddLargeMcbEntry</b> adds a new mapping to an existing map control block (MCB). File systems use MCB structures to map virtual block numbers (VBN) for a file to the corresponding logical block numbers (LBN) on disk.

<div class="alert"><b>Note</b>    The upper 32 bits of the LBN are ignored, but they must be set to zero. Only the lower 32 bits are used. </div>
<div> </div>
If a new mapping run to be added overlaps an existing mapping run, <b>FsRtlAddLargeMcbEntry</b> merges them into a single mapping run. 

If a pool allocation failure occurs, <b>FsRtlAddLargeMcbEntry</b> raises a STATUS_INSUFFICIENT_RESOURCES exception. To gain control if this pool allocation failure occurs, the driver should wrap the call to <b>FsRtlAddLargeMcbEntry</b> in a <b>try-except</b> or <b>try-finally</b> statement.

To initialize an MCB, call <a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializelargemcb~r1.md">FsRtlInitializeLargeMcb</a>. To uninitialize an MCB, call <a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtluninitializelargemcb.md">FsRtlUninitializeLargeMcb</a>. 




## -see-also

<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtluninitializelargemcb.md">FsRtlUninitializeLargeMcb</a>



<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlsplitlargemcb~r2.md">FsRtlSplitLargeMcb</a>



<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtllookuplastlargemcbentry~r2.md">FsRtlLookupLastLargeMcbEntry</a>



<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlremovelargemcbentry~r2.md">FsRtlRemoveLargeMcbEntry</a>



<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtltruncatelargemcb~r1.md">FsRtlTruncateLargeMcb</a>



<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtllookuplargemcbentry~r6.md">FsRtlLookupLargeMcbEntry</a>



<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializelargemcb~r1.md">FsRtlInitializeLargeMcb</a>



<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlnumberofrunsinlargemcb.md">FsRtlNumberOfRunsInLargeMcb</a>



<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtllookuplastlargemcbentryandindex~r3.md">FsRtlLookupLastLargeMcbEntryAndIndex</a>



<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlgetnextlargemcbentry~r4.md">FsRtlGetNextLargeMcbEntry</a>



 

 


