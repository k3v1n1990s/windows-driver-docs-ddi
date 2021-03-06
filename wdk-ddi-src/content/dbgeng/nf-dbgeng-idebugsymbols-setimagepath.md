---
UID: NF:dbgeng.IDebugSymbols.SetImagePath
title: IDebugSymbols::SetImagePath method
author: windows-driver-content
description: The SetImagePath method sets the executable image path.
old-location: debugger\setimagepath.htm
old-project: debugger
ms.assetid: 4f6de771-c54f-4f27-900a-98e94b94f957
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: IDebugSymbols, IDebugSymbols interface [Windows Debugging], SetImagePath method, IDebugSymbols2 interface [Windows Debugging], SetImagePath method, IDebugSymbols2::SetImagePath, IDebugSymbols3 interface [Windows Debugging], SetImagePath method, IDebugSymbols3::SetImagePath, IDebugSymbols::SetImagePath, IDebugSymbols_062aa9c4-33c9-4a73-a11f-7d5e6b94e96c.xml, SetImagePath method [Windows Debugging], SetImagePath method [Windows Debugging], IDebugSymbols interface, SetImagePath method [Windows Debugging], IDebugSymbols2 interface, SetImagePath method [Windows Debugging], IDebugSymbols3 interface, SetImagePath,IDebugSymbols.SetImagePath, dbgeng/IDebugSymbols2::SetImagePath, dbgeng/IDebugSymbols3::SetImagePath, dbgeng/IDebugSymbols::SetImagePath, debugger.setimagepath
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: dbgeng.h
req.include-header: Dbgeng.h
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
-	IDebugSymbols.SetImagePath
-	IDebugSymbols2.SetImagePath
-	IDebugSymbols3.SetImagePath
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugSymbols::SetImagePath method


## -description


The <b>SetImagePath</b>  method sets the executable image path.


## -syntax


````
HRESULT SetImagePath(
  [in] PCSTR Path
);
````


## -parameters




### -param Path [in]

Specifies the new executable image path.  This is a string that contains directories separated by semicolons (<b>;</b>).


## -returns



This method can also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.

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



The executable image path is used by the engine when searching for executable images.

The executable image path can consist of several directories separated by semicolons.  These directories are searched in order.




## -see-also

<a href="..\dbgeng\nn-dbgeng-idebugsymbols3.md">IDebugSymbols3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546851">GetImagePath</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff538092">AppendImagePath</a>



<a href="..\dbgeng\nn-dbgeng-idebugsymbols.md">IDebugSymbols</a>



<a href="..\dbgeng\nn-dbgeng-idebugsymbols2.md">IDebugSymbols2</a>



 

 


