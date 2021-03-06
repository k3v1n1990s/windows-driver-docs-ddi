---
UID: NF:printerextension.IPrinterQueue2.SendBidiSetRequestAsync
title: IPrinterQueue2::SendBidiSetRequestAsync method
author: windows-driver-content
description: Uses an XML string value to send a Bidi Set request as an asynchronous operation.
old-location: print\iprinterqueue2_sendbidisetrequestasync.htm
old-project: print
ms.assetid: 05FF8A47-A586-4DA7-94AD-A7186265ADB4
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IPrinterQueue2, IPrinterQueue2 interface [Print Devices], SendBidiSetRequestAsync method, IPrinterQueue2::SendBidiSetRequestAsync, SendBidiSetRequestAsync method [Print Devices], SendBidiSetRequestAsync method [Print Devices], IPrinterQueue2 interface, SendBidiSetRequestAsync,IPrinterQueue2.SendBidiSetRequestAsync, print.iprinterqueue2_sendbidisetrequestasync, printerextension/IPrinterQueue2::SendBidiSetRequestAsync
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: printerextension.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
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
-	COM
api_location:
-	Printerextension.h
api_name:
-	IPrinterQueue2.SendBidiSetRequestAsync
product: Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---

# IPrinterQueue2::SendBidiSetRequestAsync method


## -description


Uses an XML string value to send a Bidi Set request as an asynchronous operation.

This method allows the user to perform device maintenance tasks from within a UWP device app  for printers.


## -syntax


````
HRESULT SendBidiSetRequestAsync(
  [in]          BSTR                            bstrBidiRequest,
  [in]          IPrinterBidiSetRequestCallback  *pCallback,
  [out, retval] IPrinterExtensionAsyncOperation ** ppAsyncOperation
);
````


## -parameters




### -param bstrBidiRequest [in]

XML string that is used to transfer the data for the  Set request.


### -param pCallback [in]

Callback object for the Bidi Set request.


### -param ppAsyncOperation [out, retval]

Context object associated with the asynchronous Bidi Set  request (operation).


## -returns



This method returns the appropriate <b>HRESULT</b> value.




## -see-also

<a href="..\printerextension\nn-printerextension-iprinterextensionasyncoperation.md">IPrinterExtensionAsyncOperation</a>



<a href="..\printerextension\nn-printerextension-iprinterqueue2.md">IPrinterQueue2</a>



<a href="..\printerextension\nn-printerextension-iprinterbidisetrequestcallback.md">IPrinterBidiSetRequestCallback</a>



 

 


