---
UID: NF:ndis.NdisAllocateNetBufferList
title: NdisAllocateNetBufferList function
author: windows-driver-content
description: Call the NdisAllocateNetBufferList function to allocate and initialize a NET_BUFFER_LIST structure from a NET_BUFFER_LIST structure pool.
old-location: netvista\ndisallocatenetbufferlist.htm
old-project: netvista
ms.assetid: 9c821aac-9abd-4041-a15e-64306ada1c02
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: NdisAllocateNetBufferList, NdisAllocateNetBufferList function [Network Drivers Starting with Windows Vista], ndis/NdisAllocateNetBufferList, ndis_netbuf_functions_ref_85e4ad07-739d-4c37-b436-d9ca95c9db92.xml, netvista.ndisallocatenetbufferlist
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
-	NdisAllocateNetBufferList
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisAllocateNetBufferList function


## -description


Call the 
  <b>NdisAllocateNetBufferList</b> function to allocate and initialize a 
  <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure from a
  NET_BUFFER_LIST structure pool.


## -syntax


````
PNET_BUFFER_LIST NdisAllocateNetBufferList(
  _In_ NDIS_HANDLE PoolHandle,
  _In_ USHORT      ContextSize,
  _In_ USHORT      ContextBackFill
);
````


## -parameters




### -param PoolHandle [in]

A NET_BUFFER_LIST structure pool handle that was previously returned from a call to 
     <a href="..\ndis\nf-ndis-ndisallocatenetbufferlistpool.md">
     NdisAllocateNetBufferListPool</a>.


### -param ContextSize [in]

The amount of 
     <i>used data space</i> in the 
     <a href="..\ndis\ns-ndis-_net_buffer_list_context.md">NET_BUFFER_LIST_CONTEXT</a> structure
     to reserve for the caller. The 
     <i>ContextSize</i> must be a multiple of the value defined by MEMORY_ALLOCATION_ALIGNMENT.


### -param ContextBackFill [in]

The amount of 
     <i>unused data space</i> (backfill space) that the caller requires. NDIS adds this value to the 
     <i>ContextSize</i> and allocates additional space. The 
     <i>ContextBackFill</i> must be a multiple of the value defined by MEMORY_ALLOCATION_ALIGNMENT.


## -returns



<b>NdisAllocateNetBufferList</b> returns a pointer to the allocated NET_BUFFER_LIST structure. If the
     allocation was unsuccessful, this pointer is <b>NULL</b>.




## -remarks



You can call the 
    <b>NdisAllocateNetBufferList</b> or 
    <a href="..\ndis\nf-ndis-ndisallocatenetbufferandnetbufferlist.md">
    NdisAllocateNetBufferAndNetBufferList</a> function to allocate a 
    <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure from a pool.

<div class="alert"><b>Note</b>  <a href="..\ndis\ns-ndis-_net_buffer.md">NET_BUFFER</a> and 
    <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structures must be allocated
    from an NDIS buffer pool. A driver must not allocate and initialize a NET_BUFFER_LIST or NET_BUFFER
    structure from its private memory pool or the stack.</div>
<div> </div>
If you call 
    <b>NdisAllocateNetBufferList</b> and the NET_BUFFER_LIST structure pool was allocated by calling the 
    <a href="..\ndis\nf-ndis-ndisallocatenetbufferlistpool.md">
    NdisAllocateNetBufferListPool</a> function with the 
    <b>fAllocateNetBuffer</b> member of the 
    <a href="..\ndis\ns-ndis-_net_buffer_list_pool_parameters.md">NET_BUFFER_LIST_POOL_PARAMETERS</a> structure set to <b>TRUE</b>, NDIS allocates a
    NET_BUFFER_LIST, 
    <a href="..\ndis\ns-ndis-_net_buffer.md">NET_BUFFER</a>, MDL, and data.

Call the 
    <a href="..\ndis\nf-ndis-ndisfreenetbufferlist.md">NdisFreeNetBufferList</a> function to
    free a NET_BUFFER_LIST structure.




## -see-also

<a href="..\ndis\nf-ndis-ndisfreenetbufferlist.md">NdisFreeNetBufferList</a>



<a href="..\ndis\nf-ndis-ndisallocatenetbufferlistpool.md">
   NdisAllocateNetBufferListPool</a>



<a href="..\ndis\nf-ndis-ndisallocatenetbufferandnetbufferlist.md">
   NdisAllocateNetBufferAndNetBufferList</a>



<a href="..\ndis\ns-ndis-_net_buffer_list_pool_parameters.md">NET_BUFFER_LIST_POOL_PARAMETERS</a>



<a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a>



<a href="..\ndis\ns-ndis-_net_buffer.md">NET_BUFFER</a>



<a href="..\ndis\ns-ndis-_net_buffer_list_context.md">NET_BUFFER_LIST_CONTEXT</a>



 

 


