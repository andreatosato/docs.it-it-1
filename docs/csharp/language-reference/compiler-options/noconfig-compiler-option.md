---
title: -noconfig (opzioni del compilatore C#)
ms.date: 07/20/2015
f1_keywords:
- /noconfig
helpviewer_keywords:
- /noconfig compiler option [C#]
- csc.rsp
- -noconfig compiler option [C#]
- noconfig compiler option [C#]
ms.assetid: cd26967e-e494-4c8c-b5c9-af13b2f78b2e
ms.openlocfilehash: b689a4bf0d8a1e57bf36f8ded7f2c9308f241670
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43527303"
---
# <a name="-noconfig-c-compiler-options"></a>-noconfig (opzioni del compilatore C#)
L'opzione **-noconfig** indica al compilatore di non eseguire la compilazione con il file csc.rsp, caricato e reso disponibile dalla stessa directory in cui si trova il file csc.exe.  
  
## <a name="syntax"></a>Sintassi  
  
```console  
-noconfig  
```  
  
## <a name="remarks"></a>Note  
 Il file csc.rsp fa riferimento a tutti gli assembly forniti con .NET Framework. I riferimenti effettivi inclusi nell'ambiente di sviluppo di Visual Studio .NET dipendono dal tipo di progetto.  
  
 È possibile modificare il file csc.rsp e specificare altre opzioni del compilatore da includere in ogni compilazione eseguita dalla riga di comando usando il file csc.exe (ad eccezione dell'opzione **-noconfig**).  
  
 Le opzioni passate al comando **csc** verranno elaborate nel compilatore per ultime. Le opzioni della riga di comando eseguiranno pertanto l'override delle impostazioni relative alle stesse opzioni nel file csc.rsp.  
  
 Se non si vuole che il compilatore cerchi e usi le impostazioni del file csc.rsp, specificare **-noconfig**.  
  
 Questa opzione del compilatore non è disponibile in Visual Studio e non può essere modificata a livello di codice.  
  
## <a name="see-also"></a>Vedere anche  

- [Opzioni del compilatore C#](../../../csharp/language-reference/compiler-options/index.md)  
- [Gestione delle proprietà di progetti e soluzioni](/visualstudio/ide/managing-project-and-solution-properties)
