---
title: Weitere Informationen zu .NET Core
description: Erfahren Sie mehr zu .NET Core.
author: richlander
ms.author: mairaw
ms.date: 08/01/2018
ms.openlocfilehash: d9943246b683c8fd892e7bc5fd09a10b72e31a5f
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2018
ms.locfileid: "48252220"
---
# <a name="about-net-core"></a>Weitere Informationen zu .NET Core

.NET Core weist folgende Merkmale auf:

- **Plattformübergreifend:** Ist unter den [Betriebssystemen](https://github.com/dotnet/core/blob/master/os-lifecycle-policy.md) Windows, macOS und Linux lauffähig.
- **Architekturübergreifende Konsistenz:** Führt Ihren Code in unterschiedlichen Architekturen (z.B. x64, x86 und ARM) mit demselben Verhalten aus.
- **Befehlszeilentools:** Umfasst benutzerfreundliche Befehlszeilentools, mit denen Sie lokal und in Continuous Integration-Szenarios entwickeln können.
- **Flexible Bereitstellung:** Kann in Ihre App eingebunden oder parallel zu ihr installiert werden – auf Benutzer- oder Computerbasis. Kann mit [Docker-Containern](docker/index.md) verwendet werden.
- **Kompatibel:** .NET Core ist über [.NET Standard](../standard/net-standard.md) mit .NET Framework, Xamarin und Mono kompatibel.
- **Open Source:** Die .NET Core-Plattform ist eine Open Source-Plattform, die MIT- und Apache 2-Lizenzen verwendet. .NET Core ist ein [.NET Foundation](https://dotnetfoundation.org/)-Projekt.
- **Von Microsoft unterstützt:** .NET Core wird entsprechend den Richtlinien unter [.NET Support Policy (Richtlinien für die .NET-Unterstützung)](https://www.microsoft.com/net/core/support/) von Microsoft unterstützt.

## <a name="languages"></a>Sprachen

C#, Visual Basic und F# können verwendet werden, um Anwendungen und Bibliotheken für .NET Core zu schreiben. Diese Sprachen können in Ihren bevorzugten Text-Editoren oder Ihre bevorzugten IDEs integriert werden (oder sind es bereits), u.a. [Visual Studio](https://visualstudio.microsoft.com/vs/), [Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp), Sublime Text und Vim. Diese Integration wird teilweise dank der Projektmitwirkenden von [OmniSharp](http://www.omnisharp.net/) und [Ionide](http://ionide.io) bereitgestellt.

## <a name="apis"></a>APIs

.NET Core stellt vielseitige APIs bereit, u.a. die folgenden:

- Primitive Typen, z.B. [bool][bool] und [int][int].
- Sammlungen, z.B. <xref:System.Collections.Generic.List%601?displayProperty=nameWithType> und <xref:System.Collections.Generic.Dictionary%602?displayProperty=nameWithType>.
- Hilfstypen, z.B. <xref:System.Net.Http.HttpClient?displayProperty=nameWithType> und <xref:System.IO.FileStream?displayProperty=nameWithType>.
- Datentypen, z.B. <xref:System.Data.DataSet?displayProperty=nameWithType> und [DbSet][dbset].
- Hochleistungstypen, z.B. <xref:System.Numerics.Vector?displayProperty=nameWithType> und [Pipelines][pipelines].

Durch die Implementierung der [.NET Standard](../standard/net-standard.md)-Spezifikation ist .NET Core mit .NET Framework und Mono-APIs kompatibel.

[bool]: https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/bool
[int]: https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/int
[pipelines]: https://blogs.msdn.microsoft.com/dotnet/2018/07/09/system-io-pipelines-high-performance-io-in-net/
[dbset]: https://www.nuget.org/packages/Microsoft.EntityFrameworkCore/

## <a name="frameworks"></a>Frameworks

Mehrere Frameworks wurden basierend auf .NET Core entwickelt:

- [ASP.NET Core](/aspnet/core/)
- [Windows 10 Universelle Windows-Plattform (UWP)](https://developer.microsoft.com/windows)
- [Tizen](https://developer.tizen.org/development/training/.net-application)

## <a name="composition"></a>Aufbau

.NET Core umfasst folgende Bestandteile:

- Eine [.NET Core-Runtime](https://github.com/dotnet/coreclr), die ein Typsystem, eine Funktion zum Laden von Assemblys, einen Garbage Collector, natives Interop und andere grundlegende Dienste bereitstellt. [.NET Core-Frameworkbibliotheken](https://github.com/dotnet/corefx) stellen primitive Datentypen, Typen zur Anwendungsgestaltung und grundlegende Hilfsprogramme bereit.
- Die [ASP.NET-Runtime](https://github.com/aspnet/home), die ein Framework zum Erstellen moderner, cloudbasierter Anwendungen mit Internetverbindung, wie etwa Web-Apps, IoT-Apps und mobile Back-Ends, bietet.
- Die [.NET Core-CLI-Tools](https://github.com/dotnet/cli) und Sprachcompiler ([Roslyn](https://github.com/dotnet/roslyn) und [F#](https://github.com/microsoft/visualfsharp)), die Funktionen für .NET Core-Entwickler bereitstellen.
- Der Befehl [dotnet tool](https://github.com/dotnet/core-setup), der zum Starten von .NET Core-Anwendungen und CLI-Tools verwendet wird. Er wählt und hostet die Runtime, stellt eine Richtlinie zum Laden der Assembly bereit und startet die Anwendungen und Tools.

Die Komponenten sind wie folgt verfügbar:

- [.NET Core-Runtime:](https://www.microsoft.com/net/download/dotnet-core/2.1) enthält die .NET Core-Runtime und -Frameworkbibliotheken.
- [ASP.NET Core-Runtime:](https://www.microsoft.com/net/download/dotnet-core/2.1) enthält die ASP.NET Core-Runtime sowie die .NET Core-Runtime und -Frameworkbibliotheken.
- [.NET Core SDK:](https://www.microsoft.com/net/download/dotnet-core/2.1) enthält die .NET-CLI-Tools, die ASP.NET Core-Runtime, die .NET Core-Runtime und das .NET Core-Framework.

### <a name="open-source"></a>Open Source

[.NET Core](https://github.com/dotnet/core) ist eine Open Source-Plattform ([MIT-Lizenz](https://github.com/dotnet/core/blob/master/LICENSE.TXT)) und wurde von Microsoft im Jahr 2014 zur [.NET Foundation](https://dotnetfoundation.org) hinzugefügt. Es ist jetzt eines der aktivsten .NET-Foundation-Projekte. Es kann kostenlos von Einzelpersonen und Unternehmen, einschließlich persönlicher, wissenschaftlicher oder kommerzieller Zwecke übernommen werden. Mehrere Unternehmen verwenden .NET Core als Teil von Anwendungen, Tools, neuen Plattformen und Hostingdiensten. Einige dieser Unternehmen leisten auf GitHub bedeutende Beiträge zu .NET Core, und bieten eine Anleitung für die Produktentwicklung als Teil der [.NET Foundation Technical Steering Group](https://dotnetfoundation.org/blog/tsg-welcome) (Technische Steuerungsgruppe).

### <a name="designed-for-adaptability"></a>Für Anpassungsfähigkeit entworfen

.NET Core wurde als sehr ähnliches, aber auch einzigartiges Produkt im Vergleich zu anderen .NET-Produkten erstellt. Es wurde entwickelt, um umfassende Anpassungsfähigkeit auf neuen Plattformen und für neue Workloads zu aktivieren. Es verfügt über mehrere Betriebssysteme und CPU-Ports und kann zu vielen anderen portiert werden.

Das Produkt ist in mehrere Teile aufgeteilt, und die verschiedenen Teile können zu unterschiedlichen Zeitpunkten an neue Plattformen angepasst werden. Die Laufzeit und grundlegende plattformspezifische Bibliotheken müssen als eine Einheit portiert werden. Plattformagnostische Bibliotheken sollten wie vorhanden von der Konstruktion auf allen Plattformen funktionieren. Es gibt eine Projektverschiebung zur Verminderung der plattformspezifischen Implementierungen, um die Effizienz der Entwickler zu erhöhen. Wenn ein Algorithmus oder API so vollständig oder teilweise implementiert werden kann, wird ein plattformneutraler C#-Code bevorzugt.

Es wird häufig gefragt, wie .NET Core implementiert wird, um mehrere Betriebssysteme zu unterstützen. Dabei wird meistens gefragt, ob es separate Implementierungen gibt oder die [bedingte Kompilierung](https://en.wikipedia.org/wiki/Conditional_compilation) verwendet wird. Beides wird mit starkem Bias für bedingte Kompilierung durchgeführt.

Sie sehen im Diagramm unten, dass die große Mehrheit der [CoreFX](https://github.com/dotnet/corefx) aus plattformneutralem Code sind, der auf allen Plattformen gemeinsam genutzt wird. Ein plattformneutraler Code kann als einzelne, tragbare Assembly implementiert werden, die auf allen Plattformen verwendet wird.

![CoreFX: Zeilen-Code pro Plattform](../images/corefx-platforms-loc.png)

Windows- und Unix-Implementierungen haben eine ähnliche Größe. Windows verfügt über eine größere Implementierung, da CoreFX einige Funktionen nur für Windows implementiert, wie z.B. [Microsoft.Win32.Registry](https://github.com/dotnet/corefx/tree/master/src/Microsoft.Win32.Registry), jedoch noch nicht viele Konzepte nur für Unix implementiert. Außerdem sehen Sie, dass die Mehrheit der Linux- und Mac OS-Implementierungen für mehrere Unix-Implementierungen verwendet werden, während die spezifischen Linux- und Mac OS-Implementierungen ungefähr gleich groß sind.

Es gibt eine Mischung aus plattformspezifischen und plattformneutralen Bibliotheken in .NET Core. Sie können das Muster in einigen Beispielen sehen:

- [CoreCLR](https://github.com/dotnet/coreclr) ist plattformspezifisch. Es baut auf Subsystemen des Betriebssystems auf, z.B. auf dem Speicher-Manager und dem Threadplaner.
- [System.IO](https://github.com/dotnet/corefx/tree/master/src/System.IO) und [System.Security.Cryptography.Algorithms](https://github.com/dotnet/corefx/tree/master/src/System.Security.Cryptography.Algorithms) sind plattformspezifisch, angesichts der Tatsache, dass sich Speicher- und Kryptografie-APIs je nach Betriebssystem voneinander unterscheiden.
- [System.Collections](https://github.com/dotnet/corefx/tree/master/src/System.Collections) und [System.Linq](https://github.com/dotnet/corefx/tree/master/src/System.Linq) sind plattformneutral, angesichts der Tatsache, dass sie Datenstrukturen erstellen und verwenden.

## <a name="comparisons-to-other-net-implementations"></a>Vergleiche mit anderen .NET- Implementierungen

Möglicherweise ist es am einfachsten, die Größe und Form von .NET Core durch einen Vergleich mit vorhandenen .NET-Implementierungen zu verstehen.

### <a name="comparison-with-net-framework"></a>Vergleich mit .NET- Framework

.NET wurde erstmals in 2000 von Microsoft angekündigt, und hat sich dann von dort aus entwickelt. Das .NET Framework war in den letzten zwei Jahrzehnten die primäre .NET-Implementierung von Microsoft.

Die Hauptunterschiede zwischen .NET Core und dem .NET Framework:

- **App-Modelle:** .NET Core unterstützt nicht alle .NET Framework-App-Modelle. Das betrifft vor allem ASP.NET-Web Forms und MVC. Es wurde angekündigt, dass [.NET Core 3 WPF und Windows Forms unterstützen wird](https://blogs.msdn.microsoft.com/dotnet/2018/05/07/net-core-3-and-support-for-windows-desktop-applications/).
- **APIs:** .NET Core enthält viele .NET Framework-Basisklassenbibliotheken mit unterschiedlicher Verarbeitung (die Assemblynamen unterscheiden sich; in Typen bereitgestellte Members unterscheiden sich in wichtigen Fällen). Diese Unterschiede machen es erforderlich, dass die Quelle in einigen Fällen zu .NET Core portiert wird (weitere Informationen unter [microsoft/dotnet-apiport](https://github.com/microsoft/dotnet-apiport)). .NET Core implementiert die [.NET-Standard](../standard/net-standard.md)-API-Spezifikation.
- **Subsysteme**: .NET Core implementiert eine Teilmenge der Subsysteme in .NET Framework, mit dem Ziel einer einfacheren Implementierung und einem einfacheren Programmiermodell. Code Access Security (CAS) wird z.B. nicht unterstützt, während Reflektion unterstützt wird.
- **Plattformen**: .NET Framework unterstützt Windows und Windows-Server- während .NET Core auch Mac OS und Linux unterstützt.
- **Open Source**: .NET Core ist Open Source, während eine [schreibgeschützte Teilmenge von .NET Framework](https://github.com/microsoft/referencesource) Open Source ist.

Obwohl .NET Core einzigartig ist und sich erheblich vom .NET Framework und anderen .NET-Implementierungen unterscheidet, ist es dennoch unkompliziert, den gleichen Code in diesen Implementierungen zu verwenden. Dazu können Sie Quell- oder Binärfreigabeverfahren verwenden.

### <a name="comparison-with-mono"></a>Vergleich mit Mono

[Mono](http://www.mono-project.com/) ist die ursprüngliche plattformübergreifende und [Open Source](https://github.com/mono/mono) .NET-Implementierung, die erstmals im Jahr 2004 versendet wurde. Sie kann als Community-Klon des .NET Frameworks betrachtet werden. Das Mono-Projektteam griff auf die offenen [.NET-Standards](https://github.com/dotnet/coreclr/blob/master/Documentation/project-docs/dotnet-standards.md) (insbesondere ECMA 335) zurück, die von Microsoft veröffentlicht wurden, um eine kompatible Implementierung bereitzustellen.

Die Hauptunterschiede zwischen .NET Core und Mono:

- **Anwendungsmodelle**: Mono unterstützt eine Teilmenge der .NET Framework-Anwendungsmodelle (z.B. Windows Forms) und einige zusätzliche (z.B. [Xamarin.iOS](https://www.xamarin.com/platform)) über das Xamarin-Produkt. .NET Core unterstützt diese nicht.
- **APIs**: Mono unterstützt eine [große Teilmenge](http://docs.go-mono.com/?link=root%3a%2fclasslib) der .NET Framework-APIs, die die gleichen Assemblynamen und Fakturierung verwenden.
- **Plattformen**: Mono unterstützt zahlreiche Plattformen und CPUs.
- **Open Source**: Mono und .NET Core verwenden beide die MIT-Lizenz und sind .NET Foundation-Projekte.
- **Fokus**: In den letzten Jahren lag der primäre Fokus von Mono auf mobilen Plattformen, während sich .NET Core auf Cloud- und Desktopworkloads konzentriert hat.
