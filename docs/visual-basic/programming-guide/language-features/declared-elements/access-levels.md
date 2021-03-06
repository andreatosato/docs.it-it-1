---
title: Livelli di accesso in Visual Basic
ms.date: 05/10/2018
helpviewer_keywords:
- members [Visual Basic], accessing in Visual Basic
- Friend access modifier
- access levels, declared elements
- access levels
- access modifiers
- Public access modifier
- Protected access modifier
- Protected Friend access modifier
- Private Protected access modifier
- Private access modifier
- declared elements [Visual Basic], access level
ms.assetid: 6e06c1ab-fd78-47f0-83a8-1152780b5e1a
ms.openlocfilehash: 1e2d43f33a352d3f4502965c5368eb901e7bffdf
ms.sourcegitcommit: 22c3c8f74eaa138dbbbb02eb7d720fce87fc30a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/17/2018
---
# <a name="access-levels-in-visual-basic"></a>Livelli di accesso in Visual Basic
Il *livello di accesso* di un elemento dichiarato è l'estensione della possibilità di accedervi, vale a dire, il codice dispone dell'autorizzazione di lettura o scrittura. Ciò dipende non solo dalla modalità di dichiarazione dell'elemento stesso, ma anche dal livello di accesso del contenitore dell'elemento. Codice che non può accedere a un elemento contenitore non può accedere ai relativi elementi contenuti, anche quelli dichiarati come `Public`. Ad esempio, un `Public` variabile in un `Private` struttura accessibili dall'interno della classe che contiene la struttura, ma non dall'esterno della classe.  
  
## <a name="public"></a>Public  
 Il [pubblica](../../../../visual-basic/language-reference/modifiers/public.md) parola chiave nell'istruzione di dichiarazione specifica che l'elemento sia accessibile da qualsiasi codice nello stesso progetto, da altri progetti che fanno riferimento al progetto e da qualsiasi assembly compilato dal progetto. Nel codice seguente viene illustrato un esempio `Public` dichiarazione.  
  
```vb  
Public Class classForEverybody  
```  
  
 È possibile utilizzare `Public` solo a livello di modulo, interfaccia o spazio dei nomi. Ciò significa che è possibile dichiarare un elemento pubblico a livello di un file di origine o di spazio dei nomi, o all'interno di un'interfaccia, modulo, classe o struttura, ma non in una stored procedure.  
  
## <a name="protected"></a>Protetta  
 Il [Protected](../../../../visual-basic/language-reference/modifiers/protected.md) parola chiave nell'istruzione di dichiarazione specifica che l'elemento è accessibile solo dall'interno della stessa classe o da una classe derivata da questa classe. Nel codice seguente viene illustrato un esempio `Protected` dichiarazione.  
  
```vb  
Protected Class classForMyHeirs  
```  
  
 È possibile utilizzare `Protected` solo alla classe di livello e solo quando si dichiara un membro di una classe. Ciò significa che è possibile dichiarare un elemento protetto in una classe, ma non a livello di un file di origine o di spazio dei nomi o all'interno di un'interfaccia, modulo, struttura o stored procedure.  
  
## <a name="friend"></a>Friend  
 Il [Friend](../../../../visual-basic/language-reference/modifiers/friend.md) parola chiave nell'istruzione di dichiarazione specifica che l'elemento è accessibile dall'interno dello stesso assembly, ma non dall'esterno dell'assembly. Nel codice seguente viene illustrato un esempio `Friend` dichiarazione.  
  
```vb  
Friend stringForThisProject As String  
```  
  
 È possibile utilizzare `Friend` solo a livello di modulo, interfaccia o spazio dei nomi. Ciò significa che è possibile dichiarare un elemento friend a livello di un file di origine o di spazio dei nomi, o all'interno di un'interfaccia, modulo, classe o struttura, ma non in una stored procedure.  
  
## <a name="protected-friend"></a>Protected Friend  
 Il `Protected` e `Friend` le parole chiave nell'istruzione di dichiarazione specificano che l'elemento è possibile accedere dalle classi derivate o dall'interno dello stesso assembly o entrambi. Nel codice seguente viene illustrato un esempio `Protected Friend` dichiarazione.  
  
```vb  
Protected Friend stringForProjectAndHeirs As String  
```  
  
 È possibile utilizzare `Protected Friend` solo alla classe di livello e solo quando si dichiara un membro di una classe. Ciò significa che è possibile dichiarare un elemento protected friend in una classe, ma non a livello di un file di origine o di spazio dei nomi o all'interno di un'interfaccia, modulo, struttura o stored procedure.  
  
## <a name="private"></a>Private  
 Il [privato](../../../../visual-basic/language-reference/modifiers/private.md) parola chiave nell'istruzione di dichiarazione specifica che l'elemento sia accessibile solo da all'interno di modulo, classe o struttura stessa. Nel codice seguente viene illustrato un esempio `Private` dichiarazione.  
  
```vb  
Private numberForMeOnly As Integer  
```  
  
 Si può usare `Private` solo a livello di modulo. Ciò significa che è possibile dichiarare un elemento private all'interno di un modulo, classe o struttura, ma non a livello di un file di origine o di spazio dei nomi, in un'interfaccia o in una stored procedure.  
  
 A livello di modulo, il `Dim` istruzione senza alcuna parola chiave livello di accesso è equivalente a un `Private` dichiarazione. Tuttavia, è consigliabile utilizzare il `Private` (parola chiave) per rendere il codice più facile da leggere e interpretare.  

## <a name="private-protected"></a>Protetto privato

Il [privato protetto](../../../language-reference/modifiers/private-protected.md) parola chiave nell'istruzione di dichiarazione specifica che l'elemento sia accessibile solo da all'interno della stessa classe, nonché dalle classi derivate trovate nello stesso assembly come la classe che lo contiene. Il `Private Protected` modificatore di accesso è supportato a partire da Visual Basic 15,5.

L'esempio seguente mostra un `Private Protected` dichiarazione:

```vb
Private Protected internalValue As Integer
```

È possibile dichiarare un `Private Protected` elemento solo all'interno di una classe. Non è possibile dichiarare all'interno di un'interfaccia o struttura, né può dichiara la classe a livello di un file di origine o di spazio dei nomi, all'interno di un'interfaccia o una struttura o in una stored procedure.

Il `Private Protected` modificatore di accesso è supportato da Visual Basic 15,5 e versioni successive. Per usarlo, aggiungere l'elemento seguente al file di progetto (*. vbproj) di Visual Basic. Purché 15,5 Visual Basic o versione successiva è installato nel sistema, consente di sfruttare tutte le funzionalità del linguaggio è supportata dalla versione più recente del compilatore Visual Basic:

```xml
<PropertyGroup>
   <LangVersion>latest</LangVersion>
</PropertyGroup>
```

Utilizzare il `Private Protected` modificatore di accesso, è necessario aggiungere l'elemento seguente al file di progetto (*. vbproj) di Visual Basic:

```xml
<PropertyGroup>
   <LangVersion>15.5</LangVersion>
</PropertyGroup>
```

 ## <a name="access-modifiers"></a>Modificatori di accesso  
 Le parole chiave che specificano il livello di accesso vengono chiamate *modificatori di accesso*. Nella tabella seguente vengono confrontati i modificatori di accesso.  
  
|Modificatore di accesso|Livello di accesso concesso|Elementi che è possibile dichiarare con questo livello di accesso|Contesto della dichiarazione all'interno del quale è possibile utilizzare questo modificatore|  
|---------------------|--------------------------|-----------------------------------------------------|----------------------------------------------------------------|  
|`Public`|Senza restrizioni:<br /><br /> Può accedere qualsiasi codice che è possibile visualizzare un elemento pubblico|Interfacce<br /><br /> Moduli<br /><br /> Classi<br /><br /> Strutture<br /><br /> Membri di struttura<br /><br /> Procedure<br /><br /> Proprietà<br /><br /> Variabili membro<br /><br /> Costanti<br /><br /> Enumerazioni<br /><br /> Eventi<br /><br /> Dichiarazioni esterne<br /><br /> Delegati|File di origine<br /><br /> Spazio dei nomi<br /><br /> Interfaccia<br /><br /> Modulo<br /><br /> Classe<br /><br /> Struttura|  
|`Protected`|Derivazionali:<br /><br /> La classe che dichiara un elemento protetto, o una classe derivata da esso, è possibile accedere all'elemento di codice|Interfacce<br /><br /> Classi<br /><br /> Strutture<br /><br /> Procedure<br /><br /> Proprietà<br /><br /> Variabili membro<br /><br /> Costanti<br /><br /> Enumerazioni<br /><br /> Eventi<br /><br /> Dichiarazioni esterne<br /><br /> Delegati|Classe|  
|`Friend`|Assembly:<br /><br /> Codice dell'assembly che dichiara che un elemento friend può accedervi|Interfacce<br /><br /> Moduli<br /><br /> Classi<br /><br /> Strutture<br /><br /> Membri di struttura<br /><br /> Procedure<br /><br /> Proprietà<br /><br /> Variabili membro<br /><br /> Costanti<br /><br /> Enumerazioni<br /><br /> Eventi<br /><br /> Dichiarazioni esterne<br /><br /> Delegati|File di origine<br /><br /> Spazio dei nomi<br /><br /> Interfaccia<br /><br /> Modulo<br /><br /> Classe<br /><br /> Struttura|  
|`Protected` `Friend`|Unione di `Protected` e `Friend`:<br /><br /> Il codice nella stessa classe o nello stesso assembly, come un elemento protected friend o una qualsiasi classe derivata dalla classe dell'elemento accesso è consentito.|Interfacce<br /><br /> Classi<br /><br /> Strutture<br /><br /> Procedure<br /><br /> Proprietà<br /><br /> Variabili membro<br /><br /> Costanti<br /><br /> Enumerazioni<br /><br /> Eventi<br /><br /> Dichiarazioni esterne<br /><br /> Delegati|Classe|  
|`Private`|Contesto della dichiarazione:<br /><br /> Codice del tipo che dichiara un elemento private, incluso il codice dei tipi di contenuto, è possibile accedere all'elemento|Interfacce<br /><br /> Classi<br /><br /> Strutture<br /><br /> Membri di struttura<br /><br /> Procedure<br /><br /> Proprietà<br /><br /> Variabili membro<br /><br /> Costanti<br /><br /> Enumerazioni<br /><br /> Eventi<br /><br /> Dichiarazioni esterne<br /><br /> Delegati|Modulo<br /><br /> Classe<br /><br /> Struttura|
|`Private Protected`|Il codice della classe che dichiara un elemento protetto private o codice in una classe derivata trovato nello stesso assembly come classe di bas.|Interfacce<br /><br /> Classi<br /><br /> Strutture<br /><br /> Procedure<br /><br /> Proprietà<br /><br /> Variabili membro<br /><br /> Costanti<br /><br /> Enumerazioni<br /><br /> Eventi<br /><br /> Dichiarazioni esterne<br /><br /> Delegati|Classe|
  
## <a name="see-also"></a>Vedere anche  
 [Istruzione Dim](../../../../visual-basic/language-reference/statements/dim-statement.md)  
 [Static](../../../../visual-basic/language-reference/modifiers/static.md)  
 [Nomi di elementi dichiarati](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)  
 [Riferimenti a elementi dichiarati](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)  
 [Caratteristiche di elementi dichiarati](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)  
 [Durata in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)  
 [Ambito in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)  
 [Procedura: controllare la disponibilità di una variabile](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-control-the-availability-of-a-variable.md)  
 [Variabili](../../../../visual-basic/programming-guide/language-features/variables/index.md)  
 [Dichiarazione di variabile](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
