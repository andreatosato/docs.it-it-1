---
title: Quando distribuire i contenitori di Windows a Service Fabric
description: Modernizzare le applicazioni .NET esistenti con i contenitori di Windows e Cloud di Azure | Quando distribuire i contenitori di Windows a Service Fabric
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/30/2018
ms.openlocfilehash: c41db8b37c883f9369a6b8d1f8bccbc0535f504c
ms.sourcegitcommit: 88f251b08bf0718ce119f3d7302f514b74895038
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/10/2018
---
# <a name="when-to-deploy-windows-containers-to-service-fabric"></a><span data-ttu-id="abd84-103">Quando distribuire i contenitori di Windows a Service Fabric</span><span class="sxs-lookup"><span data-stu-id="abd84-103">When to deploy Windows Containers to Service Fabric</span></span>

<span data-ttu-id="abd84-104">Le applicazioni basate sui contenitori di Windows, rapidamente è necessario utilizzare le piattaforme che allontana ulteriormente da macchine virtuali IaaS.</span><span class="sxs-lookup"><span data-stu-id="abd84-104">Applications that are based on Windows Containers will quickly need to use platforms that move even further away from IaaS VMs.</span></span> <span data-ttu-id="abd84-105">Per migliorare la scalabilità automatica e scalabilità elevate e per ottenere miglioramenti significativi in un'esperienza di gestione completa per le distribuzioni, aggiornamenti, controllo delle versioni, rollback e il monitoraggio dello stato.</span><span class="sxs-lookup"><span data-stu-id="abd84-105">This is for improved automated scalability and high scalability, and to gain significant improvements in a complete management experience for deployments, upgrades, versioning, rollbacks, and health monitoring.</span></span> <span data-ttu-id="abd84-106">È possibile raggiungere questi obiettivi con orchestrator Azure Service Fabric, disponibile nel cloud di Microsoft Azure, ma anche in locale, o anche in un altro cloud.</span><span class="sxs-lookup"><span data-stu-id="abd84-106">You can achieve these goals with the orchestrator Azure Service Fabric, available in the Microsoft Azure cloud, but also on-premises, or even in another cloud.</span></span>

<span data-ttu-id="abd84-107">Molte organizzazioni sono sollevamento e spostamento di applicazioni monolitiche esistenti per i contenitori per due motivi:</span><span class="sxs-lookup"><span data-stu-id="abd84-107">Many organizations are lifting and shifting existing monolithic applications to containers for two reasons:</span></span>

-   <span data-ttu-id="abd84-108">Riduzione dei costi, a causa di consolidamento e la rimozione dell'hardware esistente, o da applicazioni in esecuzione in una densità più elevata.</span><span class="sxs-lookup"><span data-stu-id="abd84-108">Cost reductions, either due to consolidation and removal of existing hardware, or from running applications at a higher density.</span></span>

-   <span data-ttu-id="abd84-109">Un contratto di distribuzione coerente tra lo sviluppo e operazioni.</span><span class="sxs-lookup"><span data-stu-id="abd84-109">A consistent deployment contract between development and operations.</span></span>

<span data-ttu-id="abd84-110">Utilizzare la riduzione dei costi è riconosciuto, ed è probabile che tutte le organizzazioni sono la ricerca di tale obiettivo.</span><span class="sxs-lookup"><span data-stu-id="abd84-110">Pursuing cost reductions is understandable, and it's likely that all organizations are chasing that goal.</span></span> <span data-ttu-id="abd84-111">Distribuzione uniforme è più difficile da valutare, ma è ugualmente importante.</span><span class="sxs-lookup"><span data-stu-id="abd84-111">Consistent deployment is harder to evaluate, but it's equally as important.</span></span> <span data-ttu-id="abd84-112">Un contratto a distribuzione uniforme è indicato che gli sviluppatori possono scegliere di utilizzare la tecnologia e adeguato alle esigenze e il team operativo Ottiene un unico modo per distribuire e gestire applicazioni.</span><span class="sxs-lookup"><span data-stu-id="abd84-112">A consistent deployment contract says that developers are free to choose to use the technology that suits them, and the operations team gets a single way to deploy and manage applications.</span></span> <span data-ttu-id="abd84-113">Il presente contratto consente di attenuare il problema della presenza di gestire la complessità delle numerose tecnologie diverse operazioni o imporre agli sviluppatori di usare solo alcune delle tecnologie.</span><span class="sxs-lookup"><span data-stu-id="abd84-113">This agreement alleviates the pain of having operations deal with the complexity of many different technologies, or forcing developers to work only with certain technologies.</span></span> <span data-ttu-id="abd84-114">Ogni applicazione è in pratica, contenitore in un'immagine di distribuzione autonomo.</span><span class="sxs-lookup"><span data-stu-id="abd84-114">Essentially, each application is containerized in a self-contained deployment image.</span></span>

<span data-ttu-id="abd84-115">Alcune organizzazioni continuerà modernizzazione aggiungendo microservizi (applicazioni Cloud nativo), ma molte altre organizzazioni verranno arrestata qui (ottimizzato per il Cloud le applicazioni).</span><span class="sxs-lookup"><span data-stu-id="abd84-115">Some organizations will continue modernizing by adding microservices (Cloud-Native applications) but many other organizations will stop here (Cloud-Optimized applications).</span></span> <span data-ttu-id="abd84-116">Come illustrato nella figura 4-8, queste organizzazioni non spostare architetture microservizi perché potrebbe non necessario.</span><span class="sxs-lookup"><span data-stu-id="abd84-116">As shown in Figure 4-8, these organizations won't move to microservices architectures because they might not need to.</span></span> <span data-ttu-id="abd84-117">In ogni caso, sono già ottenere i vantaggi che utilizzando contenitori plus Service Fabric esperienza fornisce una gestione completa che include la distribuzione, viene aggiornato, il controllo delle versioni, rollback e il monitoraggio dello stato.</span><span class="sxs-lookup"><span data-stu-id="abd84-117">In any case, they already get the benefits that using containers plus Service Fabric provides-a complete management experience that includes deployment, upgrades, versioning, rollbacks, and health monitoring.</span></span>

> ![Spostare un'applicazione di Service Fabric](./media/image8.png)
>
> <span data-ttu-id="abd84-119">**Figura 4-8.**</span><span class="sxs-lookup"><span data-stu-id="abd84-119">**Figure 4-8.**</span></span> <span data-ttu-id="abd84-120">Spostare un'applicazione di Service Fabric</span><span class="sxs-lookup"><span data-stu-id="abd84-120">Lift and shift an application to Service Fabric</span></span>

<span data-ttu-id="abd84-121">Un approccio chiave a Service Fabric consiste nel riutilizzare il codice esistente e sollevare e spostare.</span><span class="sxs-lookup"><span data-stu-id="abd84-121">A key approach to Service Fabric is to reuse existing code and lift and shift.</span></span> <span data-ttu-id="abd84-122">Pertanto, è possibile eseguire la migrazione di applicazioni .NET Framework corrente, usando i contenitori di Windows e distribuirli a Service Fabric.</span><span class="sxs-lookup"><span data-stu-id="abd84-122">Therefore, you can migrate your current .NET Framework applications, by using Windows Containers, and deploy them to Service Fabric.</span></span> <span data-ttu-id="abd84-123">Sarà più semplice mantenere passare modernizzazione, infine, tramite l'aggiunta di nuovi microservizi.</span><span class="sxs-lookup"><span data-stu-id="abd84-123">It will be easier to keep going modernizing, eventually, by adding new microservices.</span></span>

<span data-ttu-id="abd84-124">Quando si confrontano Service Fabric per altri orchestrators, è importante evidenziare che Service Fabric è maturo all'esecuzione dei servizi e applicazioni basate su Windows.</span><span class="sxs-lookup"><span data-stu-id="abd84-124">When comparing Service Fabric to other orchestrators, it's important to highlight that Service Fabric is mature at running Windows-based applications and services.</span></span> <span data-ttu-id="abd84-125">Service Fabric è stato in esecuzione servizi basati su Windows e le applicazioni, inclusi i prodotti di livello 1, mission-critical da Microsoft per gli anni.</span><span class="sxs-lookup"><span data-stu-id="abd84-125">Service Fabric has been running Windows-based services and applications, including Tier-1, mission-critical products from Microsoft for years.</span></span> <span data-ttu-id="abd84-126">Era il primo orchestrator in disponibilità generale per i contenitori di Windows.</span><span class="sxs-lookup"><span data-stu-id="abd84-126">It was the first orchestrator to have general availability for Windows Containers.</span></span> <span data-ttu-id="abd84-127">Altri contenitori, ad esempio Kubernetes, controller di dominio/OS e Docker Swarm, sono più maturi in Linux, ma meno avanzata di servizi dell'infrastruttura per applicazioni Windows e i contenitori di Windows.</span><span class="sxs-lookup"><span data-stu-id="abd84-127">Other containers, like Kubernetes, DC/OS, and Docker Swarm, are more mature in Linux, but less mature than Service Fabric for Windows-based applications and Windows Containers.</span></span>

<span data-ttu-id="abd84-128">L'obiettivo finale di Service Fabric è ridurre la complessità della compilazione di applicazioni utilizzando un approccio di microservizi.</span><span class="sxs-lookup"><span data-stu-id="abd84-128">The ultimate goal of Service Fabric is to reduce the complexities of building applications by using a microservices approach.</span></span> <span data-ttu-id="abd84-129">Infine si desidera un microservizi per determinati tipi di applicazioni per evitare costosi riprogettazioni.</span><span class="sxs-lookup"><span data-stu-id="abd84-129">You eventually want a microservices for certain types of applications to avoid costly redesigns.</span></span> <span data-ttu-id="abd84-130">È possibile iniziare quando necessario, deprecare i servizi, aggiungere nuovi servizi e le sviluppare l'applicazione con utilizzo cliente.</span><span class="sxs-lookup"><span data-stu-id="abd84-130">You can start small, scale when needed, deprecate services, add new services, and evolve your application with customer use.</span></span> <span data-ttu-id="abd84-131">Esistono molti altri problemi che devono ancora essere risolti affinché microservizi più accessibile per la maggior parte degli sviluppatori.</span><span class="sxs-lookup"><span data-stu-id="abd84-131">There are many other problems that are yet to be solved to make microservices more approachable for most developers.</span></span> <span data-ttu-id="abd84-132">Se attualmente sono appena sollevamento e spostamento di un'applicazione con i contenitori di Windows, ma si sta pensando di aggiunta di microservizi basato sui contenitori in futuro, che è l'ideale Service Fabric.</span><span class="sxs-lookup"><span data-stu-id="abd84-132">If you currently are just lifting and shifting an application with Windows Containers, but you are thinking about adding microservices based on containers in the future, that is the Service Fabric sweet spot.</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="abd84-133">[Precedente](when-to-deploy-windows-containers-to-azure-vms-iaas-cloud.md)
[Successivo](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)</span><span class="sxs-lookup"><span data-stu-id="abd84-133">[Previous](when-to-deploy-windows-containers-to-azure-vms-iaas-cloud.md)
[Next](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)</span></span>