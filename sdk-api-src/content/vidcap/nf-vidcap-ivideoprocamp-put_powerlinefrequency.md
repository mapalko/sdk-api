---
UID: NF:vidcap.IVideoProcAmp.put_PowerlineFrequency
title: IVideoProcAmp::put_PowerlineFrequency (vidcap.h)
description: The put_PowerlineFrequency method sets the camera's power line frequency setting. This setting enables the camera to perform anti-flicker processing.
old-location: dshow\ivideoprocamp_put_powerlinefrequency.htm
tech.root: DirectShow
ms.assetid: ef490cec-4f25-432a-b6a5-3e16044314e4
ms.date: 12/05/2018
ms.keywords: IVideoProcAmp interface [DirectShow],put_PowerlineFrequency method, IVideoProcAmp.put_PowerlineFrequency, IVideoProcAmp::put_PowerlineFrequency, IVideoProcAmpput_PowerlineFrequency, dshow.ivideoprocamp_put_powerlinefrequency, put_PowerlineFrequency, put_PowerlineFrequency method [DirectShow], put_PowerlineFrequency method [DirectShow],IVideoProcAmp interface, vidcap/IVideoProcAmp::put_PowerlineFrequency
f1_keywords:
- vidcap/IVideoProcAmp.put_PowerlineFrequency
dev_langs:
- c++
req.header: vidcap.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows XP with SP2 [desktop apps only]
req.target-min-winversvr: Windows Server 2003 R2 [desktop apps only]
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
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- Vidcap.h
api_name:
- IVideoProcAmp.put_PowerlineFrequency
targetos: Windows
req.typenames: 
req.redist: 
ms.custom: 19H1
---

# IVideoProcAmp::put_PowerlineFrequency


## -description


The <code>put_PowerlineFrequency</code> method sets the camera's power line frequency setting. This setting enables the camera to perform anti-flicker processing.


## -parameters




### -param Value [in]

Specifies one of the following values.

<table>
<tr>
<th>Value
                </th>
<th>Description
                </th>
</tr>
<tr>
<td>0</td>
<td>Disabled.</td>
</tr>
<tr>
<td>1</td>
<td>50 Hz.</td>
</tr>
<tr>
<td>2</td>
<td>60 Hz.</td>
</tr>
</table>
 


### -param Flags [in]

Zero or more flags. See <a href="https://docs.microsoft.com/previous-versions/windows/desktop/api/strmif/ne-strmif-videoprocampflags">VideoProcAmpFlags</a>. If the VideoProcAmp_Flags_Auto flag is used, the <i>Value</i> parameter is ignored and the camera sets the default value.


## -returns



Returns an <b>HRESULT</b> value.




## -see-also




<a href="https://docs.microsoft.com/windows/desktop/DirectShow/error-and-success-codes">Error and Success Codes</a>



<a href="https://docs.microsoft.com/windows/desktop/api/vidcap/nn-vidcap-ivideoprocamp">IVideoProcAmp Interface</a>
 

 

