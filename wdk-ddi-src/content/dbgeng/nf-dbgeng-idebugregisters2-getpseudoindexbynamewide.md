---
UID: NF:dbgeng.IDebugRegisters2.GetPseudoIndexByNameWide
title: IDebugRegisters2::GetPseudoIndexByNameWide method
author: windows-driver-content
description: The GetPseudoIndexByNameWide method returns the index of a pseudo-register.
old-location: debugger\getpseudoindexbynamewide.htm
old-project: debugger
ms.assetid: 86b76d13-d8b5-4336-a010-87d7753a367c
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: GetPseudoIndexByNameWide method [Windows Debugging], GetPseudoIndexByNameWide method [Windows Debugging], IDebugRegisters2 interface, GetPseudoIndexByNameWide,IDebugRegisters2.GetPseudoIndexByNameWide, IDebugRegisters2, IDebugRegisters2 interface [Windows Debugging], GetPseudoIndexByNameWide method, IDebugRegisters2::GetPseudoIndexByNameWide, dbgeng/IDebugRegisters2::GetPseudoIndexByNameWide, debugger.getpseudoindexbynamewide
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: dbgeng.h
req.include-header: DbgEng.h
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
-	dbgeng.h
api_name:
-	IDebugRegisters2.GetPseudoIndexByNameWide
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugRegisters2::GetPseudoIndexByNameWide method


## -description


The <b>GetPseudoIndexByNameWide</b>  method returns the index of a pseudo-register.


## -syntax


````
HRESULT GetPseudoIndexByNameWide(
  [in]  PCWSTR Name,
  [out] PULONG Index
);
````


## -parameters




### -param Name [in]

Specifies the name of the pseudo-register whose index is requested.  The name includes the leading dollar sign ( <b>$</b> ), for example, "$frame".


### -param Index [out]

Receives the index of the pseudo-register.


## -returns



This list does not contain all the errors that might occur.  For a list of possible errors, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff549771">HRESULT Values</a>.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The method was successful.

</td>
</tr>
</table>
 




## -remarks



For the names of all the pseudo-registers, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff553485">Pseudo-Register Syntax</a>.

For an overview of the <a href="..\dbgeng\nn-dbgeng-idebugregisters.md">IDebugRegisters</a> interface and other register-related methods, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff554369">Registers</a>.




## -see-also

<a href="..\dbgeng\nn-dbgeng-idebugregisters2.md">IDebugRegisters2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548189">GetPseudoDescription</a>



 

 


