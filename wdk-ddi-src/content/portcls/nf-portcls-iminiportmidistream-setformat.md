---
UID: NF:portcls.IMiniportMidiStream.SetFormat
title: IMiniportMidiStream::SetFormat method
author: windows-driver-content
description: The SetFormat method sets the KS data format of the MIDI stream.
old-location: audio\iminiportmidistream_setformat.htm
old-project: audio
ms.assetid: 35e11004-c716-4c6a-ba0a-be04750afb7a
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: IMiniportMidiStream, IMiniportMidiStream interface [Audio Devices], SetFormat method, IMiniportMidiStream::SetFormat, SetFormat method [Audio Devices], SetFormat method [Audio Devices], IMiniportMidiStream interface, SetFormat,IMiniportMidiStream.SetFormat, audio.iminiportmidistream_setformat, audmp-routines_9e75b920-4cc0-4acb-83e6-f970524e0587.xml, portcls/IMiniportMidiStream::SetFormat
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Universal
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	portcls.h
api_name:
-	IMiniportMidiStream.SetFormat
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---

# IMiniportMidiStream::SetFormat method


## -description


The <code>SetFormat</code> method sets the KS data format of the MIDI stream.


## -syntax


````
NTSTATUS SetFormat(
  [in] PKSDATAFORMAT DataFormat
);
````


## -parameters




### -param DataFormat [in]

Specifies the new format for the stream. This parameter is a pointer to a structure of type <a href="..\ks\ns-ks-ksdataformat.md">KSDATAFORMAT</a>.


## -returns



<code>SetFormat</code> returns STATUS_SUCCESS if the call was successful. Otherwise, the method returns an appropriate error code.




## -remarks



The <code>SetFormat</code> method essentially does nothing because the data format of a MIDI stream cannot be changed to anything other than MIDI. This method is provided for the sake of completeness and for orthogonality with the <code>SetFormat</code> methods in the <b>IMiniportWaveCyclic</b> and <b>IMiniportWavePci</b> interfaces. See the trivial implementation of this method in the fmsynth sample audio driver in the Microsoft Windows Driver Kit (WDK). You can use the sample code as a template for your own implementation. 




## -see-also

<a href="..\ks\ns-ks-ksdataformat.md">KSDATAFORMAT</a>



<a href="..\portcls\nn-portcls-iminiportmidistream.md">IMiniportMidiStream</a>



 

 


