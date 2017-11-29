---
title: ICLRStrongName::StrongNameSignatureVerificationFromImage-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRStrongName.StrongNameSignatureVerificationFromImage
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRStrongName::StrongNameSignatureVerificationFromImage
helpviewer_keywords:
- ICLRStrongName::StrongNameSignatureVerificationFromImage method [.NET Framework hosting]
- StrongNameSignatureVerificationFromImage method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: da91c138-ee30-4fd4-a040-464d97d7e41a
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f312e1eade6de57df9660a349570398d9cd912b7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="iclrstrongnamestrongnamesignatureverificationfromimage-method"></a><span data-ttu-id="4ff88-102">ICLRStrongName::StrongNameSignatureVerificationFromImage-Methode</span><span class="sxs-lookup"><span data-stu-id="4ff88-102">ICLRStrongName::StrongNameSignatureVerificationFromImage Method</span></span>
<span data-ttu-id="4ff88-103">Überprüft, ob eine Assembly, die bereits in den Arbeitsspeicher zugeordnet wurde für den zugehörigen öffentlichen Schlüssel gültig ist.</span><span class="sxs-lookup"><span data-stu-id="4ff88-103">Verifies that an assembly that has already been mapped to memory is valid for the associated public key.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ff88-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4ff88-104">Syntax</span></span>  
  
```  
HRESULT StrongNameSignatureVerificationFromImage (  
    [in]  BYTE    *pbBase,  
    [in]  DWORD   dwLength,  
    [in]  DWORD   dwInFlags,  
    [out] DWORD   *pdwOutFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4ff88-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="4ff88-105">Parameters</span></span>  
 `pbBase`  
 <span data-ttu-id="4ff88-106">[in] Die relative virtuelle Adresse des zugeordneten Assemblymanifests.</span><span class="sxs-lookup"><span data-stu-id="4ff88-106">[in] The relative virtual address of the mapped assembly manifest.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="4ff88-107">[in] Die Größe in Bytes, der das zugeordnete Bild.</span><span class="sxs-lookup"><span data-stu-id="4ff88-107">[in] The size, in bytes, of the mapped image.</span></span>  
  
 `dwInFlags`  
 <span data-ttu-id="4ff88-108">[in] Flags, die das Überprüfungsverhalten beeinflussen.</span><span class="sxs-lookup"><span data-stu-id="4ff88-108">[in] Flags that influence verification behavior.</span></span> <span data-ttu-id="4ff88-109">Die folgenden Werte werden unterstützt:</span><span class="sxs-lookup"><span data-stu-id="4ff88-109">The following values are supported:</span></span>  
  
-   <span data-ttu-id="4ff88-110">`SN_INFLAG_FORCE_VER`(0 x 00000001) - Überprüfung erzwingt, auch wenn es zum Überschreiben der registrierungseinstellungen für die erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="4ff88-110">`SN_INFLAG_FORCE_VER` (0x00000001) - Forces verification even if it is necessary to override registry settings.</span></span>  
  
-   <span data-ttu-id="4ff88-111">`SN_INFLAG_INSTALL`(0 x 00000002) – gibt an, dass dies die erste Überprüfung für dieses Image ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="4ff88-111">`SN_INFLAG_INSTALL` (0x00000002) - Specifies that this is the first verification performed on this image.</span></span>  
  
-   <span data-ttu-id="4ff88-112">`SN_INFLAG_ADMIN_ACCESS`(0 x 00000004) – gibt an, dass der Cache Zugriff nur für Benutzer gewährt wird, die über Administratorrechte verfügen.</span><span class="sxs-lookup"><span data-stu-id="4ff88-112">`SN_INFLAG_ADMIN_ACCESS` (0x00000004) - Specifies that the cache will allow access only to users who have administrative privileges.</span></span>  
  
-   <span data-ttu-id="4ff88-113">`SN_INFLAG_USER_ACCESS`(0 x 00000008) – gibt an, dass die Assembly nur auf den aktuellen Benutzer zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="4ff88-113">`SN_INFLAG_USER_ACCESS` (0x00000008) - Specifies that the assembly will be accessible only to the current user.</span></span>  
  
-   <span data-ttu-id="4ff88-114">`SN_INFLAG_ALL_ACCESS`(0 x 00000010) – gibt an, dass keine Gewährleistung der Einschränkung der Cache bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="4ff88-114">`SN_INFLAG_ALL_ACCESS` (0x00000010) - Specifies that the cache will provide no guarantees of access restriction.</span></span>  
  
-   <span data-ttu-id="4ff88-115">`SN_INFLAG_RUNTIME`(0 x 80000000) - reserviert für interne Debuggen.</span><span class="sxs-lookup"><span data-stu-id="4ff88-115">`SN_INFLAG_RUNTIME` (0x80000000) - Reserved for internal debugging.</span></span>  
  
 `pdwOutFlags`  
 <span data-ttu-id="4ff88-116">[out] Ein Flag für zusätzliche Ausgabeinformationen.</span><span class="sxs-lookup"><span data-stu-id="4ff88-116">[out] A flag for additional output information.</span></span> <span data-ttu-id="4ff88-117">Der folgende Wert wird unterstützt:</span><span class="sxs-lookup"><span data-stu-id="4ff88-117">The following value is supported:</span></span>  
  
-   <span data-ttu-id="4ff88-118">`SN_OUTFLAG_WAS_VERIFIED`(0 x 00000001) - dieser Wert wird festgelegt, um `false` um anzugeben, dass die Überprüfung aufgrund der registrierungseinstellungen für die erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="4ff88-118">`SN_OUTFLAG_WAS_VERIFIED` (0x00000001) - This value is set to `false` to specify that the verification succeeded due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4ff88-119">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="4ff88-119">Return Value</span></span>  
 <span data-ttu-id="4ff88-120">`S_OK`Wenn die Methode erfolgreich abgeschlossen. andernfalls ein HRESULT-Wert, der Fehler weist darauf hin (finden Sie unter [häufig auftretende HRESULT-Werte](http://go.microsoft.com/fwlink/?LinkId=213878) eine Liste).</span><span class="sxs-lookup"><span data-stu-id="4ff88-120">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](http://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4ff88-121">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4ff88-121">Requirements</span></span>  
 <span data-ttu-id="4ff88-122">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4ff88-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4ff88-123">**Header:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="4ff88-123">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="4ff88-124">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="4ff88-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4ff88-125">**.NET Framework-Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4ff88-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ff88-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4ff88-126">See Also</span></span>  
 [<span data-ttu-id="4ff88-127">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4ff88-127">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)