---
title: Fogli di stile incorporati in un documento
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: d79fb295-ebc7-438d-ba1b-05be7d534834
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 65987c5e29d593758b21259d6367202c882df2de
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/18/2018
ms.locfileid: "45742648"
---
# <a name="style-sheet-directives-embedded-in-a-document"></a>Fogli di stile incorporati in un documento

Può accadere che il codice XML esistente contenga la direttiva dei fogli di stile di `<?xml:stylesheet?>` che viene accettata da Microsoft Internet Explorer come alternativa alla sintassi `<?xml-stylesheet?>`. Quando i dati XML contengono una direttiva `<?xml:stylesheet?>`, come nei dati seguenti, se si tenta di caricare questi dati nel DOM XML, viene generata un'eccezione.

```xml
<?xml version="1.0" ?>
<?xml:stylesheet type="text/xsl" href="test2.xsl"?>
<root>
    <test>Node 1</test>
    <test>Node 2</test>
</root>
```

Questo si verifica perché `<?xml:stylesheet?>` viene considerata una **ProcessingInstruction** non valida per il DOM. In base alla specifica XML degli spazi dei nomi, una **ProcessingInstruction** può essere solo un NCName (No Column Name, nome senza due punti).

In base alla sezione 6 della specifica sugli spazi dei nomi in XML, la conformità dei metodi **Load** e **LoadXml** alla specifica significa che in un documento:

- Tutti i tipi di elementi e i nomi di attributi contengono uno zero o un segno di due punti.

- Nessun nome di entità, destinazione di ProcessingInstruction o nome di notazione contiene alcun segno di due punti.

Poiché `<?xml:stylesheet?>` contiene un segno di due punti, viene violata la regola del secondo punto.

Secondo la raccomandazione W3C (World Wide Web Consortium) [Associating Style Sheets with XML documents Version 1.0](https://www.w3.org/TR/xml-stylesheet/), l'istruzione di elaborazione per associare un foglio di stile XSL a un documento XML è `<?xml-stylesheet?>`, con un trattino al posto del segno di due punti.

## <a name="see-also"></a>Vedere anche

- [Modello DOM (Document Object Mode) XML](xml-document-object-model-dom.md)
