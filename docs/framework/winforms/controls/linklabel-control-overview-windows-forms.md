---
title: Cenni preliminari sul controllo LinkLabel (Windows Form)
ms.date: 03/30/2017
f1_keywords:
- LinkLabel
helpviewer_keywords:
- links [Windows Forms], LinkLabel control
- Label control [Windows Forms], about Label control
- LinkLabel control [Windows Forms], about LinkLabel control
ms.assetid: 9e248549-10ca-43a3-bb5e-60f583d369f1
ms.openlocfilehash: 40326a9055ff51efae5f4c64744d0966870c6f6b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="linklabel-control-overview-windows-forms"></a>Cenni preliminari sul controllo LinkLabel (Windows Form)
Windows Form <xref:System.Windows.Forms.LinkLabel> controllo consente di aggiungere collegamenti ipertestuali alle applicazioni Windows Form. È possibile utilizzare il <xref:System.Windows.Forms.LinkLabel> controllo per tutti gli elementi che è possibile utilizzare il <xref:System.Windows.Forms.Label> controllare per; è inoltre possibile impostare una parte del testo come un collegamento a un file, una cartella o una pagina Web.  
  
## <a name="what-you-can-do-with-the-linklabel-control"></a>Cosa si può fare con il controllo LinkLabel  
 Oltre a tutte le proprietà, metodi e gli eventi del <xref:System.Windows.Forms.Label> (controllo), il <xref:System.Windows.Forms.LinkLabel> controllo dispone di proprietà per i collegamenti ipertestuali e i colori dei collegamenti. Il <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> proprietà imposta l'area di testo che attiva il collegamento. Il <xref:System.Windows.Forms.LinkLabel.LinkColor%2A>, <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A>, e <xref:System.Windows.Forms.LinkLabel.ActiveLinkColor%2A> impostano i colori del collegamento. Il <xref:System.Windows.Forms.LinkLabel.LinkClicked> eventi determina cosa accade quando si seleziona il testo del collegamento.  
  
 L'utilizzo di più semplice la <xref:System.Windows.Forms.LinkLabel> controllo consiste nel visualizzare un singolo collegamento mediante il <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> proprietà, ma è anche possibile visualizzare più collegamenti ipertestuali utilizzando il <xref:System.Windows.Forms.LinkLabel.Links%2A> proprietà. Il <xref:System.Windows.Forms.LinkLabel.Links%2A> proprietà consente di accedere a una raccolta di collegamenti. È inoltre possibile specificare i dati di <xref:System.Windows.Forms.LinkLabel.Link.LinkData%2A> proprietà di ogni singolo <xref:System.Windows.Forms.LinkLabel.Link> oggetto. Il valore di <xref:System.Windows.Forms.LinkLabel.Link.LinkData%2A> proprietà può essere utilizzata per archiviare il percorso di un file di visualizzazione o l'indirizzo di un sito Web.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.LinkLabel>  
 [Panoramica sul controllo Label](../../../../docs/framework/winforms/controls/label-control-overview-windows-forms.md)  
 [Procedura: Eseguire il collegamento a un oggetto o a una pagina Web con il controllo LinkLabel di Windows Form](../../../../docs/framework/winforms/controls/link-to-an-object-or-web-page-with-wf-linklabel-control.md)  
 [Procedura: Modificare l'aspetto del controllo LinkLabel di Windows Form](../../../../docs/framework/winforms/controls/how-to-change-the-appearance-of-the-windows-forms-linklabel-control.md)
