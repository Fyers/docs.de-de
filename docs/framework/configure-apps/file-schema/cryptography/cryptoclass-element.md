---
title: '&lt;CryptoClass&gt; Element'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/cryptoNameMapping/cryptoClasses/cryptoClass
- http://schemas.microsoft.com/.NetConfiguration/v2.0#cryptoClass
helpviewer_keywords:
- cryptoClass element
- <cryptoClass> element
ms.assetid: 03db52ef-010e-44ea-b6fd-b9c900ecad50
author: mcleblanc
ms.author: markl
ms.openlocfilehash: e74cc5fa99473562b158cd5068fb8bbaeb6a4a17
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/26/2018
ms.locfileid: "47196979"
---
# <a name="ltcryptoclassgt-element"></a>&lt;CryptoClass&gt; Element
Enthält eine Kryptografieklasse, die einem Anzeigenamen im Element [\<nameEntry>](../../../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md) zugeordnet ist.  
  
 \<configuration>  
\<"mscorlib" >  
\<CryptographySettings >  
\<CryptoNameMapping >  
\<CryptoClasses >  
\<CryptoClass >  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<cryptoClass customClassName="fully qualified type name" />  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|`customClassName`|Erforderliches Attribut.<br /><br /> Enthält die Informationen für die Kryptografieklasse. Verwenden Sie dieses Attribut, um einen kurzen Namen für die Klasse bereitzustellen. Geben Sie eine Zeichenfolge, die die in angegebenen Anforderungen erfüllt [angeben vollständig gekennzeichneter Typnamen](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`cryptoClasses`|Enthält eine Liste von Kryptografieklassen, die einem Anzeigenamen im Element [\<nameEntry>](../../../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md) zugeordnet sind.|  
|`cryptographySettings`|Enthält Kryptografieeinstellungen.|  
|`cryptoNameMapping`|Enthält die Zuordnung von Klassen zu den Anzeigenamen.|  
|`mscorlib`|Enthält das Element [\<cryptographySettings>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptographysettings-element.md).|  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird gezeigt, wie mithilfe der  **\<CryptoClass >** Element auf eine kryptografischen Klasse verweisen und die Runtime zu konfigurieren. Sie können dann an die Zeichenfolge "RSA" übergeben der <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> -Methode und die Verwendung der <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> -Methode zur Rückgabe einer `MyCryptoRSAClass` Objekt.  
  
```xml  
<configuration>  
   <mscorlib>  
      <cryptographySettings>  
         <cryptoNameMapping>  
            <cryptoClasses>  
               <cryptoClass   MyCryptoRSA="MyCryptoRSAClass, MyAssembly  
                  Culture=neutral, PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
            </cryptoClasses>  
            <nameEntry name="RSA" class="MyCryptoRSA"/>  
            <nameEntry name="System.Security.Cryptography.AsymmetricAlgorithm"  
                       class="MyCryptoRSA"/>  
         </cryptoNameMapping>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Konfigurationsdateischema](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [Cryptography Settings Schema (Schema für Kryptografieeinstellungen)](../../../../../docs/framework/configure-apps/file-schema/cryptography/index.md)  
 [Kryptografische Dienste](../../../../../docs/standard/security/cryptographic-services.md)  
 [Konfigurieren kryptografischer Klassen](../../../../../docs/framework/configure-apps/configure-cryptography-classes.md)
