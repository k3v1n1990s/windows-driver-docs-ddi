---
UID: NF:dbgeng.IDebugControl3.GetExtensionByPath
title: IDebugControl3::GetExtensionByPath method
author: windows-driver-content
description: The GetExtensionByPath method returns the handle for an already loaded extension library.
old-location: debugger\getextensionbypath.htm
old-project: debugger
ms.assetid: 32755878-3f52-4e52-b093-1678c8b8bb42
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: GetExtensionByPath method [Windows Debugging], GetExtensionByPath method [Windows Debugging], IDebugControl interface, GetExtensionByPath method [Windows Debugging], IDebugControl2 interface, GetExtensionByPath method [Windows Debugging], IDebugControl3 interface, GetExtensionByPath,IDebugControl3.GetExtensionByPath, IDebugControl interface [Windows Debugging], GetExtensionByPath method, IDebugControl2 interface [Windows Debugging], GetExtensionByPath method, IDebugControl2::GetExtensionByPath, IDebugControl3, IDebugControl3 interface [Windows Debugging], GetExtensionByPath method, IDebugControl3::GetExtensionByPath, IDebugControl::GetExtensionByPath, IDebugControl_821ee348-ddb2-4464-93cd-b6a58e267795.xml, dbgeng/IDebugControl2::GetExtensionByPath, dbgeng/IDebugControl3::GetExtensionByPath, dbgeng/IDebugControl::GetExtensionByPath, debugger.getextensionbypath
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
-	IDebugControl.GetExtensionByPath
-	IDebugControl2.GetExtensionByPath
-	IDebugControl3.GetExtensionByPath
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugControl3::GetExtensionByPath method


## -description


The <b>GetExtensionByPath</b>  method returns the handle for an already loaded extension library.


## -syntax


````
HRESULT GetExtensionByPath(
  [in]  PCSTR    Path,
  [out] PULONG64 Handle
);
````


## -parameters




### -param Path [in]

Specifies the fully qualified path and file name of the extension library.


### -param Handle [out]

Receives the handle of the extension library.


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



Extension libraries are loaded into the <a href="https://msdn.microsoft.com/1cc2c055-447c-44cd-94d4-ae3dfa8243fb">host engine</a>, which is where this method looks for the requested extension library.  <i>Path</i> is a path and file name for the host engine.

For more information on using extension libraries, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff539033">Calling Extensions and Extension Functions</a>.




## -see-also

<a href="..\dbgeng\nn-dbgeng-idebugcontrol3.md">IDebugControl3</a>



<a href="..\dbgeng\nn-dbgeng-idebugcontrol.md">IDebugControl</a>



<a href="..\dbgeng\nn-dbgeng-idebugcontrol2.md">IDebugControl2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537892">AddExtension</a>



 

 


