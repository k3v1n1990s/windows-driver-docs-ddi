---
UID: NI:gnssdriver.IOCTL_GNSS_GET_CHIPSETINFO
title: IOCTL_GNSS_GET_CHIPSETINFO
author: windows-driver-content
description: The IOCTL_GNSS_GET_CHIPSETINFO control code is used by the GNSS manufacturing test application to get information about the GNSS chipset.
old-location: gnss\ioctl_gnss_get_chipsetinfo.htm
old-project: gnss
ms.assetid: 9E57757B-65BA-40FF-98F9-F771C48EFF9E
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: IOCTL_GNSS_GET_CHIPSETINFO, IOCTL_GNSS_GET_CHIPSETINFO control code [Sensor Devices], gnss.ioctl_gnss_get_chipsetinfo, gnssdriver/IOCTL_GNSS_GET_CHIPSETINFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: gnssdriver.h
req.include-header: 
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
-	gnssdriver.h
api_name:
-	IOCTL_GNSS_GET_CHIPSETINFO
product: Windows
targetos: Windows
req.typenames: GNSS_SUPL_CERT_ACTION
---

# IOCTL_GNSS_GET_CHIPSETINFO IOCTL


## -description


The <b>IOCTL_GNSS_GET_CHIPSETINFO</b> 
   control code is used by the GNSS manufacturing test application to get information about the GNSS chipset. This information may be used by the test applications to decide which sets of tests should be executed, in which order, and map the response codes from the self tests into error conditions specific to the manufacturer or the chipset.


## -ioctlparameters




### -input-buffer

Set to NULL.


### -input-buffer-length

Set to 0.


### -output-buffer

A pointer to a <a href="..\gnssdriver\ns-gnssdriver-gnss_chipsetinfo.md">GNSS_CHIPSETINFO</a> structure.


### -output-buffer-length

Set to sizeof(GNSS_CHIPSETINFO).


### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

<b>Irp-&gt;IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> code. 


## -remarks



<h3><a id="GNSS_test_application_notes"></a><a id="gnss_test_application_notes"></a><a id="GNSS_TEST_APPLICATION_NOTES"></a>GNSS test application notes</h3>
The GNSS test application must wait for the response from the GNSS driver and be resilient to the GNSS driver not responding.

<h3><a id="GNSS_driver_notes"></a><a id="gnss_driver_notes"></a><a id="GNSS_DRIVER_NOTES"></a>GNSS driver notes</h3>
The GNSS driver must respond with the information about the GNSS chipset.




## -see-also

<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendioctlsynchronously.md">WdfIoTargetSendIoctlSynchronously</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542894">Creating IOCTL Requests in Drivers</a>



<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendinternalioctlotherssynchronously.md">WdfIoTargetSendInternalIoctlOthersSynchronously</a>



<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendinternalioctlsynchronously.md">WdfIoTargetSendInternalIoctlSynchronously</a>



 

 

