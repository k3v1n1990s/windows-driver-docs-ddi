---
UID: NS:d3dukmdt.D3DDDI_RESERVEGPUVIRTUALADDRESS
title: D3DDDI_RESERVEGPUVIRTUALADDRESS
author: windows-driver-content
description: D3DDDI_RESERVEGPUVIRTUALADDRESS is used with pfnReserveGpuVirtualAddressCb to reserve an address range in the graphics processing unit (GPU) virtual address space of the current process.
old-location: display\d3dddi_reservegpuvirtualaddress.htm
old-project: display
ms.assetid: 89E8FCC6-B618-4D7E-B1E6-59E85261BE3C
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3DDDI_RESERVEGPUVIRTUALADDRESS, D3DDDI_RESERVEGPUVIRTUALADDRESS structure [Display Devices], d3dukmdt/D3DDDI_RESERVEGPUVIRTUALADDRESS, display.d3dddi_reservegpuvirtualaddress
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dukmdt.h
req.include-header: D3dumddi.h, D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
-	HeaderDef
api_location:
-	d3dukmdt.h
api_name:
-	D3DDDI_RESERVEGPUVIRTUALADDRESS
product: Windows
targetos: Windows
req.typenames: D3DDDI_RESERVEGPUVIRTUALADDRESS
---

# D3DDDI_RESERVEGPUVIRTUALADDRESS structure


## -description


<b>D3DDDI_RESERVEGPUVIRTUALADDRESS</b> is used with <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_reservegpuvirtualaddresscb.md">pfnReserveGpuVirtualAddressCb</a> to reserve an address range in the graphics processing unit (GPU) virtual address space of the current process.


## -syntax


````
typedef struct D3DDDI_RESERVEGPUVIRTUALADDRESS {
  union {
    D3DKMT_HANDLE hPagingQueue;
    D3DKMT_HANDLE hAdapter;
  };
  D3DGPU_VIRTUAL_ADDRESS BaseAddress;
  D3DGPU_VIRTUAL_ADDRESS MinimumAddress;
  D3DGPU_VIRTUAL_ADDRESS MaximumAddress;
  D3DGPU_SIZE_T          Size;
  union {
    D3DDDIGPUVIRTUALADDRESS_RESERVATION_TYPE ReservationType;
    UINT                                     Reserved0;
  };
  union {
    UINT64 DriverProtection;
    UINT64 Reserved1;
  };
  D3DGPU_VIRTUAL_ADDRESS VirtualAddress;
  union {
    UINT64 PagingFenceValue;
    UINT64 Reserved2;
  };
} D3DDDI_RESERVEGPUVIRTUALADDRESS;
````


## -struct-fields




### -field BaseAddress

(Optional) If <b>non-NULL</b>, the video memory manager will attempt to use this address as the base address for the reserved range. If the range from <b>BaseAddress</b> to <b>BaseAddress</b>+<b>Size</b> isn’t free, the call will fail. When this parameter is <b>non-NULL</b>, <b>MinimumAddress</b> and <b>MaximumAddress</b> are ignored.

<b>BaseAddress</b> is in bytes and must be aligned to 64KB boundary.


If <b>NULL</b> is specified the video memory manager will pick the base address for the allocation within the specified <b>MinimumAddress</b> and <b>MaximumAddress</b>.



### -field MinimumAddress

(Optional) Specifies the minimum GPU virtual address to consider for the reserved range.

<b>MinimumAddress</b> is in bytes and must be aligned to 64KB boundary.

This parameter is ignored when <b>BaseAddress</b> != <b>NULL</b>.


### -field MaximumAddress

(Optional) Specifies the maximum GPU virtual address to consider for the reserved range. the video memory manager will guarantee that <b>BaseAddress</b>+<b>Size</b> &lt;= <b>MaximumAddress</b>. If this is set to NULL the video memory manager will not apply any limit.

<b>MaximumAddress</b> is in bytes and must be aligned to 64KB boundary.

This parameter is ignored when <b>BaseAddress</b> != <b>NULL</b>.


### -field Size

Specify the size of the range to reserve in bytes. Must be a multiple of 64KB.


### -field VirtualAddress

[out] The reserved virtual address.


#### - DriverProtection

Specifies the driver-specific protection


#### - PagingFenceValue

Paging fence identifier for synchronization


#### - ReservationType

Specifies the virtual address reservation type.


#### - Reserved0

This member is reserved and should be set to zero.


#### - Reserved1

This member is reserved and should be set to zero.


#### - Reserved2

This member is reserved and should be set to zero.


#### - hAdapter

DirectX graphics adapter handle. 


#### - hPagingQueue

Paging queue to synchronize the operation on.


## -see-also

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_reservegpuvirtualaddresscb.md">pfnReserveGpuVirtualAddressCb</a>



 

 


