---
title: 'Gewusst wie: Anzeigen von Unterelementen in Spalten mit dem ListView-Steuerelement in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- list items
- Details view
- ListView control [Windows Forms], adding ListSubItems
- subitems
ms.assetid: e465f044-cde7-4fd9-a687-788a73a0f554
ms.openlocfilehash: efee926301bc358bb7645ba67826f412c0d0dbbe
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33532505"
---
# <a name="how-to-display-subitems-in-columns-with-the-windows-forms-listview-control"></a>Gewusst wie: Anzeigen von Unterelementen in Spalten mit dem ListView-Steuerelement in Windows Forms
Windows Forms <xref:System.Windows.Forms.ListView> Steuerelement kann zusätzliche Text oder Unterelemente für jedes Element in der Detailansicht anzeigen. Die erste Spalte zeigt den Elementtext, z. B. eine Mitarbeiter-Nummer. Das zweite, dritte und die nachfolgende Spalten die erste Zweitens anzuzeigen und die folgenden verbundenen Unterelemente.  
  
### <a name="to-add-subitems-to-a-list-item"></a>Ein Listenelement Unterelemente hinzu  
  
1.  Fügen Sie alle Spalten benötigt. Da die erste Spalte des Elements angezeigt werden <xref:System.Windows.Forms.ListView.Text%2A> -Eigenschaft, benötigen Sie eine Spalte mehr als Unterelemente vorhanden sind. Weitere Informationen zum Hinzufügen von Spalten finden Sie unter [wie: Hinzufügen von Spalten zum ListView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-columns-to-the-windows-forms-listview-control.md).  
  
2.  Rufen Sie die <xref:System.Windows.Forms.ListViewItem.ListViewSubItemCollection.Add%2A> -Methode der Auflistung zurückgegeben werden, indem Sie die <xref:System.Windows.Forms.ListViewItem.SubItems%2A> Eigenschaft eines Elements. Das folgende Codebeispiel legt fest, die Employee Name "und" Department für ein Listenelement.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#61](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#61)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#61](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#61)]  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über das ListView-Steuerelement](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)  
 [Gewusst wie: Hinzufügen und Entfernen von Elementen mit dem ListView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)  
 [Gewusst wie: Hinzufügen von Spalten zum ListView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-columns-to-the-windows-forms-listview-control.md)  
 [Gewusst wie: Anzeigen von Symbolen für das ListView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-display-icons-for-the-windows-forms-listview-control.md)  
 [Gewusst wie: Hinzufügen von benutzerdefinierten Daten zu einem TreeView- oder ListView-Steuerelement (Windows Forms)](../../../../docs/framework/winforms/controls/add-custom-information-to-a-treeview-or-listview-control-wf.md)
