---
UID: NF:ndis.NdisFreeNetBufferListContext
title: NdisFreeNetBufferListContext function
author: windows-driver-content
description: Call the NdisFreeNetBufferListContext function to release context space in the NET_BUFFER_LIST_CONTEXT structure of a NET_BUFFER_LIST structure.
old-location: netvista\ndisfreenetbufferlistcontext.htm
old-project: netvista
ms.assetid: e5554790-a7a2-4c0d-a6ae-585ea909cd3d
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: NdisFreeNetBufferListContext, NdisFreeNetBufferListContext function [Network Drivers Starting with Windows Vista], ndis/NdisFreeNetBufferListContext, ndis_netbuf_functions_ref_ee330dac-2453-46e7-a298-7d4a59caf0ab.xml, netvista.ndisfreenetbufferlistcontext
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_NetBuffer_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	ndis.lib
-	ndis.dll
api_name:
-	NdisFreeNetBufferListContext
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisFreeNetBufferListContext function


## -description


Call the 
  <b>NdisFreeNetBufferListContext</b> function to release context space in the 
  <a href="..\ndis\ns-ndis-_net_buffer_list_context.md">NET_BUFFER_LIST_CONTEXT</a> structure of a
  
  <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure.


## -syntax


````
VOID NdisFreeNetBufferListContext(
  _In_ PNET_BUFFER_LIST NetBufferList,
  _In_ USHORT           ContextSize
);
````


## -parameters




### -param NetBufferList [in]

A pointer to a previously allocated NET_BUFFER_LIST structure.


### -param ContextSize [in]

The amount of context space to free.


## -returns



None




## -remarks



<b>NdisFreeNetBufferListContext</b> releases context space that was allocated in a previous call to 
    <a href="..\ndis\nf-ndis-ndisallocatenetbufferlistcontext.md">
    NdisAllocateNetBufferListContext</a>. If 
    <b>NdisAllocateNetBufferListContext</b> allocated memory to satisfy in the call to 
    <b>NdisAllocateNetBufferListContext</b>, 
    <b>NdisFreeNetBufferListContext</b> frees the allocated memory.




## -see-also

<a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a>



<a href="..\ndis\ns-ndis-_net_buffer_list_context.md">NET_BUFFER_LIST_CONTEXT</a>



<a href="..\ndis\nf-ndis-ndisallocatenetbufferlistcontext.md">
   NdisAllocateNetBufferListContext</a>



 

 


