---
title: AssemblyAttributesGoHereSM
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: AssemblyAttributesGoHereSM
api_location: alink.dll
api_type: COM
f1_keywords: AssemblyAttributesGoHereSM
helpviewer_keywords:
- AssemblyAttributesGoHereSM type
- Alink API, AssemblyAttributesGoHereSM type
ms.assetid: 4cf9bf39-1527-49e0-a0e9-55e7a018bf66
topic_type: apiref
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 912bd97b0b907f9edb27254bbf3419a684e6d697
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="assemblyattributesgoheresm"></a><span data-ttu-id="b36c6-102">AssemblyAttributesGoHereSM</span><span class="sxs-lookup"><span data-stu-id="b36c6-102">AssemblyAttributesGoHereSM</span></span>
<span data-ttu-id="b36c6-103">Wird von ALink als Platzhalter verwendet, um Informationen über benutzerdefinierte Attribute zu speichern.</span><span class="sxs-lookup"><span data-stu-id="b36c6-103">Used by ALink as a placeholder to store information about custom attributes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b36c6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b36c6-104">Syntax</span></span>  
  
```  
AssemblyAttributeGoHereSM  
```  
  
## <a name="remarks"></a><span data-ttu-id="b36c6-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b36c6-105">Remarks</span></span>  
 <span data-ttu-id="b36c6-106">Verweise auf diesen Typ können in NETMODULE-Dateien eingebettet sein, deren Quellen benutzerdefinierte Assemblyattribute enthalten.</span><span class="sxs-lookup"><span data-stu-id="b36c6-106">References to this type might be embedded inside netmodules whose sources contain assembly custom attributes.</span></span> <span data-ttu-id="b36c6-107">Beim Erstellen eines Assemblymanifests aus mindestens einer NETMODULE-Datei, die Verweise auf diese Typen enthält, verwendet ALink die zu diesen Verweisen gehörenden Informationen, um echte benutzerdefinierte Attribute auszugeben.</span><span class="sxs-lookup"><span data-stu-id="b36c6-107">When building an assembly manifest from one or more netmodules that contain references to these types, ALink uses information attached to these references to emit real custom attributes.</span></span> <span data-ttu-id="b36c6-108">Daher wird dieser Typ nie instanziiert, und Verweise auf diesen Typ werden nur als Teil des Buildprozesses verwendet und erfüllen in der endgültigen Assembly keinen Zweck.</span><span class="sxs-lookup"><span data-stu-id="b36c6-108">As such, this type is never instantiated, and references to it are used only as part of the build process and serve no purpose in the final assembly.</span></span>  
  
 <span data-ttu-id="b36c6-109">Verweise auf diesen Typ geben benutzerdefinierte Attribute an, die sicherheitsrelevant sind und mehrfach verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b36c6-109">References to this type indicate custom attributes that are security related and multiple-use.</span></span>  
  
 <span data-ttu-id="b36c6-110">Diese Typen sind in .NET Framework mit "intern" markiert und befinden sich in <xref:System.Runtime.CompilerServices>.</span><span class="sxs-lookup"><span data-stu-id="b36c6-110">These types are marked "internal" within the .NET Framework, and are located in <xref:System.Runtime.CompilerServices>.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b36c6-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b36c6-111">Requirements</span></span>  
 <span data-ttu-id="b36c6-112">mscorlib.dll</span><span class="sxs-lookup"><span data-stu-id="b36c6-112">mscorlib.dll</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b36c6-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b36c6-113">See Also</span></span>  
 [<span data-ttu-id="b36c6-114">AssemblyAttributesGoHere</span><span class="sxs-lookup"><span data-stu-id="b36c6-114">AssemblyAttributesGoHere</span></span>](../../../../docs/framework/unmanaged-api/alink/assemblyattributesgohere.md)  
 [<span data-ttu-id="b36c6-115">AssemblyAttributesGoHereM</span><span class="sxs-lookup"><span data-stu-id="b36c6-115">AssemblyAttributesGoHereM</span></span>](../../../../docs/framework/unmanaged-api/alink/assemblyattributesgoherem.md)  
 [<span data-ttu-id="b36c6-116">AssemblyAttributesGoHereS</span><span class="sxs-lookup"><span data-stu-id="b36c6-116">AssemblyAttributesGoHereS</span></span>](../../../../docs/framework/unmanaged-api/alink/assemblyattributesgoheres.md)