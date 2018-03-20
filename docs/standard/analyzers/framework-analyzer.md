---
title: "Die .NET Security Analyzer – .NET"
description: Erfahren Sie, wie Sie die .NET Security Analyzer im Pakt mit den .NET Framework-Analyzern verwenden, um Sicherheitsrisiken zu ermitteln und zu beheben.
keywords: .NET, .NET Core
author: billwagner
ms.author: billwagner
ms.date: 01/25/2018
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.openlocfilehash: 06a387d72d06609182c8894dd874b241a5d7b69c
ms.sourcegitcommit: 3a96c706e4dbb4667bf3bf37edac9e1666646f93
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/27/2018
---
# <a name="the-net-framework-analyzer"></a><span data-ttu-id="adf71-104">Der .NET Framework Analyzer</span><span class="sxs-lookup"><span data-stu-id="adf71-104">The .NET Framework Analyzer</span></span>

<span data-ttu-id="adf71-105">Sie können den .NET Framework Analyzer verwenden, um potenzielle Probleme in Ihrem auf .NET Framework basierenden Anwendungscode zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="adf71-105">You can use the .NET Framework Analyzer to find potential issues in your .NET Framework-based application code.</span></span> <span data-ttu-id="adf71-106">Dieses Analysetool findet mögliche Probleme und schlägt Lösungen zu deren Behebung vor.</span><span class="sxs-lookup"><span data-stu-id="adf71-106">This analyzer finds potential issues and suggests fixes to them.</span></span>

<span data-ttu-id="adf71-107">Das Analysetool wird interaktiv in Visual Studio ausgeführt, während Sie Code schreiben, oder im Rahmen eines CI-Builds.</span><span class="sxs-lookup"><span data-stu-id="adf71-107">The analyzer runs interactively in Visual Studio as you write your code or as part of a CI build.</span></span> <span data-ttu-id="adf71-108">Sie sollten das Analysetool Ihrem Projekt so früh wie möglich im Entwicklungszyklus hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="adf71-108">You should add the analyzer to your project as early as possible in your development.</span></span> <span data-ttu-id="adf71-109">Je früher Sie potenzielle Probleme in Ihrem Code finden, desto einfacher lassen sie sich beheben.</span><span class="sxs-lookup"><span data-stu-id="adf71-109">The sooner you find any potential issues in your code, the easier they are to fix.</span></span> <span data-ttu-id="adf71-110">Sie können das Tool aber zu jedem Zeitpunkt im Entwicklungszyklus hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="adf71-110">However, you can add it at any time in the development cycle.</span></span> <span data-ttu-id="adf71-111">Es findet Probleme mit vorhandenem Code und warnt bei neuen Problemen, wenn Sie mit der Entwicklung fortfahren.</span><span class="sxs-lookup"><span data-stu-id="adf71-111">It finds any issues with the existing code and warns about new issues as you keep developing.</span></span>

## <a name="installing-and-configuring-the-net-framework-analyzer"></a><span data-ttu-id="adf71-112">Installieren und Konfigurieren des .NET Framework Analyzers</span><span class="sxs-lookup"><span data-stu-id="adf71-112">Installing and configuring the .NET Framework Analyzer</span></span>

<span data-ttu-id="adf71-113">Die .NET Security Analyzer müssen als NuGet-Paket in jedem Projekt installiert werden, in dem sie ausgeführt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="adf71-113">The .NET Security Analyzers must be installed as a NuGet package on every project where you want them to run.</span></span> <span data-ttu-id="adf71-114">Sie müssen nur von einem Entwickler zum Projekt hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="adf71-114">Only one developer needs to add them to the project.</span></span> <span data-ttu-id="adf71-115">Das Analyzerpaket stellt eine Projektabhängigkeit dar und wird auf den Computern aller Entwickler ausgeführt, sobald eine aktualisierte Projektmappe vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="adf71-115">The analyzer package is a project dependency and will run on every developer's machine once it has the updated solution.</span></span>

<span data-ttu-id="adf71-116">Der .NET Framework Analyzer wird im NuGet-Paket [Microsoft.NetFramework.Analyzers](https://www.nuget.org/packages/Microsoft.NetFramework.Analyzers/) bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="adf71-116">The .NET Framework Analyzer is delivered in the [Microsoft.NetFramework.Analyzers](https://www.nuget.org/packages/Microsoft.NetFramework.Analyzers/) NuGet package.</span></span> <span data-ttu-id="adf71-117">Dieses Paket stellt nur die spezifischen Analysetools für das .NET Framework bereit und umfasst auch Sicherheitsanalysetools.</span><span class="sxs-lookup"><span data-stu-id="adf71-117">This package provides only the analyzers specific to the .NET Framework, which includes security analyzers.</span></span> <span data-ttu-id="adf71-118">In den meisten Fällen werden Sie das NuGet-Paket [Microsoft.CodeAnalysis.FxCopAnalyzers](https://www.nuget.org/packages/Microsoft.CodeAnalysis.FxCopAnalyzers) benötigen.</span><span class="sxs-lookup"><span data-stu-id="adf71-118">In most cases, you'll want the [Microsoft.CodeAnalysis.FxCopAnalyzers](https://www.nuget.org/packages/Microsoft.CodeAnalysis.FxCopAnalyzers) NuGet package.</span></span> <span data-ttu-id="adf71-119">Das aggregierte FxCopAnalyzers-Paket enthält alle Framework-Analysetools im Framework.Analyzers-Paket sowie die folgenden Analysetools:</span><span class="sxs-lookup"><span data-stu-id="adf71-119">The FxCopAnalyzers aggregate package contains all the framework analyzers included in the Framework.Analyzers package as well as the following analyzers:</span></span>
- <span data-ttu-id="adf71-120">[Microsoft.CodeQuality.Analyzers](https://www.nuget.org/packages/Microsoft.CodeQuality.Analyzers): Bietet allgemeine Empfehlungen und Empfehlungen für .NET Standard-APIs.</span><span class="sxs-lookup"><span data-stu-id="adf71-120">[Microsoft.CodeQuality.Analyzers](https://www.nuget.org/packages/Microsoft.CodeQuality.Analyzers): Provides general guidance and guidance for .NET Standard APIs</span></span>
- <span data-ttu-id="adf71-121">[Microsoft.NetCore.Analyzers](https://www.nuget.org/packages/Microsoft.NetCore.Analyzers): Bietet Analysetools speziell für .NET Core-APIs.</span><span class="sxs-lookup"><span data-stu-id="adf71-121">[Microsoft.NetCore.Analyzers](https://www.nuget.org/packages/Microsoft.NetCore.Analyzers): Provides analyzers specific to .NET Core APIs.</span></span>
- <span data-ttu-id="adf71-122">[Text.Analyzers](https://www.nuget.org/packages/Text.Analyzers): Bietet Empfehlungen für in Form von Code bereitgestellten Text, einschließlich Kommentaren.</span><span class="sxs-lookup"><span data-stu-id="adf71-122">[Text.Analyzers](https://www.nuget.org/packages/Text.Analyzers): Provides guidance for text included as code, including comments.</span></span>

<span data-ttu-id="adf71-123">Um das Paket zu installieren, klicken Sie mit der rechten Maustaste auf das Projekt, und wählen Sie „Abhängigkeiten verwalten“ aus.</span><span class="sxs-lookup"><span data-stu-id="adf71-123">To install it, right-click on the project, and select "Manage Dependencies".</span></span>
<span data-ttu-id="adf71-124">Suchen Sie im NuGet-Explorer nach „NetFramework Analyzer“ oder nach „Fx Cop Analyzer“, wenn Sie Letzteren bevorzugen.</span><span class="sxs-lookup"><span data-stu-id="adf71-124">From the NuGet explorer, search for "NetFramework Analyzer", or if you prefer, "Fx Cop Analyzer".</span></span> <span data-ttu-id="adf71-125">Installieren Sie die letzte als stabil bekannte Version in allen Projekten Ihrer Projektmappe.</span><span class="sxs-lookup"><span data-stu-id="adf71-125">Install the latest stable version in all projects in your solution.</span></span>

## <a name="using-the-net-framework-analyzer"></a><span data-ttu-id="adf71-126">Verwenden des .NET Framework Analyzers</span><span class="sxs-lookup"><span data-stu-id="adf71-126">Using the .NET Framework Analyzer</span></span>

<span data-ttu-id="adf71-127">Sobald das NuGet-Paket installiert ist, erstellen Sie Ihre Projektmappe.</span><span class="sxs-lookup"><span data-stu-id="adf71-127">Once the NuGet package is installed, build your solution.</span></span> <span data-ttu-id="adf71-128">Das Analysetool meldet alle Probleme, die es in Ihrer Codebasis ermittelt.</span><span class="sxs-lookup"><span data-stu-id="adf71-128">The analyzer will report any issues it locates in your codebase.</span></span> <span data-ttu-id="adf71-129">Die Probleme werden in Form von Warnungen im Visual Studio-Fenster „Fehlerliste“ gemeldet, wie in der folgenden Abbildung veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="adf71-129">The issues are reported as warnings in the Visual Studio Error List window, as shown in the following image:</span></span>

![Probleme, die vom Framework Analyzer gemeldet werden.](./media/framework-analyzers-2.png)

<span data-ttu-id="adf71-131">Während Sie Code schreiben, werden potenzielle Probleme mit Wellenlinien unter dem fraglichen Codesegment angezeigt.</span><span class="sxs-lookup"><span data-stu-id="adf71-131">As you write code, you see squiggles underneath any potential issue in your code.</span></span>
<span data-ttu-id="adf71-132">Wenn Sie mit der Maus auf ein potenzielles Problem zeigen, werden Details zum Problem sowie Vorschläge für eine mögliche Behebung angezeigt, wie in der folgenden Abbildung veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="adf71-132">Hover over any issue and you see details about the issue, and suggestions for any possible fix, as shown in the following image:</span></span>

![Interaktiver Bericht zu Fehlern, die vom Framework-Analysetool gefunden wurden](./media/framework-analyzers-1.png)

<span data-ttu-id="adf71-134">Die Analysetools untersuchen den Code in Ihrer Projektmappe und liefern Ihnen eine Liste mit Warnungen zu jedem dieser möglichen Probleme:</span><span class="sxs-lookup"><span data-stu-id="adf71-134">The analyzers examine the code in your solution and provide you with a list of warnings for any of these issues:</span></span>

### <a name="ca1058-types-should-not-extend-certain-base-types"></a><span data-ttu-id="adf71-135">CA1058: Typen sollten bestimmte Basistypen nicht erweitern</span><span class="sxs-lookup"><span data-stu-id="adf71-135">CA1058: Types should not extend certain base types</span></span>

<span data-ttu-id="adf71-136">Es gibt einige wenige Typen in .NET Framework, aus denen Sie nicht direkt ableiten sollten.</span><span class="sxs-lookup"><span data-stu-id="adf71-136">There are a small number of types in the .NET Framework that you should not derived from directly.</span></span> 

<span data-ttu-id="adf71-137">**Kategorie:** Entwurf</span><span class="sxs-lookup"><span data-stu-id="adf71-137">**Category:** Design</span></span>

<span data-ttu-id="adf71-138">**Schweregrad:** Warnung</span><span class="sxs-lookup"><span data-stu-id="adf71-138">**Severity:** Warning</span></span>

<span data-ttu-id="adf71-139">Zusatzinformationen: [CA1058: Typen sollten bestimmte Basistypen nicht erweitern](/visualstudio/code-quality/ca1058-types-should-not-extend-certain-base-types)</span><span class="sxs-lookup"><span data-stu-id="adf71-139">Additional information: [CA:1058: Types should not extend certain base types](/visualstudio/code-quality/ca1058-types-should-not-extend-certain-base-types)</span></span>

### <a name="ca2153-do-not-catch-corrupted-state-exceptions"></a><span data-ttu-id="adf71-140">CA2153: Keine Corrupted State Exceptions abfangen</span><span class="sxs-lookup"><span data-stu-id="adf71-140">CA2153: Do not catch corrupted state exceptions</span></span>

<span data-ttu-id="adf71-141">Durch das Abfangen von Corrupted State Exceptions könnten Fehler (z.B. Zugriffsverletzungen) verschleiert werden, was zu einem inkonsistenten Ausführungsstatus führen oder es Angreifern erleichtern könnte, ein System zu gefährden.</span><span class="sxs-lookup"><span data-stu-id="adf71-141">Catching corrupted state exceptions could mask errors (such as access violations), resulting in an inconsistent state of execution or making it easier for attackers to compromise a system.</span></span> <span data-ttu-id="adf71-142">Fangen Sie stattdessen einen spezifischeren Satz von Ausnahmetypen ab, und behandeln Sie diese, oder lösen Sie die Ausnahme erneut aus.</span><span class="sxs-lookup"><span data-stu-id="adf71-142">Instead, catch and handle a more specific set of exception type(s) or re-throw the exception</span></span>

<span data-ttu-id="adf71-143">**Kategorie:** Sicherheit</span><span class="sxs-lookup"><span data-stu-id="adf71-143">**Category:** Security</span></span>

<span data-ttu-id="adf71-144">**Schweregrad:** Warnung</span><span class="sxs-lookup"><span data-stu-id="adf71-144">**Severity:** Warning</span></span>

<span data-ttu-id="adf71-145">Zusatzinformationen; [CA2153: Keine Corrupted State Exceptions abfangen](/visualstudio/code-quality/ca2153-avoid-handling-corrupted-state-exceptions)</span><span class="sxs-lookup"><span data-stu-id="adf71-145">Additional information: [## CA2153: Do not catch corrupted state exceptions](/visualstudio/code-quality/ca2153-avoid-handling-corrupted-state-exceptions)</span></span>

### <a name="ca2229-implement-serialization-constructors"></a><span data-ttu-id="adf71-146">CA2229: Serialisierungskonstruktoren implementieren</span><span class="sxs-lookup"><span data-stu-id="adf71-146">CA2229: Implement serialization constructors</span></span>

<span data-ttu-id="adf71-147">Das Analysetool generiert diese Warnung, wenn Sie einen Typ erstellen, der die <xref:System.Runtime.Serialization.ISerializable>-Schnittstelle implementiert, aber den erforderlichen Serialisierungskonstruktor nicht definiert.</span><span class="sxs-lookup"><span data-stu-id="adf71-147">The analyzer generates this warning when you create a type that implements the <xref:System.Runtime.Serialization.ISerializable> interface but does not define the required serialization constructor.</span></span> <span data-ttu-id="adf71-148">Um einen Verstoß gegen diese Regel zu beheben, implementieren Sie den Serialisierungskonstruktor.</span><span class="sxs-lookup"><span data-stu-id="adf71-148">To fix a violation of this rule, implement the serialization constructor.</span></span> <span data-ttu-id="adf71-149">Definieren Sie den Konstruktor bei einer versiegelten Klasse als privaten Konstruktor. Definieren Sie ihn andernfalls als geschützten Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="adf71-149">For a sealed class, make the constructor private; otherwise, make it protected.</span></span> <span data-ttu-id="adf71-150">Der Serialisierungskonstruktor weist die folgende Signatur auf:</span><span class="sxs-lookup"><span data-stu-id="adf71-150">The serialization constructor has the following signature:</span></span>

```csharp
public class MyItemType
{
    // The special constructor is used to deserialize values.
    public MyItemType(SerializationInfo info, StreamingContext context)
    {
        // implementation removed.
    }
}
```

<span data-ttu-id="adf71-151">**Kategorie:** Verwendung</span><span class="sxs-lookup"><span data-stu-id="adf71-151">**Category:** Usage</span></span>

<span data-ttu-id="adf71-152">**Schweregrad:** Warnung</span><span class="sxs-lookup"><span data-stu-id="adf71-152">**Severity:** Warning</span></span>

<span data-ttu-id="adf71-153">Zusatzinformationen: [CA2229: Serialisierungskonstruktoren implementieren](/visualstudio/code-quality/ca2229-implement-serialization-constructors)</span><span class="sxs-lookup"><span data-stu-id="adf71-153">Additional information: [CA2229: Implement serialization constructors](/visualstudio/code-quality/ca2229-implement-serialization-constructors)</span></span>

### <a name="ca2235-mark-all-non-serializable-fields"></a><span data-ttu-id="adf71-154">CA2235: Alle nicht serialisierbaren Felder markieren</span><span class="sxs-lookup"><span data-stu-id="adf71-154">CA2235: Mark all non-serializable fields</span></span>

<span data-ttu-id="adf71-155">Ein Instanzenfeld eines Typs, der nicht serialisierbar ist, ist in einem serialisierbaren Typ deklariert.</span><span class="sxs-lookup"><span data-stu-id="adf71-155">An instance field of a type that is not serializable is declared in a type that is serializable.</span></span> <span data-ttu-id="adf71-156">Sie müssen dieses Feld explizit mit dem <xref:System.NonSerializedAttribute> markieren, um diese Warnung zu beheben.</span><span class="sxs-lookup"><span data-stu-id="adf71-156">You must explicitly mark that field with the <xref:System.NonSerializedAttribute> to fix this warning.</span></span>

<span data-ttu-id="adf71-157">**Kategorie:** Verwendung</span><span class="sxs-lookup"><span data-stu-id="adf71-157">**Category:** Usage</span></span>

<span data-ttu-id="adf71-158">**Schweregrad:** Warnung</span><span class="sxs-lookup"><span data-stu-id="adf71-158">**Severity:** Warning</span></span>

<span data-ttu-id="adf71-159">Zusatzinformationen: [CA2235: Alle nicht serialisierbaren Felder markieren](/visualstudio/code-quality/ca2235-mark-all-non-serializable-fields)</span><span class="sxs-lookup"><span data-stu-id="adf71-159">Additional information: [CA2235: Mark all non-serializable fields](/visualstudio/code-quality/ca2235-mark-all-non-serializable-fields)</span></span>

### <a name="ca2237-mark-iserializable-types-with-serializable"></a><span data-ttu-id="adf71-160">CA2237: ISerializable-Typen als serialisierbar markieren</span><span class="sxs-lookup"><span data-stu-id="adf71-160">CA2237: Mark ISerializable types with serializable</span></span>

<span data-ttu-id="adf71-161">Damit Typen von der Common Language Runtime als serialisierbar erkannt werden, müssen sie mit dem <xref:System.SerializableAttribute>-Attribut markiert werden, auch wenn der Typ durch die Implementierung der <xref:System.Runtime.Serialization.ISerializable>-Schnittstelle eine benutzerdefinierte Serialisierungsroutine verwendet.</span><span class="sxs-lookup"><span data-stu-id="adf71-161">To be recognized by the common language runtime as serializable, types must be marked by using the <xref:System.SerializableAttribute> attribute even when the type uses a custom serialization routine by implementing the <xref:System.Runtime.Serialization.ISerializable> interface.</span></span>

<span data-ttu-id="adf71-162">**Kategorie:** Verwendung</span><span class="sxs-lookup"><span data-stu-id="adf71-162">**Category:** Usage</span></span>

<span data-ttu-id="adf71-163">**Schweregrad:** Warnung</span><span class="sxs-lookup"><span data-stu-id="adf71-163">**Severity:** Warning</span></span>

<span data-ttu-id="adf71-164">Zusatzinformationen: [CA2237: ISerializable-Typen als serialisierbar markieren](/visualstudio/code-quality/ca2237-mark-iserializable-types-with-serializableattribute)</span><span class="sxs-lookup"><span data-stu-id="adf71-164">Additional information: [CA2237: Mark ISerializable types with serializable](/visualstudio/code-quality/ca2237-mark-iserializable-types-with-serializableattribute)</span></span>

### <a name="ca3075-insecure-dtd-processing-in-xml"></a><span data-ttu-id="adf71-165">CA3075: Unsichere DTD-Verarbeitung in XML</span><span class="sxs-lookup"><span data-stu-id="adf71-165">CA3075: Insecure DTD processing in XML</span></span>

<span data-ttu-id="adf71-166">Wenn Sie unsichere <xref:System.Xml.XmlReaderSettings.DtdProcessing%2A> -Instanzen oder externe Entitätsquellen verweisen, kann der Parser unter Umständen nicht vertrauenswürdige Eingaben akzeptieren und Angreifern vertrauliche Informationen offenlegen.</span><span class="sxs-lookup"><span data-stu-id="adf71-166">If you use insecure <xref:System.Xml.XmlReaderSettings.DtdProcessing%2A> instances or reference external entity sources, the parser may accept untrusted input and disclose sensitive information to attackers.</span></span>  

<span data-ttu-id="adf71-167">**Kategorie:** Sicherheit</span><span class="sxs-lookup"><span data-stu-id="adf71-167">**Category:** Security</span></span>

<span data-ttu-id="adf71-168">**Schweregrad:** Warnung</span><span class="sxs-lookup"><span data-stu-id="adf71-168">**Severity:** Warning</span></span>

<span data-ttu-id="adf71-169">Zusatzinformationen: [A3075: Unsichere DTD-Verarbeitung in XML](/visualstudio/code-quality/ca2237-mark-iserializable-types-with-serializableattribute)</span><span class="sxs-lookup"><span data-stu-id="adf71-169">Additional information: [A3075: Insecure DTD processing in XML](/visualstudio/code-quality/ca2237-mark-iserializable-types-with-serializableattribute)</span></span>


### <a name="ca5350-do-not-use-weak-cryptographic-algorithms"></a><span data-ttu-id="adf71-170">CA5350: Keine schwachen Kryptografiealgorithmen verwenden</span><span class="sxs-lookup"><span data-stu-id="adf71-170">CA5350: Do not use weak cryptographic algorithms</span></span>

<span data-ttu-id="adf71-171">Kryptografiealgorithmen verlieren im Lauf der Zeit an Stärke, da Angriffe immer ausgefeilter werden.</span><span class="sxs-lookup"><span data-stu-id="adf71-171">Cryptographic algorithms degrade over time as attacks become more advanced.</span></span> <span data-ttu-id="adf71-172">Je nach Typ und Anwendung dieses Kryptografiealgorithmus kann eine weitere Verschlechterung der kryptografischen Stärke dazu führen, dass Angreifer verschlüsselte Nachrichten lesen und manipulieren, digitale Signaturen fälschen, Hashinhalte manipulieren oder auf andere Weise ein Kryptografiesystem gefährden, das auf diesem Algorithmus basiert.</span><span class="sxs-lookup"><span data-stu-id="adf71-172">Depending on the type and application of this cryptographic algorithm, further degradation of its cryptographic strength may allow attackers to read enciphered messages, tamper with enciphered messages, forge digital signatures, tamper with hashed content, or otherwise compromise any cryptosystem based on this algorithm.</span></span> <span data-ttu-id="adf71-173">Verwenden Sie für die Verschlüsselung einen AES-Algorithmus (AES-256, AES-192 und AES-128 sind akzeptabel) mit einer Schlüssellänge von mindestens 128 Bits.</span><span class="sxs-lookup"><span data-stu-id="adf71-173">For encryption, use an AES algorithm (AES-256, AES-192 and AES-128 are acceptable) with a key length greater than or equal to 128 bits.</span></span> <span data-ttu-id="adf71-174">Verwenden Sie für das Hashing eine Hashfunktion in der SHA-2-Familie, wie z.B. SHA-2 512, SHA-2 384 oder SHA-2 256.</span><span class="sxs-lookup"><span data-stu-id="adf71-174">For hashing, use a hashing function in the SHA-2 family, such as SHA-2 512, SHA-2 384, or SHA-2 256.</span></span>

<span data-ttu-id="adf71-175">**Kategorie:** Sicherheit</span><span class="sxs-lookup"><span data-stu-id="adf71-175">**Category:** Security</span></span>

<span data-ttu-id="adf71-176">**Schweregrad:** Warnung</span><span class="sxs-lookup"><span data-stu-id="adf71-176">**Severity:** Warning</span></span>

<span data-ttu-id="adf71-177">Zusatzinformationen: [CA5350: Keine schwachen Kryptografiealgorithmen verwenden](/visualstudio/code-quality/ca5350-do-not-use-weak-cryptographic-algorithms)</span><span class="sxs-lookup"><span data-stu-id="adf71-177">Additional information: [CA5350: Do not use weak cryptographic algorithms](/visualstudio/code-quality/ca5350-do-not-use-weak-cryptographic-algorithms)</span></span>

### <a name="ca5351-do-not-use-broken-cryptographic-algorithms"></a><span data-ttu-id="adf71-178">CA5351 Keine durchbrochenen kryptografischen Algorithmen verwenden</span><span class="sxs-lookup"><span data-stu-id="adf71-178">CA5351: Do not use broken cryptographic algorithms</span></span>

<span data-ttu-id="adf71-179">Es gibt einen Angriff, der es rechnerisch möglich macht, diesen Algorithmus zu durchbrechen.</span><span class="sxs-lookup"><span data-stu-id="adf71-179">An attack making it computationally feasible to break this algorithm exists.</span></span> <span data-ttu-id="adf71-180">Dies ermöglicht es Angreifern, die kryptografischen Garantien zu durchbrechen, die der Algorithmus bereitstellen soll.</span><span class="sxs-lookup"><span data-stu-id="adf71-180">This allows attackers to break the cryptographic guarantees it is designed to provide.</span></span> <span data-ttu-id="adf71-181">Je nach Typ und Anwendung dieses Kryptografiealgorithmus kann dies dazu führen, dass Angreifer verschlüsselte Nachrichten lesen und manipulieren, digitale Signaturen fälschen, Hashinhalte manipulieren oder auf andere Weise ein Kryptografiesystem gefährden, das auf diesem Algorithmus basiert.</span><span class="sxs-lookup"><span data-stu-id="adf71-181">Depending on the type and application of this cryptographic algorithm, this may allow attackers to read enciphered messages, tamper with enciphered messages, forge digital signatures, tamper with hashed content, or otherwise compromise any cryptosystem based on this algorithm.</span></span> <span data-ttu-id="adf71-182">Verwenden Sie für die Verschlüsselung einen AES-Algorithmus (AES-256, AES-192 und AES-128 sind akzeptabel) mit einer Schlüssellänge von mindestens 128 Bits.</span><span class="sxs-lookup"><span data-stu-id="adf71-182">For encryption, use an AES algorithm (AES-256, AES-192 and AES-128 are acceptable) with a key length greater than or equal to 128 bits.</span></span> <span data-ttu-id="adf71-183">Verwenden Sie für das Hashing eine Hashfunktion in der SHA-2-Familie, wie z.B. SHA512, SHA384 oder SHA256.</span><span class="sxs-lookup"><span data-stu-id="adf71-183">For hashing, use a hashing function in the SHA-2 family, such as SHA512, SHA384, or SHA256.</span></span> <span data-ttu-id="adf71-184">Verwenden Sie für digitale Signaturen RSA mit einer Schlüssellänge von mindestens 2048 Bits oder ECDSA mit einer Schlüssellänge von mindestens 256 Bits.</span><span class="sxs-lookup"><span data-stu-id="adf71-184">For digital signatures, use RSA with a key length greater than or equal to 2048-bits, or ECDSA with a key length greater than or equal to 256 bits.</span></span>

<span data-ttu-id="adf71-185">**Kategorie:** Sicherheit</span><span class="sxs-lookup"><span data-stu-id="adf71-185">**Category:** Security</span></span>

<span data-ttu-id="adf71-186">**Schweregrad:** Warnung</span><span class="sxs-lookup"><span data-stu-id="adf71-186">**Severity:** Warning</span></span>

<span data-ttu-id="adf71-187">Zusatzinformationen: [CA5351: Keine durchbrochenen Kryptografiealgorithmen verwenden](/visualstudio/code-quality/ca5351-do-not-use-broken-cryptographic-algorithms)</span><span class="sxs-lookup"><span data-stu-id="adf71-187">Additional Information: [CA5351: Do not use broken cryptographic algorithms](/visualstudio/code-quality/ca5351-do-not-use-broken-cryptographic-algorithms)</span></span>

