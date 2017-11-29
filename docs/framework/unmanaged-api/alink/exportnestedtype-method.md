---
title: ExportNestedType-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IALink.ExportNestedType
- ExportNestedType
api_location: alink.dll
api_type: COM
f1_keywords: ExportNestedType
helpviewer_keywords: ExportNestedType method
ms.assetid: dec7df60-4d30-47c8-99db-72e0419e5f76
topic_type: apiref
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 378d1e8b21b8d3993377ac08ff7006c420117bfe
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="exportnestedtype-method"></a><span data-ttu-id="27d6e-102">ExportNestedType-Methode</span><span class="sxs-lookup"><span data-stu-id="27d6e-102">ExportNestedType Method</span></span>
<span data-ttu-id="27d6e-103">Gibt geschachtelte Typen als "Exportierbar" markieren.</span><span class="sxs-lookup"><span data-stu-id="27d6e-103">Specifies nested types as exportable.</span></span> <span data-ttu-id="27d6e-104">Die [ExportType-Methode](../../../../docs/framework/unmanaged-api/alink/exporttype-method.md) kann auch geschachtelte Typen exportieren, aber diese Methode ist schneller.</span><span class="sxs-lookup"><span data-stu-id="27d6e-104">The [ExportType Method](../../../../docs/framework/unmanaged-api/alink/exporttype-method.md) can also export nested types, but this method is faster.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27d6e-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="27d6e-105">Syntax</span></span>  
  
```  
HRESULT ExportNestedType(  
    mdAssembly      AssemblyID,  
    mdToken         FileToken,  
    mdTypeDef       TypeToken,  
    mdExportedType  ParentType,  
    LPCWSTR         pszTypename,  
    DWORD           dwFlags,  
    mdExportedType* pType  
) PURE;   
```  
  
#### <a name="parameters"></a><span data-ttu-id="27d6e-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="27d6e-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="27d6e-107">ID der Assembly exportieren.</span><span class="sxs-lookup"><span data-stu-id="27d6e-107">ID of assembly to export from.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="27d6e-108">Datei-Token oder übergeordnete Assembly der Datei, definiert den Typ als exportierbar festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="27d6e-108">File token or Assembly of file that defines the type to be made exportable.</span></span>  
  
 `TypeToken`  
 <span data-ttu-id="27d6e-109">Geben Sie ein Token vom Typ als exportierbar festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="27d6e-109">Type token of type to be made exportable.</span></span>  
  
 `ParentType`  
 <span data-ttu-id="27d6e-110">Token des übergeordneten Typs.</span><span class="sxs-lookup"><span data-stu-id="27d6e-110">Token of parent type.</span></span>  
  
 `pszTypename`  
 <span data-ttu-id="27d6e-111">Voll qualifizierten Typnamen zu exportieren.</span><span class="sxs-lookup"><span data-stu-id="27d6e-111">Fully qualified type name to export.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="27d6e-112">`ComType`Flags, z. B. `tdPublic` oder `tdNested`.</span><span class="sxs-lookup"><span data-stu-id="27d6e-112">`ComType` flags such as `tdPublic` or `tdNested`.</span></span> <span data-ttu-id="27d6e-113">Dieser Wert möglicherweise übergeben werden, um [DefineExportedType-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md).</span><span class="sxs-lookup"><span data-stu-id="27d6e-113">This value may be passed to [DefineExportedType Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md).</span></span>  
  
 `pType`  
 <span data-ttu-id="27d6e-114">Empfängt Token für den exportierten Typ.</span><span class="sxs-lookup"><span data-stu-id="27d6e-114">Receives token for exported type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="27d6e-115">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="27d6e-115">Return Value</span></span>  
 <span data-ttu-id="27d6e-116">Gibt S_OK zurück, wenn die Methode erfolgreich ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="27d6e-116">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="27d6e-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="27d6e-117">Requirements</span></span>  
 <span data-ttu-id="27d6e-118">Erfordert alink.h</span><span class="sxs-lookup"><span data-stu-id="27d6e-118">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27d6e-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="27d6e-119">See Also</span></span>  
 [<span data-ttu-id="27d6e-120">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="27d6e-120">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="27d6e-121">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="27d6e-121">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="27d6e-122">ALink-API</span><span class="sxs-lookup"><span data-stu-id="27d6e-122">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)