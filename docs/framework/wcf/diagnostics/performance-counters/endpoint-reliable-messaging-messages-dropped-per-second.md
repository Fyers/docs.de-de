---
title: 'Endpunkt: Reliable Messaging Messages Dropped Per Second'
ms.date: 03/30/2017
ms.assetid: ea3c4fc0-1e0f-4863-8879-57bc6c113018
ms.openlocfilehash: 8f935bee06d175ce454bd7f58a1afbbe9ab505ad
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2018
ms.locfileid: "43863503"
---
# <a name="endpoint-reliable-messaging-messages-dropped-per-second"></a>Endpunkt: Reliable Messaging Messages Dropped Per Second
Indikatorname: Reliable Messaging Sessions Dropped Per Second.  
  
## <a name="description"></a>Beschreibung  
 Gesamtzahl der zuverlässigen Messagingnachrichten, die pro Sekunde an diesem Endpunkt verworfen wurden.  
  
 Dieser Indikator wird der Leistungsindikator vom Typ [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), dessen Wert anhand der folgenden Formel berechnet wird.  
  
 (N 1 - N 0)/( (D 1 - D 0)/F)
