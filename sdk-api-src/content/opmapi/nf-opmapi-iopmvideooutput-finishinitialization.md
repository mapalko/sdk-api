---
UID: NF:opmapi.IOPMVideoOutput.FinishInitialization
title: IOPMVideoOutput::FinishInitialization (opmapi.h)
description: Completes the initialization sequence for an Output Protection Manager (OPM) session.
old-location: mf\iopmvideooutput_iopmvideooutput__finishinitialization.htm
tech.root: medfound
ms.assetid: 7551e374-8745-405b-9879-d35a92d661ea
ms.date: 12/05/2018
ms.keywords: FinishInitialization, FinishInitialization method [Media Foundation], FinishInitialization method [Media Foundation],IOPMVideoOutput interface, IOPMVideoOutput interface [Media Foundation],FinishInitialization method, IOPMVideoOutput.FinishInitialization, IOPMVideoOutput::FinishInitialization, mf.iopmvideooutput_iopmvideooutput__finishinitialization, opmapi/IOPMVideoOutput::FinishInitialization
f1_keywords:
- opmapi/IOPMVideoOutput.FinishInitialization
dev_langs:
- c++
req.header: opmapi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows Vista [desktop apps only]
req.target-min-winversvr: Windows Server 2008 [desktop apps only]
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
- opmapi.h
api_name:
- IOPMVideoOutput.FinishInitialization
targetos: Windows
req.typenames: 
req.redist: 
ms.custom: 19H1
---

# IOPMVideoOutput::FinishInitialization


## -description


Completes the initialization sequence for an Output Protection Manager (OPM) session.


## -parameters




### -param pParameters [in]

Pointer to an <a href="https://docs.microsoft.com/windows/win32/api/ksopmapi/ns-ksopmapi-opm_encrypted_initialization_parameters">OPM_ENCRYPTED_INITIALIZATION_PARAMETERS</a> structure. Initialize this structure as described in the Remarks session.


## -returns



Returns an <b>HRESULT. </b>Possible values include, but are not limited to, those in the following table.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The method succeeded.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>ERROR_GRAPHICS_OPM_DRIVER_INTERNAL_ERROR</b></dt>
</dl>
</td>
<td width="60%">
An unexpected error occurred the display driver.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>ERROR_GRAPHICS_OPM_INVALID_ENCRYPTED_PARAMETERS</b></dt>
</dl>
</td>
<td width="60%">
The encrypted parameters in <i>pParameters</i> are incorrect.

</td>
</tr>
</table>
 




## -remarks



This method is equivalent to the <b>IAMCertifiedOutputProtection::SessionSequenceStart</b> method in Certified Output Protection Protocol (COPP).

The <i>pParameters</i> parameter points to an <b>OPM_ENCRYPTED_INITIALIZATION_PARAMETERS</b> structure that contains a 256-byte array. Before calling the method, prepare this array as follows. First, concatenate the following numbers:

<ul>
<li>The 128-bit number returned in the <i>prnRandomNumber</i> parameter of the <a href="https://docs.microsoft.com/windows/desktop/api/opmapi/nf-opmapi-iopmvideooutput-startinitialization">IOPMVideoOutput::StartInitialization</a> method.</li>
<li>The AES signing key. This value is a 128-bit random number generated by the application.</li>
<li>The initial sequence number for OPM status requests. This value is a 32-bit random number generated by the application. </li>
<li>The initial sequence number for OPM commands. This value is a 32-bit random number generated by the application.</li>
</ul>
Encrypt this number with RAEAS-OAEP, encryption using the display driver's public encryption key. The public encryption key is contained in the certificate returned in the <i>ppbCertificate</i> parameter of the <b>StartInitialization</b> method.

The application must use cryptographically secure random numbers. The <b>CryptGenRandom</b> function is recommended, although not required.




## -see-also




<a href="https://docs.microsoft.com/windows/desktop/api/opmapi/nn-opmapi-iopmvideooutput">IOPMVideoOutput</a>



<a href="https://docs.microsoft.com/windows/desktop/medfound/output-protection-manager">Output Protection Manager</a>
 

 

