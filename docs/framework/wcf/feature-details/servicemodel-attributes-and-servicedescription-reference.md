---
title: ServiceModel-Attribute und ServiceDescription-Referenz
ms.date: 03/30/2017
ms.assetid: 4ab86b17-eab9-4846-a881-0099f9a7cc64
ms.openlocfilehash: cc7c36ff7a1c81227f118ee7113be8f7f9eb2e9f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33505969"
---
# <a name="servicemodel-attributes-and-servicedescription-reference"></a>ServiceModel-Attribute und ServiceDescription-Referenz
Die *beschreibungsstruktur* ist die Hierarchie der Typen (beginnend mit der <xref:System.ServiceModel.Description.ServiceDescription?displayProperty=nameWithType> Klasse), die zusammen jeden Aspekt eines Diensts beschreiben. Windows Communication Foundation (WCF) verwendet eine beschreibungsstruktur zum Erstellen einer gültigen Dienstlaufzeit, zum Veröffentlichen von Web Services Description Language (WSDL), XML-Schemadefinitionssprache (XSD) sowie Richtlinienassertionen (Metadaten) über den Dienst, mit denen Clients können Verbinden mit und verwenden Sie den Dienst und zum Generieren verschiedener Code- und konfigurationsdateidarstellungen der beschreibungsstrukturwerte.  
  
 Dieses Thema beschreibt, wie vertragsbezogene Eigenschaften aus dem Dienstvertrag abgerufen, wie sie implementiert und der Beschreibungsstruktur hinzugefügt werden. In einigen Fällen werden Attributwerte in Verhaltenseigenschaften umgewandelt, und das Verhalten wird dann in die Beschreibungsstruktur eingefügt. Weitere Informationen dazu, wie der beschreibungsstrukturwerte in Metadaten umgewandelt werden, finden Sie unter [ServiceDescription und WSDL-Verweis](../../../../docs/framework/wcf/feature-details/servicedescription-and-wsdl-reference.md).  
  
## <a name="mapping-operations-to-the-description-tree"></a>Zuordnen von Vorgängen zur Beschreibungsstruktur  
 In WCF-Anwendungen werden Dienstverträge nach Schnittstellen (oder Klassen) modelliert, die Attribute verwenden, um die Schnittstelle oder Klasse und ihre Methoden als eine vorgangsgruppierung zu markieren. Wenn eine <xref:System.ServiceModel.ServiceHost>-Klasse geöffnet ist, werden Dienstverträge und Implementierungen immer wieder reflektiert und mit den Konfigurationsinformationen in eine Beschreibungsstruktur zusammengeführt.  
  
 Es gibt zwei Typen von vorgangsmodellen: das *Parameter* Modell und die *Nachrichtenvertrag* Modell. Das Parametermodell verwendet verwaltete Methoden, die keinen Parameter oder Rückgabewerttyp besitzen, der von der Klasse <xref:System.ServiceModel.MessageContractAttribute?displayProperty=nameWithType> markiert wird. In diesem Modell Entwickler Steuern der Serialisierung der Parameter und Rückgabewerte, aber WCF generiert die Werte, die verwendet werden, um die beschreibungsstruktur für den Dienst und seinen Vertrag zu füllen.  
  
 In Konfigurationsdateien angegebene Bindungen werden direkt in die Eigenschaft <xref:System.ServiceModel.Description.ServiceEndpoint.Binding%2A?displayProperty=nameWithType> geladen.  
  
|ServiceBehaviorAttribute-Eigenschaft|Beschreibungsstrukturwert beeinflusst|  
|---------------------------------------|-------------------------------------|  
|name|<xref:System.ServiceModel.Description.ServiceDescription.Name%2A>|  
|Namespace|<xref:System.ServiceModel.Description.ServiceDescription.Namespace%2A>|  
|ConfigurationName|<xref:System.ServiceModel.Description.ServiceDescription.ConfigurationName%2A>|  
|IgnoreExtensionDataObject|Legt die Eigenschaft <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior.IgnoreExtensionDataObject%2A> für alle Vorgänge fest.|  
|MaxItemsInObjectGraph|Legt die Eigenschaft <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior.MaxItemsInObjectGraph%2A> für alle Vorgänge fest.|  
  
|ServiceContractAttribute-Eigenschaft|Beschreibungsstrukturwert beeinflusst|  
|---------------------------------------|-------------------------------------|  
|CallbackContract|<xref:System.ServiceModel.Description.ContractDescription.CallbackContractType%2A>, <xref:System.ServiceModel.Description.MessageDescription> hat allen Operationen <xref:System.ServiceModel.Description.OperationDescription.Messages%2A> hinzugefügt.|  
|ConfigurationName|<xref:System.ServiceModel.Description.ContractDescription.ConfigurationName%2A>|  
|ProtectionLevel|<xref:System.ServiceModel.Description.ContractDescription.ProtectionLevel%2A> und möglicherweise untergeordnete Schutzebenen. Weitere Informationen über die Schutzebene Hierarchie finden Sie unter [Verständnis Schutzebene](../../../../docs/framework/wcf/understanding-protection-level.md).|  
|SessionMode|<xref:System.ServiceModel.Description.ContractDescription.SessionMode%2A>|  
  
|ServiceKnownTypesAttribute-Wert|Beschreibungsstrukturwert beeinflusst|  
|--------------------------------------|-------------------------------------|  
|MethodName|<xref:System.ServiceModel.Description.OperationDescription.KnownTypes%2A>|  
  
|OperationContractAttribute-Wert|Beschreibungsstrukturwert beeinflusst|  
|--------------------------------------|-------------------------------------|  
|Aktion|<xref:System.ServiceModel.Description.MessageDescription.Action%2A> für die Ausgabe- oder Eingabenachricht, abhängig vom Vertrag/Rückrufvertrag.|  
|AsyncPattern|Wenn "true", <xref:System.ServiceModel.Description.OperationDescription.BeginMethod%2A> und <xref:System.ServiceModel.Description.OperationDescription.EndMethod%2A>|  
|IsOneWay|Wird einer einzelnen <xref:System.ServiceModel.Description.MessageDescription> in <xref:System.ServiceModel.Description.OperationDescription.Messages%2A> zugeordnet|  
|IsInitiating|<xref:System.ServiceModel.Description.OperationDescription.IsInitiating%2A>|  
|IsTerminating|<xref:System.ServiceModel.Description.OperationDescription.IsTerminating%2A>|  
|name|<xref:System.ServiceModel.Description.OperationDescription.Name%2A>|  
|ProtectionLevel|<xref:System.ServiceModel.Description.OperationDescription.ProtectionLevel%2A> und möglicherweise untergeordnete Schutzebenen. Weitere Informationen über die Schutzebene Hierarchie finden Sie unter [Verständnis Schutzebene](../../../../docs/framework/wcf/understanding-protection-level.md).|  
|ReplyAction|<xref:System.ServiceModel.Description.MessageDescription.Action%2A> für die Ausgabe- oder Eingabenachricht, abhängig vom Vertrag/Rückrufvertrag.|  
  
|FaultContractAttribute-Wert|Beschreibungsstrukturwert beeinflusst|  
|----------------------------------|-------------------------------------|  
|Aktion|<xref:System.ServiceModel.Description.FaultDescription.Action%2A>, abhängig vom Vertrag/Rückrufvertrag.|  
|DetailType|<xref:System.ServiceModel.Description.FaultDescription.DetailType%2A>|  
|name|<xref:System.ServiceModel.Description.FaultDescription.Name%2A>|  
|Namespace|<xref:System.ServiceModel.Description.FaultDescription.Namespace%2A>|  
|ProtectionLevel|<xref:System.ServiceModel.Description.FaultDescription.ProtectionLevel%2A>|  
  
|DataContractFormatAttribute-Wert|Beschreibungsstrukturwert beeinflusst|  
|---------------------------------------|-------------------------------------|  
|Mit|Der Wert <xref:System.ServiceModel.DataContractFormatAttribute.Style%2A> ist auf <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior> für den Vorgang festgelegt.|  
  
|XmlSerializerFormatAttribute-Wert|Beschreibungsstrukturwert beeinflusst|  
|----------------------------------------|-------------------------------------|  
|Stil|Diese <xref:System.ServiceModel.XmlSerializerFormatAttribute>-Eigenschaft ist auf <xref:System.ServiceModel.Description.XmlSerializerOperationBehavior> für den Vorgang festgelegt.|  
|Mit|<xref:System.ServiceModel.XmlSerializerFormatAttribute> ist auf <xref:System.ServiceModel.Description.XmlSerializerOperationBehavior> für den Vorgang festgelegt.|  
  
|TransactionFlowAttribute-Wert|Beschreibungsstrukturwert beeinflusst|  
|------------------------------------|-------------------------------------|  
|TransactionFlowOption|<xref:System.ServiceModel.TransactionFlowAttribute> wird der Eigenschaft <xref:System.ServiceModel.Description.OperationDescription.Behaviors%2A> als Vorgangsverhalten hinzugefügt.|  
  
|MessageContractAttribute-Wert|Beschreibungsstrukturwert beeinflusst|  
|------------------------------------|-------------------------------------|  
|ProtectionLevel|<xref:System.ServiceModel.Description.MessageDescription.ProtectionLevel%2A>|  
|WrapperName|<xref:System.ServiceModel.Description.MessageBodyDescription.WrapperName%2A>|  
|WrapperNamespace|<xref:System.ServiceModel.Description.MessageBodyDescription.WrapperNamespace%2A>|  
  
|MessageHeaderAttribute-Wert|Beschreibungsstrukturwert beeinflusst|  
|----------------------------------|-------------------------------------|  
|Akteur|<xref:System.ServiceModel.Description.MessageHeaderDescription.Actor%2A> für den entsprechenden Header in <xref:System.ServiceModel.Description.MessageDescription.Headers%2A>|  
|MustUnderstand|<xref:System.ServiceModel.Description.MessageHeaderDescription.MustUnderstand%2A> für den entsprechenden Header in <xref:System.ServiceModel.Description.MessageDescription.Headers%2A>|  
|name|<xref:System.ServiceModel.Description.MessagePartDescription.Name%2A> für den entsprechenden Header in <xref:System.ServiceModel.Description.MessageDescription.Headers%2A>|  
|Namespace|<xref:System.ServiceModel.Description.MessagePartDescription.Namespace%2A> für den entsprechenden Header in <xref:System.ServiceModel.Description.MessageDescription.Headers%2A>|  
|ProtectionLevel|<xref:System.ServiceModel.Description.MessagePartDescription.ProtectionLevel%2A> für den entsprechenden Header in <xref:System.ServiceModel.Description.MessageDescription.Headers%2A>|  
|Relay|<xref:System.ServiceModel.Description.MessageHeaderDescription.Relay%2A> für den entsprechenden Header in <xref:System.ServiceModel.Description.MessageDescription.Headers%2A>|  
  
|MessageBodyMemberAttribute-Wert|Beschreibungsstrukturwert beeinflusst|  
|--------------------------------------|-------------------------------------|  
|name|<xref:System.ServiceModel.Description.MessagePartDescription.Name%2A> für die entsprechende Stelle im <xref:System.ServiceModel.Description.MessageBodyDescription.Parts%2A>|  
|Namespace|<xref:System.ServiceModel.Description.MessagePartDescription.Namespace%2A> für die entsprechende Stelle im <xref:System.ServiceModel.Description.MessageBodyDescription.Parts%2A>|  
|Reihenfolge|<xref:System.ServiceModel.Description.MessagePartDescription.Index%2A> für die entsprechende Stelle im <xref:System.ServiceModel.Description.MessageBodyDescription.Parts%2A>|  
|ProtectionLevel|<xref:System.ServiceModel.Description.MessagePartDescription.ProtectionLevel%2A> für die entsprechende Stelle im <xref:System.ServiceModel.Description.MessageBodyDescription.Parts%2A>|  
  
|MessageHeaderArrayAttribute-Wert|Beschreibungsstrukturwert beeinflusst|  
|---------------------------------------|-------------------------------------|  
|Akteur|<xref:System.ServiceModel.Description.MessageHeaderDescription.Actor%2A>|  
|MustUnderstand|<xref:System.ServiceModel.Description.MessageHeaderDescription.MustUnderstand%2A>|  
|name|<xref:System.ServiceModel.Description.MessagePartDescription.Name%2A>|  
|Namespace|<xref:System.ServiceModel.Description.MessagePartDescription.Namespace%2A>|  
|ProtectionLevel|<xref:System.ServiceModel.Description.MessagePartDescription.ProtectionLevel%2A>|  
|Relay|<xref:System.ServiceModel.Description.MessageHeaderDescription.Relay%2A>|  
  
|MessagePropertyAttribute-Wert|Beschreibungsstrukturwert beeinflusst|  
|------------------------------------|-------------------------------------|  
|name|<xref:System.ServiceModel.Description.MessagePartDescription.Name%2A>|  
  
|MessageParameterAttribute-Wert|Beschreibungsstrukturwert beeinflusst|  
|-------------------------------------|-------------------------------------|  
|name|<xref:System.ServiceModel.Description.MessagePartDescription.Name%2A> für die entsprechende Stelle im <xref:System.ServiceModel.Description.MessageBodyDescription.Parts%2A>|  
  
 Weitere Informationen dazu, wie der beschreibungsstrukturwerte in Metadaten umgewandelt werden, finden Sie unter [ServiceDescription und WSDL-Verweis](../../../../docs/framework/wcf/feature-details/servicedescription-and-wsdl-reference.md).  
  
## <a name="see-also"></a>Siehe auch  
 [ServiceDescription und WSDL-Verweis](../../../../docs/framework/wcf/feature-details/servicedescription-and-wsdl-reference.md)
