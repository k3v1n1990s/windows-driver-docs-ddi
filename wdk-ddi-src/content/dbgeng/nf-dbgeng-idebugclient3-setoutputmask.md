---
UID: NF:dbgeng.IDebugClient3.SetOutputMask
title: IDebugClient3::SetOutputMask method
author: windows-driver-content
description: The SetOutputMask method sets the output mask for the client.
old-location: debugger\setoutputmask.htm
old-project: debugger
ms.assetid: 8fef4def-9735-4623-841b-a18995d4d403
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: IDebugClient interface [Windows Debugging], SetOutputMask method, IDebugClient2 interface [Windows Debugging], SetOutputMask method, IDebugClient2::SetOutputMask, IDebugClient3, IDebugClient3 interface [Windows Debugging], SetOutputMask method, IDebugClient3::SetOutputMask, IDebugClient4 interface [Windows Debugging], SetOutputMask method, IDebugClient4::SetOutputMask, IDebugClient5 interface [Windows Debugging], SetOutputMask method, IDebugClient5::SetOutputMask, IDebugClient::SetOutputMask, IDebugClient_85242101-702d-4c9a-b71a-5eddd76a4fa6.xml, SetOutputMask method [Windows Debugging], SetOutputMask method [Windows Debugging], IDebugClient interface, SetOutputMask method [Windows Debugging], IDebugClient2 interface, SetOutputMask method [Windows Debugging], IDebugClient3 interface, SetOutputMask method [Windows Debugging], IDebugClient4 interface, SetOutputMask method [Windows Debugging], IDebugClient5 interface, SetOutputMask,IDebugClient3.SetOutputMask, dbgeng/IDebugClient2::SetOutputMask, dbgeng/IDebugClient3::SetOutputMask, dbgeng/IDebugClient4::SetOutputMask, dbgeng/IDebugClient5::SetOutputMask, dbgeng/IDebugClient::SetOutputMask, debugger.setoutputmask
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
-	IDebugClient.SetOutputMask
-	IDebugClient2.SetOutputMask
-	IDebugClient3.SetOutputMask
-	IDebugClient4.SetOutputMask
-	IDebugClient5.SetOutputMask
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugClient3::SetOutputMask method


## -description


The <b>SetOutputMask</b> method sets the output mask for the client.


## -syntax


````
HRESULT SetOutputMask(
  [in] ULONG Mask
);
````


## -parameters




### -param Mask [in]

Specifies the new output mask for the client.  See <a href="https://msdn.microsoft.com/library/windows/hardware/ff541518">DEBUG_OUTPUT_XXX</a> for a description of the possible values for <i>Mask</i>.


## -returns



This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.

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



For an overview of output in the debugger engine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff550971">Input and Output</a>.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff556750">SetOtherOutputMask</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient5.md">IDebugClient5</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient4.md">IDebugClient4</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient3.md">IDebugClient3</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient.md">IDebugClient</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548080">GetOutputMask</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient2.md">IDebugClient2</a>



 

 


