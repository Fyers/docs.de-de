---
title: 'Vorgehensweise: Erstellen eines Workflowdiensts zum Verarbeiten eines vorhandenen Dienstvertrags'
ms.date: 03/30/2017
ms.assetid: 11d11b59-acc4-48bf-8e4b-e97b516aa0a9
ms.openlocfilehash: 146b3bba3a880c780644eecd277827823793b5e8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33515304"
---
# <a name="how-to-create-a-workflow-service-that-consumes-an-existing-service-contract"></a>Vorgehensweise: Erstellen eines Workflowdiensts zum Verarbeiten eines vorhandenen Dienstvertrags
[!INCLUDE[net_v45](../../../includes/net-v45-md.md)]-Funktionen verbessern die Integration zwischen Webdiensten und Workflows in Form der Vertrag zuerst-Workflowentwicklung. Das Tool für die Vertrag zuerst-Workflowentwicklung ermöglicht es Ihnen, den Vertrag zuerst im Code zu entwerfen. Das Tool generiert dann automatisch eine Aktivitätsvorlage für die Vertragsvorgänge in der Toolbox.  
  
> [!NOTE]
>  Dieses Thema enthält eine schrittweise Anleitung zum Erstellen eines Vertrag zuerst-Workflowdiensts. Weitere Informationen zur Entwicklung von Vertrag zuerst-Workflow Service finden Sie unter [Vertrag zuerst-Workflowdienstentwicklung](../../../docs/framework/windows-workflow-foundation/contract-first-workflow-service-development.md).  
  
### <a name="creating-the-workflow-project"></a>Erstellen des Workflowprojekts  
  
1.  Wählen Sie in Visual Studio **Datei**, **neues Projekt**. Wählen Sie die **WCF** unter den Knoten der **c#** Knoten in der **Vorlagen** Struktur, und wählen Sie die **WCF-Workflowdienstanwendung** Vorlage.  
  
2.  Nennen Sie das neue Projekt `ContractFirst` , und klicken Sie auf **Ok**.  
  
### <a name="creating-the-service-contract"></a>Erstellen des Dienstvertrags  
  
1.  Mit der rechten Maustaste des Projekts im **Projektmappen-Explorer** , und wählen Sie **hinzufügen**, **neues Element...** . Wählen Sie die **Code** Knoten auf der linken Seite und die **Klasse** Vorlage auf der rechten Seite. Benennen Sie die neue Klasse `IBookService` , und klicken Sie auf **Ok**.  
  
2.  Fügen Sie `System.Servicemodel` im oberen Bereich des angezeigten Codefensters eine Using-Anweisung hinzu.  
  
    ```  
    using System.ServiceModel;  
    ```  
  
3.  Ändern Sie die Beispielklassendefinition in die folgende Schnittstellendefinition.  
  
    ```  
    [ServiceContract]  
        public interface IBookService  
        {  
            [OperationContract]  
            void Buy(string bookName);  
  
            [OperationContract(IsOneWay=true)]  
            void Checkout();  
        }  
    ```  
  
4.  Erstellen Sie das Projekt, indem Sie drücken **STRG + UMSCHALT + B**.  
  
### <a name="importing-the-service-contract"></a>Importieren des Dienstvertrags  
  
1.  Mit der rechten Maustaste des Projekts im **Projektmappen-Explorer** , und wählen Sie **Dienstvertrag importieren**. Klicken Sie unter  **\<aktuelles Projekt >**, öffnen Sie alle untergeordneten Knoten, und wählen Sie **IBookService**. Klicken Sie auf **OK**.  
  
2.  Es wird ein Dialogfeld mit dem Hinweis geöffnet, dass der Vorgang erfolgreich abgeschlossen wurde und dass die generierten Aktivitäten in der Toolbox angezeigt werden, nachdem Sie das Projekt erstellt haben. Klicken Sie auf **OK**.  
  
3.  Erstellen Sie das Projekt, indem Sie drücken **STRG + UMSCHALT + B**, damit die importierten Aktivitäten in der Toolbox angezeigt werden.  
  
4.  In **Projektmappen-Explorer**, Service1.xamlx zu öffnen. Der Workflowdienst wird im Designer angezeigt.  
  
5.  Wählen Sie die **Sequenz** Aktivität. Klicken Sie im Eigenschaftenfenster auf die **...** die Schaltfläche in der **ImplementedContract** Eigenschaft. In der **Typauflistungs-Editor** Fenster, das angezeigt wird, klicken Sie auf die **Typ** Dropdownliste, und wählen Sie die **nach Typen suchen...** Eintrag. In der **.NET-Typ suchen und auswählen** Dialogfeld unter  **\<aktuelles Projekt >**, öffnen Sie alle untergeordneten Knoten, und wählen Sie **IBookService**. Klicken Sie auf **OK**. In der **Typauflistungs-Editor** Dialogfeld klicken Sie auf **OK**.  
  
6.  Wählen Sie aus, und löschen Sie die **ReceiveRequest** und **SendResponse** Aktivitäten.  
  
7.  Ziehen Sie aus der Toolbox eine **Buy_ReceiveAndSendReply** und ein **Checkout_Receive** -Aktivität auf die **sequenzieller Dienst** Aktivität.
