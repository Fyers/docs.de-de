---
title: Schlüsselwort „params“ (C#-Referenz)
ms.date: 07/20/2015
f1_keywords:
- params_CSharpKeyword
- params
helpviewer_keywords:
- parameters [C#], params
- params keyword [C#]
ms.assetid: 1690815e-b52b-4967-8380-5780aff08012
ms.openlocfilehash: 089e31f3aad12c2303619e2a1998d0d6a5a0ad86
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2018
ms.locfileid: "47208775"
---
# <a name="params-c-reference"></a>params (C#-Referenz)

Mithilfe des Schlüsselworts `params` kann ein [Methodenparameter](method-parameters.md) angegeben werden, der eine variable Anzahl von Argumenten akzeptiert.

Sie können eine durch Trennzeichen getrennte Liste der Argumente des in der Parameterdeklaration angegebenen Typs oder ein Array der Argumente des angegebenen Typs senden. Sie können auch auf das Senden von Argumenten verzichten. Wenn Sie keine Argumente senden, ist die Länge der `params`-Liste 0 (null).

Nach dem `params`-Schlüsselwort sind keine zusätzlichen Parameter in einer Methodendeklaration zugelassen. Gleichzeitig ist nur ein `params`-Schlüsselwort in einer Methodendeklaration zulässig.

Der deklarierte Typ des `params`-Parameters muss wie im folgenden Beispiel gezeigt ein eindimensionales Array sein. Andernfalls tritt der Compilerfehler [CS0225](../../misc/cs0225.md) ein.

## <a name="example"></a>Beispiel

Im folgenden Beispiel werden verschiedene Methoden veranschaulicht, in denen Argumente an einen `params`-Parameter gesendet werden können.

[!code-csharp[csrefKeywordsMethodParams#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsMethodParams/CS/csrefKeywordsMethodParams.cs#5)] 

## <a name="c-language-specification"></a>C#-Sprachspezifikation

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Programmierhandbuch](../../programming-guide/index.md)
- [C#-Schlüsselwörter](index.md)
- [Methodenparameter](method-parameters.md)