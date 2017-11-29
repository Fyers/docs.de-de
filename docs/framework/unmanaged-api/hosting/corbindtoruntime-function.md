---
title: CorBindToRuntime-Funktion
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorBindToRuntime
api_location:
- mscoree.dll
- mscoreei.dll
api_type: DLLExport
f1_keywords: CorBindToRuntime
helpviewer_keywords: CorBindToRuntime function [.NET Framework hosting]
ms.assetid: 799740aa-46ec-4532-95da-6444565b4971
topic_type: apiref
caps.latest.revision: "20"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a833be39f93082e8d2c0cb28f435f754143721f2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="corbindtoruntime-function"></a><span data-ttu-id="b58f9-102">CorBindToRuntime-Funktion</span><span class="sxs-lookup"><span data-stu-id="b58f9-102">CorBindToRuntime Function</span></span>
<span data-ttu-id="b58f9-103">Ermöglicht es nicht verwalteten Hosts, die Common Language Runtime (CLR) in einen Prozess zu laden.</span><span class="sxs-lookup"><span data-stu-id="b58f9-103">Enables unmanaged hosts to load the common language runtime (CLR) into a process.</span></span>  
  
 <span data-ttu-id="b58f9-104">Diese Funktion ist in [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] veraltet.</span><span class="sxs-lookup"><span data-stu-id="b58f9-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b58f9-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="b58f9-105">Syntax</span></span>  
  
```  
HRESULT CorBindToRuntime (  
    [in]  LPCWSTR     pwszVersion,   
    [in]  LPCWSTR     pwszBuildFlavor,   
    [in]  REFCLSID    rclsid,   
    [in]  REFIID      riid,   
    [out] LPVOID FAR  *ppv  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b58f9-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="b58f9-106">Parameters</span></span>  
 `pwszVersion`  
 <span data-ttu-id="b58f9-107">[in] Eine Zeichenfolge, die die Version der zu ladenden CLR beschreibt.</span><span class="sxs-lookup"><span data-stu-id="b58f9-107">[in] A string describing the version of the CLR you want to load.</span></span>  
  
 <span data-ttu-id="b58f9-108">Eine Versionsnummer in .NET Framework besteht aus vier Teilen, die durch Punkte getrennt: *"Hauptversion.Nebenversion.Build.Revision" vorliegen*.</span><span class="sxs-lookup"><span data-stu-id="b58f9-108">A version number in the .NET Framework consists of four parts separated by periods: *major.minor.build.revision*.</span></span> <span data-ttu-id="b58f9-109">Die als `pwszVersion` übergebene Zeichenfolge muss mit dem Buchstaben "v" beginnen, auf den die ersten drei Teile der Versionsnummer folgen (z. B. "v1.0.1529").</span><span class="sxs-lookup"><span data-stu-id="b58f9-109">The string passed as `pwszVersion` must start with the character "v" followed by the first three parts of the version number (for example, "v1.0.1529").</span></span>  
  
 <span data-ttu-id="b58f9-110">Einige Versionen der CLR werden mit einer Richtlinienanweisung installiert, welche die Kompatibilität mit früheren Versionen der CLR angibt.</span><span class="sxs-lookup"><span data-stu-id="b58f9-110">Some versions of the CLR are installed with a policy statement that specifies compatibility with previous versions of the CLR.</span></span> <span data-ttu-id="b58f9-111">In der Standardeinstellung wertet das Startmodul `pwszVersion` anhand von Richtlinienanweisungen aus und lädt die neueste Version der Common Language Runtime, die mit der angeforderten Version kompatibel ist.</span><span class="sxs-lookup"><span data-stu-id="b58f9-111">By default, the startup shim evaluates `pwszVersion` against policy statements and loads the latest version of the runtime that is compatible with the version being requested.</span></span> <span data-ttu-id="b58f9-112">Ein Host kann erzwingen, dass das Startmodul die Richtlinienauswertung überspringt und genau die in `pwszVersion` angegebene Version lädt, indem wie unten beschrieben der Wert `STARTUP_LOADER_SAFEMODE` für den `flags`-Parameter übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="b58f9-112">A host can force the shim to skip policy evaluation and load the exact version specified in `pwszVersion` by passing a value of  `STARTUP_LOADER_SAFEMODE` for the `flags` parameter, as described below.</span></span>  
  
 <span data-ttu-id="b58f9-113">Wenn der Aufrufer null für gibt `pwszVersion`, die neueste Version der Laufzeit geladen wird.</span><span class="sxs-lookup"><span data-stu-id="b58f9-113">If the caller specifies null for `pwszVersion`, the latest version of the runtime is loaded.</span></span> <span data-ttu-id="b58f9-114">Übergeben von Null erhält der Host keine Kontrolle über die Version der Laufzeit geladen wird.</span><span class="sxs-lookup"><span data-stu-id="b58f9-114">Passing null gives the host no control over which version of the runtime is loaded.</span></span> <span data-ttu-id="b58f9-115">Auch wenn dieser Ansatz in einigen Szenarien angemessen sein kann, wird das Angeben einer bestimmten zu ladenden Version durch den Host dringend empfohlen.</span><span class="sxs-lookup"><span data-stu-id="b58f9-115">Although this approach may be appropriate in some scenarios, it is strongly recommended that the host supply a specific version to load.</span></span>  
  
 `pwszBuildFlavor`  
 <span data-ttu-id="b58f9-116">[in] Eine Zeichenfolge, die angibt, ob der Serverbuild oder der Arbeitsstationsbuild der CLR geladen werden soll.</span><span class="sxs-lookup"><span data-stu-id="b58f9-116">[in] A string that specifies whether to load the server or the workstation build of the CLR.</span></span> <span data-ttu-id="b58f9-117">Gültige Werte sind `svr` und `wks`.</span><span class="sxs-lookup"><span data-stu-id="b58f9-117">Valid values are `svr` and `wks`.</span></span> <span data-ttu-id="b58f9-118">Der Serverbuild wurde so optimiert, dass mehrere Prozessoren zur Ausführung der Garbage Collection genutzt werden können. Der Arbeitsstationsbuild wurde für die Ausführung von Clientanwendungen auf einem Computer mit einem einzelnen Prozessor optimiert.</span><span class="sxs-lookup"><span data-stu-id="b58f9-118">The server build is optimized to take advantage of multiple processors for garbage collections, and the workstation build is optimized for client applications running on a single-processor machine.</span></span>  
  
 <span data-ttu-id="b58f9-119">Wenn `pwszBuildFlavor` auf festgelegt ist null, wird das Arbeitsstationsbuild geladen.</span><span class="sxs-lookup"><span data-stu-id="b58f9-119">If `pwszBuildFlavor` is set to null, the workstation build is loaded.</span></span> <span data-ttu-id="b58f9-120">Bei Ausführung auf einem Computer mit einem Prozessor wird immer das Arbeitsstationsbuild geladen, selbst wenn `pwszBuildFlavor` festgelegt ist, um `svr`.</span><span class="sxs-lookup"><span data-stu-id="b58f9-120">When running on a single-processor machine, the workstation build is always loaded, even if `pwszBuildFlavor` is set to `svr`.</span></span> <span data-ttu-id="b58f9-121">Jedoch wenn `pwszBuildFlavor` auf festgelegt ist `svr` und gleichzeitige Garbagecollection angegeben wird (finden Sie in der Beschreibung der `flags` Parameter), das Serverbuild geladen wird.</span><span class="sxs-lookup"><span data-stu-id="b58f9-121">However, if `pwszBuildFlavor` is set to `svr` and concurrent garbage collection is specified (see the description of the `flags` parameter), the server build is loaded.</span></span>  
  
 `rclsid`  
 <span data-ttu-id="b58f9-122">[in] Die `CLSID` der Co-Klasse, die entweder implementiert die [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) oder [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="b58f9-122">[in] The `CLSID` of the coclass that implements either the [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) or the [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) interface.</span></span> <span data-ttu-id="b58f9-123">Unterstützte Werte sind "CLSID_CorRuntimeHost" oder "CLSID_CLRRuntimeHost".</span><span class="sxs-lookup"><span data-stu-id="b58f9-123">Supported values are CLSID_CorRuntimeHost or CLSID_CLRRuntimeHost.</span></span>  
  
 `riid`  
 <span data-ttu-id="b58f9-124">[in] Die `IID` der angeforderten Schnittstelle aus `rclsid`.</span><span class="sxs-lookup"><span data-stu-id="b58f9-124">[in] The `IID` of the requested interface from `rclsid`.</span></span> <span data-ttu-id="b58f9-125">Unterstützte Werte sind "IID_ICorRuntimeHost" oder "IID_ICLRRuntimeHost".</span><span class="sxs-lookup"><span data-stu-id="b58f9-125">Supported values are IID_ICorRuntimeHost or IID_ICLRRuntimeHost.</span></span>  
  
 `ppv`  
 <span data-ttu-id="b58f9-126">[out] Der zurückgegebene Schnittstellenzeiger auf `riid`.</span><span class="sxs-lookup"><span data-stu-id="b58f9-126">[out] The returned interface pointer to `riid`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b58f9-127">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b58f9-127">Remarks</span></span>  
 <span data-ttu-id="b58f9-128">Wenn `pwszVersion` eine Laufzeitversion angibt, die nicht vorhanden ist, gibt `CorBindToRuntimeEx` den HRESULT-Wert CLR_E_SHIM_RUNTIMELOAD zurück.</span><span class="sxs-lookup"><span data-stu-id="b58f9-128">If `pwszVersion` specifies a runtime version that does not exist, `CorBindToRuntimeEx` returns an HRESULT value of CLR_E_SHIM_RUNTIMELOAD.</span></span>  
  
## <a name="execution-context-and-flow-of-windows-identity"></a><span data-ttu-id="b58f9-129">Ausführungskontext und Übergabe der Windows-Identität</span><span class="sxs-lookup"><span data-stu-id="b58f9-129">Execution Context and Flow of Windows Identity</span></span>  
 <span data-ttu-id="b58f9-130">In Version 1 der CLR wird das <xref:System.Security.Principal.WindowsIdentity>-Objekt nicht über asynchrone Punkte wie neue Threads, Threadpools oder Zeitgeberrückrufe übergeben.</span><span class="sxs-lookup"><span data-stu-id="b58f9-130">In version 1 of the CLR, the <xref:System.Security.Principal.WindowsIdentity> object does not flow across asynchronous points such as new threads, thread pools, or timer callbacks.</span></span> <span data-ttu-id="b58f9-131">In Version 2.0 der CLR umschließt ein <xref:System.Threading.ExecutionContext>-Objekt einige Informationen zum aktuell ausgeführten Thread und übergibt ihn über einen asynchronen Punkt, aber innerhalb der Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="b58f9-131">In version 2.0 of the CLR, an <xref:System.Threading.ExecutionContext> object wraps some information about the currently executing thread and flows it across any asynchronous point, but not across application domain boundaries.</span></span> <span data-ttu-id="b58f9-132">Auf ähnliche Weise wird auch das <xref:System.Security.Principal.WindowsIdentity>-Objekt über einen asynchronen Punkt übergeben.</span><span class="sxs-lookup"><span data-stu-id="b58f9-132">Similarly, the <xref:System.Security.Principal.WindowsIdentity> object also flows across any asynchronous point.</span></span> <span data-ttu-id="b58f9-133">Deshalb wird auch der aktuelle Identitätswechsel auf dem Thread (sofern vorhanden) übergeben.</span><span class="sxs-lookup"><span data-stu-id="b58f9-133">Therefore, the current impersonation on the thread, if any, flows too.</span></span>  
  
 <span data-ttu-id="b58f9-134">Sie können den Fluss auf zwei Weisen ändern:</span><span class="sxs-lookup"><span data-stu-id="b58f9-134">You can alter the flow in two ways:</span></span>  
  
1.  <span data-ttu-id="b58f9-135">Durch Ändern der <xref:System.Threading.ExecutionContext>-Einstellungen wird die Übergabe für einzelne Threads unterdrückt (siehe die Methoden <xref:System.Threading.ExecutionContext.SuppressFlow%2A>, <xref:System.Security.SecurityContext.SuppressFlow%2A> und <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A>).</span><span class="sxs-lookup"><span data-stu-id="b58f9-135">By modifying the <xref:System.Threading.ExecutionContext> settings to suppress the flow on a per-thread basis (see the <xref:System.Threading.ExecutionContext.SuppressFlow%2A>, <xref:System.Security.SecurityContext.SuppressFlow%2A>, and <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A> methods).</span></span>  
  
2.  <span data-ttu-id="b58f9-136">Durch Ändern des Prozessstandardmodus in den Kompatibilitätsmodus für Version 1; hier wird das <xref:System.Security.Principal.WindowsIdentity>-Objekt nicht über asynchrone Punkte übergeben, unabhängig von den <xref:System.Threading.ExecutionContext>-Einstellungen des aktuellen Threads.</span><span class="sxs-lookup"><span data-stu-id="b58f9-136">By changing the process default mode to the version 1 compatibility mode, where the <xref:System.Security.Principal.WindowsIdentity> object does not flow across any asynchronous point, regardless of the <xref:System.Threading.ExecutionContext> settings on the current thread.</span></span> <span data-ttu-id="b58f9-137">Wie der Standardmodus geändert wird, hängt davon ab, ob Sie zum Laden der CLR eine verwaltete ausführbare Datei oder eine nicht verwaltete Hostschnittstelle verwenden:</span><span class="sxs-lookup"><span data-stu-id="b58f9-137">How you change the default mode depends on whether you use a managed executable or an unmanaged hosting interface to load the CLR:</span></span>  
  
    1.  <span data-ttu-id="b58f9-138">Bei verwalteten ausführbaren Dateien, legen Sie die `enabled` Attribut des der [ \<LegacyImpersonationPolicy >](../../../../docs/framework/configure-apps/file-schema/runtime/legacyimpersonationpolicy-element.md) Element `true`.</span><span class="sxs-lookup"><span data-stu-id="b58f9-138">For managed executables, you must set the `enabled` attribute of the [\<legacyImpersonationPolicy>](../../../../docs/framework/configure-apps/file-schema/runtime/legacyimpersonationpolicy-element.md) element to `true`.</span></span>  
  
    2.  <span data-ttu-id="b58f9-139">Legen Sie bei nicht verwalteten Hostschnittstellen das `STARTUP_LEGACY_IMPERSONATION`-Flag im `flags`-Parameter fest, wenn Sie die `CorBindToRuntimeEx`-Funktion aufrufen.</span><span class="sxs-lookup"><span data-stu-id="b58f9-139">For unmanaged hosting interfaces, set the `STARTUP_LEGACY_IMPERSONATION` flag in the `flags` parameter when calling the `CorBindToRuntimeEx` function.</span></span>  
  
     <span data-ttu-id="b58f9-140">Der Kompatibilitätsmodus für Version 1 gilt für den gesamten Prozess und alle Anwendungsdomänen im Prozess.</span><span class="sxs-lookup"><span data-stu-id="b58f9-140">The version 1 compatibility mode applies to the entire process and to all the application domains in the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b58f9-141">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b58f9-141">Remarks</span></span>  
 <span data-ttu-id="b58f9-142">[CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) und `CorBindToRuntime` führen Sie den gleichen Vorgang, aber die `CorBindToRuntimeEx` -Funktion können Sie Flags festlegen, um das Verhalten der CLR anzugeben.</span><span class="sxs-lookup"><span data-stu-id="b58f9-142">[CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) and `CorBindToRuntime` perform the same operation, but the `CorBindToRuntimeEx` function allows you to set flags to specify the behavior of the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b58f9-143">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b58f9-143">Requirements</span></span>  
 <span data-ttu-id="b58f9-144">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b58f9-144">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b58f9-145">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b58f9-145">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b58f9-146">**Bibliothek:** "Mscoree.dll"</span><span class="sxs-lookup"><span data-stu-id="b58f9-146">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b58f9-147">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b58f9-147">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b58f9-148">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b58f9-148">See Also</span></span>  
 [<span data-ttu-id="b58f9-149">CorBindToCurrentRuntime-Funktion</span><span class="sxs-lookup"><span data-stu-id="b58f9-149">CorBindToCurrentRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)  
 [<span data-ttu-id="b58f9-150">CorBindToRuntimeByCfg-Funktion</span><span class="sxs-lookup"><span data-stu-id="b58f9-150">CorBindToRuntimeByCfg Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md)  
 [<span data-ttu-id="b58f9-151">CorBindToRuntimeEx-Funktion</span><span class="sxs-lookup"><span data-stu-id="b58f9-151">CorBindToRuntimeEx Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)  
 [<span data-ttu-id="b58f9-152">CorBindToRuntimeHost-Funktion</span><span class="sxs-lookup"><span data-stu-id="b58f9-152">CorBindToRuntimeHost Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md)  
 [<span data-ttu-id="b58f9-153">ICorRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b58f9-153">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)  
 [<span data-ttu-id="b58f9-154">Veraltete CLR-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="b58f9-154">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)