---
title: Modelli di programmazione asincrona
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- asynchronous design patterns, .NET Framework
- .NET Framework, asynchronous design patterns
ms.assetid: 4ece5c0b-f8fe-4114-9862-ac02cfe5a5d7
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e399a512d2bee636aec35e008c0632ce9c5fa781
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/09/2018
ms.locfileid: "44249036"
---
# <a name="asynchronous-programming-patterns"></a>Modelli di programmazione asincrona

In .NET Framework sono disponibili tre modelli per l'esecuzione di operazioni asincrone:  
  
- **Modello di programmazione asincrona (APM)** (detto anche modello <xref:System.IAsyncResult>), dove le operazioni asincrone richiedono i metodi `Begin` e `End` (ad esempio, `BeginWrite` e `EndWrite` per le operazioni di scrittura asincrona). Questo modello non è più consigliato per i nuovi sviluppi. Per altre informazioni, vedere [Asynchronous Programming Model (APM)](../../../docs/standard/asynchronous-programming-patterns/asynchronous-programming-model-apm.md) (Modello di programmazione asincrona, APM).  
  
- **Modello asincrono basato su eventi (EAP)**, che richiede un metodo con suffisso `Async` oltre a uno o più eventi, tipi delegati di gestore eventi e tipi derivati da `EventArg`. EAP è stato introdotto in .NET Framework 2.0. Non è consigliabile per i nuovi sviluppi. Per ulteriori informazioni, vedere [Event-based Asynchronous Pattern (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md) (Modello asincrono basato su eventi, EAP).  
  
- **Modello asincrono basato su attività (TAP)**, che usa un unico metodo per rappresentare l'inizio e il completamento di un'operazione asincrona. TAP è stato introdotto in.NET Framework 4 ed è l'approccio consigliato per la programmazione asincrona in .NET Framework. Le parole chiave [async](~/docs/csharp/language-reference/keywords/async.md) e [await](~/docs/csharp/language-reference/keywords/await.md) in C# e gli operatori [Async](~/docs/visual-basic/language-reference/modifiers/async.md) e [Await](~/docs/visual-basic/language-reference/operators/await-operator.md) nel linguaggio Visual Basic aggiungono supporto del linguaggio per TAP. Per altre informazioni, vedere [Task-based Asynchronous Pattern (TAP)](../../../docs/standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md) (Modello asincrono basato su attività, TAP).  
  
## <a name="comparing-patterns"></a>Confronto tra modelli  

Per un rapido confronto tra le procedure delle operazioni asincrone dei tre modelli, considerare un metodo `Read` che legga una specifica quantità di rati in un determinato buffer, iniziando da uno specifico offset:  
  
```csharp  
public class MyClass  
{  
    public int Read(byte [] buffer, int offset, int count);  
}  
```  
  
La controparte APM di questo metodo esporrà i metodi `BeginRead` e `EndRead`:  
  
```csharp  
public class MyClass  
{  
    public IAsyncResult BeginRead(  
        byte [] buffer, int offset, int count,   
        AsyncCallback callback, object state);  
    public int EndRead(IAsyncResult asyncResult);  
}  
```  
  
La controparte EAP esporrà il seguente set di tipi e membri:  
  
```csharp  
public class MyClass  
{  
    public void ReadAsync(byte [] buffer, int offset, int count);  
    public event ReadCompletedEventHandler ReadCompleted;  
}  
```  
  
La controparte TAP esporrà il seguente metodo `ReadAsync` singolo:  
  
```csharp  
public class MyClass  
{  
    public Task<int> ReadAsync(byte [] buffer, int offset, int count);  
}  
```  
  
Per una trattazione completa di TAP, APM ed EAP, vedere i collegamenti disponibili nella sezione successiva.  
  
## <a name="related-topics"></a>Argomenti correlati

| Titolo | Descrizione |
| ----- | ----------- |
| [Asynchronous Programming Model (APM)](../../../docs/standard/asynchronous-programming-patterns/asynchronous-programming-model-apm.md) (Modello di programmazione asincrona, APM) | Viene descritto il modello legacy che usa l'interfaccia <xref:System.IAsyncResult> per ottenere un comportamento asincrono. Questo modello non è consigliabile per i nuovi sviluppi. |
| [Event-based Asynchronous Pattern (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md) (Modello asincrono basato su eventi, EAP) | Viene descritto il modello legacy per fornire il comportamento asincrono basato su eventi. Questo modello non è consigliabile per i nuovi sviluppi. |
| [Modello asincrono basato su attività (TAP)](../../../docs/standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md) | Viene descritto il nuovo modello asincrono basato sullo spazio dei nomi <xref:System.Threading.Tasks>. Questo modello è l'approccio consigliato per la programmazione asincrona in .NET Framework 4 e versioni successive. |

## <a name="see-also"></a>Vedere anche

- [Programmazione asincrona in C#](~/docs/csharp/async.md)   
- [Programmazione asincrona in F#](~/docs/fsharp/tutorials/asynchronous-and-concurrent-programming/async.md)   
- [Programmazione asincrona con Async e Await (Visual Basic)](~/docs/visual-basic/programming-guide/concepts/async/index.md)
