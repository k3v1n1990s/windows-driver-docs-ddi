---
UID: NF:prnasntp.IPrintUnidiAsyncNotifyRegistration.AsyncGetNotification
title: IPrintUnidiAsyncNotifyRegistration::AsyncGetNotification method
author: windows-driver-content
description: "."
old-location: print\iprintunidiasyncnotifyregistration_asyncgetnotification.htm
old-project: print
ms.assetid: 48C444CD-4D8B-491A-98EB-27B8796FD3A7
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: AsyncGetNotification method [Print Devices], AsyncGetNotification method [Print Devices], IPrintUnidiAsyncNotifyRegistration interface, AsyncGetNotification,IPrintUnidiAsyncNotifyRegistration.AsyncGetNotification, IPrintUnidiAsyncNotifyRegistration, IPrintUnidiAsyncNotifyRegistration interface [Print Devices], AsyncGetNotification method, IPrintUnidiAsyncNotifyRegistration::AsyncGetNotification, print.iprintunidiasyncnotifyregistration_asyncgetnotification, prnasntp/IPrintUnidiAsyncNotifyRegistration::AsyncGetNotification
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: prnasntp.h
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
-	COM
api_location:
-	Prnasntp.h
api_name:
-	IPrintUnidiAsyncNotifyRegistration.AsyncGetNotification
product: Windows
targetos: Windows
req.typenames: USERDATA, *PUSERDATA
req.product: Windows 10 or later.
---

# IPrintUnidiAsyncNotifyRegistration::AsyncGetNotification method


## -description





## -syntax


````
HRESULT AsyncGetNotification(
  [in] IAsyncGetSendNotificationCookie *pCookie
);
````


## -parameters




### -param EQUALNULL






#### - pCookie [in]


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -see-also

<a href="..\prnasntp\nn-prnasntp-iprintunidiasyncnotifyregistration.md">IPrintUnidiAsyncNotifyRegistration</a>



 

 


