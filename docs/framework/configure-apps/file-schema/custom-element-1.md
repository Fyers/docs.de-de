---
title: "Benutzerdefiniertes Element für \"SingleTagSectionHandler\""
ms.date: 05/01/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
f1_keywords: http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName
helpviewer_keywords: custom element
ms.assetid: e62056c6-b351-40eb-afc0-cc13fc44e45e
author: guardrex
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 496967bc3638344d2b39d428b85270b575b325ed
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="custom-element-for-singletagsectionhandler"></a><span data-ttu-id="8daac-102">Benutzerdefiniertes Element für "SingleTagSectionHandler"</span><span class="sxs-lookup"><span data-stu-id="8daac-102">Custom element for SingleTagSectionHandler</span></span>

<span data-ttu-id="8daac-103">Definiert die Einstellungen in eine benutzerdefinierte Konfigurationsabschnitt, der von definiert wird ein</span><span class="sxs-lookup"><span data-stu-id="8daac-103">Defines settings in a custom configuration section that is defined by a</span></span> <section> <span data-ttu-id="8daac-104">Element- und verwendet die <xref:System.Configuration.SingleTagSectionHandler> Klasse.</span><span class="sxs-lookup"><span data-stu-id="8daac-104">element and uses the <xref:System.Configuration.SingleTagSectionHandler> class.</span></span>

<span data-ttu-id="8daac-105">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="8daac-105">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="8daac-106">&nbsp;&nbsp;*\<SectionName >*</span><span class="sxs-lookup"><span data-stu-id="8daac-106">&nbsp;&nbsp;*\<sectionName>*</span></span>

## <a name="syntax"></a><span data-ttu-id="8daac-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="8daac-107">Syntax</span></span>

```xml
<sectionName key="value" key2="value2" ... />
```

## <a name="attributes"></a><span data-ttu-id="8daac-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="8daac-108">Attributes</span></span>

<span data-ttu-id="8daac-109">Attribute und Attributwerte werden vom Benutzer definiert sind.</span><span class="sxs-lookup"><span data-stu-id="8daac-109">Attributes and attribute values are user defined.</span></span>

## <a name="parent-element"></a><span data-ttu-id="8daac-110">Übergeordnetes Element</span><span class="sxs-lookup"><span data-stu-id="8daac-110">Parent element</span></span>

|     | <span data-ttu-id="8daac-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8daac-111">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="8daac-112">**\<configuration>**</span><span class="sxs-lookup"><span data-stu-id="8daac-112">**\<configuration>**</span></span>](~/docs/framework/configure-apps/file-schema/configuration-element.md) | <span data-ttu-id="8daac-113">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="8daac-113">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="8daac-114">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8daac-114">Child elements</span></span>

<span data-ttu-id="8daac-115">Keine</span><span class="sxs-lookup"><span data-stu-id="8daac-115">None</span></span>

## <a name="remarks"></a><span data-ttu-id="8daac-116">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8daac-116">Remarks</span></span>

<span data-ttu-id="8daac-117">Die  **\<SectionName >** Element ist ein benutzerdefiniertes Element definiert, indem Sie eine [  **\<Abschnitt >** ](~/docs/framework/configure-apps/file-schema/section-element.md) -Tag in die [  **\<ConfigSections >** ](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) Element.</span><span class="sxs-lookup"><span data-stu-id="8daac-117">The **\<sectionName>** element is a custom element defined by a [**\<section>**](~/docs/framework/configure-apps/file-schema/section-element.md) tag in the [**\<configSections>**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) element.</span></span> <span data-ttu-id="8daac-118">Gibt das Konfigurationssystem ein <xref:System.Collections.IDictionary> Objekt beim Aufrufen von <xref:System.Configuration.Configuration.GetSection(System.String)?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="8daac-118">The configuration system returns a <xref:System.Collections.IDictionary> object when you call <xref:System.Configuration.Configuration.GetSection(System.String)?displayProperty=nameWithType>.</span></span>

## <a name="example"></a><span data-ttu-id="8daac-119">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8daac-119">Example</span></span>

<span data-ttu-id="8daac-120">Das folgende Beispiel deklariert ein benutzerdefiniertes Element aufgerufen  **\<SampleSection >** enthält Einstellungen, die durch Lesen der <xref:System.Configuration.SingleTagSectionHandler> Klasse:</span><span class="sxs-lookup"><span data-stu-id="8daac-120">The following example declares a custom element called **\<sampleSection>** that contains settings read by the <xref:System.Configuration.SingleTagSectionHandler> class:</span></span>

```xml
<configuration>
  <configSections>
    <section name="sampleSection" 
             type="System.Configuration.SingleTagSectionHandler" />
  </configSections>
  <sampleSection setting1="Value1" 
                 setting2="value two" 
                 setting3="third value" />
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="8daac-121">Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="8daac-121">Configuration file</span></span>

<span data-ttu-id="8daac-122">Dieses Element kann in der Anwendungskonfigurationsdatei Computerkonfigurationsdatei verwendet werden (*"Machine.config"*), und *"Web.config"* Dateien, die nicht auf Anwendungsebene Verzeichnis sind.</span><span class="sxs-lookup"><span data-stu-id="8daac-122">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="8daac-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8daac-123">See also</span></span>

[<span data-ttu-id="8daac-124">Konfigurationsdateischema für .NET Framework</span><span class="sxs-lookup"><span data-stu-id="8daac-124">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)