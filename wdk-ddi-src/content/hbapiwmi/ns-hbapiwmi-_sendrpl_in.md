---
UID: NS:hbapiwmi._SendRPL_IN
title: "_SendRPL_IN"
author: windows-driver-content
description: The SendRPL_IN structure is used to deliver input parameter data to the SendRPL WMI method.
old-location: storage\sendrpl_in.htm
old-project: storage
ms.assetid: 0c084258-2bd6-47a8-a060-d4ba2734ebed
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PSendRPL_IN, PSendRPL_IN, PSendRPL_IN structure pointer [Storage Devices], SendRPL_IN, SendRPL_IN structure [Storage Devices], _SendRPL_IN, hbapiwmi/PSendRPL_IN, hbapiwmi/SendRPL_IN, storage.sendrpl_in, structs-Fibre_3babb7ed-9d87-4154-b038-8e503750eed4.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: hbapiwmi.h
req.include-header: Hbapiwmi.h
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
-	hbapiwmi.h
api_name:
-	SendRPL_IN
product: Windows
targetos: Windows
req.typenames: SendRPL_IN, *PSendRPL_IN
---

# _SendRPL_IN structure


## -description


The SendRPL_IN structure is used to deliver input parameter data to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff565488">SendRPL</a> WMI method.


## -syntax


````
typedef struct _SendRPL_IN {
  UCHAR PortWWN[8];
  UCHAR AgentWWN[8];
  ULONG agent_domain;
  ULONG portIndex;
} SendRPL_IN, *PSendRPL_IN;
````


## -struct-fields




### -field PortWWN

Contains a worldwide name for the local port through which the read port list (RPL) command is sent. 


### -field AgentWWN

Contains a worldwide name for the port that is to be queried for a list of ports of type FC_Port. For a definition of FC_Port, see the T11 committee's specification for <i>Fibre Channel HBA API</i>. 


### -field agent_domain

Contains the domain number for the domain controller that is to be queried for a list of ports of type FC_Port. For a definition of FC_Port, see the T11 committee's specification for <i>Fibre Channel HBA API</i>. 


### -field portIndex

Contains the port index of the first port in the list of ports of type FC_Port to be returned. 


## -remarks



The WMI tool suite generates a declaration of the SendRPL_IN structure in <i>Hbapiwmi.h </i>when it compiles the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562506">MSFC_HBAAdapterMethods WMI Class</a>.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff565488">SendRPL</a>



 

 


