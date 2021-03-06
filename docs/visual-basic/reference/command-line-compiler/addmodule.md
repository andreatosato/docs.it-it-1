---
title: -addmodule
ms.date: 03/09/2018
helpviewer_keywords:
- /addmodule compiler option [Visual Basic]
- addmodule compiler option [Visual Basic]
- -addmodule compiler option [Visual Basic]
ms.assetid: fb4b89d4-4926-4f20-868d-427fa28497b2
ms.openlocfilehash: 2fefdf81ab25d2e109f265f0c895a3415ad5673d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33656006"
---
# <a name="-addmodule"></a>-addmodule
Fa sì che il compilatore renda disponibili per il progetto in compilazione tutte le informazioni sui tipi presenti nei file specificati.  
  
## <a name="syntax"></a>Sintassi  
  
```  
-addmodule:fileList  
```  
  
## <a name="arguments"></a>Argomenti  
 `fileList`  
 Obbligatorio. Elenco delimitato da virgole dei file che contengono i metadati, ma non contengono manifesti dell'assembly. I nomi di file contenenti spazi devono essere racchiusi tra virgolette ("").  
  
## <a name="remarks"></a>Note  
 I file elencati mediante il `fileList` parametro deve essere creato con il `-target:module` opzione o con equivalente del compilatore `-target:module`.  
  
 Tutti i moduli aggiunti con `-addmodule` deve essere nella stessa directory del file di output in fase di esecuzione. Ovvero, è possibile specificare un modulo in qualsiasi directory in fase di compilazione, ma il modulo deve essere nella directory dell'applicazione in fase di esecuzione. In caso contrario, viene visualizzato un <xref:System.TypeLoadException> errore.  
  
 Se si specifica, in modo implicito o esplicito, qualsiasi[-destinazione (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md) opzione diverso `-target:module` con `-addmodule`, i file passati a `-addmodule` diventano parte dell'assembly del progetto. È necessario un assembly per l'esecuzione di un file di output che contiene uno o più file aggiunti con `-addmodule`.  
  
 Utilizzare [/reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md) per importare i metadati da un file contenente un assembly.  
  
> [!NOTE]
>  Il `-addmodule` opzione non è disponibile all'interno dell'ambiente di sviluppo di Visual Studio; è disponibile solo durante la compilazione dalla riga di comando.  
  
## <a name="example"></a>Esempio  
 Il codice seguente crea un modulo.  
  
 [!code-vb[VbVbalrCompiler#47](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/addmodule_1.vb)]  
  
 Il codice riportato di seguito Importa i tipi del modulo.  
  
 [!code-vb[VbVbalrCompiler#48](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/addmodule_2.vb)]  
  
 Quando si esegue `t1`, restituisce come output `802`.  
  
## <a name="see-also"></a>Vedere anche  
 [Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)  
 [-target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)  
 [-riferimenti (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)  
 [Esempi di righe di comando di compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
