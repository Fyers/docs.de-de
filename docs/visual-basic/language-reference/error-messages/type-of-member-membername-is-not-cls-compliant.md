---
title: Typ des Members &#39; &lt;Membername&gt; &#39; ist nicht CLS-kompatibel.
ms.date: 07/20/2015
f1_keywords:
- bc40025
- vbc40025
helpviewer_keywords:
- BC40025
ms.assetid: adbd34bb-43d2-4266-90e7-cd1afaf49b4e
ms.openlocfilehash: 5735b5104884a702a649a029116be7446424ec67
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2018
ms.locfileid: "43480995"
---
# <a name="type-of-member-39ltmembernamegt39-is-not-cls-compliant"></a>Typ des Members &#39; &lt;Membername&gt; &#39; ist nicht CLS-kompatibel.
Der Datentyp angegeben werden, für die dieses Element ist nicht Teil der [Sprachenunabhängigkeit und sprachunabhängige Komponenten](../../../standard/language-independence-and-language-independent-components.md) (CLS). Dies ist kein Fehler in der Komponente, da die [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] und Visual Basic unterstützt diesen Datentyp. Allerdings kann in eine andere Komponente, die in streng CLS-kompatiblem Code geschrieben diesen Datentyp nicht unterstützt. Eine solche Komponente möglicherweise nicht erfolgreich mit der Komponente interagieren können.  
  
 Die folgenden Visual Basic-Datentypen sind nicht CLS-kompatibel:  
  
-   [SByte-Datentyp](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)  
  
-   [UInteger-Datentyp](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
  
-   [ULong-Datentyp](../../../visual-basic/language-reference/data-types/ulong-data-type.md)  
  
-   [UShort-Datentyp](../../../visual-basic/language-reference/data-types/ushort-data-type.md)  
  
 Standardmäßig ist diese Meldung eine Warnung. Weitere Informationen zum Ausblenden von Warnungen aus, oder zum Behandeln von Warnungen als Fehler finden Sie unter [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Fehler-ID:** BC40025  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Wenn die Komponente nur mit anderen Schnittstellen [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] Komponenten oder nicht mit anderen Komponenten verbunden, Sie müssen keine Änderungen vornehmen.  
  
-   Wenn Sie mit einer Komponente, die nicht für geschriebenen anbinden, müssen die [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)], Sie möglicherweise fest, über Reflektion oder anhand der Dokumentation gibt an, ob sie diesen Datentyp unterstützt. Wenn dies der Fall ist, müssen Sie keine Änderungen vornehmen.  
  
-   Wenn Sie mit einer Komponente verbunden sind, die diesen Datentyp nicht unterstützt, müssen Sie es mit den ähnlichsten CLS-kompatiblen Typ ersetzen. Anstelle von `UInteger` könnten Sie beispielsweise `Integer` verwenden, wenn Sie den Wertebereich über 2.147.483.647 nicht benötigen. Wenn Sie den erweiterten Bereich benötigen, können Sie `UInteger` durch `Long`ersetzen.  
  
-   Beachten Sie beim Verbinden mit Automatisierungs- oder COM-Objekten, dass einige Typen über andere Datenbreiten als im [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] verfügen. Zum Beispiel umfasst `uint` in anderen Umgebungen oft 16 Bits. Wenn Sie ein 16-Bit-Argument an eine solche Komponente übergeben, deklarieren Sie sie als `UShort` anstelle von `UInteger` in verwaltetem Visual Basic-Code.  
  
## <a name="see-also"></a>Siehe auch  
 [Reflexion](../../../framework/reflection-and-codedom/reflection.md)  
 
