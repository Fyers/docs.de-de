---
title: Verwenden von generischen Auflistungen
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- collections [.NET Framework], generic
- generic collections [.NET Framework]
ms.assetid: e7b868b1-11fe-4ac5-bed3-de68aca47739
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9831212cf65e3913bae2431e4746b5def03430b6
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/28/2018
ms.locfileid: "47210096"
---
# <a name="when-to-use-generic-collections"></a>Verwenden von generischen Auflistungen
Das Verwenden von generischen Auflistungen wird generell empfohlen, da Sie den unmittelbaren Vorteil die Typsicherheit erhalten, ohne von einem Basisauflistungstyp abweichen und typenspezifische Member implementieren zu müssen. Generische Auflistungstypen bieten allgemein auch eine bessere Leistung als die entsprechenden nicht generischen Auflistungstypen (und besser als Typen, die von nicht generischen Basisauflistungstypen abgeleitet sind), wenn die Auflistungselemente Werttypen sind, da bei generischen Typen keine Notwendigkeit zum Einschließen der Elemente besteht.  
  
 Für Programme, die auf [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] oder höher abzielen, sollten Sie die generischen Auflistungsklassen im <xref:System.Collections.Concurrent> -Namespace verwenden, wenn mehrere Threads möglicherweise Elemente gleichzeitig der Auflistung hinzufügen oder daraus entfernen.  
  
 Die folgenden generischen Typen entsprechen vorhandenen Auflistungstypen:  
  
-   <xref:System.Collections.Generic.List%601> ist die generische Klasse, die <xref:System.Collections.ArrayList>entspricht.  
  
-   <xref:System.Collections.Generic.Dictionary%602> und <xref:System.Collections.Concurrent.ConcurrentDictionary%602> sind die generischen Klassen, die <xref:System.Collections.Hashtable>entsprechen.  
  
-   <xref:System.Collections.ObjectModel.Collection%601> ist die generische Klasse, die <xref:System.Collections.CollectionBase>entspricht. <xref:System.Collections.ObjectModel.Collection%601> kann als Basisklasse verwendet werden, ist aber im Gegensatz zu <xref:System.Collections.CollectionBase>nicht abstrakt. Dadurch kann sie viel einfacher verwendet werden.  
  
-   <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> ist die generische Klasse, die <xref:System.Collections.ReadOnlyCollectionBase>entspricht. <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> ist nicht abstrakt und verfügt über einen Konstruktor, der es einfach macht, eine vorhandene <xref:System.Collections.Generic.List%601> als schreibgeschützte Auflistung verfügbar zu machen.  
  
-   Die generischen Klassen <xref:System.Collections.Generic.Queue%601>, <xref:System.Collections.Concurrent.ConcurrentQueue%601>, <xref:System.Collections.Generic.Stack%601>, <xref:System.Collections.Concurrent.ConcurrentStack%601>und <xref:System.Collections.Generic.SortedList%602> entsprechen den jeweiligen nicht generischen Klassen mit denselben Namen.  
  
## <a name="additional-types"></a>Zusätzliche Typen  
 Einige generische Auflistungstypen haben keine nicht generischen Entsprechungen. Hierzu gehören Folgende:  
  
-   <xref:System.Collections.Generic.LinkedList%601> ist eine vielfältig einsetzbare verknüpfte Liste, die O(1)-Einfüge- und Löschvorgänge bereitstellt.  
  
-   <xref:System.Collections.Generic.SortedDictionary%602> ist ein sortiertes Wörterbuch mit O(log `n`)-Einfüge- und Abrufvorgängen – eine nützliche Alternative zu <xref:System.Collections.Generic.SortedList%602>.  
  
-   <xref:System.Collections.ObjectModel.KeyedCollection%602> ist eine Mischung aus Liste und Wörterbuch und bietet eine Möglichkeit, Objekte zu speichern, die ihre eigenen Schlüssel enthalten.  
  
-   <xref:System.Collections.Concurrent.BlockingCollection%601> implementiert eine Auflistungsklasse mit Begrenzungs- und Blockadefunktionen.  
  
-   <xref:System.Collections.Concurrent.ConcurrentBag%601> ermöglicht das schnelle Einfügen und Entfernen unsortierter Elemente.  
  
## <a name="linq-to-objects"></a>LINQ to Objects  
 Mit der LINQ to Objects-Funktion können Sie LINQ-Abfragen für den Zugriff auf Objekte im Arbeitsspeicher verwenden, solange der Objekttyp die <xref:System.Collections.IEnumerable?displayProperty=nameWithType> - oder <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> -Schnittstelle implementiert. LINQ-Abfragen bieten ein allgemeines Muster für den Datenzugriff, sind normalerweise präziser und besser lesbar als standardmäßige `foreach` -Schleifen und stellen Filter-, Sortier- und Gruppierungsfunktionen bereit. LINQ-Abfragen können auch die Leistung verbessern. Weitere Informationen finden Sie unter [LINQ to Objects](https://msdn.microsoft.com/library/73cafe73-37cf-46e7-bfa7-97c7eea7ced9) und [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md).  
  
## <a name="additional-functionality"></a>Zusätzliche Funktionen  
 Einige der generischen Typen besitzen Funktionen, die es in den nicht generischen Auflistungstypen nicht gibt. Die <xref:System.Collections.Generic.List%601> -Klasse, die der nicht generischen <xref:System.Collections.ArrayList> -Klasse entspricht, hat z. B. eine Reihe von Methoden, die generische Delegaten akzeptieren, z. B. den <xref:System.Predicate%601> -Delegaten, mit dem Sie Methoden zum Durchsuchen der Liste angeben können, den <xref:System.Action%601> -Delegaten, der Methoden für die einzelnen Listenelemente darstellt, und den <xref:System.Converter%602> -Delegaten, mit dem Sie Konvertierungen zwischen Typen definieren können.  
  
 Mit der <xref:System.Collections.Generic.List%601> -Klasse können Sie Ihre eigenen generischen <xref:System.Collections.Generic.IComparer%601> -Schnittstellenimplementierungen zum Sortieren und Durchsuchen der Liste angeben. Die Klassen <xref:System.Collections.Generic.SortedDictionary%602> und <xref:System.Collections.Generic.SortedList%602> verfügen ebenfalls über diese Funktion. Darüber hinaus ermöglichen Ihnen diese Klassen das Angeben von Vergleichen beim Erstellen der Auflistung. In ähnlicher Weise können Sie mit den Klassen <xref:System.Collections.Generic.Dictionary%602> und <xref:System.Collections.ObjectModel.KeyedCollection%602> eigene Gleichheitsvergleiche angeben.  
  
## <a name="see-also"></a>Siehe auch

- [Sammlungen und Datenstrukturen](../../../docs/standard/collections/index.md)  
- [Häufig verwendete Auflistungstypen](../../../docs/standard/collections/commonly-used-collection-types.md)  
- [Generika](../../../docs/standard/generics/index.md)
