---
title: 'Procedura: aggiungere controlli a un Windows Form'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms controls, adding to form
- controls [Windows Forms], adding
ms.assetid: 2af86001-9d62-4154-87fb-66db2c3cd9fd
ms.openlocfilehash: 1b803a93f865eaa4db6751187213c4bb01d2a5ee
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/08/2018
ms.locfileid: "44213092"
---
# <a name="how-to-add-controls-to-windows-forms"></a>Procedura: aggiungere controlli a un Windows Form
La maggior parte dei moduli sono progettati con l'aggiunta di controlli alla superficie del form per definire l'interfaccia utente (UI). Oggetto *controllo* è un componente in un formato utilizzato per visualizzare informazioni o accettare l'input dell'utente. Per altre informazioni sui controlli, vedere [Windows Forms Controls](../../../../docs/framework/winforms/controls/index.md).  
  
> [!NOTE]
>  Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-draw-a-control-on-a-form"></a>Per disegnare un controllo in un form  
  
1.  Aprire il form. Per altre informazioni, vedere [procedura: visualizzare Windows Form nella finestra di progettazione](https://msdn.microsoft.com/library/bf3f1e5b-ea07-4529-85c6-6af3ded0cec5).  
  
2.  Nel **casella degli strumenti**, fare clic sul controllo da aggiungere al form.  
  
3.  Nel form, fare clic su cui l'angolo superiore sinistro del controllo da trovare e trascinare in cui si desidera l'angolo inferiore destro del controllo da individuare.  
  
     Il controllo viene aggiunto al form con il percorso specificato e le dimensioni.  
  
    > [!NOTE]
    >  Ogni controllo ha una dimensione predefinita definita. È possibile aggiungere un controllo al form nella dimensione predefinita del controllo trascinandolo dal **casella degli strumenti** al form.  
  
### <a name="to-drag-a-control-to-a-form"></a>Trascinare un controllo a un form  
  
1.  Aprire il form. Per altre informazioni, vedere [procedura: visualizzare Windows Form nella finestra di progettazione](https://msdn.microsoft.com/library/bf3f1e5b-ea07-4529-85c6-6af3ded0cec5).  
  
2.  Nel **casella degli strumenti**, scegliere il controllo desiderato e trascinarlo nel form.  
  
     Il controllo viene aggiunto al form nella posizione specificata nella dimensione predefinita.  
  
    > [!NOTE]
    >  È possibile fare doppio clic su un controllo nel **casella degli strumenti** per aggiungerlo all'angolo superiore sinistro del form nella dimensione predefinita.  
  
     È anche possibile aggiungere dinamicamente controlli a un form in fase di esecuzione. Nell'esempio di codice seguente, un <xref:System.Windows.Forms.TextBox> controllo verrà aggiunto al modulo quando un <xref:System.Windows.Forms.Button> si fa clic sul controllo.  
  
    > [!NOTE]
    >  La procedura seguente presuppone l'esistenza di un form con un **sul pulsante** controllo `Button1`, già posizionato su di esso.  
  
### <a name="to-add-a-control-to-a-form-programmatically"></a>Per aggiungere un controllo a un form a livello di codice  
  
1.  Nel metodo che gestisce il pulsante `Click` evento all'interno di classe del modulo, inserire il codice simile al seguente per aggiungere un riferimento alla variabile di controllo, imposta il controllo `Location`e aggiungere il controllo.  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click  
       Dim MyText As New TextBox()  
       MyText.Location = New Point(25, 25)  
       Me.Controls.Add(MyText)  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)   
    {  
       TextBox myText = new TextBox();  
       myText.Location = new Point(25,25);  
       this.Controls.Add (myText);  
    }  
    ```  
  
    ```cpp  
    private:  
      System::Void button1_Click(System::Object ^  sender,  
        System::EventArgs ^  e)  
      {  
        TextBox ^ myText = gcnew TextBox();  
        myText->Location = Point(25,25);  
        this->Controls->Add(myText);  
      }  
    ```  
  
    > [!NOTE]
    >  È anche possibile aggiungere codice per inizializzare le altre proprietà del controllo.  
  
    > [!IMPORTANT]
    >  Si potrebbe esporre il computer locale a un rischio per la sicurezza attraverso la rete facendo riferimento a un malintenzionato `UserControl`. Questa è solo un problema nel caso di un utente con un controllo personalizzato, seguito dall'utente erroneamente aggiungendolo al progetto.  
  
## <a name="see-also"></a>Vedere anche  
 [Controlli Windows Form](../../../../docs/framework/winforms/controls/index.md)  
 [Disposizione di controlli in Windows Form](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)  
 [Procedura: Ridimensionare i controlli di un Windows Form](../../../../docs/framework/winforms/controls/how-to-resize-controls-on-windows-forms.md)  
 [Procedura: Impostare il testo visualizzato da un controllo Windows Form](../../../../docs/framework/winforms/controls/how-to-set-the-text-displayed-by-a-windows-forms-control.md)  
 [Controlli da usare in Windows Form](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)
