---
title: Wichtige Erkenntnisse – serverlose apps
description: Serverless bietet viele Vorteile und verfügt über eine eigene Herausforderungen. Eine Zusammenfassung der wichtigsten Erkenntnisse dieses Leitfadens.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 055facf7ef46c18f8cda518da9a9f3e114dec1a2
ms.sourcegitcommit: 4c158beee818c408d45a9609bfc06f209a523e22
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2018
ms.locfileid: "49369829"
---
# <a name="conclusion"></a>Schlussbemerkung

Die folgende wesentliche Punkte sind die wichtigsten Erkenntnisse dieses Leitfadens.

**Die Vorteile der Verwendung von serverlosen.** Serverlose Lösungen bieten einen wichtigen Vorteil bei der kosteneinsparung, da in einem Modell für die nutzungsbasierte Bezahlung serverlose implementiert wird. Serverless ermöglicht es, die unabhängig voneinander skalieren, zu testen und Bereitstellen der einzelnen Komponenten Ihrer Anwendung. Serverless eignet sich eindeutig um microservicearchitekturen zu implementieren und vollständig in einer DevOps-Pipeline integriert.

**-Code als eine Bereitstellungseinheit.** Serverless abstrahiert die Hardware, Betriebssystem und Runtime von der Anwendung. Serverless ermöglicht die Konzentration auf die Geschäftslogik im Code als Einheit der Bereitstellung.

**Trigger und Bindungen.** Serverless erleichtert die Integration mit Speicher-APIs und anderen Cloudressourcen. Azure Functions bietet Trigger zum Ausführen von Code und Bindungen für die Interaktion mit Ressourcen.

**Microservices.** Die Microservices-Architektur wird der bevorzugte Ansatz für verteilte und große oder komplexe unternehmenskritische Anwendungen immer, die auf mehreren unabhängigen Subsystemen in Form von autonomen Diensten basieren. In einem Microservice basierende Architektur wird die Anwendung als eine Sammlung von Diensten erstellt, die entwickelt, getestet, versioniert, bereitgestellt und unabhängig voneinander skaliert werden können. Serverlose Konzepte ist eine Architektur eignet sich ideal für diese Dienste zu erstellen.

**Serverlosen Plattformen.** Serverlose ist nicht nur der Code aus. Plattformen, die serverlose Architekturen zu unterstützen, enthalten serverlose Workflows und Orchestrierung, serverlose messaging und Event-Dienste sowie serverlose Datenbanken.

**Serverlose Herausforderungen.** Serverless führt Herausforderungen im Zusammenhang mit verteilten-Anwendungsentwicklung, z.B. fragmentierte und unabhängige Datenmodelle, resilienz, versionsverwaltung und Dienstermittlung. Serverless möglicherweise nicht ideal geeignet sein, auf lang ausgeführte Prozesse oder Komponenten, die von einer engeren Koppelung profitieren.

**Serverlose als ein Tool, das nicht in der Toolbox.** Serverlose Konzepte ist nicht in die Projektmappe auf die Anwendungsarchitektur exklusive. Es ist ein Tool, das als Teil einer hybridanwendung genutzt werden kann, die traditionell Ebenen, monolithische Anwendung-Back-Ends und Container enthalten können. Serverless kann verwendet werden, um vorhandene Lösungen erweitern, und ist keiner nichts Ansatz zur Anwendungsentwicklung.

>[!div class="step-by-step"]
[Vorherige](serverless-business-scenarios.md)