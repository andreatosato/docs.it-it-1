---
title: Aggiungere contenuto a una casella di testo utilizzando l'automazione interfaccia utente
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adding content to text boxes
- text boxes, adding content
- UI Automation, adding content to text boxes
ms.assetid: 8bdd1a73-1ecb-4a05-a891-a7827ebb767f
author: Xansky
ms.author: mhopkins
ms.openlocfilehash: 7c4772d36a88dfede04f7592c1cab776ddcd7d7d
ms.sourcegitcommit: 69229651598b427c550223d3c58aba82e47b3f82
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/04/2018
ms.locfileid: "48581785"
---
# <a name="add-content-to-a-text-box-using-ui-automation"></a>Aggiungere contenuto a una casella di testo utilizzando l'automazione interfaccia utente
> [!NOTE]
>  Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>. Per informazioni aggiornate sulle [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], vedere [Windows Automation API: automazione dell'interfaccia utente](https://go.microsoft.com/fwlink/?LinkID=156746).  
  
 In questo argomento contiene codice di esempio che illustra come usare [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] inserire testo in una casella di testo a riga singola. Viene fornito un metodo alternativo per i controlli di testo multilinea e accattivanti in cui [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] non è applicabile. Ai fini del confronto, l'esempio illustra anche come usare i metodi Win32 per ottenere gli stessi risultati.  
  
## <a name="example"></a>Esempio  
 La procedura di esempio seguente con una sequenza di controlli di testo in un'applicazione di destinazione. Ogni controllo di testo viene testato per verificare se un <xref:System.Windows.Automation.ValuePattern> oggetto può essere ottenuto da quest'ultimo usando il <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> (metodo). Se il controllo di testo supporta <xref:System.Windows.Automation.ValuePattern>, il <xref:System.Windows.Automation.ValuePattern.SetValue%2A> metodo viene utilizzato per inserire una stringa definita dall'utente nel controllo di testo. In caso contrario, il <xref:System.Windows.Forms.SendKeys.SendWait%2A?displayProperty=nameWithType> viene usato il metodo.  
  
 [!code-csharp[InsertText#InsertText](../../../samples/snippets/csharp/VS_Snippets_Wpf/InsertText/CSharp/Window1.xaml.cs#inserttext)]
 [!code-vb[InsertText#InsertText](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InsertText/VisualBasic/Window1.xaml.vb#inserttext)]  
  
## <a name="see-also"></a>Vedere anche  
 [TextPattern Insert Text Sample](https://msdn.microsoft.com/library/67353f93-7ee2-42f2-ab76-5c078cf6ca16)
