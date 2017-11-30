---
title: Debug Silverlight
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- debugging API [Silverlight]
- Silverlight, debugging
ms.assetid: 5e903e04-17d0-4014-ac9a-a43330ec8b1c
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: bf39d2dd12207d594c7bf5bd5b249d82c3f15d3c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="silverlight-debugging"></a>Debug Silverlight
Gli argomenti in questa sezione descrivono l'ambiente e le interfacce forniti da Common Language Runtime (CLR) per supportare il debug delle applicazioni basate su Silverlight in esecuzione nel sistema operativo Windows o sulla piattaforma Macintosh.  
  
## <a name="in-this-section"></a>Contenuto della sezione  
 [Funzione EnumerateCLRs](../../../../docs/framework/unmanaged-api/debugging/enumerateclrs-function.md)  
 Fornisce un meccanismo per l'enumerazione di CLR in un processo.  
  
 [Funzione CloseCLREnumeration](../../../../docs/framework/unmanaged-api/debugging/closeclrenumeration-function.md)  
 Chiude tutti gli eventi continuano l'avvio CLR validi posizionati in una matrice di handle restituita dal [funzione EnumerateCLRs](../../../../docs/framework/unmanaged-api/debugging/enumerateclrs-function.md)e libera la memoria per le matrici del percorso stringa e di handle.  
  
 [Funzione CreateCoreClrDebugTarget](../../../../docs/framework/unmanaged-api/debugging/createcoreclrdebugtarget-function.md)  
 Crea una connessione a una destinazione remota per l'enumerazione del runtime e dei processi.  
  
 [Funzione CreateCordbObject](../../../../docs/framework/unmanaged-api/debugging/createcordbobject-function.md)  
 Crea un'interfaccia del debugger che fornisce la funzionalità per creare un'istanza di una sessione di debug gestita in un processo remoto.  
  
 [Funzione CreateVersionStringFromModule](../../../../docs/framework/unmanaged-api/debugging/createversionstringfrommodule-function.md)  
 Crea una stringa di versione da un percorso CLR in un processo di destinazione.  
  
 [CreateDebuggingInterfaceFromVersion (funzione)](../../../../docs/framework/unmanaged-api/debugging/createdebugginginterfacefromversion-function-for-silverlight.md)  
 Accetta una stringa di versione CLR restituiti da [funzione CreateVersionStringFromModule](../../../../docs/framework/unmanaged-api/debugging/createversionstringfrommodule-function.md)funzione e restituisce un'interfaccia del debugger corrispondente.  
  
 [Struttura CoreClrDebugProcInfo](../../../../docs/framework/unmanaged-api/debugging/coreclrdebugprocinfo-structure.md)  
 Rappresenta un processo in esecuzione in un computer remoto.  
  
 [Struttura CoreClrDebugRuntimeInfo](../../../../docs/framework/unmanaged-api/debugging/coreclrdebugruntimeinfo-structure.md)  
 Rappresenta un'istanza di Common Language Runtime (CLR) che viene caricata in un processo in un computer remoto.  
  
 [Funzione GetStartupNotificationEvent](../../../../docs/framework/unmanaged-api/debugging/getstartupnotificationevent-function.md)  
 Crea o apre un handle dell'evento che verrà segnalato da qualsiasi CLR (Common Language Runtime) caricato nel processo di destinazione specificato.  
  
 [Interfaccia ICoreClrDebugTarget](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-interface.md)  
 Crea una connessione a una destinazione remota per l'enumerazione del runtime e dei processi.  
  
 [Funzione InitDbgTransportManager](../../../../docs/framework/unmanaged-api/debugging/initdbgtransportmanager-function.md)  
 Inizializza il gestore trasporto per connettersi a una destinazione remota per l'enumerazione del runtime e dei processi.  
  
 [Funzione ShutdownDbgTransportManager](../../../../docs/framework/unmanaged-api/debugging/shutdowndbgtransportmanager-function.md)  
 Arresta il gestore trasporto per una connessione a un computer di destinazione remoto.  
  
## <a name="see-also"></a>Vedere anche  
 [Coclassi di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-coclasses.md)  
 [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [Funzioni statiche globali di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)  
 [Enumerazioni di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)  
 [Strutture di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)