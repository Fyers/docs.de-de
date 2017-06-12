---
title: "UI Automation Support for the TreeItem Control Type | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-bcl"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "control types, Tree Item"
  - "Tree Item control type"
  - "UI Automation, Tree Item control type"
ms.assetid: 229f341a-477f-434e-b877-4db9973068eb
caps.latest.revision: 22
author: "Xansky"
ms.author: "mhopkins"
manager: "markl"
caps.handback.revision: 22
---
# UI Automation Support for the TreeItem Control Type
> [!NOTE]
>  Diese Dokumentation ist für .NET Framework\-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]\-Klassen verwenden möchten, die im <xref:System.Windows.Automation>\-Namespace definiert sind. Aktuelle Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] finden Sie auf der Seite zur [Windows\-Automatisierungs\-API: UI\-Automatisierung](http://go.microsoft.com/fwlink/?LinkID=156746).  
  
 Dieses Thema enthält Informationen über [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]\-Unterstützung für den Steuerelementtyp „TreeItem“. In [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] umfasst ein Steuerelementtyp eine Reihe von Bedingungen, die ein Steuerelement erfüllen muss, damit die <xref:System.Windows.Automation.AutomationElement.ControlTypeProperty>\-Eigenschaft verwendet werden kann. Die Bedingungen schließen bestimmte Richtlinien für [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]\-Struktur, [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]\-Eigenschaftswerte und Steuerelementmuster ein.  
  
 Der TreeItem\-Steuerelementtyp stellt einen Knoten innerhalb eines Strukturcontainers dar. Jeder Knoten kann andere Knoten enthalten, die als untergeordnete Knoten bezeichnet werden. Übergeordnete Knoten oder Knoten mit untergeordneten Knoten können in erweiterter oder reduzierter Form angezeigt werden.  
  
 In den folgenden Abschnitten werden die [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]\-Struktur, \-Eigenschaften, \-Steuerelementmuster und \-Ereignisse definiert, die für den Steuerelementtyp „TreeItem“ erforderlich sind. Die [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]\-Anforderungen gelten für alle Strukturelement\-Steuerelemente in [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)] oder [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)].  
  
<a name="Required_UI_Automation_Tree_Structure"></a>   
## Erforderliche Benutzeroberflächenautomatisierungs\-Struktur  
 In der folgende Tabelle werden die Steuerelementansicht und die Inhaltsansicht der [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]\-Struktur für Strukturelement\-Steuerelemente sowie die möglichen Inhalte der Ansichten beschrieben. Weitere Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]\-Struktur finden Sie unter [UI Automation Tree Overview](../../../docs/framework/ui-automation/ui-automation-tree-overview.md).  
  
|Steuerelementansicht|Inhaltsansicht|  
|--------------------------|--------------------|  
|TreeItem<br /><br /> -   CheckBox \(0 oder 1\)<br />-   Image \(0 oder 1\)<br />-   Button \(0 oder 1\)<br />-   TreeItem \(beliebige Anzahl\)|TreeItem<br /><br /> -   TreeItem \(beliebige Anzahl\)|  
  
 Strukturelement\-Steuerelemente können in der Inhaltsansicht der [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]\-Struktur keine oder mehrere untergeordnete Elemente aufweisen. Wenn das Strukturelement\-Steuerelement mehr Funktionen aufweist als diejenigen, die von den unten aufgelisteten Steuerelementmustern verfügbar gemacht werden, muss das Steuerelement auf dem Steuerelementtyp „DataItem“ basieren.  
  
 Reduzierte Strukturelemente werden erst dann in der Steuerelementansicht oder in der Inhaltsansicht angezeigt, wenn sie erweitert und sichtbar werden \(oder durch einen Bildlauf angezeigt werden können\).  
  
 Die Steuerelementansicht kann weitere Details für ein Steuerelement enthalten, wie etwa für ein zugeordnetes Bild oder eine Schaltfläche. Ein Element in einer Gliederungsansicht kann beispielsweise ein Bild sowie eine Schaltfläche zum Erweitern oder Reduzieren der Gliederung enthalten. Diese Detailobjekte werden nicht in der Inhaltsansicht angezeigt, da die Informationen bereits vom übergeordneten Strukturelement dargestellt werden. Strukturelemente, die sich außerhalb des Bildschirms befinden, werden sowohl in der Steuerelement\- als auch in der Inhaltsansicht der [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]\-Struktur angezeigt. Ihre <xref:System.Windows.Automation.AutomationElement.IsOffscreenProperty> muss auf „true“ festgelegt sein.  
  
<a name="Required_UI_Automation_Properties"></a>   
## Erforderliche Benutzeroberflächenautomatisierungs\-Eigenschaften  
 Die folgende Tabelle enthält die [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]\-Eigenschaften, deren Werte oder Definitionen für Listensteuerelemente besonders relevant sind. Weitere Informationen zu [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]\-Eigenschaften finden Sie unter [UI Automation Properties for Clients](../../../docs/framework/ui-automation/ui-automation-properties-for-clients.md).  
  
|[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]\-Eigenschaft|Wert|Notizen|  
|----------------------------------------------------------------------------------------|----------|-------------|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationIdProperty>|Siehe Hinweise.|Der Wert dieser Eigenschaft muss für alle Steuerelemente in einer Anwendung eindeutig sein.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty>|Siehe Hinweise.|Das äußere Rechteck, das das gesamte Steuerelement enthält.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ClickablePointProperty>|Siehe Hinweise.|Diese Eigenschaft muss eine Position des Elements zurückgeben, wodurch der Auswahlzustand des Elements geändert wird bzw. wodurch es den Fokus erhält.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ControlTypeProperty>|TreeItem|Dieser Wert ist für alle Benutzeroberflächen\-Frameworks gleich.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsContentElementProperty>|True|Das Strukturelement\-Steuerelement ist stets in der Inhaltsansicht der [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]\-Struktur enthalten.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsControlElementProperty>|True|Das Strukturelement\-Steuerelement ist stets in der Steuerelementansicht der [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]\-Struktur enthalten.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsOffscreenProperty>|Siehe Hinweise.|Diese Eigenschaft wird festgelegt, um anzugeben, wann ein Strukturelement\-Steuerelement sich außerhalb des Bildschirms befindet.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsKeyboardFocusableProperty>|Siehe Hinweise.|Wenn das Steuerelement den Tastaturfokus erhalten kann, muss es diese Eigenschaft unterstützen.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ItemTypeProperty>|Siehe Hinweise.|Wenn das Strukturelement\-Steuerelement durch ein visuelles Symbol anzeigt, dass es sich um einen bestimmten Objekttyp handelt, muss diese Eigenschaft unterstützt werden und angeben, worum es sich bei dem Objekt handelt.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LabeledByProperty>|`Null`|Strukturelement\-Steuerelemente sind selbstbezeichnend.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LocalizedControlTypeProperty>|„Strukturelement“|Lokalisierte Zeichenfolge für den Steuerelementtyp „TreeItem“.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.NameProperty>|Siehe Hinweise.|Diese Eigenschaft macht den für jedes Strukturelement\-Steuerelement angezeigten Text verfügbar.|  
  
<a name="Required_UI_Automation_Control_Patterns"></a>   
## Erforderliche Benutzeroberflächenautomatisierungs\-Steuerelementmuster  
 Die folgende Tabelle enthält die [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]\-Steuerelementmuster, die von allen Listensteuerelementen unterstützt werden müssen. Weitere Informationen zu Steuerelementmustern finden Sie unter [UI Automation Control Patterns Overview](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md).  
  
|Steuerelementmuster\/Mustereigenschaft|Unterstützung\/Wert|Notizen|  
|--------------------------------------------|-------------------------|-------------|  
|<xref:System.Windows.Automation.Provider.IInvokeProvider>|Variabel|Implementieren Sie dieses Steuerelementmuster, wenn das Strukturelement über einen einzelnen, ausführbaren Befehl verfügt.|  
|<xref:System.Windows.Automation.Provider.IExpandCollapseProvider>|Ja|Alle Strukturelemente können erweitert oder reduziert werden.|  
|<xref:System.Windows.Automation.Provider.IExpandCollapseProvider.ExpandCollapseState%2A>|Erweitert, reduziert oder Blattknoten|Strukturelemente sind Blattknoten, wenn sie nicht erweitert oder reduziert werden.|  
|<xref:System.Windows.Automation.Provider.IScrollItemProvider>|Variabel|Implementieren Sie dieses Steuerelementmuster, wenn der Strukturcontainer das Scroll\-Steuerelementmuster unterstützt.|  
|<xref:System.Windows.Automation.Provider.ISelectionItemProvider>|Variabel|Implementieren Sie dieses Steuerelementmuster, wenn eine aktive Auswahl möglich ist, die erhalten bleibt, wenn der Benutzer zum Strukturcontainer zurückkehrt.|  
|<xref:System.Windows.Automation.Provider.ISelectionItemProvider.SelectionContainer%2A>|Ja|Diese Eigenschaft macht den gleichen Container für alle Elemente innerhalb des Containers verfügbar.|  
|<xref:System.Windows.Automation.Provider.IToggleProvider>|Variabel|Implementieren Sie dieses Steuerelementmuster, wenn dem Strukturelement ein Kontrollkästchen zugeordnet ist.|  
  
<a name="Required_UI_Automation_Events"></a>   
## Erforderliche Benutzeroberflächenautomatisierungs\-Ereignisse  
 Die folgende Tabelle enthält die [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]\-Ereignisse, die von allen Strukturelement\-Steuerelementen unterstützt werden müssen. Weitere Informationen zu Ereignissen finden Sie unter [UI Automation Events Overview](../../../docs/framework/ui-automation/ui-automation-events-overview.md).  
  
|[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]\-Ereignis|Unterstützung|Notizen|  
|-------------------------------------------------------------------------------------|-------------------|-------------|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationFocusChangedEvent>|Erforderlich|Keine|  
|Durch geänderte <xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty>\-Eigenschaft ausgelöstes Ereignis.|Erforderlich|Keine|  
|Durch geänderte <xref:System.Windows.Automation.AutomationElementIdentifiers.IsEnabledProperty>\-Eigenschaft ausgelöstes Ereignis.|Erforderlich|Keine|  
|Durch geänderte <xref:System.Windows.Automation.AutomationElementIdentifiers.IsOffscreenProperty>\-Eigenschaft ausgelöstes Ereignis.|Erforderlich|Keine|  
|Durch geänderte <xref:System.Windows.Automation.AutomationElementIdentifiers.ItemStatusProperty>\-Eigenschaft ausgelöstes Ereignis.|Variabel|Keine|  
|Durch geänderte <xref:System.Windows.Automation.AutomationElementIdentifiers.NameProperty>\-Eigenschaft ausgelöstes Ereignis.|Erforderlich|Keine|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.StructureChangedEvent>|Erforderlich|Keine|  
|Durch geänderte <xref:System.Windows.Automation.ExpandCollapsePatternIdentifiers.ExpandCollapseStateProperty>\-Eigenschaft ausgelöstes Ereignis.|Erforderlich|Keine|  
|<xref:System.Windows.Automation.InvokePatternIdentifiers.InvokedEvent>|Variabel|Keine|  
|Durch geänderte <xref:System.Windows.Automation.MultipleViewPatternIdentifiers.CurrentViewProperty>\-Eigenschaft ausgelöstes Ereignis.|Variabel|Keine|  
|<xref:System.Windows.Automation.SelectionItemPatternIdentifiers.ElementAddedToSelectionEvent>|Variabel|Keine|  
|<xref:System.Windows.Automation.SelectionItemPatternIdentifiers.ElementRemovedFromSelectionEvent>|Variabel|Keine|  
|<xref:System.Windows.Automation.SelectionItemPatternIdentifiers.ElementSelectedEvent>|Variabel|Keine|  
|Durch geänderte <xref:System.Windows.Automation.TogglePatternIdentifiers.ToggleStateProperty>\-Eigenschaft ausgelöstes Ereignis.|Variabel|Keine|  
|Durch geänderte <xref:System.Windows.Automation.ValuePatternIdentifiers.ValueProperty>\-Eigenschaft ausgelöstes Ereignis.|Variabel|Keine|  
  
## Siehe auch  
 <xref:System.Windows.Automation.ControlType.TreeItem>   
 [UI Automation Control Types Overview](../../../docs/framework/ui-automation/ui-automation-control-types-overview.md)   
 [UI Automation Overview](../../../docs/framework/ui-automation/ui-automation-overview.md)