---
UID: NS:pmi._PMI_CONFIGURATION
title: "_PMI_CONFIGURATION"
author: windows-driver-content
description: The PMI_CONFIGURATION structure contains information about the current power metering and budgeting configuration of a power meter.
old-location: powermeter\pmi_configuration.htm
old-project: powermeter
ms.assetid: 976b812e-deb2-445f-b69d-e00d10c6e5d8
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: "*PPMI_CONFIGURATION, PMI_CONFIGURATION, PMI_CONFIGURATION structure [Power Metering and Budgeting Devices], PPMI_CONFIGURATION, PPMI_CONFIGURATION structure pointer [Power Metering and Budgeting Devices], PowerMeterRef_f3279ebc-cd57-40e8-8571-a7d0d6bf3edc.xml, _PMI_CONFIGURATION, pmi/PMI_CONFIGURATION, pmi/PPMI_CONFIGURATION, powermeter.pmi_configuration"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: pmi.h
req.include-header: Pmi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7, Windows Server 2008 R2, and later versions of the Windows operating systems.
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
-	pmi.h
api_name:
-	PMI_CONFIGURATION
product: Windows
targetos: Windows
req.typenames: PMI_CONFIGURATION, *PPMI_CONFIGURATION
---

# _PMI_CONFIGURATION structure


## -description


The PMI_CONFIGURATION structure contains information about the current power metering and budgeting configuration of a power meter.


## -syntax


````
typedef struct _PMI_CONFIGURATION {
  ULONG                  Version;
  USHORT                 Size;
  PMI_CONFIGURATION_TYPE ConfigurationType;
  union {
    PMI_MEASUREMENT_CONFIGURATION MeasurementConfiguration;
    PMI_BUDGETING_CONFIGURATION   BudgetingConfiguration;
    PMI_THRESHOLD_CONFIGURATION   ThresholdConfiguration;
  } Configuration;
} PMI_CONFIGURATION, *PPMI_CONFIGURATION;
````


## -struct-fields




### -field Version

A value that specifies the version of this structure. For Windows 7, Windows Server 2008 R2, and later versions of Windows, this value must be 1.


### -field Size

A value, in units of bytes, that specifies the size of the structure.


### -field ConfigurationType

A <a href="..\pmi\ne-pmi-pmi_configuration_type.md">PMI_CONFIGURATION_TYPE</a> enumeration value that specifies the data type of the <b>Configuration</b> member.


### -field Configuration

A union of the supported Power Meter Interface (PMI) configuration structures. Based on the value of the <b>ConfigurationType</b> member, one of the following <b>Configuration</b> submembers is used to reference the following PMI configuration structures:



#### MeasurementConfiguration

A <a href="..\pmi\ns-pmi-_pmi_budgeting_configuration.md">PMI_BUDGETING_CONFIGURATION</a> structure that contains information about the budgeting configuration of the power meter.

The <b>Configuration</b> member contains this structure if the <b>ConfigurationType</b> member is set to <b>PmiBudgetingConfiguration</b>.



#### BudgetingConfiguration

A <a href="..\pmi\ns-pmi-_pmi_measurement_configuration.md">PMI_MEASUREMENT_CONFIGURATION</a> structure that contains information about the measurement configuration of the power meter.

The <b>Configuration</b> member contains this structure if the <b>ConfigurationType</b> member is set to <b>PmiMeasurementConfiguration</b>.



#### ThresholdConfiguration

A <a href="..\pmi\ns-pmi-_pmi_threshold_configuration.md">PMI_THRESHOLD_CONFIGURATION</a> structure that contains information about the threshold configuration of the power meter.

The <b>Configuration</b> member contains this structure if the <b>ConfigurationType</b> member is set to <b>PmiThresoldConfiguration</b>.


## -remarks



The PMI_CONFIGURATION structure is used to query many different PMI configuration settings that are supported by a power meter. 

The PMI configuration information is returned through an <a href="..\pmi\ni-pmi-ioctl_pmi_get_configuration.md">IOCTL_PMI_GET_CONFIGURATION</a> I/O control (IOCTL) query request. The input data of this query request is set to a <a href="..\pmi\ne-pmi-pmi_configuration_type.md">PMI_CONFIGURATION_TYPE</a> enumerator value that specifies the type of PMI configuration data to return.

If the IOCTL query request completes successfully, the request returns a PMI_CONFIGURATION structure. The <b>Configuration</b> member of this structure contains data that is formatted as the requested PMI configuration structure.

For example, if an IOCTL query request of <a href="..\pmi\ni-pmi-ioctl_pmi_get_configuration.md">IOCTL_PMI_GET_CONFIGURATION</a> is made with the input data set to <b>PmiBudgetingConfiguration</b> and the request completes successfully, the request returns a PMI_CONFIGURATION structure with its members set to the following values:

<ul>
<li>
The <b>ConfigurationType</b> member is set to <b>PmiBudgetingConfiguration</b>.

</li>
<li>
The <b>Configuration</b> member contains data that is  formatted as a <a href="..\pmi\ns-pmi-_pmi_budgeting_configuration.md">PMI_BUDGETING_CONFIGURATION</a> structure.

</li>
</ul>



## -see-also

<a href="..\pmi\ne-pmi-pmi_configuration_type.md">PMI_CONFIGURATION_TYPE</a>



<a href="..\pmi\ns-pmi-_pmi_budgeting_configuration.md">PMI_BUDGETING_CONFIGURATION</a>



<a href="..\pmi\ns-pmi-_pmi_threshold_configuration.md">PMI_THRESHOLD_CONFIGURATION</a>



<a href="..\pmi\ni-pmi-ioctl_pmi_get_configuration.md">IOCTL_PMI_GET_CONFIGURATION</a>



<a href="..\pmi\ns-pmi-_pmi_measurement_configuration.md">PMI_MEASUREMENT_CONFIGURATION</a>



 

 


