---
title: IMetaDataImport::EnumMemberRefs-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.EnumMemberRefs
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::EnumMemberRefs
helpviewer_keywords:
- EnumMemberRefs method [.NET Framework metadata]
- IMetaDataImport::EnumMemberRefs method [.NET Framework metadata]
ms.assetid: e97c97a6-6e4f-41f5-9af1-9b3cf3bdbd6b
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: a9a47d723aaf7dd83bc488a07b040b43a206be55
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportenummemberrefs-method"></a><span data-ttu-id="d4c48-102">IMetaDataImport::EnumMemberRefs-Methode</span><span class="sxs-lookup"><span data-stu-id="d4c48-102">IMetaDataImport::EnumMemberRefs Method</span></span>
<span data-ttu-id="d4c48-103">Zählt MemberRef-Token auf, die Elemente des angegebenen Typs darstellen.</span><span class="sxs-lookup"><span data-stu-id="d4c48-103">Enumerates MemberRef tokens representing members of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4c48-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d4c48-104">Syntax</span></span>  
  
```  
HRESULT EnumMemberRefs (  
   [in, out] HCORENUM    *phEnum,   
   [in]   mdToken        tkParent,   
   [out]  mdMemberRef    rMemberRefs[],   
   [in]   ULONG          cMax,   
   [out]  ULONG          *pcTokens  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d4c48-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d4c48-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="d4c48-106">[in, out] Ein Zeiger auf den Enumerator.</span><span class="sxs-lookup"><span data-stu-id="d4c48-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `tkParent`  
 <span data-ttu-id="d4c48-107">[in] Eine TypeDef, TypeRef-Token, MethodDef oder ModuleRef-Token für den Typ, dessen Member aufgelistet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="d4c48-107">[in] A TypeDef, TypeRef, MethodDef, or ModuleRef token for the type whose members are to be enumerated.</span></span>  
  
 `rMemberRefs`  
 <span data-ttu-id="d4c48-108">[out] Das Array zum Speichern von MemberRef-Token verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d4c48-108">[out] The array used to store MemberRef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="d4c48-109">[in] Die maximale Größe des `rMemberRefs`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="d4c48-109">[in] The maximum size of the `rMemberRefs` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="d4c48-110">[out] Die tatsächliche Anzahl der zurückgegebenen MemberRef-Token `rMemberRefs`.</span><span class="sxs-lookup"><span data-stu-id="d4c48-110">[out] The actual number of MemberRef tokens returned in `rMemberRefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d4c48-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="d4c48-111">Return Value</span></span>  
  
|<span data-ttu-id="d4c48-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d4c48-112">HRESULT</span></span>|<span data-ttu-id="d4c48-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d4c48-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="d4c48-114">`EnumMemberRefs`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="d4c48-114">`EnumMemberRefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="d4c48-115">Es gibt keine MemberRef-Token aufgelistet werden.</span><span class="sxs-lookup"><span data-stu-id="d4c48-115">There are no MemberRef tokens to enumerate.</span></span> <span data-ttu-id="d4c48-116">In diesem Fall `pcTokens` auf 0 (null) ist.</span><span class="sxs-lookup"><span data-stu-id="d4c48-116">In that case, `pcTokens` is to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d4c48-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d4c48-117">Requirements</span></span>  
 <span data-ttu-id="d4c48-118">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d4c48-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d4c48-119">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="d4c48-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d4c48-120">**Bibliothek:** als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="d4c48-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d4c48-121">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d4c48-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4c48-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d4c48-122">See Also</span></span>  
 [<span data-ttu-id="d4c48-123">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d4c48-123">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="d4c48-124">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d4c48-124">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)