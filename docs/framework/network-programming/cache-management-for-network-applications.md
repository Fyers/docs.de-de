---
title: Cacheverwaltung für Netzwerkanwendungen
ms.date: 03/30/2017
helpviewer_keywords:
- cache [.NET Framework], network applications
- network resources, caching
- Internet, caching
ms.assetid: fc258a40-f370-434f-ae09-4a8cb11ddaeb
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 1e0b3ed66977dd6587789e3d88f532b699653c6f
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/26/2018
ms.locfileid: "47195575"
---
# <a name="cache-management-for-network-applications"></a>Cacheverwaltung für Netzwerkanwendungen
Dieses Thema und seine zugehörigen Unterthemen beschreiben die Zwischenspeicherung von Ressourcen, die mithilfe der <xref:System.Net.WebClient>-, <xref:System.Net.WebRequest>-, <xref:System.Net.HttpWebRequest>- und <xref:System.Net.FtpWebRequest>-Klassen erhalten werden.  
  
 Ein Zwischenspeicher dient als temporärer Speicher von Ressourcen, die von einer Anwendung angefordert wurden. Wenn eine Anwendung mehrere Male die gleiche Ressource anfordert, kann die Ressource aus dem Zwischenspeicher zurückgegeben werden. Der Mehraufwand einer erneuten Aufforderung vom Server wird somit verhindert. Zwischenspeichern kann die Anwendungsleistung durch Verringern des Zeitaufwands für den Abruf einer angeforderten Ressource verbessern. Zwischenspeichern kann auch den Netzwerkverkehr verringern, indem die Anzahl der Roundtrips zum Server reduziert werden. Bei der Zwischenspeicherung wird die Leistung verbessert, aber sie erhöht auch das Risiko, dass die an die Anwendung zurückgegebene Ressource veraltet ist, was bedeutet, dass sie nicht identisch zu der Ressource ist, die vom Server gesendet worden wäre, wenn das Zwischenspeichern nicht in Gebrauch wäre.  
  
 Durch Zwischenspeichern können nicht autorisierte Benutzer vertrauliche Daten lesen oder verarbeiten. Eine authentifizierte Antwort, die zwischengespeichert ist, kann möglicherweise ohne eine zusätzliche Autorisierung aus dem Zwischenspeicher abgerufen werden. Wenn das Zwischenspeichern aktiviert wurde, ändern Sie <xref:System.Net.WebRequest.CachePolicy%2A> auf <xref:System.Net.Cache.RequestCacheLevel.BypassCache> oder <xref:System.Net.Cache.RequestCacheLevel.NoCacheNoStore>, um es für diese Anforderung zu deaktivieren.  
  
 Aus Sicherheitsgründen wird das Zwischenspeichern **nicht** für Szenarios der mittleren Ebene empfohlen.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Cacherichtlinie](../../../docs/framework/network-programming/cache-policy.md)  
 Erläutert, was eine Cacherichtlinie ist und wie sie definiert werden kann.  
  
 [Speicherortbasierte Cacherichtlinien](../../../docs/framework/network-programming/location-based-cache-policies.md)  
 Definiert jeden Typ von verfügbaren speicherortbasierten Cacherichtlinien für Ressourcen von Hypertext Transfer Protocol (http und https).  
  
 [Zeitbasierte Cacherichtlinien](../../../docs/framework/network-programming/time-based-cache-policies.md)  
 Beschreibt die Kriterien, die zum Anpassen einer zeitbasierten Cacherichtlinie verwendet werden können.  
  
 [Konfigurieren der Zwischenspeicherung in den Netzwerkanwendungen](../../../docs/framework/network-programming/configuring-caching-in-network-applications.md)  
 Beschreibt, wie Sie programmgesteuert Cacherichtlinien und Anforderungen erstellen, die Zwischenspeicher verwenden.  
  
## <a name="reference"></a>Referenz  
 <xref:System.Net.Cache>  
 Definiert die Typen und Enumerationen, mit denen Cacherichtlinien für Ressourcen definiert werden, die mithilfe der Klassen <xref:System.Net.WebRequest>, <xref:System.Net.HttpWebRequest> und <xref:System.Net.FtpWebRequest> abgerufen werden.
