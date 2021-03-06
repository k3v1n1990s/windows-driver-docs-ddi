---
UID: NF:ntifs.FsRtlSetupAdvancedHeaderEx
title: FsRtlSetupAdvancedHeaderEx macro
author: windows-driver-content
description: The FsRtlSetupAdvancedHeaderEx macro is used by file systems to initialize an FSRTL_ADVANCED_FCB_HEADER structure for use with both stream and file contexts.
old-location: ifsk\fsrtlsetupadvancedheaderex.htm
old-project: ifsk
ms.assetid: 41e5d9f2-ac0b-4834-bca8-88ed872f2f70
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: FsRtlSetupAdvancedHeaderEx, FsRtlSetupAdvancedHeaderEx function [Installable File System Drivers], fsrtlref_9214990b-2568-43d9-801a-c43514a6448f.xml, ifsk.fsrtlsetupadvancedheaderex, ntifs/FsRtlSetupAdvancedHeaderEx
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: ntifs.h
req.include-header: Ntifs.h, Fltkernel.h
req.target-type: Desktop
req.target-min-winverclnt: Available on Update Rollup for Microsoft Windows 2000 Service Pack 4 (SP4) and on Windows XP and later versions of the Windows operating systems.
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntifs.h
api_name:
-	FsRtlSetupAdvancedHeaderEx
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# FsRtlSetupAdvancedHeaderEx macro


## -description


The <b>FsRtlSetupAdvancedHeaderEx</b> macro is used by file systems to initialize an <a href="..\ntifs\ns-ntifs-_fsrtl_advanced_fcb_header.md">FSRTL_ADVANCED_FCB_HEADER</a> structure for use with both stream and file contexts.


## -syntax


````
VOID FsRtlSetupAdvancedHeaderEx(
  _In_     PFSRTL_ADVANCED_FCB_HEADER AdvancedHeader,
  _In_opt_ PFAST_MUTEX                FastMutex,
  _In_opt_ PVOID                      *FileContextSupportPointer
);
````


## -parameters




### -param _advhdr

TBD


### -param _fmutx

TBD


### -param _fctxptr

TBD






#### - AdvancedHeader [in]

Pointer to the <a href="..\ntifs\ns-ntifs-_fsrtl_advanced_fcb_header.md">FSRTL_ADVANCED_FCB_HEADER</a> structure to be initialized. 


#### - FastMutex [in, optional]

Pointer to an initialized fast mutex that will be used to synchronize access to certain FSRTL_ADVANCED_FCB_HEADER members (for more information, see <a href="..\ntifs\ns-ntifs-_fsrtl_advanced_fcb_header.md">FSRTL_ADVANCED_FCB_HEADER</a>). The fast mutex must be allocated from nonpaged pool. This parameter is optional and can be <b>NULL</b>. Callers should set this parameter to <b>NULL</b> if they intend to use an already existing fast mutex object. If <i>FastMutex</i> is <b>NULL</b>, the caller must explicitly set the <b>FastMutex</b> member of the FSRTL_ADVANCED_FCB_HEADER structure, contained in the stream context object, to point to the existing fast mutex. (This can be done before or after calling <b>FsRtlSetupAdvancedHeaderEx</b>.)


#### - FileContextSupportPointer [in, optional]

A pointer to a pointer field used by the file system runtime library (FSRTL) package to track file contexts. 

This parameter is optional and can be <b>NULL</b>.  In particular:

<ul>
<li>
 For Microsoft Windows operating systems released prior to Windows Vista: Callers must set this parameter to <b>NULL</b>.

</li>
<li>
 For Windows operating systems starting with Windows Vista: If <i>FileContextSupportPointer</i> is not <b>NULL</b>, <i>FileContextSupportPointer</i> must be a pointer to a PVOID variable inside a per-file structure for the file system that created the structure.  To indicate that the file system driver does not support file contexts, callers must set <i>FileContextSupportPointer</i> to <b>NULL</b>.

</li>
</ul>

## -remarks



File systems use the <b>FsRtlSetupAdvancedHeaderEx</b> macro to initialize an FSRTL_ADVANCED_FCB_HEADER structure for use with stream and file contexts. 

When the advanced FCB header structure is no longer required, the file system must call <a href="..\ntifs\nf-ntifs-fsrtlteardownperstreamcontexts.md">FsRtlTeardownPerStreamContexts</a> to free all associated stream and file context structures.

For more information, see <a href="https://msdn.microsoft.com/d908ee30-a433-460c-8c14-883702b4f810">Tracking Per-Stream Context in a Legacy File System Filter Driver</a>. 




## -see-also

<a href="..\ntifs\nf-ntifs-fsrtlgetperstreamcontextpointer.md">FsRtlGetPerStreamContextPointer</a>



<a href="..\ntifs\nf-ntifs-fsrtlinitperstreamcontext.md">FsRtlInitPerStreamContext</a>



<a href="..\ntifs\nf-ntifs-fsrtllookupperstreamcontext.md">FsRtlLookupPerStreamContext</a>



<a href="..\ntifs\ns-ntifs-_fsrtl_advanced_fcb_header.md">FSRTL_ADVANCED_FCB_HEADER</a>



<a href="..\ntifs\nf-ntifs-fsrtlteardownperstreamcontexts.md">FsRtlTeardownPerStreamContexts</a>



<a href="..\ntifs\nf-ntifs-fsrtlremoveperstreamcontext.md">FsRtlRemovePerStreamContext</a>



<a href="..\ntifs\nf-ntifs-fsrtlinsertperstreamcontext.md">FsRtlInsertPerStreamContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547285">FsRtlSupportsPerStreamContexts</a>



<a href="..\ntifs\ns-ntifs-_fsrtl_per_stream_context.md">FSRTL_PER_STREAM_CONTEXT</a>



 

 


