---
title: 'Gewusst wie: Erstellen eines Dokuments mit Namespaces (LINQ to XML) (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: cc5b0d4d-360c-4ada-94fa-2d2916e989be
ms.openlocfilehash: 204d8a9cbb6ce47c6334c7309d27910c75b90ae0
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43499925"
---
# <a name="how-to-create-a-document-with-namespaces-linq-to-xml-visual-basic"></a>Gewusst wie: Erstellen eines Dokuments mit Namespaces (LINQ to XML) (Visual Basic)
In diesem Thema wird das Erstellen eines Dokuments mit Namespaces in Visual Basic beschrieben.  
  
 Bei Verwendung von XML-Literalen in Visual Basic können Benutzer einen globalen XML-Standardnamespace definieren. Dieser Namespace ist der Standardnamespace für die XML-Literale und für die XML-Eigenschaften. Der XML-Standardnamespace kann auf Projekt- oder auf Dateiebene definiert werden. Bei Definition auf Dateiebene wird der auf der Projektebene definierte Standardnamespace außer Kraft gesetzt.  
  
 Sie können auch andere Namespaces definieren und die Namespacepräfixe für diese Namespaces angeben.  
  
 Standardnamespaces und Namespaces mit einem Präfix werden mit dem `Imports`-Schlüsselwort definiert.  
  
 Weitere Informationen finden Sie unter [Einführung in die XML-Literale in Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/introduction-to-xml-literals.md).  
  
 Beachten Sie, dass der XML-Standardnamespace nur für Elemente, nicht aber für Attribute gültig ist. Attribute befinden sind standardmäßig nie in einem Namespace. Sie können aber ein Namespacepräfix verwenden, um ein Attribut in einen Namespace zu setzen.  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel erstellt ein Dokument, das einen Namespace enthält:  
  
```vb  
Imports <xmlns:aw="http://www.adventure-works.com">  
Module Module1  
    Sub Main()  
        Dim root As XElement = _  
            <aw:Root>  
                <aw:Child aw:Att="attvalue"/>  
            </aw:Root>  
        Console.WriteLine(root)  
    End Sub  
End Module  
```  
  
 Dieses Beispiel erzeugt die folgende Ausgabe:  
  
```xml  
<aw:Root xmlns:aw="http://www.adventure-works.com">  
  <aw:Child aw:Att="attvalue" />  
</aw:Root>  
```  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel erstellt ein Dokument, das zwei Namespaces enthält, wovon ein Namespace der Standardnamespace ist:  
  
```vb  
Imports <xmlns="http://www.adventure-works.com">  
Imports <xmlns:fc="www.fourthcoffee.com">  
  
Module Module1  
  
    Sub Main()  
        Dim root As XElement = _  
            <Root>  
                <Child Att="attvalue"/>  
                <fc:Child2>child2 content</fc:Child2>  
            </Root>  
        Console.WriteLine(root)  
    End Sub  
  
End Module  
```  
  
 Dieses Beispiel erzeugt die folgende Ausgabe:  
  
```xml  
<Root xmlns:fc="www.fourthcoffee.com" xmlns="http://www.adventure-works.com">  
  <Child Att="attvalue" />  
  <fc:Child2>child2 content</fc:Child2>  
</Root>  
```  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel erstellt ein Dokument, das zwei Namespaces enthält, die beide ein Namespacepräfix besitzen.  
  
 Beim Serialisieren in eine XML-Struktur gibt [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] je nach Bedarf Namespacedeklarationen aus, sodass sich jedes Element in dem für ihn vorgesehenen Namespace befindet.  
  
```vb  
Imports <xmlns:aw="http://www.adventure-works.com">  
Imports <xmlns:fc="www.fourthcoffee.com">  
  
Module Module1  
  
    Sub Main()  
        Dim root As XElement = _  
            <aw:Root>  
                <fc:Child>  
                    <aw:DifferentChild>other content</aw:DifferentChild>  
                </fc:Child>  
                <aw:Child2>c2 content</aw:Child2>  
                <fc:Child3>c3 content</fc:Child3>  
            </aw:Root>  
        Console.WriteLine(root)  
    End Sub  
  
End Module  
```  
  
 Dieses Beispiel erzeugt die folgende Ausgabe:  
  
```xml  
<aw:Root xmlns:fc="www.fourthcoffee.com" xmlns:aw="http://www.adventure-works.com">  
  <fc:Child>  
    <aw:DifferentChild>other content</aw:DifferentChild>  
  </fc:Child>  
  <aw:Child2>c2 content</aw:Child2>  
  <fc:Child3>c3 content</fc:Child3>  
</aw:Root>  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Arbeiten mit XML-Namespaces (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md)
