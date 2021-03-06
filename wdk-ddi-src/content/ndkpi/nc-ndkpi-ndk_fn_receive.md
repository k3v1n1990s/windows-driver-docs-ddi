---
UID: NC:ndkpi.NDK_FN_RECEIVE
title: NDK_FN_RECEIVE
author: windows-driver-content
description: The NdkReceive (NDK_FN_RECEIVE) function posts a receive request on an NDK queue pair (QP).
old-location: netvista\ndk_fn_receive.htm
old-project: netvista
ms.assetid: DC40C6B5-3F52-4A7E-B8FC-917ACDF8309A
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: NDK_FN_RECEIVE, NdkReceive, NdkReceive callback function [Network Drivers Starting with Windows Vista], ndkpi/NdkReceive, netvista.ndk_fn_receive
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ndkpi.h
req.include-header: Ndkpi.h
req.target-type: Windows
req.target-min-winverclnt: None supported,Supported in NDIS 6.30 and later.
req.target-min-winversvr: Windows Server 2012
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
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	ndkpi.h
api_name:
-	NdkReceive
product: Windows
targetos: Windows
req.typenames: NDIS_WWAN_VISIBLE_PROVIDERS, *PNDIS_WWAN_VISIBLE_PROVIDERS
---

# NDK_FN_RECEIVE callback


## -description



   The <i>NdkReceive</i> (<i>NDK_FN_RECEIVE</i>) function posts a receive request on an NDK queue pair (QP).  
  


## -prototype


````
NDK_FN_RECEIVE NdkReceive;

NTSTATUS NdkReceive(
  _In_     NDK_QP                         *pNdkQp,
  _In_opt_ PVOID                          RequestContext,
           _In_reads_(nSge) CONST NDK_SGE *pSgl,
  _In_     ULONG                          nSge
)
{ ... }
````


## -parameters




### -param *pNdkQp [in]

A pointer to an NDK queue pair (QP) object
(<a href="..\ndkpi\ns-ndkpi-_ndk_qp.md">NDK_QP</a>).


### -param RequestContext [in, optional]

A context value to be returned in the <b>RequestContext</b> member of the <a href="..\ndkpi\ns-ndkpi-_ndk_result.md">NDK_RESULT</a> structure for this request.



### -param NDK_SGE


### -param nSge [in]

The number of SGE structures in the array  that is specified in the <i>pSgl</i>
parameter.


#### - pSgl

An array of SGE structures (<a href="..\ndkpi\ns-ndkpi-_ndk_sge.md">NDK_SGE</a>) that represent the buffers to receive incoming data.



## -returns



The 
     <i>NdkReceive</i> function returns one of the following NTSTATUS codes.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The request was posted successfully. A completion entry will be queued to the CQ when the work request is completed.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>Other status codes</b></dt>
</dl>
</td>
<td width="60%">
An error occurred. 

</td>
</tr>
</table>
 




## -remarks



<i>NdkReceive</i> posts a receive request on a queue pair (QP).




## -see-also

<a href="..\ndkpi\ns-ndkpi-_ndk_qp.md">NDK_QP</a>



<a href="..\ndkpi\ns-ndkpi-_ndk_sge.md">NDK_SGE</a>



<a href="https://msdn.microsoft.com/2BF6F253-FCB4-4A61-9A67-81092F3C44E4">NDKPI Work Request Posting Requirements</a>



<a href="..\ndkpi\ns-ndkpi-_ndk_result.md">NDK_RESULT</a>



 

 


