---
title: ICorDebugProcess5-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess5
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess5
helpviewer_keywords: ICorDebugProcess5 interface [.NET Framework debugging]
ms.assetid: 30a39d79-1f10-4328-9c5d-094ed824e2ba
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0f0a46e18121a222ee62fec207dde938d1e967b5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugprocess5-interface"></a><span data-ttu-id="6ec83-102">ICorDebugProcess5-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6ec83-102">ICorDebugProcess5 Interface</span></span>
<span data-ttu-id="6ec83-103">ICorDebugProcess-Schnittstelle, um Zugriff auf den verwalteten Heap an, um Informationen zum Garbagecollection verwalteten Objekte bereitzustellen unterstützen erweitert, und lädt bestimmen, ob ein Debugger Bilder vom lokalen systemeigenen Imagecache von Anwendung.</span><span class="sxs-lookup"><span data-stu-id="6ec83-103">Extends the ICorDebugProcess interface to support access to the managed heap, to provide information about garbage collection of managed objects, and to determine whether a debugger loads images from the application local native image cache.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6ec83-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="6ec83-104">Methods</span></span>  
  
|<span data-ttu-id="6ec83-105">Methode</span><span class="sxs-lookup"><span data-stu-id="6ec83-105">Method</span></span>|<span data-ttu-id="6ec83-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6ec83-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6ec83-107">EnableNGenPolicy-Methode</span><span class="sxs-lookup"><span data-stu-id="6ec83-107">EnableNGenPolicy Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enablengenpolicy-method.md)|<span data-ttu-id="6ec83-108">Legt einen Wert, der bestimmt, wie eine Anwendung während der Ausführung unter einem verwalteten Debugger systemeigene Abbilder lädt.</span><span class="sxs-lookup"><span data-stu-id="6ec83-108">Sets a value that determines how an application loads native images while running under a managed debugger.</span></span>|  
|[<span data-ttu-id="6ec83-109">EnumerateGCReferences-Methode</span><span class="sxs-lookup"><span data-stu-id="6ec83-109">EnumerateGCReferences Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerategcreferences-method.md)|<span data-ttu-id="6ec83-110">Ruft einen Enumerator für alle Objekte, die in einem Prozess speicherbereinigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="6ec83-110">Gets an enumerator for all objects that are to be garbage-collected in a process.</span></span>|  
|[<span data-ttu-id="6ec83-111">EnumerateHandles-Methode</span><span class="sxs-lookup"><span data-stu-id="6ec83-111">EnumerateHandles Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md)|<span data-ttu-id="6ec83-112">Ruft einen Enumerator für die Objekt-Handles in einem Prozess ab.</span><span class="sxs-lookup"><span data-stu-id="6ec83-112">Gets an enumerator for object handles in a process.</span></span>|  
|[<span data-ttu-id="6ec83-113">EnumerateHeap-Methode</span><span class="sxs-lookup"><span data-stu-id="6ec83-113">EnumerateHeap Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheap-method.md)|<span data-ttu-id="6ec83-114">Ruft einen Enumerator für Objekte im verwalteten Heap.</span><span class="sxs-lookup"><span data-stu-id="6ec83-114">Gets an enumerator for objects on the managed heap.</span></span>|  
|[<span data-ttu-id="6ec83-115">EnumerateHeapRegions-Methode</span><span class="sxs-lookup"><span data-stu-id="6ec83-115">EnumerateHeapRegions Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheapregions-method.md)|<span data-ttu-id="6ec83-116">Ruft einen Enumerator für die Regionen des verwalteten Heaps.</span><span class="sxs-lookup"><span data-stu-id="6ec83-116">Gets an enumerator for regions of the managed heap.</span></span>|  
|[<span data-ttu-id="6ec83-117">GetArrayLayout-Methode</span><span class="sxs-lookup"><span data-stu-id="6ec83-117">GetArrayLayout Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getarraylayout-method.md)|<span data-ttu-id="6ec83-118">Ruft Informationen zum Layout eines Arrays im Arbeitsspeicher ab.</span><span class="sxs-lookup"><span data-stu-id="6ec83-118">Gets information about the layout of an array in memory.</span></span>|  
|[<span data-ttu-id="6ec83-119">GetGCHeapInformation-Methode</span><span class="sxs-lookup"><span data-stu-id="6ec83-119">GetGCHeapInformation Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md)|<span data-ttu-id="6ec83-120">Ruft einen Zeiger auf eine [COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) -Struktur, die Informationen zu Objekten enthält, die Garbage Collection auf dem verwalteten Heap werden sollen.</span><span class="sxs-lookup"><span data-stu-id="6ec83-120">Gets a pointer to a [COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) structure that contains information about objects that are to be garbage-collected on the managed heap.</span></span>|  
|[<span data-ttu-id="6ec83-121">GetObject-Methode</span><span class="sxs-lookup"><span data-stu-id="6ec83-121">GetObject Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getobject-method.md)|<span data-ttu-id="6ec83-122">Ruft einen Zeiger auf ein Objekt ab, auf dem verwalteten Heap.</span><span class="sxs-lookup"><span data-stu-id="6ec83-122">Gets a pointer to an object on the managed heap.</span></span>|  
|[<span data-ttu-id="6ec83-123">GetTypeFields-Methode</span><span class="sxs-lookup"><span data-stu-id="6ec83-123">GetTypeFields Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefields-method.md)|<span data-ttu-id="6ec83-124">Ruft einen Zeiger auf ein Array, das Feldinformationen für einen Typ auf Grundlage seines Bezeichners Typ enthält.</span><span class="sxs-lookup"><span data-stu-id="6ec83-124">Gets a pointer to an array that contains field information for a type based on its type identifier.</span></span>|  
|[<span data-ttu-id="6ec83-125">GetTypeForTypeID-Methode</span><span class="sxs-lookup"><span data-stu-id="6ec83-125">GetTypeForTypeID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefortypeid-method.md)|<span data-ttu-id="6ec83-126">Ruft ein Objekt vom Typ, der Informationen zu einem Objekt basierend auf seiner Typenbezeichnern bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="6ec83-126">Gets a type object that provides information about an object based on its type identifiers.</span></span>|  
|[<span data-ttu-id="6ec83-127">GetTypeID-Methode</span><span class="sxs-lookup"><span data-stu-id="6ec83-127">GetTypeID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypeid-method.md)|<span data-ttu-id="6ec83-128">Ruft die Typ-ID für das Objekt an einer angegebenen Adresse an.</span><span class="sxs-lookup"><span data-stu-id="6ec83-128">Gets the type identifier for the object at a specified address.</span></span>|  
|[<span data-ttu-id="6ec83-129">GetTypeLayout-Methode</span><span class="sxs-lookup"><span data-stu-id="6ec83-129">GetTypeLayout Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypelayout-method.md)|<span data-ttu-id="6ec83-130">Ruft Informationen zum Layout eines Objekts im Arbeitsspeicher auf Grundlage seines Bezeichners Typ ab.</span><span class="sxs-lookup"><span data-stu-id="6ec83-130">Gets information about the layout of an object in memory based on its type identifier.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6ec83-131">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6ec83-131">Remarks</span></span>  
 <span data-ttu-id="6ec83-132">Diese Schnittstelle erweitert logisch die ICorDebugProcess ICorDebugProcess2, und [ICorDebugProcess3](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess3-interface.md) Schnittstellen.</span><span class="sxs-lookup"><span data-stu-id="6ec83-132">This interface logically extends the ICorDebugProcess, ICorDebugProcess2, and [ICorDebugProcess3](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess3-interface.md) interfaces.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6ec83-133">Diese Schnittstelle unterstützt keine Remote aufgerufen werden, von einem anderen Computer oder einem anderen Prozess.</span><span class="sxs-lookup"><span data-stu-id="6ec83-133">This interface does not support being called remotely, either from another machine or from another process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6ec83-134">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6ec83-134">Requirements</span></span>  
 <span data-ttu-id="6ec83-135">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6ec83-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6ec83-136">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6ec83-136">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6ec83-137">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6ec83-137">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6ec83-138">**.NET Framework-Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6ec83-138">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ec83-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6ec83-139">See Also</span></span>  
 [<span data-ttu-id="6ec83-140">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="6ec83-140">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="6ec83-141">Debuggen</span><span class="sxs-lookup"><span data-stu-id="6ec83-141">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)