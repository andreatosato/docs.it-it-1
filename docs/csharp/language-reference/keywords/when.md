---
title: when (Riferimenti per C#)
ms.date: 03/07/2017
f1_keywords:
- when_CSharpKeyword
- when
helpviewer_keywords:
- when keyword [C#]
ms.assetid: dd543335-ae37-48ac-9560-bd5f047b9aea
ms.openlocfilehash: a71cbdce256b1c1bd5d101d66f216fb229d70adf
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/29/2018
ms.locfileid: "47401131"
---
 # <a name="when-c-reference"></a>when (Riferimenti per C#)

È possibile usare la parola chiave contestuale `when` per specificare una condizione di filtro in due contesti:

- Nell'istruzione `catch` di un blocco [try/catch](try-catch.md) o [try/catch/finally](try-catch-finally.md).
- Nell'etichetta `case` di un'istruzione [switch](switch.md).

## <a name="when-in-a-catch-statement"></a>`when` in un'istruzione `catch`

A partire da C# 6 `When` può essere usata in un'istruzione `catch` per specificare una condizione che deve essere vera per eseguire il gestore di una determinata eccezione. La sintassi è la seguente:

```csharp
catch ExceptionType [e] when (expr)
```
dove *expr* è un'espressione che dà come risultato un valore booleano. Se restituisce `true`, il gestore di eccezioni viene eseguito, se restituisce `false`, non viene eseguito. 

Nell'esempio seguente viene usata la parola chiave `when` per eseguire in modo condizionale i gestori per un elemento <xref:System.Net.Http.HttpRequestException> in base al testo del messaggio dell'eccezione.

 [!code-csharp[when-with-catch](../../../../samples/snippets/csharp/language-reference/keywords/when/catch.cs)]  
  
## <a name="when-in-a-switch-statement"></a>`when` in un'istruzione `switch`

A partire da C# 7.0 non è più necessario che le etichette `case` siano reciprocamente esclusive e l'ordine in cui le etichette `case` appaiono in un'istruzione `switch` può determinare quale blocco switch eseguire. La parola chiave `when` può essere usata per specificare una condizione di filtro che fa sì che l'etichetta case associata sia vera solo se è vera anche la condizione di filtro. La sintassi è la seguente:

```csharp
case (expr) when (when-condition):
```
dove *expr* è un modello costante o un modello del tipo che viene confrontato con l'espressione di corrispondenza e *when-condition* è qualsiasi espressione booleana. 

Nell'esempio seguente viene usata la parola chiave `when` per testare gli oggetti `Shape` che hanno un'area pari a zero, nonché una varietà di oggetti `Shape` che hanno un'area maggiore di zero. 

 [!code-csharp[when-with-case#1](../../../../samples/snippets/csharp/language-reference/keywords/when/when.cs#1)]  

## <a name="see-also"></a>Vedere anche

- [Istruzione switch](switch.md)  
- [Istruzione try/catch](try-catch.md)  
- [Istruzione try/catch/finally](try-catch-finally.md) 
