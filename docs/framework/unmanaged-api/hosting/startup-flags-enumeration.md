---
title: STARTUP_FLAGS-Enumeration
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: STARTUP_FLAGS
api_location: mscoree.dll
api_type: COM
f1_keywords: STARTUP_FLAGS
helpviewer_keywords: STARTUP_FLAGS enumeration [.NET Framework hosting]
ms.assetid: 4f043594-0c45-4bc6-988e-a6793f0d8d06
topic_type: apiref
caps.latest.revision: "22"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ebfb45e6d568b4fa1db209264e02332df636474f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="startupflags-enumeration"></a><span data-ttu-id="6bff5-102">STARTUP_FLAGS-Enumeration</span><span class="sxs-lookup"><span data-stu-id="6bff5-102">STARTUP_FLAGS Enumeration</span></span>
<span data-ttu-id="6bff5-103">Enthält Werte, die das Startverhalten der Common Language Runtime (CLR) angeben.</span><span class="sxs-lookup"><span data-stu-id="6bff5-103">Contains values that indicate the startup behavior of the common language runtime (CLR).</span></span> <span data-ttu-id="6bff5-104">Standardmäßig erfolgt die Garbage Collection nicht gleichzeitig, und nur die Basisklassenbibliothek wird in den domänenneutralen Bereich geladen.</span><span class="sxs-lookup"><span data-stu-id="6bff5-104">By default, garbage collection is non-concurrent, and only the base class library is loaded into the domain-neutral area.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6bff5-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="6bff5-105">Syntax</span></span>  
  
```  
typedef enum {  
    STARTUP_CONCURRENT_GC                         = 0x1,  
    STARTUP_LOADER_OPTIMIZATION_MASK              = 0x3<<1,  
    STARTUP_LOADER_OPTIMIZATION_SINGLE_DOMAIN     = 0x1<<1,  
    STARTUP_LOADER_OPTIMIZATION_MULTI_DOMAIN      = 0x2<<1,  
    STARTUP_LOADER_OPTIMIZATION_MULTI_DOMAIN_HOST = 0x3<<1,  
  
    STARTUP_LOADER_SAFEMODE                       = 0x10,  
    STARTUP_LOADER_SETPREFERENCE                  = 0x100,  
  
    STARTUP_SERVER_GC                             = 0x1000,  
    STARTUP_HOARD_GC_VM                           = 0x2000,  
  
    STARTUP_SINGLE_VERSION_HOSTING_INTERFACE      = 0x4000,  
    STARTUP_LEGACY_IMPERSONATION                  = 0x10000,  
    STARTUP_DISABLE_COMMITTHREADSTACK             = 0x20000,  
    STARTUP_ALWAYSFLOW_IMPERSONATION              = 0x40000,  
    STARTUP_TRIM_GC_COMMIT                        = 0x80000,  
  
    STARTUP_ETW                                   = 0x100000,  
    STARTUP_ARM                                   = 0x400000  
} STARTUP_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="6bff5-106">Member</span><span class="sxs-lookup"><span data-stu-id="6bff5-106">Members</span></span>  
  
|<span data-ttu-id="6bff5-107">Member</span><span class="sxs-lookup"><span data-stu-id="6bff5-107">Member</span></span>|<span data-ttu-id="6bff5-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6bff5-108">Description</span></span>|  
|------------|-----------------|  
|`STARTUP_CONCURRENT_GC`|<span data-ttu-id="6bff5-109">Gibt an, dass die gleichzeitige Garbage Collection verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="6bff5-109">Specifies that concurrent garbage collection should be used.</span></span> <span data-ttu-id="6bff5-110">Wenn der Aufrufer den Serverbuild und die gleichzeitige Garbage Collection auf einem Computer mit nur einem Prozessor anfordert, werden stattdessen der Arbeitsstationsbuild und die nicht gleichzeitige Garbage Collection ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="6bff5-110">If the caller asks for the server build and concurrent garbage collection on a single-processor machine, the workstation build and non-concurrent garbage collection are run instead.</span></span> <span data-ttu-id="6bff5-111">**Hinweis:** gleichzeitige Garbagecollection wird nicht unterstützt, in Anwendungen, die den WOW64 ausgeführt werden X86 Emulator auf 64-Bit-Systemen, die Implementierung der Intel Itanium-Architektur (früher als IA-64 bezeichnet).</span><span class="sxs-lookup"><span data-stu-id="6bff5-111">**Note:**  Concurrent garbage collection is not supported in applications that are running the WOW64 x86 emulator on 64-bit systems that implement the Intel Itanium architecture (formerly called IA-64).</span></span> <span data-ttu-id="6bff5-112">Weitere Informationen zur Verwendung von WOW64 auf 64-Bit-Windows-Systemen, finden Sie unter [Ausführen von 32-Bit-Anwendungen](http://msdn.microsoft.com/library/windows/desktop/aa384249.aspx).</span><span class="sxs-lookup"><span data-stu-id="6bff5-112">For more information about using WOW64 on 64-bit Windows systems, see [Running 32-bit Applications](http://msdn.microsoft.com/library/windows/desktop/aa384249.aspx).</span></span>|  
|`STARTUP_LOADER_OPTIMIZATION_MASK`|<span data-ttu-id="6bff5-113">Gibt an, dass eine Ladeprogrammoptimierung stattfinden soll.</span><span class="sxs-lookup"><span data-stu-id="6bff5-113">Specifies that loader optimization shall occur.</span></span>|  
|`STARTUP_LOADER_OPTIMIZATION_SINGLE_DOMAIN`|<span data-ttu-id="6bff5-114">Gibt an, dass keine Assemblys als domänenneutral geladen werden.</span><span class="sxs-lookup"><span data-stu-id="6bff5-114">Specifies that no assemblies are loaded as domain-neutral.</span></span>|  
|`STARTUP_LOADER_OPTIMIZATION_MULTI_DOMAIN`|<span data-ttu-id="6bff5-115">Gibt an, dass alle Assemblys als domänenneutral geladen werden.</span><span class="sxs-lookup"><span data-stu-id="6bff5-115">Specifies that all assemblies are loaded as domain-neutral.</span></span>|  
|`STARTUP_LOADER_OPTIMIZATION_MULTI_DOMAIN_HOST`|<span data-ttu-id="6bff5-116">Gibt an, dass alle Assemblys mit starkem Namen als domänenneutral geladen werden.</span><span class="sxs-lookup"><span data-stu-id="6bff5-116">Specifies that all strong-named assemblies are loaded as domain-neutral.</span></span>|  
|`STARTUP_LOADER_SAFEMODE`|<span data-ttu-id="6bff5-117">Gibt an, dass die CLR-Versionsrichtlinie nicht auf die übergebene Version angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="6bff5-117">Specifies that CLR version policy will not be applied to the version passed in.</span></span> <span data-ttu-id="6bff5-118">Die angegebene Version der CLR wird geladen.</span><span class="sxs-lookup"><span data-stu-id="6bff5-118">The exact version specified of the CLR will be loaded.</span></span> <span data-ttu-id="6bff5-119">Das Startmodul wertet keine Richtlinien aus, um die neueste kompatible Version zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="6bff5-119">The shim does not evaluate policy to determine the latest compatible version.</span></span>|  
|`STARTUP_LOADER_SETPREFERENCE`|<span data-ttu-id="6bff5-120">Gibt an, dass die bevorzugte Laufzeit festgelegt, aber noch nicht gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="6bff5-120">Specifies that the preferred runtime will be set, but not actually started.</span></span>|  
|`STARTUP_SERVER_GC`|<span data-ttu-id="6bff5-121">Gibt an, dass die Garbage Collection auf dem Server verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="6bff5-121">Specifies that the server garbage collection will be used.</span></span>|  
|`STARTUP_HOARD_GC_VM`|<span data-ttu-id="6bff5-122">Gibt an, dass die Garbage Collection die verwendete virtuelle Adresse beibehält.</span><span class="sxs-lookup"><span data-stu-id="6bff5-122">Specifies that garbage collection will keep the virtual address used.</span></span>|  
|`STARTUP_SINGLE_VERSION_HOSTING_INTERFACE`|<span data-ttu-id="6bff5-123">Gibt an, dass das Kombinieren einer Hostingschnittstelle nicht zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="6bff5-123">Specifies that mixing a hosting interface will not be allowed.</span></span>|  
|`STARTUP_LEGACY_IMPERSONATION`|<span data-ttu-id="6bff5-124">Gibt an, dass ein Identitätswechsel standardmäßig nicht über asynchrone Punkte übergeben werden sollte.</span><span class="sxs-lookup"><span data-stu-id="6bff5-124">Specifies that impersonation should not flow across asynchronous points by default.</span></span>|  
|`STARTUP_DISABLE_COMMITTHREADSTACK`|<span data-ttu-id="6bff5-125">Gibt an, dass der vollständige Threadstapel nicht übergeben werden sollte, wenn die Ausführung des Threads beginnt.</span><span class="sxs-lookup"><span data-stu-id="6bff5-125">Specifies that the full thread stack should not be committed when the thread starts running.</span></span>|  
|`STARTUP_ALWAYSFLOW_IMPERSONATION`|<span data-ttu-id="6bff5-126">Gibt an, dass verwaltete Identitätswechsel und durch Plattformaufruf erreichte Identitätswechsel über asynchrone Punkte übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="6bff5-126">Specifies that managed impersonations and impersonations achieved through platform invoke will flow across asynchronous points.</span></span> <span data-ttu-id="6bff5-127">Standardmäßig werden nur verwaltete Identitätswechsel über asynchrone Punkte übergeben.</span><span class="sxs-lookup"><span data-stu-id="6bff5-127">By default, only managed impersonations will flow across asynchronous points.</span></span>|  
|`STARTUP_TRIM_GC_COMMIT`|<span data-ttu-id="6bff5-128">Gibt an, dass von der Garbage Collection weniger belegter Speicher verwendet wird, wenn der verfügbare Systemarbeitsspeicher zu gering ist.</span><span class="sxs-lookup"><span data-stu-id="6bff5-128">Specifies that garbage collection will use less committed space when system memory is low.</span></span> <span data-ttu-id="6bff5-129">Finden Sie unter `gcTrimCommitOnLowMemory` in [Optimierung für freigegebenes Webhosting](../../../../docs/standard/garbage-collection/optimization-for-shared-web-hosting.md).</span><span class="sxs-lookup"><span data-stu-id="6bff5-129">See `gcTrimCommitOnLowMemory` in [Optimization for Shared Web Hosting](../../../../docs/standard/garbage-collection/optimization-for-shared-web-hosting.md).</span></span>|  
|`STARTUP_ETW`|<span data-ttu-id="6bff5-130">Gibt an, dass die Ereignisablaufverfolgung für Windows (ETW) für Common Language Runtime-Ereignisse aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="6bff5-130">Specifies that event tracing for Windows (ETW) is enabled for common language runtime events.</span></span> <span data-ttu-id="6bff5-131">Ab Windows Vista, ist ereignisablaufverfolgung immer aktiviert, damit dieses Flag keine Auswirkung hat.</span><span class="sxs-lookup"><span data-stu-id="6bff5-131">Beginning with Windows Vista, event tracing is always enabled, so this flag has no effect.</span></span> <span data-ttu-id="6bff5-132">Finden Sie unter [Steuern der Protokollierung in .NET Framework](../../../../docs/framework/performance/controlling-logging.md).</span><span class="sxs-lookup"><span data-stu-id="6bff5-132">See [Controlling .NET Framework Logging](../../../../docs/framework/performance/controlling-logging.md).</span></span>|  
|`STARTUP_ARM`|<span data-ttu-id="6bff5-133">Gibt an, dass die Ressourcenüberwachung der Anwendungsdomäne aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="6bff5-133">Specifies that application domain resource monitoring is enabled.</span></span> <span data-ttu-id="6bff5-134">Finden Sie unter der <xref:System.AppDomain.MonitoringIsEnabled%2A?displayProperty=nameWithType> Eigenschaft und [ \<AppDomainResourceMonitoring >-Element](../../../../docs/framework/configure-apps/file-schema/runtime/appdomainresourcemonitoring-element.md).</span><span class="sxs-lookup"><span data-stu-id="6bff5-134">See the <xref:System.AppDomain.MonitoringIsEnabled%2A?displayProperty=nameWithType> property and [\<appDomainResourceMonitoring> Element](../../../../docs/framework/configure-apps/file-schema/runtime/appdomainresourcemonitoring-element.md).</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6bff5-135">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6bff5-135">Requirements</span></span>  
 <span data-ttu-id="6bff5-136">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6bff5-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6bff5-137">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="6bff5-137">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6bff5-138">**Bibliothek:** "Mscoree.dll"</span><span class="sxs-lookup"><span data-stu-id="6bff5-138">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6bff5-139">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6bff5-139">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6bff5-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6bff5-140">See Also</span></span>  
 [<span data-ttu-id="6bff5-141">Hosten von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="6bff5-141">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)