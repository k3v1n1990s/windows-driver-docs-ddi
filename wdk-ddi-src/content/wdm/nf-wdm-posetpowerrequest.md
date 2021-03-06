---
UID: NF:wdm.PoSetPowerRequest
title: PoSetPowerRequest function
author: windows-driver-content
description: The PoSetPowerRequest routine increments the count for the specified power request type.
old-location: kernel\posetpowerrequest.htm
old-project: kernel
ms.assetid: 5670a4dd-3804-4532-8765-2fdffe1c4a0b
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: PoSetPowerRequest, PoSetPowerRequest routine [Kernel-Mode Driver Architecture], kernel.posetpowerrequest, portn_8f3abb03-a324-4841-b630-b62344d656ce.xml, wdm/PoSetPowerRequest
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 7.
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	PoSetPowerRequest
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# PoSetPowerRequest function


## -description


The <b>PoSetPowerRequest</b> routine increments the count for the specified power request type.


## -syntax


````
NTSTATUS PoSetPowerRequest(
  _Inout_ PVOID              PowerRequest,
  _In_    POWER_REQUEST_TYPE Type
);
````


## -parameters




### -param PowerRequest [in, out]

A pointer to a power request object that was created by the <a href="..\wdm\nf-wdm-pocreatepowerrequest.md">PoCreatePowerRequest</a> routine.


### -param Type [in]

The type of power request. Set this parameter to the following <a href="..\wdm\ne-wdm-_power_request_type.md">POWER_REQUEST_TYPE</a> enumeration value:

<ul>
<li>
<b>PowerRequestSystemRequired</b>

</li>
</ul>

## -returns



<b>PoSetPowerRequest</b> returns STATUS_SUCCESS if the call is successful. If the call fails, possible error return codes include the following:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NOT_SUPPORTED</b></dt>
</dl>
</td>
<td width="60%">
The <i>Type</i> parameter is set to an unsupported value.

</td>
</tr>
</table>
 




## -remarks



A driver can call the <b>PoSetPowerRequest</b> routine to request that the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559829">power manager</a> override several types of default power behavior, which are specified as <a href="..\wdm\ne-wdm-_power_request_type.md">POWER_REQUEST_TYPE</a> enumeration values. To restore the default behavior, the driver cancels the request by calling the <a href="..\wdm\nf-wdm-poclearpowerrequest.md">PoClearPowerRequest</a> routine.

The power manager maintains a count of the active requests for each power request type. The <b>PoSetPowerRequest</b> routine increments the count for the specified power request type by one. The <b>PoClearPowerRequest</b> routine decrements the count by one. A nonzero count indicates that requests from one or more components are active. After the count decrements to zero, the computer reverts to the default behavior for the specified power request type.




## -see-also

<a href="..\wdm\nf-wdm-pocreatepowerrequest.md">PoCreatePowerRequest</a>



<a href="..\wdm\nf-wdm-poclearpowerrequest.md">PoClearPowerRequest</a>



<a href="..\wdm\ne-wdm-_power_request_type.md">POWER_REQUEST_TYPE</a>



 

 


