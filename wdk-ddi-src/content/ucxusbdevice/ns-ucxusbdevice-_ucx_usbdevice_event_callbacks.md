---
UID: NS:ucxusbdevice._UCX_USBDEVICE_EVENT_CALLBACKS
title: "_UCX_USBDEVICE_EVENT_CALLBACKS"
author: windows-driver-content
description: This structure provides a list of UCX USB device event callback functions.
old-location: buses\_ucx_usbdevice_event_callbacks.htm
old-project: usbref
ms.assetid: 7A320D48-E71C-40FE-A2EF-201CFCE55145
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PUCX_USBDEVICE_EVENT_CALLBACKS, P_UCX_USBDEVICE_EVENT_CALLBACKS, P_UCX_USBDEVICE_EVENT_CALLBACKS structure pointer [Buses], UCX_USBDEVICE_EVENT_CALLBACKS, UCX_USBDEVICE_EVENT_CALLBACKS structure [Buses], _UCX_USBDEVICE_EVENT_CALLBACKS, buses._ucx_usbdevice_event_callbacks, ucxusbdevice/P_UCX_USBDEVICE_EVENT_CALLBACKS, ucxusbdevice/_UCX_USBDEVICE_EVENT_CALLBACKS"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ucxusbdevice.h
req.include-header: Ucxclass.h
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ucxusbdevice.h
api_name:
-	UCX_USBDEVICE_EVENT_CALLBACKS
product: Windows
targetos: Windows
req.typenames: UCX_USBDEVICE_EVENT_CALLBACKS, *PUCX_USBDEVICE_EVENT_CALLBACKS
req.product: Windows 10 or later.
---

# _UCX_USBDEVICE_EVENT_CALLBACKS structure


## -description


This structure provides a list of UCX USB device event callback functions.


## -syntax


````
typedef struct _UCX_USBDEVICE_EVENT_CALLBACKS {
  ULONG                                  Size;
  PFN_UCX_USBDEVICE_ENDPOINTS_CONFIGURE  EvtUsbDeviceEndpointsConfigure;
  PFN_UCX_USBDEVICE_ENABLE               EvtUsbDeviceEnable;
  PFN_UCX_USBDEVICE_DISABLE              EvtUsbDeviceDisable;
  PFN_UCX_USBDEVICE_RESET                EvtUsbDeviceReset;
  PFN_UCX_USBDEVICE_ADDRESS              EvtUsbDeviceAddress;
  PFN_UCX_USBDEVICE_UPDATE               EvtUsbDeviceUpdate;
  PFN_UCX_USBDEVICE_HUB_INFO             EvtUsbDeviceHubInfo;
  PFN_UCX_USBDEVICE_DEFAULT_ENDPOINT_ADD EvtUsbDeviceDefaultEndpointAdd;
  PFN_UCX_USBDEVICE_ENDPOINT_ADD         EvtUsbDeviceEndpointAdd;
  PFN_UCX_USBDEVICE_SUSPEND              EvtUsbDeviceSuspend;
  PFN_UCX_USBDEVICE_RESUME               EvtUsbDeviceResume;
  PFN_UCX_USBDEVICE_GET_CHARACTERISTIC   EvtUsbDeviceGetCharacteristic;
} UCX_USBDEVICE_EVENT_CALLBACKS, *P_UCX_USBDEVICE_EVENT_CALLBACKS;
````


## -struct-fields




### -field Size

The size in bytes of this structure.


### -field EvtUsbDeviceEndpointsConfigure

A pointer to an <a href="..\ucxusbdevice\nc-ucxusbdevice-evt_ucx_usbdevice_endpoints_configure.md">EVT_UCX_USBDEVICE_ENDPOINTS_CONFIGURE</a> callback function.


### -field EvtUsbDeviceEnable

A pointer to an <a href="..\ucxusbdevice\nc-ucxusbdevice-evt_ucx_usbdevice_enable.md">EVT_UCX_USBDEVICE_ENABLE</a> callback function.


### -field EvtUsbDeviceDisable

A pointer to an <a href="..\ucxusbdevice\nc-ucxusbdevice-evt_ucx_usbdevice_disable.md">EVT_UCX_USBDEVICE_DISABLE</a> callback function.


### -field EvtUsbDeviceReset

A pointer to an <a href="..\ucxusbdevice\nc-ucxusbdevice-evt_ucx_usbdevice_reset.md">EVT_UCX_USBDEVICE_RESET</a> callback function.


### -field EvtUsbDeviceAddress

A pointer to an <a href="..\ucxusbdevice\nc-ucxusbdevice-evt_ucx_usbdevice_address.md">EVT_UCX_USBDEVICE_ADDRESS</a> callback function.


### -field EvtUsbDeviceUpdate

A pointer to an <a href="..\ucxusbdevice\nc-ucxusbdevice-evt_ucx_usbdevice_update.md">EVT_UCX_USBDEVICE_UPDATE</a> callback function.


### -field EvtUsbDeviceHubInfo

A pointer to an <a href="..\ucxusbdevice\nc-ucxusbdevice-evt_ucx_usbdevice_hub_info.md">EVT_UCX_USBDEVICE_HUB_INFO</a> callback function.


### -field EvtUsbDeviceDefaultEndpointAdd

A pointer to an <a href="..\ucxusbdevice\nc-ucxusbdevice-evt_ucx_usbdevice_default_endpoint_add.md">EVT_UCX_USBDEVICE_DEFAULT_ENDPOINT_ADD</a> callback function.


### -field EvtUsbDeviceEndpointAdd

A pointer to an <a href="..\ucxusbdevice\nc-ucxusbdevice-evt_ucx_usbdevice_endpoint_add.md">EVT_UCX_USBDEVICE_ENDPOINT_ADD</a> callback function.


### -field EvtUsbDeviceSuspend

A pointer to an <a href="..\ucxusbdevice\nc-ucxusbdevice-evt_ucx_usbdevice_suspend.md">EVT_UCX_USBDEVICE_SUSPEND</a> callback function.


### -field EvtUsbDeviceResume

A pointer to an <a href="..\ucxusbdevice\nc-ucxusbdevice-evt_ucx_usbdevice_resume.md">EVT_UCX_USBDEVICE_RESUME</a> callback function.


### -field EvtUsbDeviceGetCharacteristic

A pointer to an <a href="..\ucxusbdevice\nc-ucxusbdevice-evt_ucx_usbdevice_get_characteristic.md">EVT_UCX_USBDEVICE_GET_CHARACTERISTIC</a> callback function.


## -see-also

<a href="..\ucxusbdevice\nf-ucxusbdevice-ucxusbdeviceinitseteventcallbacks.md">UcxUsbDeviceInitSetEventCallbacks</a>



<a href="..\ucxusbdevice\nf-ucxusbdevice-ucx_usbdevice_event_callbacks_init.md">UCX_USBDEVICE_EVENT_CALLBACKS_INIT</a>



 

 


