---
UID: NS:wmilib._WMILIB_CONTEXT
title: "_WMILIB_CONTEXT"
author: windows-driver-content
description: The WMILIB_CONTEXT structure provides registration information for a driver's data blocks and event blocks and defines entry points for the driver's WMI library callback routines.
old-location: kernel\wmilib_context.htm
old-project: kernel
ms.assetid: c9319f35-9745-47c4-a98d-4321e0d39f86
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: "*PWMILIB_CONTEXT, PWMILIB_CONTEXT, PWMILIB_CONTEXT structure pointer [Kernel-Mode Driver Architecture], WMILIB_CONTEXT, WMILIB_CONTEXT structure [Kernel-Mode Driver Architecture], _WMILIB_CONTEXT, kernel.wmilib_context, kstruct_d_b6452306-8092-4c47-aacf-c3ccd558d1f5.xml, wmilib/PWMILIB_CONTEXT, wmilib/WMILIB_CONTEXT"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wmilib.h
req.include-header: Wmilib.h
req.target-type: Windows
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
req.irql: PASSIVE_LEVEL (see Remarks section)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wmilib.h
api_name:
-	WMILIB_CONTEXT
product: Windows
targetos: Windows
req.typenames: WMILIB_CONTEXT, *PWMILIB_CONTEXT
req.product: Windows 10 or later.
---

# _WMILIB_CONTEXT structure


## -description


The <b>WMILIB_CONTEXT</b> structure provides registration information for a driver's data blocks and event blocks and defines entry points for the driver's WMI library callback routines. 


## -syntax


````
typedef struct _WMILIB_CONTEXT {
  ULONG                 GuidCount;
  PWMIGUIDREGINFO       GuidList;
  PWMI_QUERY_REGINFO    QueryWmiRegInfo;
  PWMI_QUERY_DATABLOCK  QueryWmiDataBlock;
  PWMI_SET_DATABLOCK    SetWmiDataBlock;
  PWMI_SET_DATAITEM     SetWmiDataItem;
  PWMI_EXECUTE_METHOD   ExecuteWmiMethod;
  PWMI_FUNCTION_CONTROL WmiFunctionControl;
} WMILIB_CONTEXT, *PWMILIB_CONTEXT;
````


## -struct-fields




### -field GuidCount

Specifies the number of blocks registered by the driver.


### -field GuidList

Pointer to an array of <b>GuidCount</b> <a href="..\wmilib\ns-wmilib-_wmiguidreginfo.md">WMIGUIDREGINFO</a> structures that contain registration information for each block.


### -field QueryWmiRegInfo

Pointer to the driver's <a href="..\wmilib\nc-wmilib-wmi_query_reginfo_callback.md">DpWmiQueryReginfo</a> routine, which is a required entry point for drivers that call WMI library support routines.


### -field QueryWmiDataBlock

Pointer to the driver's <a href="..\wmilib\nc-wmilib-wmi_query_datablock_callback.md">DpWmiQueryDataBlock</a> routine, which is a required entry point for drivers that call WMI library support routines.


### -field SetWmiDataBlock

Pointer to the driver's <a href="..\wmilib\nc-wmilib-wmi_set_datablock_callback.md">DpWmiSetDataBlock</a> routine, which is an optional entry point for drivers that call WMI library support routines. If the driver does not implement this routine, it must set this member to <b>NULL</b>. In this case, WMI returns STATUS_WMI_READ_ONLY to the caller in response to any <a href="https://msdn.microsoft.com/library/windows/hardware/ff550831">IRP_MN_CHANGE_SINGLE_INSTANCE</a> request.


### -field SetWmiDataItem

Pointer to the driver's <a href="..\wmilib\nc-wmilib-wmi_set_dataitem_callback.md">DpWmiSetDataItem</a> routine, which is an optional entry point for drivers that call WMI library support routines. If the driver does not implement this routine, it must set this member to <b>NULL</b>. In this case, WMI returns STATUS_WMI_READ_ONLY to the caller in response to any <a href="https://msdn.microsoft.com/library/windows/hardware/ff550836">IRP_MN_CHANGE_SINGLE_ITEM</a> request.


### -field ExecuteWmiMethod

Pointer to the driver's <a href="..\wmilib\nc-wmilib-wmi_execute_method_callback.md">DpWmiExecuteMethod</a> routine, which is an optional entry point for drivers that call WMI library support routines. If the driver does not implement this routine, it must set this member to <b>NULL</b>. In this case, WMI returns STATUS_INVALID_DEVICE_REQUEST to the caller in response to any <a href="https://msdn.microsoft.com/library/windows/hardware/ff550868">IRP_MN_EXECUTE_METHOD</a> request.


### -field WmiFunctionControl

Pointer to the driver's <a href="..\wmilib\nc-wmilib-wmi_function_control_callback.md">DpWmiFunctionControl</a> routine, which is an optional entry point for drivers that call WMI library support routines. If the driver does not implement this routine, it must set this member to <b>NULL</b>. In this case, WMI returns STATUS_SUCCESS to the caller in response to any <b>IRP_MN_ENABLE_<i>XXX</i></b> or <b>IRP_MN_DISABLE_<i>XXX</i></b> request.


## -remarks



A driver that handles WMI IRPs by calling WMI library support routines stores an initialized <b>WMILIB_CONTEXT</b> structure (or a pointer to such a structure) in its device extension. A driver can use the same <b>WMILIB_CONTEXT</b> structure for multiple device objects if each device object supplies the same set of data blocks. 

When the driver receives an <a href="https://msdn.microsoft.com/library/windows/hardware/ff550813">IRP_MJ_SYSTEM_CONTROL</a> request, it calls <a href="..\wmilib\nf-wmilib-wmisystemcontrol.md">WmiSystemControl</a> with a pointer to its <b>WMILIB_CONTEXT</b> structure, a pointer to its device object, and a pointer to the IRP. <b>WmiSystemControl</b> determines whether the IRP contains a WMI request and, if so, handles the request by calling the driver's appropriate <i>DpWmiXxx</i> routine.

Memory for this structure can be allocated from paged pool.




## -see-also

<a href="..\wmilib\nf-wmilib-wmisystemcontrol.md">WmiSystemControl</a>



<a href="..\wmilib\nc-wmilib-wmi_function_control_callback.md">DpWmiFunctionControl</a>



<a href="..\wmilib\nc-wmilib-wmi_execute_method_callback.md">DpWmiExecuteMethod</a>



<a href="..\wmilib\nc-wmilib-wmi_set_dataitem_callback.md">DpWmiSetDataItem</a>



<a href="..\wmilib\nc-wmilib-wmi_query_reginfo_callback.md">DpWmiQueryReginfo</a>



<a href="..\wmilib\ns-wmilib-_wmiguidreginfo.md">WMIGUIDREGINFO</a>



<a href="..\wmilib\nc-wmilib-wmi_set_datablock_callback.md">DpWmiSetDataBlock</a>



<a href="..\wmilib\nc-wmilib-wmi_query_datablock_callback.md">DpWmiQueryDataBlock</a>



 

 


