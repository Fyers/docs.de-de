---
title: Fusion-Schnittstellen
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- interfaces [.NET Framework fusion]
- fusion interfaces [.NET Framework]
- unmanaged interfaces [.NET Framework], fusion
ms.assetid: e2cf98b7-40c1-4f74-86c7-8a76dd9da677
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f1742025bed977dfd377a78db42df42c1bc43966
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="fusion-interfaces"></a><span data-ttu-id="07592-102">Fusion-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="07592-102">Fusion Interfaces</span></span>
<span data-ttu-id="07592-103">In diesem Abschnitt wird beschrieben, die nicht verwalteten Schnittstellen, die die Fusion-API verwendet, um die Eigenschaften der Ressourcen einer Anwendung zugreifen und die richtigen Versionen dieser Ressourcen für die Anwendung zu suchen.</span><span class="sxs-lookup"><span data-stu-id="07592-103">This section describes the unmanaged interfaces that the fusion API uses to access the properties of an application's resources and to locate the correct versions of those resources for the application.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="07592-104">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="07592-104">In This Section</span></span>  
 [<span data-ttu-id="07592-105">IAppIdAuthority-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="07592-105">IAppIdAuthority Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iappidauthority-interface.md)  
 <span data-ttu-id="07592-106">Stellt Methoden, die zum Generieren und Vergleichen von Schlüsseln für Anwendungsidentitäten und Verweise.</span><span class="sxs-lookup"><span data-stu-id="07592-106">Provides methods that generate and compare keys for application identities and references.</span></span>  
  
 [<span data-ttu-id="07592-107">IAssemblyCache-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="07592-107">IAssemblyCache Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md)  
 <span data-ttu-id="07592-108">Bietet eine Darstellung des globalen Assemblycaches.</span><span class="sxs-lookup"><span data-stu-id="07592-108">Provides a representation of the global assembly cache.</span></span>  
  
 [<span data-ttu-id="07592-109">IAssemblyCacheItem-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="07592-109">IAssemblyCacheItem Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md)  
 <span data-ttu-id="07592-110">Stellt eine einzelne Assembly im globalen Assemblycache.</span><span class="sxs-lookup"><span data-stu-id="07592-110">Represents a single assembly in the global assembly cache.</span></span>  
  
 [<span data-ttu-id="07592-111">IAssemblyEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="07592-111">IAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md)  
 <span data-ttu-id="07592-112">Stellt einen Enumerator für ein Array von `IAssemblyName` Objekte.</span><span class="sxs-lookup"><span data-stu-id="07592-112">Represents an enumerator for an array of `IAssemblyName` objects.</span></span>  
  
 [<span data-ttu-id="07592-113">IAssemblyName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="07592-113">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)  
 <span data-ttu-id="07592-114">Stellt Methoden zum Beschreiben und Arbeiten mit eindeutige Identität einer Assembly bereit.</span><span class="sxs-lookup"><span data-stu-id="07592-114">Provides methods for describing and working with an assembly's unique identity.</span></span>  
  
 [<span data-ttu-id="07592-115">IDefinitionAppId-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="07592-115">IDefinitionAppId Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/idefinitionappid-interface.md)  
 <span data-ttu-id="07592-116">Stellt einen eindeutigen Bezeichner für den Code, der die Anwendung im aktuellen Bereich definiert.</span><span class="sxs-lookup"><span data-stu-id="07592-116">Represents a unique identifier for the code that defines the application in the current scope.</span></span>  
  
 [<span data-ttu-id="07592-117">IDefinitionIdentity-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="07592-117">IDefinitionIdentity Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md)  
 <span data-ttu-id="07592-118">Stellt die eindeutige Signatur des Codes, der die Anwendung im aktuellen Bereich definiert.</span><span class="sxs-lookup"><span data-stu-id="07592-118">Represents the unique signature of the code that defines the application in the current scope.</span></span>  
  
 [<span data-ttu-id="07592-119">IEnumDefinitionIdentity-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="07592-119">IEnumDefinitionIdentity Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/ienumdefinitionidentity-interface.md)  
 <span data-ttu-id="07592-120">Dient als Enumerator für eine Auflistung von `IDefinitionIdentity` Objekte.</span><span class="sxs-lookup"><span data-stu-id="07592-120">Serves as the enumerator for a collection of `IDefinitionIdentity` objects.</span></span>  
  
 [<span data-ttu-id="07592-121">IEnumIDENTITY_ATTRIBUTE-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="07592-121">IEnumIDENTITY_ATTRIBUTE Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/ienumidentity-attribute-interface.md)  
 <span data-ttu-id="07592-122">Dient als Enumerator für die Attribute des Codeobjekts im aktuellen Bereich.</span><span class="sxs-lookup"><span data-stu-id="07592-122">Serves as an enumerator for the attributes of the code object in the current scope.</span></span>  
  
 [<span data-ttu-id="07592-123">IEnumReferenceIdentity-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="07592-123">IEnumReferenceIdentity Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/ienumreferenceidentity-interface.md)  
 <span data-ttu-id="07592-124">Dient als Enumerator für eine Auflistung von `IReferenceIdentity` Objekte.</span><span class="sxs-lookup"><span data-stu-id="07592-124">Serves as an enumerator for a collection of `IReferenceIdentity` objects.</span></span>  
  
 [<span data-ttu-id="07592-125">IIdentityAuthority-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="07592-125">IIdentityAuthority Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iidentityauthority-interface.md)  
 <span data-ttu-id="07592-126">Verwaltet die Identitätsschlüssel für Codeobjekte.</span><span class="sxs-lookup"><span data-stu-id="07592-126">Manages identity keys for code objects.</span></span>  
  
 [<span data-ttu-id="07592-127">IInstallReferenceEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="07592-127">IInstallReferenceEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceenum-interface.md)  
 <span data-ttu-id="07592-128">Stellt einen Enumerator für die referenzierten Assemblys im globalen Assemblycache installiert.</span><span class="sxs-lookup"><span data-stu-id="07592-128">Represents an enumerator for the referenced assemblies installed in the global assembly cache.</span></span>  
  
 [<span data-ttu-id="07592-129">IInstallReferenceItem-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="07592-129">IInstallReferenceItem Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceitem-interface.md)  
 <span data-ttu-id="07592-130">Stellt ein Element im globalen Assemblycache installiert.</span><span class="sxs-lookup"><span data-stu-id="07592-130">Represents an item installed in the global assembly cache.</span></span>  
  
 [<span data-ttu-id="07592-131">IReferenceAppId-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="07592-131">IReferenceAppId Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/ireferenceappid-interface.md)  
 <span data-ttu-id="07592-132">Stellt einen Verweis auf den eindeutigen Bezeichner für die Anwendung im aktuellen Bereich.</span><span class="sxs-lookup"><span data-stu-id="07592-132">Represents a reference to the unique identifier for the application in the current scope.</span></span>  
  
 [<span data-ttu-id="07592-133">IReferenceIdentity-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="07592-133">IReferenceIdentity Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/ireferenceidentity-interface.md)  
 <span data-ttu-id="07592-134">Stellt einen Verweis auf die eindeutige Signatur des ein Codeobjekt dar.</span><span class="sxs-lookup"><span data-stu-id="07592-134">Represents a reference to the unique signature of a code object.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="07592-135">Verweis</span><span class="sxs-lookup"><span data-stu-id="07592-135">Reference</span></span>  
 <xref:System.Reflection>  
  
 <xref:System.Reflection.Emit>  
  
## <a name="related-sections"></a><span data-ttu-id="07592-136">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="07592-136">Related Sections</span></span>  
 [<span data-ttu-id="07592-137">Globale statische Fusionsfunktionen</span><span class="sxs-lookup"><span data-stu-id="07592-137">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)  
  
 [<span data-ttu-id="07592-138">Fusion-Enumerationen</span><span class="sxs-lookup"><span data-stu-id="07592-138">Fusion Enumerations</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-enumerations.md)  
  
 [<span data-ttu-id="07592-139">Fusion-Strukturen</span><span class="sxs-lookup"><span data-stu-id="07592-139">Fusion Structures</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-structures.md)