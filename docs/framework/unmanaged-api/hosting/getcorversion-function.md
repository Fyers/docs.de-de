---
title: GetCORVersion-Funktion
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: GetCORVersion
api_location:
- mscoree.dll
- mscoreei.dll
api_type: DLLExport
f1_keywords: GetCORVersion
helpviewer_keywords: GetCORVersion function [.NET Framework hosting]
ms.assetid: 2f09cd37-bf3a-4cc5-87b0-adc42a7eed31
topic_type: apiref
caps.latest.revision: "17"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 6218714030892531f3b9ed4b4a79917347d250db
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="getcorversion-function"></a><span data-ttu-id="264b2-102">GetCORVersion-Funktion</span><span class="sxs-lookup"><span data-stu-id="264b2-102">GetCORVersion Function</span></span>
<span data-ttu-id="264b2-103">Gibt die Versionsnummer der common Language Runtime (CLR), die im aktuellen Prozess ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="264b2-103">Returns the version number of the common language runtime (CLR) that is running in the current process.</span></span>  
  
 <span data-ttu-id="264b2-104">Diese Funktion ist in [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] veraltet.</span><span class="sxs-lookup"><span data-stu-id="264b2-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="264b2-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="264b2-105">Syntax</span></span>  
  
```  
HRESULT GetCORVersion (  
    [in] LPWSTR  pbuffer,  
    [in]  DWORD   cchBuffer,   
    [out] DWORD*  dwlength  
);   
```  
  
#### <a name="parameters"></a><span data-ttu-id="264b2-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="264b2-106">Parameters</span></span>  
 `pbuffer`  
 <span data-ttu-id="264b2-107">Ein Zeiger auf einen Puffer, in dem die CLR gibt eine Zeichenfolge, die Version der Laufzeit, die derzeit in den Prozess geladen wird.</span><span class="sxs-lookup"><span data-stu-id="264b2-107">A pointer to a buffer in which the CLR returns a string specifying the version of the runtime that is currently loaded into the process.</span></span> <span data-ttu-id="264b2-108">Die zurückgegebene Zeichenfolge hat das gleiche Format wie Zeichenfolgen, die an [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md), z. B. "v1.0.1216".</span><span class="sxs-lookup"><span data-stu-id="264b2-108">The returned string takes the same form as strings passed to [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md), for example, "v1.0.1216".</span></span> <span data-ttu-id="264b2-109">Wenn die Common Language Runtime noch nicht in den Prozess geladen wurde, gibt die Funktion die entsprechenden Verzeichnisinformationen für die neueste Version der Laufzeit auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="264b2-109">If the runtime has not yet been loaded into the process, the function returns the appropriate directory information for the latest version of the runtime installed on the computer.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="264b2-110">Die Anzahl der Zeichen (`WCHAR`s), können in gespeicherten werden `pbuffer`.</span><span class="sxs-lookup"><span data-stu-id="264b2-110">The number of characters (`WCHAR`s) that can be held in `pbuffer`.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="264b2-111">Ein Zeiger auf die Anzahl der Zeichen, die tatsächlich im zurückgegebenen `pbuffer`.</span><span class="sxs-lookup"><span data-stu-id="264b2-111">A pointer to the number of characters actually returned in `pbuffer`.</span></span> <span data-ttu-id="264b2-112">Wenn `pbuffer` ist ein null-Zeiger, die Common Language Runtime gibt E_POINTER zurück.</span><span class="sxs-lookup"><span data-stu-id="264b2-112">If `pbuffer` is a null pointer, the runtime returns E_POINTER.</span></span> <span data-ttu-id="264b2-113">Wenn die Anzahl der Zeichen größer ist die Länge von `pbuffer` , gibt die Runtime ERROR_INSUFFICIENT_BUFFER.</span><span class="sxs-lookup"><span data-stu-id="264b2-113">If the number of characters is greater then the length of `pbuffer` , the runtime returns ERROR_INSUFFICIENT_BUFFER.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="264b2-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="264b2-114">Requirements</span></span>  
 <span data-ttu-id="264b2-115">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="264b2-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="264b2-116">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="264b2-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="264b2-117">**Bibliothek:** "Mscoree.dll"</span><span class="sxs-lookup"><span data-stu-id="264b2-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="264b2-118">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="264b2-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="264b2-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="264b2-119">See Also</span></span>  
 [<span data-ttu-id="264b2-120">Veraltete CLR-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="264b2-120">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)