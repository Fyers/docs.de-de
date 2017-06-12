---
title: "Gewusst wie: Zuweisen von schreibgesch&#252;tzten Spalten im DataGridView-Steuerelement in Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Datenblätter, Schreibgeschützte Spalten"
  - "DataGridView-Steuerelement [Windows Forms], Schreibgeschützte Spalten"
ms.assetid: 2bb73ebb-1a55-4362-9fda-e50574c087d5
caps.latest.revision: 18
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# Gewusst wie: Zuweisen von schreibgesch&#252;tzten Spalten im DataGridView-Steuerelement in Windows Forms
Nicht alle Daten sind zum Bearbeiten bestimmt.  Im <xref:System.Windows.Forms.DataGridView>\-Steuerelement bestimmt der Wert der Spalteneigenschaft <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A>, ob Benutzer Zellen in dieser Spalte bearbeiten können.  Informationen darüber, wie Sie das Steuerelement vollständig schreibgeschützt machen, finden Sie unter[Gewusst wie: Verhindern, das Zeilen im DataGridView\-Steuerelement in Windows Forms hinzugefügt und gelöscht werden](../../../../docs/framework/winforms/controls/prevent-row-addition-and-deletion-datagridview.md).  
  
 Visual Studio bietet Unterstützung für diese Aufgabe.  Siehe auch [Gewusst wie: Festlegen von schreibgeschützten Spalten im DataGridView\-Steuerelement in Windows Forms mithilfe des Designers](http://msdn.microsoft.com/library/xd4k3c7e\(v=vs.110\)).  
  
### So weisen Sie eine schreibgeschützte Spalte programmgesteuert zu  
  
-   Legen Sie die <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A?displayProperty=fullName>\-Eigenschaft auf `true` fest.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#064](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#064)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#064](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#064)]  
  
## Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
-   Ein <xref:System.Windows.Forms.DataGridView>\-Steuerelement mit dem Namen `dataGridView1` mit einer Spalte namens `CompanyName`.  
  
-   Verweise auf die Assemblys <xref:System?displayProperty=fullName> und <xref:System.Windows.Forms?displayProperty=fullName>.  
  
## Siehe auch  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridView.Columns%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A?displayProperty=fullName>   
 [Grundlegende Spalten\-, Zeilen\- und Zellfeatures im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/basic-column-row-and-cell-features-wf-datagridview-control.md)   
 [Gewusst wie: Verhindern, das Zeilen im DataGridView\-Steuerelement in Windows Forms hinzugefügt und gelöscht werden](../../../../docs/framework/winforms/controls/prevent-row-addition-and-deletion-datagridview.md)