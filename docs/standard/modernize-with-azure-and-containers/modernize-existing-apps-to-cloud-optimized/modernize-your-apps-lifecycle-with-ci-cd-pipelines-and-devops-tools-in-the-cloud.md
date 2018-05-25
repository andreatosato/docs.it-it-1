---
title: Modernizzare del ciclo di vita dell'app con le pipeline CI/CD-ROM e gli strumenti DevOps nel cloud
description: Modernizzare le applicazioni .NET esistenti con i contenitori di Windows e Cloud di Azure | Modernizzare del ciclo di vita dell'app con le pipeline CI/CD e gli strumenti DevOps nel cloud
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/30/2018
ms.openlocfilehash: 63907a1911b4c95f0dbecb2af33964225cf3e7b1
ms.sourcegitcommit: 88f251b08bf0718ce119f3d7302f514b74895038
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/10/2018
---
# <a name="modernize-your-apps-lifecycle-with-cicd-pipelines-and-devops-tools-in-the-cloud"></a><span data-ttu-id="e6b43-103">Modernizzare del ciclo di vita dell'app con le pipeline CI/CD-ROM e gli strumenti DevOps nel cloud</span><span class="sxs-lookup"><span data-stu-id="e6b43-103">Modernize your app's lifecycle with CI/CD pipelines and DevOps tools in the cloud</span></span>

<span data-ttu-id="e6b43-104">Aziende necessario innovazione a un ritmo rapido per essere competitivi in marketplace.</span><span class="sxs-lookup"><span data-stu-id="e6b43-104">Today’s businesses need to innovate at a rapid pace to be competitive in the marketplace.</span></span> <span data-ttu-id="e6b43-105">Recapito di alta qualità, le applicazioni moderne richiede gli strumenti DevOps e i processi di importanza cruciale per implementare questo ciclo costante dell'innovazione.</span><span class="sxs-lookup"><span data-stu-id="e6b43-105">Delivering high-quality, modern applications requires DevOps tools and processes that are critical to implement this constant cycle of innovation.</span></span> <span data-ttu-id="e6b43-106">Con gli strumenti DevOps appropriati, gli sviluppatori possono semplificare la distribuzione continua e ottenere più rapidamente applicazioni innovative disposizione degli utenti.</span><span class="sxs-lookup"><span data-stu-id="e6b43-106">With the right DevOps tools, developers can streamline continuous deployment and get innovative applications into the hands of users more quickly.</span></span>

<span data-ttu-id="e6b43-107">Sebbene procedure consigliate di integrazione e la distribuzione continua sono ben definite, l'introduzione di contenitori introduce nuove considerazioni, in particolare quando si lavora con le applicazioni multi-contenitore.</span><span class="sxs-lookup"><span data-stu-id="e6b43-107">Although continuous integration and deployment practices are well established, the introduction of containers introduces new considerations, particularly when you are working with multi-container applications.</span></span>

<span data-ttu-id="e6b43-108">Visual Studio Team Services supporta l'integrazione continua e distribuzione di applicazioni multi-contenitore a un'ampia gamma di ambienti mediante le attività di distribuzione ufficiale del Team Services:</span><span class="sxs-lookup"><span data-stu-id="e6b43-108">Visual Studio Team Services supports continuous integration and deployment of multi-container applications to a variety of environments through the official Team Services deployment tasks:</span></span>

-   <span data-ttu-id="e6b43-109">[Distribuire in una macchina virtuale Host Docker autonoma](https://docs.microsoft.com/vsts/build-release/apps/cd/deploy-docker-windowsvm) (Linux o Windows Server 2016 o versioni successive)</span><span class="sxs-lookup"><span data-stu-id="e6b43-109">[Deploy to standalone Docker Host VM](https://docs.microsoft.com/vsts/build-release/apps/cd/deploy-docker-windowsvm) (Linux or Windows Server 2016 or later)</span></span>

-   [<span data-ttu-id="e6b43-110">Distribuire a Service Fabric</span><span class="sxs-lookup"><span data-stu-id="e6b43-110">Deploy to Service Fabric</span></span>](https://docs.microsoft.com/azure/service-fabric/service-fabric-tutorial-deploy-app-with-cicd-vsts)

-   [<span data-ttu-id="e6b43-111">Distribuire il servizio di contenitore di Azure – Kubernetes</span><span class="sxs-lookup"><span data-stu-id="e6b43-111">Deploy to Azure Container Service – Kubernetes</span></span>](https://docs.microsoft.com/vsts/build-release/apps/cd/azure/deploy-container-kubernetes)

<span data-ttu-id="e6b43-112">Ma è anche possibile distribuire [Docker Swarm](https://blogs.msdn.microsoft.com/jcorioland/2016/11/29/full-ci-cd-pipeline-to-deploy-multi-containers-application-on-azure-container-service-docker-swarm-using-visual-studio-team-services/) o controller di dominio o del sistema operativo tramite le attività di Team Services basato su script.</span><span class="sxs-lookup"><span data-stu-id="e6b43-112">But you also can deploy to [Docker Swarm](https://blogs.msdn.microsoft.com/jcorioland/2016/11/29/full-ci-cd-pipeline-to-deploy-multi-containers-application-on-azure-container-service-docker-swarm-using-visual-studio-team-services/) or DC/OS by using Team Services script-based tasks.</span></span>

<span data-ttu-id="e6b43-113">Per continuare agevolare la flessibilità di distribuzione, questi strumenti offrono si verifica nella distribuzione di dev-a-a-produzione di prova eccellente per carichi di lavoro contenitore, con una gamma di sviluppo e le soluzioni CI/CD-ROM.</span><span class="sxs-lookup"><span data-stu-id="e6b43-113">To continue facilitating deployment agility, these tools provide excellent dev-to-test-to-production deployment experiences for container workloads, with a choice of development and CI/CD solutions.</span></span>

<span data-ttu-id="e6b43-114">Figura 4-12 illustra una pipeline di distribuzione continua che distribuisce un cluster Kubernetes contenitore nel servizio di Azure.</span><span class="sxs-lookup"><span data-stu-id="e6b43-114">Figure 4-12 shows a continuous deployment pipeline that deploys to a Kubernetes cluster in Azure Container Service.</span></span>

![Pipeline distribuzione continua di Visual Studio Team Services, la distribuzione in un cluster Kubernetes](./media/image12.png)

> <span data-ttu-id="e6b43-116">**Figura 4-12.**</span><span class="sxs-lookup"><span data-stu-id="e6b43-116">**Figure 4-12.**</span></span> <span data-ttu-id="e6b43-117">Pipeline distribuzione continua di Visual Studio Team Services, la distribuzione in un cluster Kubernetes</span><span class="sxs-lookup"><span data-stu-id="e6b43-117">Visual Studio Team Services continuous deployment pipeline, deploying to a Kubernetes cluster</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="e6b43-118">[Precedente](modernize-your-apps-with-monitoring-and-telemetry.md)
[Successivo](migrate-to-hybrid-cloud-scenarios.md)</span><span class="sxs-lookup"><span data-stu-id="e6b43-118">[Previous](modernize-your-apps-with-monitoring-and-telemetry.md)
[Next](migrate-to-hybrid-cloud-scenarios.md)</span></span>