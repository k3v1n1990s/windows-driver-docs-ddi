---
UID: NS:dbgeng._DEBUG_PROCESSOR_IDENTIFICATION_ALL
title: "_DEBUG_PROCESSOR_IDENTIFICATION_ALL"
author: windows-driver-content
description: This union contains relevant information for a processor the supported processors.
old-location: debugger\debug_processor_identification_all.htm
old-project: debugger
ms.assetid: 2C4C03BC-0D84-4151-B1A1-FE76F0355CD6
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*PDEBUG_PROCESSOR_IDENTIFICATION_ALL, DEBUG_PROCESSOR_IDENTIFICATION_ALL, DEBUG_PROCESSOR_IDENTIFICATION_ALL union [Windows Debugging], _DEBUG_PROCESSOR_IDENTIFICATION_ALL, dbgeng/DEBUG_PROCESSOR_IDENTIFICATION_ALL, debugger.debug_processor_identification_all"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: dbgeng.h
req.include-header: DbgEng.h
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
-	DbgEng.h
api_name:
-	DEBUG_PROCESSOR_IDENTIFICATION_ALL
product: Windows
targetos: Windows
req.typenames: DEBUG_PROCESSOR_IDENTIFICATION_ALL, *PDEBUG_PROCESSOR_IDENTIFICATION_ALL
---

# _DEBUG_PROCESSOR_IDENTIFICATION_ALL structure


## -description


This union contains relevant information for a processor the supported processors. 


## -syntax


````
typedef union _DEBUG_PROCESSOR_IDENTIFICATION_ALL {
  DEBUG_PROCESSOR_IDENTIFICATION_ALPHA Alpha;
  DEBUG_PROCESSOR_IDENTIFICATION_AMD64 Amd64;
  DEBUG_PROCESSOR_IDENTIFICATION_IA64  Ia64;
  DEBUG_PROCESSOR_IDENTIFICATION_X86   X86;
  DEBUG_PROCESSOR_IDENTIFICATION_ARM   Arm;
  DEBUG_PROCESSOR_IDENTIFICATION_ARM64 Arm64;
} DEBUG_PROCESSOR_IDENTIFICATION_ALL;
````


## -struct-fields




### -field Alpha

An Alpha processor as a <a href="..\dbgeng\ns-dbgeng-_debug_processor_identification_alpha.md">DEBUG_PROCESSOR_IDENTIFICATION_ALPHA</a> struct.


### -field Amd64

An AMD64 processor as a <a href="..\dbgeng\ns-dbgeng-_debug_processor_identification_amd64.md">DEBUG_PROCESSOR_IDENTIFICATION_AMD64</a> stuct. 


### -field Ia64

An Italium architecture processor as a <a href="..\dbgeng\ns-dbgeng-_debug_processor_identification_ia64.md">DEBUG_PROCESSOR_IDENTIFICATION_IA64</a> stuct.


### -field X86

An x86 processor as a <a href="..\dbgeng\ns-dbgeng-_debug_processor_identification_x86.md">DEBUG_PROCESSOR_IDENTIFICATION_X86</a> struct.


### -field Arm

An ARM processor as a <a href="..\dbgeng\ns-dbgeng-_debug_processor_identification_arm.md">DEBUG_PROCESSOR_IDENTIFICATION_ARM</a> struct.


### -field Arm64

An ARM64 processor as a <a href="..\dbgeng\ns-dbgeng-_debug_processor_identification_arm64.md">DEBUG_PROCESSOR_IDENTIFICATION_ARM64</a> struct. 


## -see-also

<a href="..\dbgeng\ns-dbgeng-_debug_processor_identification_alpha.md">DEBUG_PROCESSOR_IDENTIFICATION_ALPHA</a>



<a href="..\dbgeng\ns-dbgeng-_debug_processor_identification_arm64.md">DEBUG_PROCESSOR_IDENTIFICATION_ARM64</a>



<a href="..\dbgeng\ns-dbgeng-_debug_processor_identification_ia64.md">DEBUG_PROCESSOR_IDENTIFICATION_IA64</a>



<a href="..\dbgeng\ns-dbgeng-_debug_processor_identification_amd64.md">DEBUG_PROCESSOR_IDENTIFICATION_AMD64</a>



<a href="..\dbgeng\ns-dbgeng-_debug_processor_identification_arm.md">DEBUG_PROCESSOR_IDENTIFICATION_ARM</a>



<a href="..\dbgeng\ns-dbgeng-_debug_processor_identification_x86.md">DEBUG_PROCESSOR_IDENTIFICATION_X86</a>



 

 


