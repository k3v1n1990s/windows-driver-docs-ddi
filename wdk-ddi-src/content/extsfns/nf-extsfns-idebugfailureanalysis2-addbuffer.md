---
UID: NF:extsfns.IDebugFailureAnalysis2.AddBuffer
title: IDebugFailureAnalysis2::AddBuffer method
author: windows-driver-content
description: The AddBuffer method adds a new FA entry to a DebugFailureAnalysis object, and writes the bytes from a specified buffer to the data block of the new FA entry.
old-location: debugger\idebugfailureanalysis2_addbuffer.htm
old-project: debugger
ms.assetid: E6510000-E390-4631-9D47-5A57AB845EF6
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: AddBuffer method [Windows Debugging], AddBuffer method [Windows Debugging], IDebugFailureAnalysis2 interface, AddBuffer,IDebugFailureAnalysis2.AddBuffer, IDebugFailureAnalysis2, IDebugFailureAnalysis2 interface [Windows Debugging], AddBuffer method, IDebugFailureAnalysis2::AddBuffer, debugger.idebugfailureanalysis2_addbuffer, extsfns/IDebugFailureAnalysis2::AddBuffer
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: extsfns.h
req.include-header: 
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
-	COM
api_location:
-	extsfns.h
api_name:
-	IDebugFailureAnalysis2.AddBuffer
product: Windows
targetos: Windows
req.typenames: FA_EXTENSION_PLUGIN_PHASE
---

# IDebugFailureAnalysis2::AddBuffer method


## -description


The <b>AddBuffer</b> method adds a new <a href="https://msdn.microsoft.com/759DE159-F2A8-4BB1-AAF5-B2B91C4F91B0">FA entry</a> to a <a href="..\extsfns\nn-extsfns-idebugfailureanalysis2.md">DebugFailureAnalysis</a> object, and writes the bytes from a specified buffer to the data block of the new FA entry.


## -syntax


````
FA_ENTRY AddBuffer(
       FA_TAG        Tag,
  [in] FA_ENTRY_TYPE EntryType,
  [in] PVOID         Buf,
  [in] ULONG         Size
);
````


## -parameters




### -param Tag

A value in the <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/debugger/writing-an-analysis-extension-to-extend--analyze">FA_TAG</a> enumeration.


### -param EntryType [in]

A value in the <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/debugger/writing-an-analysis-extension-to-extend--analyze">FA_ENTRY_TYPE</a> enumeration. This parameter specifies the data type of the data in <i>Buf</i>.


### -param Buf [in]

A pointer to a buffer that contains the bytes to be written to the data block of the new <a href="https://msdn.microsoft.com/759DE159-F2A8-4BB1-AAF5-B2B91C4F91B0">FA entry</a>.


### -param Size [in]

The size, in bytes, of the buffer pointed to by <i>Buf</i>.


## -returns



If this method succeeds, it returns a pointer to the new <a href="..\extsfns\ns-extsfns-_fa_entry.md">FA_ENTRY</a> structure. Otherwise, it returns <b>NULL</b>.




## -remarks



This method creates a new <a href="https://msdn.microsoft.com/759DE159-F2A8-4BB1-AAF5-B2B91C4F91B0">FA entry</a> with the tag specified by <i>Tag</i>, and it associates the tag with the data type specified by <i>EntryType</i>. 




## -see-also

<a href="..\extsfns\nn-extsfns-idebugfailureanalysis2.md">IDebugFailureAnalysis2</a>



<a href="https://msdn.microsoft.com/7648F789-85D5-4247-90DD-2EAA43543483">Writing an Analysis Extension Plug-in to Extend !analyze</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/jj983423">SetBuffer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/jj983413">GetBuffer</a>



<a href="..\extsfns\nc-extsfns-ext_analysis_plugin.md">_EFN_Analyze</a>



 

 


