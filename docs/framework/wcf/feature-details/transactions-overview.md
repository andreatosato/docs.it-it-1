---
title: Panoramica sulle transazioni di Windows Communication Foundation
ms.date: 03/30/2017
helpviewer_keywords:
- transactions [WCF]
- WCF, transactions
- Windows Communication Foundation, transactions
ms.assetid: c7757854-1207-4019-8b31-552578b7d570
ms.openlocfilehash: 63f3826215f24a4bab6d84709c2f9da6a9c8f4f9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33498556"
---
# <a name="windows-communication-foundation-transactions-overview"></a>Panoramica sulle transazioni di Windows Communication Foundation
Le transazioni consentono di radunare un set di azioni o operazioni in un'unica unità di esecuzione indivisibile. Una transazione è una raccolta di operazioni con le proprietà seguenti:  
  
-   Atomicità. Questo aspetto assicura che tutti gli aggiornamenti completati in una transazione specifica vengano sottoposti a commit e resi durevoli oppure vengono tutti interrotti e sottoposti a rollback allo stato precedente.  
  
-   Coerenza. Questa caratteristica garantisce che le modifiche eseguita in una transazione rappresentano una trasformazione da uno stato coerente a un altro. Ad esempio, una transazione che trasferisce denaro da un conto corrente a un conto di risparmio non modifica il quantità di denaro nel conto generale.  
  
-   Isolamento. Questo aspetto impedisce a una transazione di applicare modifiche di cui non è stato eseguito il commit ad altre transazioni simultanee. L'isolamento garantisce l'astrazione della concorrenza mentre assicura che una transazione non abbia un impatto imprevisto sull'esecuzione di un'altra transazione.  
  
-   Durabilità. Implica che, quando è stato eseguito il commit, gli aggiornamenti alle risorse gestite (ad esempio un record di database) verranno resi persistenti rispetto agli errori.  
  
 Windows Communication Foundation (WCF) fornisce un vasta gamma di funzionalità che consentono di creare transazioni distribuite nell'applicazione di servizio Web.  
  
 WCF implementa il supporto per il protocollo WS-AtomicTransaction (WS-AT) che consente alle applicazioni WCF per propagare transazioni alle applicazioni interoperative, ad esempio servizi Web interoperativi creati mediante tecnologie di terze parti. WCF implementa inoltre il supporto per il protocollo delle transazioni OLE, che può essere usato negli scenari in cui non è necessario funzionalità di interoperabilità per abilitare il flusso delle transazioni.  
  
 È possibile usare un file di configurazione dell'applicazione per configurare associazioni che abilitano o disabilitano il flusso delle transazioni, nonché impostare il protocollo delle transazioni desiderato su un'associazione. È inoltre possibile impostare timeout delle transazioni a livello di servizio usando il file di configurazione. Per altre informazioni, vedere [l'abilitazione del flusso di transazione](../../../../docs/framework/wcf/feature-details/enabling-transaction-flow.md).  
  
 Gli attributi delle transazioni nello spazio dei nomi <xref:System.ServiceModel> consentono di eseguire le operazioni seguenti:  
  
-   Configurare timeout delle transazioni e filtri a livello di isolamento usando l'attributo <xref:System.ServiceModel.ServiceBehaviorAttribute>.  
  
-   Abilitare la funzionalità delle transazioni e configurare il comportamento di completamento delle transazioni usando l'attributo <xref:System.ServiceModel.OperationBehaviorAttribute>.  
  
-   Usare gli attributi <xref:System.ServiceModel.ServiceContractAttribute> e <xref:System.ServiceModel.OperationContractAttribute> su un metodo del contratto per richiedere, consentire o negare il flusso delle transazioni.  
  
 Per altre informazioni, vedere [gli attributi della transazione di ServiceModel](../../../../docs/framework/wcf/feature-details/servicemodel-transaction-attributes.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Attributi delle transazioni ServiceModel](../../../../docs/framework/wcf/feature-details/servicemodel-transaction-attributes.md)  
 [Attivazione del flusso delle transazioni](../../../../docs/framework/wcf/feature-details/enabling-transaction-flow.md)
