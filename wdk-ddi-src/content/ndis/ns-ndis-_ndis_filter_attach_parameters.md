---
UID: NS:ndis._NDIS_FILTER_ATTACH_PARAMETERS
title: _NDIS_FILTER_ATTACH_PARAMETERS
author: windows-driver-content
description: The NDIS_FILTER_ATTACH_PARAMETERS structure defines the initialization parameters for the filter module.
old-location: netvista\ndis_filter_attach_parameters.htm
old-project: netvista
ms.assetid: d46a1e62-9d03-4ab9-86f6-81b06c04d0f6
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: _NDIS_FILTER_ATTACH_PARAMETERS, *PNDIS_FILTER_ATTACH_PARAMETERS, NDIS_FILTER_ATTACH_PARAMETERS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NDIS_FILTER_ATTACH_PARAMETERS
req.alt-loc: ndis.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: See Remarks section
req.typenames: *PNDIS_FILTER_ATTACH_PARAMETERS, NDIS_FILTER_ATTACH_PARAMETERS
---

# _NDIS_FILTER_ATTACH_PARAMETERS structure



## -description
The <b>NDIS_FILTER_ATTACH_PARAMETERS</b> structure defines the initialization parameters for the filter
  module.



## -syntax

````
typedef struct _NDIS_FILTER_ATTACH_PARAMETERS {
  NDIS_OBJECT_HEADER                Header;
  NET_IFINDEX                       IfIndex;
  NET_LUID                          NetLuid;
  PNDIS_STRING                      FilterModuleGuidName;
  NET_IFINDEX                       BaseMiniportIfIndex;
  PNDIS_STRING                      BaseMiniportInstanceName;
  PNDIS_STRING                      BaseMiniportName;
  NDIS_MEDIA_CONNECT_STATE          MediaConnectState;
  NET_IF_MEDIA_DUPLEX_STATE         MediaDuplexState;
  ULONG64                           XmitLinkSpeed;
  ULONG64                           RcvLinkSpeed;
  NDIS_MEDIUM                       MiniportMediaType;
  NDIS_PHYSICAL_MEDIUM              MiniportPhysicalMediaType;
  NDIS_HANDLE                       MiniportMediaSpecificAttributes;
  PNDIS_OFFLOAD                     DefaultOffloadConfiguration;
  USHORT                            MacAddressLength;
  UCHAR                             CurrentMacAddress[NDIS_MAX_PHYS_ADDRESS_LENGTH];
  NET_LUID                          BaseMiniportNetLuid;
  NET_IFINDEX                       LowerIfIndex;
  NET_LUID                          LowerIfNetLuid;
  ULONG                             Flags;
#if (NDIS_SUPPORT_NDIS61)
  PNDIS_HD_SPLIT_CURRENT_CONFIG     HDSplitCurrentConfig;
#endif 
#if (NDIS_SUPPORT_NDIS620)
  PNDIS_RECEIVE_FILTER_CAPABILITIES ReceiveFilterCapabilities;
  PDEVICE_OBJECT                    MiniportPhysicalDeviceObject;
  PNDIS_NIC_SWITCH_CAPABILITIES     NicSwitchCapabilities;
#endif 
#if (NDIS_SUPPORT_NDIS630)
  BOOLEAN                           BaseMiniportIfConnectorPresent;
  PNDIS_SRIOV_CAPABILITIES          SriovCapabilities;
  PNDIS_NIC_SWITCH_INFO_ARRAY       NicSwitchArray;
#endif 
} NDIS_FILTER_ATTACH_PARAMETERS, *PNDIS_FILTER_ATTACH_PARAMETERS;
````


## -struct-fields

### -field Header

The 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure for the
     <b>NDIS_FILTER_ATTACH_PARAMETERS</b> structure. NDIS sets the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to NDIS_OBJECT_TYPE_FILTER_ATTACH_PARAMETERS.
     

To indicate the version of the <b>NDIS_FILTER_ATTACH_PARAMETERS</b> structure, NDIS sets the 
     <b>Revision</b> member to one of the following values:




### -field NDIS_FILTER_ATTACH__PARAMETERS_REVISION_4

Added various members for NDIS 6.30.

NDIS sets the 
        <b>Size</b> member to NDIS_SIZEOF_FILTER_ATTACH_PARAMETERS_REVISION_4.


### -field NDIS_FILTER_ATTACH_PARAMETERS_REVISION_3

Added the 
        <b>ReceiveFilterCapabilities</b>, 
        <b>MiniportPhysicalDeviceObject</b>, and 
        <b>NicSwitchCapabilities</b> members for NDIS 6.20.

NDIS sets the 
        <b>Size</b> member to NDIS_SIZEOF_FILTER_ATTACH_PARAMETERS_REVISION_3.


### -field NDIS_FILTER_ATTACH_PARAMETERS_REVISION_2

Added the 
        <b>HDSplitCurrentConfig</b> member for NDIS 6.1.

NDIS sets the 
        <b>Size</b> member to NDIS_SIZEOF_FILTER_ATTACH_PARAMETERS_REVISION_2.


### -field NDIS_FILTER_ATTACH_PARAMETERS_REVISION_1

Original version for NDIS 6.0.

NDIS sets the 
        <b>Size</b> member to NDIS_SIZEOF_FILTER_ATTACH_PARAMETERS_REVISION_1.

</dd>
</dl>

### -field IfIndex

The NDIS interface index of the filter module that NDIS is attaching to the driver stack.


### -field NetLuid

The NDIS network interface 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff568747">NET_LUID</a> value for the filter module that NDIS is
     attaching to the driver stack. The NET_LUID is equivalent to the interface name (<i>ifName</i> in RFC 2863
     <i>)</i>.


### -field FilterModuleGuidName

The GUID name of the filter module that NDIS is attaching.


### -field BaseMiniportIfIndex

The NDIS network interface index of the base miniport adapter. That is, if there are virtual
     miniports or filter modules that are installed over a physical miniport adapter, the value of this
     member is the interface index of the physical miniport adapter or a virtual miniport of the highest-level MUX intermediate driver.


### -field BaseMiniportInstanceName

A pointer to an NDIS_STRING type value that contains a counted Unicode string. This string
     specifies the friendly name of the interface for the base miniport adapter. For Windows 2000 and later
     versions, NDIS defines the NDIS_STRING type as a 
     <a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a> type.


### -field BaseMiniportName

The name of the base miniport adapter.


### -field MediaConnectState

The 
     <a href="https://msdn.microsoft.com/5af5e050-4b2b-45a9-8549-3a3818d7b06f">
     NET_IF_MEDIA_CONNECT_STATE</a> connection state type.


### -field MediaDuplexState

The media duplex state for the underlying miniport adapter. For more information, see 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff569606">OID_GEN_MEDIA_DUPLEX_STATE</a>.


### -field XmitLinkSpeed

The current transmit link speed of the underlying miniport adapter in bits per second. For more
     information, see 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff569594">OID_GEN_LINK_SPEED_EX</a>.


### -field RcvLinkSpeed

The current receive link speed of the underlying miniport adapter in bits per second. For more
     information, see 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff569594">OID_GEN_LINK_SPEED_EX</a>.


### -field MiniportMediaType

The 
     <b>NdisMedium</b><i>Xxx</i> type that the base underlying miniport adapter supports. For more
     information, see 
     <a href="..\ntddndis\ne-ntddndis-_ndis_medium.md">NDIS_MEDIUM</a>.


### -field MiniportPhysicalMediaType

The physical medium type for the base underlying miniport adapter. For more information, see 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff569621">OID_GEN_PHYSICAL_MEDIUM</a>.


### -field MiniportMediaSpecificAttributes

A pointer to an 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure that
     identifies a structure that contains miniport media-specific attributes, or <b>NULL</b> if there are no such
     attributes. The 
     <b>Type</b> member of the NDIS_OBJECT_HEADER structure identifies the type of the
     attributes structure. For example, if the underlying miniport adapter's media type is 
     <b>NdisMediumNative802_11</b>, then the 
     <b>Type</b> member should be
     NDIS_OBJECT_TYPE_MINIPORT_ADAPTER_NATIVE_802_11_ATTRIBUTES, and the 
     <b>MiniportMediaSpecificAttributes</b> member points to an 
     <a href="..\ndis\ns-ndis-_ndis_miniport_adapter_native_802_11_attributes.md">
     NDIS_MINIPORT_ADAPTER_NATIVE_802_11_ATTRIBUTES</a> structure.


### -field DefaultOffloadConfiguration

A pointer to an 
     <a href="..\ntddndis\ns-ntddndis-_ndis_offload.md">NDIS_OFFLOAD</a> structure which defines task
     offload attributes. The filter driver should review these attributes to obtain the task offload
     capabilities of the underlying drivers. The filter driver should modify these attributes, if necessary,
     to reflect any changes in the task offload support that it requires.


### -field MacAddressLength

The MAC address length, in bytes. The MAC address length is specific to the type of media.


### -field CurrentMacAddress

The current MAC address. For example, the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff569069">OID_802_3_CURRENT_ADDRESS</a> OID
     specifies the current MAC address for IEEE 802.3 drivers.


### -field BaseMiniportNetLuid

The NDIS network interface 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff568747">NET_LUID</a> of the base miniport adapter. That is, if
     there are virtual miniports or filter modules that are installed over a physical miniport adapter, the
     value of this member is the NET_LUID of the physical miniport adapter or a virtual miniport of the
     highest-level MUX intermediate driver.


### -field LowerIfIndex

The NDIS network interface index of the interface just below the current filter module. That is,
     if there are filter modules or NDIS 5.
     <i>x</i> filter intermediate drivers that are installed over a physical miniport
     adapter or the highest-level MUX intermediate driver, this member contains the interface index of the
     filter module interface or filter intermediate driver interface that is just below the current filter
     module. If there are no filter module or filter intermediate driver interfaces installed over the
     physical miniport adapter or the highest-level MUX intermediate driver, this member contains the
     interface index of the underlying physical miniport adapter or the highest-level MUX intermediate driver
     virtual miniport.


### -field LowerIfNetLuid

The NDIS network interface NET_LUID value of the interface just below the current filter module.
     That is, if there are filter modules or NDIS 5.
     <i>x</i> filter intermediate drivers that are installed over a physical miniport
     adapter or the highest-level MUX intermediate driver, this member contains the network interface
     NET_LUID of the filter module interface or filter intermediate driver interface that is just below the
     current filter module. If there are no filter module or filter intermediate driver interfaces installed
     over the physical miniport adapter or the highest-level MUX intermediate driver, this member contains
     the network interface NET_LUID of the underlying physical miniport adapter or the highest-level MUX
     intermediate driver virtual miniport.


### -field Flags

Reserved for future use.


### -field HDSplitCurrentConfig

A pointer to an 
     <a href="..\ntddndis\ns-ntddndis-_ndis_hd_split_current_config.md">
     NDIS_HD_SPLIT_CURRENT_CONFIG</a> structure. This structure specifies the current header-data split
     configuration of the underlying miniport adapter. This value can be <b>NULL</b> if the miniport adapter does
     not support header-data split.


### -field ReceiveFilterCapabilities

A pointer to an 
     <a href="..\ntddndis\ns-ntddndis-_ndis_receive_filter_capabilities.md">
     NDIS_RECEIVE_FILTER_CAPABILITIES</a> structure. This structure specifies the generic filtering
     capabilities that are currently enabled on the underlying miniport adapter. This value can be <b>NULL</b> if the miniport adapter does not
     support receive filtering.


### -field MiniportPhysicalDeviceObject

A pointer to a 
     <a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a> structure. This structure
     represents the physical device for the underlying miniport adapter.


### -field NicSwitchCapabilities

A pointer to an 
     <a href="..\ntddndis\ns-ntddndis-_ndis_nic_switch_capabilities.md">
     NDIS_NIC_SWITCH_CAPABILITIES</a> structure. This structure specifies the NIC switch capabilities of
     the underlying miniport adapter. This value can be <b>NULL</b> if the miniport adapter does not support NIC
     switch features.


### -field BaseMiniportIfConnectorPresent

A Boolean value that, if set to TRUE, indicates whether a network interface (if) connector is present on the underlying network adapter. This value should be set to TRUE for a physical adapter.


### -field SriovCapabilities

A pointer to an <a href="..\ntddndis\ns-ntddndis-_ndis_sriov_capabilities.md">NDIS_SRIOV_CAPABILITIES</a> structure. This structure specifies the single root I/O virtualization (SR-IOV) capabilities that are currently enabled on the underlying miniport adapter. This value can be <b>NULL</b> if the miniport adapter does not support SR-IOV features.

For more information, see <a href="https://msdn.microsoft.com/E64DD4F0-D5F8-4FFF-931B-C04C5C42D000">Single Root I/O Virtualization (SR-IOV)</a>.


### -field NicSwitchArray

A pointer to an <a href="..\ntddndis\ns-ntddndis-_ndis_nic_switch_info_array.md">NDIS_NIC_SWITCH_INFO_ARRAY</a> structure.  This array enumerates the NIC switches that have been created on the miniport adapter. NIC switches can be created only if SR-IOV is supported and enabled on the adapter. 

<div class="alert"><b>Note</b>  Starting with Windows Server 2012, Windows supports only the default NIC switch that is created on the physical function (PF) miniport adapter. Therefore, this array can contain only one element. </div>
<div> </div>

## -remarks
To define filter module attach parameters, NDIS passes a pointer to an NDIS_FILTER_ATTACH_PARAMETERS
    structure to the 
    <a href="..\ndis\nc-ndis-filter_attach.md">FilterAttach</a> function.

Filter drivers should avoid issuing unnecessary OID queries. Instead, use the information in
    NDIS_FILTER_ATTACH_PARAMETERS, when available, to obtain information about underlying drivers.


## -see-also
<dl>
<dt>
<a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-filter_attach.md">FilterAttach</a>
</dt>
<dt>
<a href="..\ntddndis\ns-ntddndis-_ndis_hd_split_current_config.md">NDIS_HD_SPLIT_CURRENT_CONFIG</a>
</dt>
<dt>
<a href="..\ntddndis\ne-ntddndis-_ndis_medium.md">NDIS_MEDIUM</a>
</dt>
<dt>
<a href="..\ndis\ns-ndis-_ndis_miniport_adapter_native_802_11_attributes.md">
   NDIS_MINIPORT_ADAPTER_NATIVE_802_11_ATTRIBUTES</a>
</dt>
<dt>
<a href="..\ntddndis\ns-ntddndis-_ndis_nic_switch_capabilities.md">NDIS_NIC_SWITCH_CAPABILITIES</a>
</dt>
<dt>
<a href="..\ntddndis\ns-ntddndis-_ndis_nic_switch_info_array.md">NDIS_NIC_SWITCH_INFO_ARRAY</a>
</dt>
<dt>
<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>
</dt>
<dt>
<a href="..\ntddndis\ns-ntddndis-_ndis_offload.md">NDIS_OFFLOAD</a>
</dt>
<dt>
<a href="..\ntddndis\ns-ntddndis-_ndis_receive_filter_capabilities.md">
   NDIS_RECEIVE_FILTER_CAPABILITIES</a>
</dt>
<dt>
<a href="..\ntddndis\ns-ntddndis-_ndis_sriov_capabilities.md">NDIS_SRIOV_CAPABILITIES</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff568744">NET_IF_MEDIA_CONNECT_STATE</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff568747">NET_LUID</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff569069">OID_802_3_CURRENT_ADDRESS</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff569594">OID_GEN_LINK_SPEED_EX</a>
</dt>
<dt>
<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-gen-media-connect-status-ex">OID_GEN_MEDIA_CONNECT_STATUS_EX</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff569606">OID_GEN_MEDIA_DUPLEX_STATE</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff569621">OID_GEN_PHYSICAL_MEDIUM</a>
</dt>
<dt>
<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_FILTER_ATTACH_PARAMETERS structure%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
