---
title: 'Gewusst wie: Starten von Diensten'
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Service applications, starting
- services, starting
ms.assetid: 9ea77955-2d96-4c3d-913c-14db7604cdad
author: ghogen
ms.openlocfilehash: b3f04deb11a23957198864c444b4872aef45b2e4
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2018
ms.locfileid: "47176746"
---
# <a name="how-to-start-services"></a>Gewusst wie: Starten von Diensten
Nachdem ein Dienst installiert wurde, muss er gestartet werden. Beim Starten wird die <xref:System.ServiceProcess.ServiceBase.OnStart%2A>-Methode für die Dienstklasse aufgerufen. In der Regel werden die Vorgänge, die vom Dienst durchgeführt werden, von der <xref:System.ServiceProcess.ServiceBase.OnStart%2A>-Methode definiert. Nachdem ein Dienst gestartet worden ist, bleibt er aktiv, solange er nicht manuell angehalten oder beendet wird.  
  
 Für Dienste kann festgelegt werden, ob sie automatisch oder manuell gestartet werden. Ein automatisch startender Dienst wird gestartet, wenn der Computer, auf dem er installiert ist, neu gestartet oder zum ersten Mal eingeschaltet wird. Ein Dienst, der manuell gestartet wird, muss von Benutzern gestartet werden.  
  
> [!NOTE]
>  Mit Visual Studio erstellte Dienste sind standardmäßig auf manuelles Starten festgelegt.  
  
 Ein Dienst kann auf verschiedene Weise manuell gestartet werden: Mit dem **Server-Explorer**, dem **Dienststeuerungs-Manager** oder indem im Code die <xref:System.ServiceProcess.ServiceController>-Komponente verwendet wird.  
  
 Die <xref:System.ServiceProcess.ServiceInstaller.StartType%2A>-Eigenschaft für die <xref:System.ServiceProcess.ServiceInstaller>-Klasse wird festgelegt, um zu bestimmen, ob ein Dienst manuell oder automatisch gestartet werden soll.  
  
### <a name="to-specify-how-a-service-should-start"></a>So geben Sie an, wie ein Dienst gestartet werden soll  
  
1.  Nachdem Sie den Dienst erstellt haben, fügen Sie die erforderlichen Installationsprogramme hinzu. Weitere Informationen finden Sie unter [Vorgehensweise: Hinzufügen von Installern zu Ihrer Dienstanwendung](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md).  
  
2.  Klicken Sie im Designer auf das Dienstinstallationsprogramm für den Dienst, mit dem Sie arbeiten.  
  
3.  Legen Sie im Fenster **Eigenschaften** die <xref:System.ServiceProcess.ServiceInstaller.StartType%2A>-Eigenschaft auf einen der folgenden Werte fest:  
  
    |Installationszeitpunkt|Festzulegender Wert|  
    |----------------------------------|--------------------|  
    |Sobald der Computer neu gestartet wird|**Automatisch**|  
    |Sobald der Dienst von einer expliziten Benutzeraktion gestartet wird|**Manuell**|  
  
    > [!TIP]
    >  Wenn der Dienst nie gestartet werden soll, legen Sie die <xref:System.ServiceProcess.ServiceInstaller.StartType%2A>-Eigenschaft auf **Deaktiviert** fest. Wenn ein Server mehrmals neu gestartet wird, kann damit Zeit gespart werden, indem das Starten von Diensten verhindert wird, die in der Regel gestartet würden.  
  
    > [!NOTE]
    >  Diese und weitere Eigenschaften können geändert werden, nachdem der Dienst installiert wurde.  
  
     Es stehen mehrere Möglichkeiten zur Verfügung, einen Dienst zu starten, dessen <xref:System.ServiceProcess.ServiceInstaller.StartType%2A>-Vorgang auf **Manuell** festgelegt ist: mit dem **Server-Explorer**, dem **Dienststeuerungs-Manager** von Windows oder programmgesteuert. Wichtig dabei ist, dass der Dienst nicht von allen Methoden im Kontext des **Dienststeuerungs-Managers** gestartet wird. Tatsächlich wird der Controller mit dem **Server-Explorer** und mit programmgesteuerten Startmethoden geändert.  
  
### <a name="to-manually-start-a-service-from-server-explorer"></a>So starten Sie einen Dienst manuell mit dem Server-Explorer  
  
1.  Fügen Sie im **Server-Explorer** den gewünschten Server hinzu, sofern dieser noch nicht aufgelistet ist. Weitere Informationen finden Sie unter „Vorgehensweise: Zugreifen auf und Initialisieren von Server-Explorer/Datenbank-Explorer“.  
  
2.  Erweitern Sie den Knoten **Dienste**, und suchen Sie den zu startenden Dienst.  
  
3.  Klicken Sie mit der rechten Maustaste auf den Dienst, und klicken Sie dann auf **Starten**.  
  
### <a name="to-manually-start-a-service-from-services-control-manager"></a>So starten Sie einen Dienst manuell mit dem Dienststeuerungs-Manager  
  
1.  Öffnen Sie den **Dienststeuerungs-Manager**, indem Sie einen der folgenden Schritte ausführen:  
  
    -   Klicken Sie in Windows XP und 2000 Professional auf dem Desktop des Computers mit der rechten Maustaste auf **Arbeitsplatz**, und klicken Sie anschließend auf **Verwalten**. Erweitern Sie im nun angezeigten Dialogfeld den Knoten **Dienste und Anwendungen**.  
  
         \- oder –  
  
    -   Klicken Sie in Windows Server 2003 und Windows 2000 Server auf **Start**, und zeigen Sie auf **Programme**. Klicken Sie auf **Verwaltung** und anschließend auf **Dienste**.  
  
        > [!NOTE]
        >  In Windows NT 4.0 kann das Dialogfeld über die **Systemsteuerung** geöffnet werden.  
  
     Der Dienst wird nun im Bereich **Dienste** des Fensters angezeigt.  
  
2.  Wählen Sie den Dienst in der Liste aus, klicken Sie mit der rechten Maustaste darauf, und klicken Sie dann auf **Starten**.  
  
### <a name="to-manually-start-a-service-from-code"></a>So starten Sie einen Dienst programmgesteuert  
  
1.  Erstellen Sie eine Instanz der <xref:System.ServiceProcess.ServiceController>-Klasse, und konfigurieren Sie sie so, dass Daten mit dem Dienst ausgetauscht werden können.  
  
2.  Starten Sie den Dienst, indem Sie die <xref:System.ServiceProcess.ServiceController.Start%2A>-Methode aufrufen.  
  
## <a name="see-also"></a>Siehe auch  
 [Einführung in Windows-Dienstanwendungen](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)  
 [Vorgehensweise: Erstellen von Windows-Diensten](../../../docs/framework/windows-services/how-to-create-windows-services.md)  
 [Vorgehensweise: Hinzufügen von Installern zur Dienstanwendung](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md)
