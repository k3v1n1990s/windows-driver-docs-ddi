---
UID: NF:fltkernel.FltSetIoPriorityHintIntoFileObject
title: FltSetIoPriorityHintIntoFileObject function
author: windows-driver-content
description: The FltSetIoPriorityHintIntoFileObject routine is used by a minifilter driver to set the I/O priority information in a file object.
old-location: ifsk\fltsetiopriorityhintintofileobject.htm
old-project: ifsk
ms.assetid: 95a56ca3-e223-49ec-9151-bedb3f3597c3
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: FltApiRef_p_to_z_981cae2b-b29c-4890-a462-163031a668d3.xml, FltSetIoPriorityHintIntoFileObject, FltSetIoPriorityHintIntoFileObject routine [Installable File System Drivers], fltkernel/FltSetIoPriorityHintIntoFileObject, ifsk.fltsetiopriorityhintintofileobject
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fltkernel.h
req.include-header: FltKernel.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows Vista.
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
req.lib: FltMgr.lib
req.dll: Fltmgr.sys
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	fltmgr.sys
api_name:
-	FltSetIoPriorityHintIntoFileObject
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltSetIoPriorityHintIntoFileObject function


## -description


The <b>FltSetIoPriorityHintIntoFileObject</b> routine is used by a minifilter driver to set the I/O priority information in a file object.


## -syntax


````
NTSTATUS FltSetIoPriorityHintIntoFileObject(
  _In_ PFILE_OBJECT     FileObject,
  _In_ IO_PRIORITY_HINT PriorityHint
);
````


## -parameters




### -param FileObject [in]

A pointer to the file object to modify. This parameter is required and cannot be <b>NULL</b>. 


### -param PriorityHint [in]

The <a href="..\wdm\ne-wdm-_io_priority_hint.md">IO_PRIORITY_HINT</a> enumeration value to set for the file object pointed to by <i>FileObject</i>.


## -returns



If the I/O priority value passed in the <i>PriorityHint</i> parameter is successfully applied to the <i>FileObject</i> structure, <b>FltSetIoPriorityHintIntoFileObject</b> returns STATUS_SUCCESS. Otherwise, it returns an appropriate NTSTATUS value, such as one of the following:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER </b></dt>
</dl>
</td>
<td width="60%">
The value of the <i>PriorityHint</i> parameter is invalid. This is an error code. 

</td>
</tr>
</table>
 




## -remarks



This routine is NONPAGED and can be called from paging I/O paths.




## -see-also

<a href="..\fltkernel\nf-fltkernel-fltretrieveiopriorityinfo.md">FltRetrieveIoPriorityInfo</a>



<a href="..\fltkernel\nf-fltkernel-fltgetiopriorityhint.md">FltGetIoPriorityHint</a>



<a href="..\fltkernel\nf-fltkernel-fltapplypriorityinfothread.md">FltApplyPriorityInfoThread</a>



<a href="..\fltkernel\nf-fltkernel-fltgetiopriorityhintfromcallbackdata.md">FltGetIoPriorityHintFromCallbackData</a>



<a href="..\fltkernel\ns-fltkernel-_flt_callback_data.md">FLT_CALLBACK_DATA</a>



<a href="..\fltkernel\nf-fltkernel-fltgetiopriorityhintfromthread.md">FltGetIoPriorityHintFromThread</a>



<a href="..\fltkernel\nf-fltkernel-fltsetiopriorityhintintocallbackdata.md">FltSetIoPriorityHintIntoCallbackData</a>



<a href="..\fltkernel\nf-fltkernel-fltsetiopriorityhintintothread.md">FltSetIoPriorityHintIntoThread</a>



<a href="..\wdm\ne-wdm-_io_priority_hint.md">IO_PRIORITY_HINT</a>



<a href="..\fltkernel\nf-fltkernel-fltgetiopriorityhintfromfileobject.md">FltGetIoPriorityHintFromFileObject</a>



 

 


