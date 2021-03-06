---
title: Utilizzo di un pennello a sfumatura per il riempimento di forme
ms.date: 03/30/2017
helpviewer_keywords:
- brushes [Windows Forms], gradient brushes
- gradient brushes
- examples [Windows Forms], gradient brushes
ms.assetid: 2c6037b9-05bd-44c0-a22a-19584b722524
ms.openlocfilehash: 857a9276a731ae5e69b3caa1a639d1315aba9901
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33525034"
---
# <a name="using-a-gradient-brush-to-fill-shapes"></a>Utilizzo di un pennello a sfumatura per il riempimento di forme
È possibile utilizzare un pennello a sfumatura per riempire una forma con un colore gradualmente. Ad esempio, è possibile utilizzare una sfumatura orizzontale per riempire una forma con colore che cambia gradualmente man mano che si sposta dal bordo sinistro della forma al bordo destro. Si supponga di un rettangolo con un bordo sinistro di colore nero (rappresentato da componenti rosso, verde e blu 0, 0, 0) e un diritto margine (rappresentato da 255, 0, 0). Se il rettangolo è 256 pixel in larghezza, il componente rosso di un determinato pixel sarà una maggiore il componente rosso di pixel alla sua sinistra. Il pixel più a sinistra in una riga ha componenti di colore (0, 0, 0), il secondo pixel è (1, 0, 0), il terzo pixel (2, 0, 0) e così via, fino a ottenere il pixel più a destra, che include componenti di colore (255, 0, 0). Questi valori di colore interpolata è costituiscono la sfumatura di colore.  
  
 Sfumatura lineare cambia colore quando si sposta orizzontalmente, verticalmente o parallela a una determinata riga inclinata. Quando si sposta sulla parte interna e limiti di un percorso, una sfumatura percorso cambia colore. È possibile personalizzare i gradienti del percorso per raggiungere una vasta gamma di effetti.  
  
 Nella figura seguente viene illustrato un rettangolo riempito con pennello sfumato lineare e un'ellisse riempita con un pennello a sfumatura.  
  
 ![Sfumatura](../../../../docs/framework/winforms/advanced/media/gradient2.png "gradient2")  
  
## <a name="in-this-section"></a>In questa sezione  
 [Procedura: Creare una sfumatura lineare](../../../../docs/framework/winforms/advanced/how-to-create-a-linear-gradient.md)  
 Viene illustrato come creare una sfumatura lineare utilizzando la <xref:System.Drawing.Drawing2D.LinearGradientBrush> classe.  
  
 [Procedura: Creare una sfumatura percorso](../../../../docs/framework/winforms/advanced/how-to-create-a-path-gradient.md)  
 Viene descritto come creare una sfumatura di percorso utilizzando il <xref:System.Drawing.Drawing2D.PathGradientBrush> classe.  
  
 [Procedura: Applicare la correzione gamma a una sfumatura](../../../../docs/framework/winforms/advanced/how-to-apply-gamma-correction-to-a-gradient.md)  
 Viene illustrato come utilizzare la correzione gamma con un pennello sfumato.  
  
## <a name="reference"></a>Riferimenti  
 <xref:System.Drawing.Drawing2D.LinearGradientBrush?displayProperty=nameWithType>  
 Contiene una descrizione di questa classe e include collegamenti a tutti i relativi membri.  
  
 <xref:System.Drawing.Drawing2D.PathGradientBrush?displayProperty=nameWithType>  
 Contiene una descrizione di questa classe e include collegamenti a tutti i relativi membri.
