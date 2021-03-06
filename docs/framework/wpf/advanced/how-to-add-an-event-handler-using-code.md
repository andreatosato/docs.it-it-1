---
title: 'Procedura: aggiungere un gestore eventi mediante codice'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- event handlers [WPF], adding
- XAML [WPF], adding event handlers
ms.assetid: 269c61e0-6bd9-4291-9bed-1c5ee66da486
ms.openlocfilehash: 782f668557c3cb081d30e7835006af63c9ca4df5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33542623"
---
# <a name="how-to-add-an-event-handler-using-code"></a>Procedura: aggiungere un gestore eventi mediante codice
In questo esempio viene illustrato come aggiungere un gestore eventi a un elemento utilizzando il codice.  
  
 Se si desidera aggiungere un gestore eventi per un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] elemento e la pagina di markup che contiene l'elemento è già stato caricato, è necessario aggiungere il gestore mediante codice. In alternativa, se si sta compilando l'albero degli elementi di un'applicazione interamente mediante codice e non la dichiarazione di tutti gli elementi usando [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], è possibile chiamare i metodi specifici per aggiungere gestori eventi per la struttura dell'elemento costruito.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente aggiunge un nuovo <xref:System.Windows.Controls.Button> a una pagina esistente definita inizialmente in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. Un file code-behind implementa un metodo del gestore eventi e quindi aggiunge tale metodo come un nuovo gestore eventi nel <xref:System.Windows.Controls.Button>.  
  
 Nell'esempio c# viene utilizzata la `+=` operatore per assegnare un gestore a un evento. Questo è lo stesso operatore utilizzato per assegnare un gestore di [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] modello di gestione degli eventi. Microsoft Visual Basic non supporta questo operatore come un modo per aggiungere gestori eventi. Richiede invece una delle due tecniche seguenti:  
  
-   Utilizzare il <xref:System.Windows.UIElement.AddHandler%2A> metodo, insieme con un `AddressOf` operatore, fare riferimento all'implementazione del gestore eventi.  
  
-   Utilizzare il `Handles` (parola chiave) come parte della definizione del gestore eventi. Questa tecnica non viene visualizzata in questo contesto. vedere [Visual Basic e la gestione degli eventi di WPF](../../../../docs/framework/wpf/advanced/visual-basic-and-wpf-event-handling.md).  
  
 [!code-xaml[RoutedEventAddRemoveHandler#XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/CSharp/default.xaml#xaml)]  
  
 [!code-csharp[RoutedEventAddRemoveHandler#Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/CSharp/default.xaml.cs#handler)]
 [!code-vb[RoutedEventAddRemoveHandler#Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/VisualBasic/default.xaml.vb#handler)]  
  
> [!NOTE]
>  Aggiunta di un gestore eventi in inizialmente analizzata [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] pagina è molto più semplice. All'interno dell'elemento oggetto in cui si desidera aggiungere il gestore dell'evento, aggiungere un attributo che corrisponde al nome dell'evento che si desidera gestire. Quindi specificare il valore dell'attributo come nome del metodo del gestore eventi definiti nel file di codice il [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] pagina. Per ulteriori informazioni, vedere [Panoramica di XAML (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md) o [indirizzato Cenni preliminari sugli eventi](../../../../docs/framework/wpf/advanced/routed-events-overview.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Cenni preliminari sugli eventi indirizzati](../../../../docs/framework/wpf/advanced/routed-events-overview.md)  
 [Procedure relative alle proprietà](../../../../docs/framework/wpf/advanced/events-how-to-topics.md)
