---
title: Eseguire la migrazione a scenari di cloud ibrido
description: Modernizzare le applicazioni .NET esistenti con i contenitori di Windows e Cloud di Azure | Eseguire la migrazione a scenari cloud ibridi
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/30/2018
ms.openlocfilehash: 8885ee8fce4f8c11c14ee8936f3ee0ffd89ece04
ms.sourcegitcommit: 88f251b08bf0718ce119f3d7302f514b74895038
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/10/2018
ms.locfileid: "33957891"
---
# <a name="migrate-to-hybrid-cloud-scenarios"></a>Eseguire la migrazione a scenari di cloud ibrido

Non è possibile eseguire la migrazione di alcune organizzazioni e aziende alcune delle proprie applicazioni per cloud pubblici, come Microsoft Azure o qualsiasi altro cloud pubblico a causa di normative o ai propri criteri. Tuttavia, è probabile che un'organizzazione potrebbe traggono profitto dalla presenza di alcune delle proprie applicazioni nel cloud pubblico e altre applicazioni in locale. Ma può provocare un ambiente misto complessità eccessiva in ambienti a causa di diverse piattaforme e tecnologie utilizzate in cloud pubblici e ambienti locali.

Microsoft offre la migliore soluzione di cloud ibrido, uno in cui è possibile ottimizzare le risorse esistenti in locale e nel cloud pubblico, mentre garantire la coerenza in un cloud ibrido di Azure. È possibile ottimizzare le competenze esistenti e ottenere un approccio flessibile e unificato per la compilazione di App eseguiti nel cloud o locale, grazie a Azure Stack (locale) e Azure (cloud pubblici).

Quando si tratta di sicurezza, è possibile centralizzare la gestione e sicurezza tra il cloud ibrido. È possibile ottenere controllo su tutti gli asset, dal Data Center nel cloud, fornendo single sign-on per on-premise e App cloud. A tale scopo estendendo Active Directory in un cloud ibrido e, utilizzando la gestione delle identità.

Infine, è possibile distribuire e analizzare facilmente i dati, utilizzare linguaggi di query per le risorse cloud e locali e applicare analitica e completo di apprendimento in Azure per arricchire i dati, indipendentemente dalla relativa origine.

## <a name="azure-stack"></a>Stack di Azure

Stack di Azure è una piattaforma di cloud ibrido che consente di fornire servizi di Azure dal Data Center dell'organizzazione. Stack di Azure è progettato per supportare nuove opzioni per le moderne applicazioni negli scenari chiave, ad esempio il bordo e ambienti non connessi o sicurezza e conformità requisiti specifici.

Figura 4-13 mostra una panoramica della piattaforma di cloud ibrido true che Microsoft offre.

![Piattaforma di cloud ibrido di Microsoft con Stack di Azure e Azure](./media/image13.jpg)

> **Figura 4-13.** Piattaforma di cloud ibrido di Microsoft con Stack di Azure e Azure

Stack di Azure viene offerto con due opzioni di distribuzione, in base alle esigenze:

-   Sistemi Stack integrate di Azure

-   Kit di sviluppo di Azure Stack

### <a name="azure-stack-integrated-systems"></a>Sistemi Stack integrate di Azure

Sistemi di Stack integrato Azure sono disponibili tramite una relazione di partner Microsoft e hardware. La relazione viene creata una soluzione che offre l'innovazione paced cloud viene bilanciato con semplicità di gestione. Perché lo Stack di Azure viene presentato come un sistema integrato di hardware e software, si verifica la giusta quantità di flessibilità e controllo, quando ancora adozione innovazione dal cloud. Sistemi di Stack integrato Azure intervallo dimensioni da 4 a 12 nodi e congiuntamente sono supportati dal partner hardware Microsoft. Utilizzare sistemi Azure Stack integrato per implementare nuovi scenari per i carichi di lavoro di produzione.

### <a name="azure-stack-development-kit"></a>Kit di sviluppo di Azure Stack

Kit di sviluppo di Microsoft Azure Stack è una distribuzione a nodo singolo dello Stack di Azure, è possibile utilizzare per valutare e informazioni sullo Stack di Azure. È anche possibile utilizzare Azure Stack Development Kit come un ambiente di sviluppo in cui è possibile sviluppare usando le API e strumenti che sono coerenti con Azure. Azure Kit di sviluppo dello Stack non deve essere utilizzato come un ambiente di produzione.

### <a name="additional-resources"></a>Risorse aggiuntive

-   **Cloud ibridi di Azure**

    [https://www.microsoft.com/cloud-platform/hybrid-cloud](https://www.microsoft.com/cloud-platform/hybrid-cloud)

-   **Azure Stack**

    [https://azure.microsoft.com/overview/azure-stack/](https://azure.microsoft.com/overview/azure-stack/)

-   **Account del servizio Active Directory per i contenitori di Windows**

    [https://docs.microsoft.com/virtualization/windowscontainers/manage-containers/manage-serviceaccounts](https://docs.microsoft.com/virtualization/windowscontainers/manage-containers/manage-serviceaccounts)

-   **Creare un contenitore con supporto di Active Directory**

    [https://blogs.msdn.microsoft.com/containerstuff/2017/01/30/create-a-container-with-active-directory-support/](https://blogs.msdn.microsoft.com/containerstuff/2017/01/30/create-a-container-with-active-directory-support/)

-   **Licenze vantaggio ibrida di Azure**

    [https://azure.microsoft.com/pricing/hybrid-use-benefit/](https://azure.microsoft.com/pricing/hybrid-use-benefit/)

>[!div class="step-by-step"]
[Precedente](modernize-your-apps-lifecycle-with-ci-cd-pipelines-and-devops-tools-in-the-cloud.md)
[Successivo](../walkthroughs-technical-get-started-overview.md)
