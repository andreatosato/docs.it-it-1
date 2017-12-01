---
title: Processo di sviluppo per Azure
description: Architettura di moderne applicazioni Web con ASP.NET Core e Azure | Processo di sviluppo per Azure
author: ardalis
ms.author: wiwagn
ms.date: 10/08/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.openlocfilehash: e676c1225f7d11381808040cf101e897e0726ad4
ms.sourcegitcommit: bbde43da655ae7bea1977f7af7345eb87bd7fd5f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/21/2017
---
# <a name="development-process-for-azure"></a><span data-ttu-id="6011a-103">Processo di sviluppo per Azure</span><span class="sxs-lookup"><span data-stu-id="6011a-103">Development process for Azure</span></span>

> <span data-ttu-id="6011a-104">_"Con il cloud, agli utenti e aziende di piccole dimensioni può blocca le dita e impostare immediatamente i servizi di livello aziendale."_</span><span class="sxs-lookup"><span data-stu-id="6011a-104">_"With the cloud, individuals and small businesses can snap their fingers and instantly set up enterprise-class services."_</span></span>  
> <span data-ttu-id="6011a-105">_-Roy Stephan_</span><span class="sxs-lookup"><span data-stu-id="6011a-105">_- Roy Stephan_</span></span>

 ## <a name="vision"></a><span data-ttu-id="6011a-106">Visione</span><span class="sxs-lookup"><span data-stu-id="6011a-106">Vision</span></span>

> <span data-ttu-id="6011a-107">*Sviluppare applicazioni ASP .NET Core ben progettate il modo in cui che si desidera, tramite Visual Studio o dotnet CLI e codice di Visual Studio o l'editor preferito.*</span><span class="sxs-lookup"><span data-stu-id="6011a-107">*Develop well-designed ASP .NET Core applications the way you like, using Visual Studio or the dotnet CLI and Visual Studio Code or your editor of choice.*</span></span>

## <a name="development-environment-for-aspnet-core-apps"></a><span data-ttu-id="6011a-108">Ambiente di sviluppo per applicazioni ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="6011a-108">Development environment for ASP.NET Core apps</span></span>

### <a name="development-tools-choices-ide-or-editor"></a><span data-ttu-id="6011a-109">Gli strumenti di sviluppo scelte: IDE o editor</span><span class="sxs-lookup"><span data-stu-id="6011a-109">Development tools choices: IDE or editor</span></span>

<span data-ttu-id="6011a-110">Se si preferisce un IDE potente e completo o un editor semplice e agile, Microsoft ha la copertura durante lo sviluppo di applicazioni ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="6011a-110">Whether you prefer a full and powerful IDE or a lightweight and agile editor, Microsoft has you covered when developing ASP.NET Core applications.</span></span>

<span data-ttu-id="6011a-111">**Visual Studio 2017.**</span><span class="sxs-lookup"><span data-stu-id="6011a-111">**Visual Studio 2017.**</span></span> <span data-ttu-id="6011a-112">Se si utilizza *Visual Studio 2017* la compilazione di ASP.NET Core applicazioni purché disponga di *lo sviluppo multipiattaforma con .NET Core* installato carico di lavoro.</span><span class="sxs-lookup"><span data-stu-id="6011a-112">If you're using *Visual Studio 2017* you can build ASP.NET Core applications as long as you have the *.NET Core cross-platform development* workload installed.</span></span> <span data-ttu-id="6011a-113">Nella figura 10-1 viene illustrato il carico di lavoro richiesto nella finestra di dialogo di installazione di Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="6011a-113">Figure 10-1 shows the required workload in the Visual Studio 2017 setup dialog.</span></span>

![](./media/image10-1.png)

<span data-ttu-id="6011a-114">**Nella figura 10-1.**</span><span class="sxs-lookup"><span data-stu-id="6011a-114">**Figure 10-1.**</span></span> <span data-ttu-id="6011a-115">Installazione del carico di lavoro di .NET Core in Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="6011a-115">Installing the .NET Core workload in Visual Studio 2017.</span></span>

[<span data-ttu-id="6011a-116">Scarica Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="6011a-116">Download Visual Studio 2017</span></span>](https://www.visualstudio.com/downloads/)

<span data-ttu-id="6011a-117">**Visual Studio Code e dotnet CLI** (strumenti multipiattaforma per Windows, Mac e Linux).</span><span class="sxs-lookup"><span data-stu-id="6011a-117">**Visual Studio Code and dotnet CLI** (Cross-Platform Tools for Mac, Linux and Windows).</span></span> <span data-ttu-id="6011a-118">Se si preferisce un editor leggero e multipiattaforma supportare qualsiasi linguaggio di sviluppo, è possibile utilizzare Microsoft Visual Studio Code e dotnet CLI.</span><span class="sxs-lookup"><span data-stu-id="6011a-118">If you prefer a lightweight and cross-platform editor supporting any development language, you can use Microsoft Visual Studio Code and the dotnet CLI.</span></span> <span data-ttu-id="6011a-119">Questi prodotti forniscono un'esperienza semplice ed efficace che consente di ottimizzare il flusso di lavoro di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="6011a-119">These products provide a simple yet robust experience that streamlines the developer workflow.</span></span> <span data-ttu-id="6011a-120">Inoltre, supporta le estensioni di Visual Studio Code per C\# e lo sviluppo web, fornire intellisense e attività di collegamento all'interno dell'editor.</span><span class="sxs-lookup"><span data-stu-id="6011a-120">Additionally, Visual Studio Code supports extensions for C\# and web development, providing intellisense and shortcut-tasks within the editor.</span></span>

[<span data-ttu-id="6011a-121">Scaricare il SDK .NET di base</span><span class="sxs-lookup"><span data-stu-id="6011a-121">Download the .NET Core SDK</span></span>](https://www.microsoft.com/net/download/core)

[<span data-ttu-id="6011a-122">Scaricare il codice di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="6011a-122">Download Visual Studio Code</span></span>](https://code.visualstudio.com/download)



## <a name="development-workflow-for-azure-hosted-aspnet-core-apps"></a><span data-ttu-id="6011a-123">Flusso di lavoro di sviluppo per applicazioni ASP.NET Core ospitato di Azure</span><span class="sxs-lookup"><span data-stu-id="6011a-123">Development workflow for Azure-hosted ASP.NET Core apps</span></span>

<span data-ttu-id="6011a-124">Il ciclo di vita di sviluppo di applicazioni viene avviato dal computer di ogni sviluppatore, la generazione di codice l'app utilizzando la lingua desiderata e il relativo test in locale.</span><span class="sxs-lookup"><span data-stu-id="6011a-124">The application development lifecycle starts from each developer's machine, coding the app using their preferred language and testing it locally.</span></span> <span data-ttu-id="6011a-125">Gli sviluppatori possono scegliere il controllo del codice sorgente preferito e possono configurare l'integrazione continua (CI) e/o recapito/distribuzione continua (CD) utilizzando un server di compilazione o in base alle funzionalità incorporate di Azure.</span><span class="sxs-lookup"><span data-stu-id="6011a-125">Developers may choose their preferred source control system and can configure Continuous Integration (CI) and/or Continuous Delivery/Deployment (CD) using a build server or based on built-in Azure features.</span></span>

<span data-ttu-id="6011a-126">Per iniziare con lo sviluppo di un'applicazione ASP.NET di base utilizzando l'elemento di configurazione/CD, è possibile utilizzare Visual Studio Team Services o l'organizzazione proprietari di Team Foundation Server (TFS).</span><span class="sxs-lookup"><span data-stu-id="6011a-126">To get started with developing an ASP.NET Core application using CI/CD, you can use Visual Studio Team Services or your organization's own Team Foundation Server (TFS).</span></span>

### <a name="initial-setup"></a><span data-ttu-id="6011a-127">Configurazione iniziale</span><span class="sxs-lookup"><span data-stu-id="6011a-127">Initial Setup</span></span>

<span data-ttu-id="6011a-128">Per creare una pipeline di rilascio per l'app, è necessario avere il codice dell'applicazione nel controllo del codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="6011a-128">To create a release pipeline for your app, you need to have your application code in source control.</span></span> <span data-ttu-id="6011a-129">Configurare un repository locale e connetterlo a un archivio remoto in un progetto team.</span><span class="sxs-lookup"><span data-stu-id="6011a-129">Set up a local repository and connect it to a remote repository in a team project.</span></span> <span data-ttu-id="6011a-130">Seguire queste istruzioni:</span><span class="sxs-lookup"><span data-stu-id="6011a-130">Follow these instructions:</span></span>

-   <span data-ttu-id="6011a-131">[Condividere il codice con Git e di Visual Studio](https://www.visualstudio.com/docs/git/share-your-code-in-git-vs) o</span><span class="sxs-lookup"><span data-stu-id="6011a-131">[Share your code with Git and Visual Studio](https://www.visualstudio.com/docs/git/share-your-code-in-git-vs) or</span></span>

-   [<span data-ttu-id="6011a-132">Condividere il codice con TFVC e Visual Studio</span><span class="sxs-lookup"><span data-stu-id="6011a-132">Share your code with TFVC and Visual Studio</span></span>](https://www.visualstudio.com/docs/tfvc/share-your-code-in-tfvc-vs)

<span data-ttu-id="6011a-133">Creare un servizio App di Azure in cui verrà distribuita l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="6011a-133">Create an Azure App Service where you'll deploy your application.</span></span> <span data-ttu-id="6011a-134">Creare un'App Web, passare al pannello delle servizi App nel portale di Azure.</span><span class="sxs-lookup"><span data-stu-id="6011a-134">Create a Web App by going to the App Services blade on the Azure portal.</span></span> <span data-ttu-id="6011a-135">Fare clic su + Aggiungi, selezionare il modello di applicazione Web, fare clic su Crea e specificare un nome e altri dettagli.</span><span class="sxs-lookup"><span data-stu-id="6011a-135">Click +Add, select the Web App template, click Create, and provide a name and other details.</span></span> <span data-ttu-id="6011a-136">L'app web sarà accessibile da {name}. azurewebsites.net.</span><span class="sxs-lookup"><span data-stu-id="6011a-136">The web app will be accessible from {name}.azurewebsites.net.</span></span>

![AzureWebApp](./media/image10-2.png)

<span data-ttu-id="6011a-138">**Figura 10-2.**</span><span class="sxs-lookup"><span data-stu-id="6011a-138">**Figure 10-2.**</span></span> <span data-ttu-id="6011a-139">Creazione di una nuova App Web di Azure App Service nel portale di Azure.</span><span class="sxs-lookup"><span data-stu-id="6011a-139">Creating a new Azure App Service Web App in the Azure Portal.</span></span>

<span data-ttu-id="6011a-140">Il processo di compilazione CI eseguirà una compilazione automatica ogni volta che viene eseguito il commit al repository di controllo codice sorgente del progetto nuovo codice.</span><span class="sxs-lookup"><span data-stu-id="6011a-140">Your CI build process will perform an automated build whenever new code is committed to the project's source control repository.</span></span> <span data-ttu-id="6011a-141">Ciò consente di verificare immediatamente che il codice verrà compilato (e, idealmente, supera i test automatizzati) e potenzialmente possono essere distribuiti.</span><span class="sxs-lookup"><span data-stu-id="6011a-141">This gives you immediate feedback that the code builds (and, ideally, passes automated tests) and can potentially be deployed.</span></span> <span data-ttu-id="6011a-142">Questa compilazione CI produrrà un web distribuire l'elemento di pacchetto e pubblicarlo per l'utilizzo dal processo di CD-ROM.</span><span class="sxs-lookup"><span data-stu-id="6011a-142">This CI build will produce a web deploy package artifact and publish it for consumption by your CD process.</span></span>

[<span data-ttu-id="6011a-143">Definire il processo di compilazione CI</span><span class="sxs-lookup"><span data-stu-id="6011a-143">Define your CI build process</span></span>](https://www.visualstudio.com/docs/build/apps/aspnet/aspnetcore-to-azure#ci)

<span data-ttu-id="6011a-144">Assicurarsi di abilitare l'integrazione continua in modo il sistema verrà accodare una compilazione ogni volta che un utente membro del team esegue il commit di nuovo codice.</span><span class="sxs-lookup"><span data-stu-id="6011a-144">Be sure to enable continuous integration so the system will queue a build whenever someone on your team commits new code.</span></span> <span data-ttu-id="6011a-145">La compilazione di test e verificare che produce un web distribuire un pacchetto come uno dei relativi elementi.</span><span class="sxs-lookup"><span data-stu-id="6011a-145">Test the build and verify that it is producing a web deploy package as one of its artifacts.</span></span>

<span data-ttu-id="6011a-146">Quando una compilazione ha esito positivo, il processo CD distribuirà i risultati della compilazione CI all'App web di Azure.</span><span class="sxs-lookup"><span data-stu-id="6011a-146">When a build succeeds, your CD process will deploy the results of your CI build to your Azure web app.</span></span> <span data-ttu-id="6011a-147">A questo scopo, creare e configurare un *versione*, che verrà distribuito del servizio App di Azure.</span><span class="sxs-lookup"><span data-stu-id="6011a-147">To configure this, you create and configure a *Release*, which will deploy to your Azure App Service.</span></span>

[<span data-ttu-id="6011a-148">Definire il processo di rilascio del CD</span><span class="sxs-lookup"><span data-stu-id="6011a-148">Define your CD release process</span></span>](https://www.visualstudio.com/docs/build/apps/aspnet/aspnetcore-to-azure#cd)

<span data-ttu-id="6011a-149">Una volta configurata la pipeline CI/CD, è possibile effettuare aggiornamenti per l'app web e ne esegue il commit in modo che vengano distribuiti nel controllo del codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="6011a-149">Once your CI/CD pipeline is configured, you can simply make updates to your web app and commit them to source control to have them deployed.</span></span>

### <a name="workflow-for-developing-azure-hosted-aspnet-core-applications"></a><span data-ttu-id="6011a-150">Flusso di lavoro per lo sviluppo di applicazioni ASP.NET Core ospitato di Azure</span><span class="sxs-lookup"><span data-stu-id="6011a-150">Workflow for developing Azure-hosted ASP.NET Core applications</span></span>

<span data-ttu-id="6011a-151">Dopo aver configurato l'account di Azure e il processo di CI/CD, lo sviluppo di applicazioni ASP.NET Core ospitato di Azure è semplice.</span><span class="sxs-lookup"><span data-stu-id="6011a-151">Once you have configured your Azure account and your CI/CD process, developing Azure-hosted ASP.NET Core applications is simple.</span></span> <span data-ttu-id="6011a-152">Di seguito sono indicati i passaggi di base che accettano in genere quando si compila un'applicazione ASP.NET di base, ospitata in Azure App Service come un'App Web, come illustrato nella figura 10-3.</span><span class="sxs-lookup"><span data-stu-id="6011a-152">The following are the basic steps you usually take when building an ASP.NET Core app, hosted in Azure App Service as a Web App, as illustrated in Figure 10-3.</span></span>

![EndToEndDevDeployWorkflow](./media/image10-3.png)

<span data-ttu-id="6011a-154">**Nella figura 10-3.**</span><span class="sxs-lookup"><span data-stu-id="6011a-154">**Figure 10-3.**</span></span> <span data-ttu-id="6011a-155">Flusso di lavoro dettagliato per la creazione di applicazioni ASP.NET Core e all'hosting in Azure</span><span class="sxs-lookup"><span data-stu-id="6011a-155">Step-by-step workflow for building ASP.NET Core apps and hosting them in Azure</span></span>

#### <a name="step-1-local-dev-environment-inner-loop"></a><span data-ttu-id="6011a-156">Passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="6011a-156">Step 1.</span></span> <span data-ttu-id="6011a-157">Ciclo interno ambiente di sviluppo locale</span><span class="sxs-lookup"><span data-stu-id="6011a-157">Local Dev Environment Inner Loop</span></span>

<span data-ttu-id="6011a-158">Sviluppo dell'applicazione ASP.NET di base per la distribuzione in Azure non è diverso dallo sviluppo dell'applicazione in caso contrario.</span><span class="sxs-lookup"><span data-stu-id="6011a-158">Developing your ASP.NET Core application for deployment to Azure is no different from developing your application otherwise.</span></span> <span data-ttu-id="6011a-159">Utilizzare l'ambiente di sviluppo locale acquisita familiarità con, se Visual Studio 2017 o dotnet CLI e codice di Visual Studio o l'editor preferito.</span><span class="sxs-lookup"><span data-stu-id="6011a-159">Use the local development environment you're comfortable with, whether that's Visual Studio 2017 or the dotnet CLI and Visual Studio Code or your preferred editor.</span></span> <span data-ttu-id="6011a-160">È possibile scrivere codice, eseguire e debug le modifiche, eseguire test automatizzati e apportare commit locale al controllo del codice sorgente fino a quando non si è pronti per il push delle modifiche nel repository di controllo del codice sorgente condiviso.</span><span class="sxs-lookup"><span data-stu-id="6011a-160">You can write code, run and debug your changes, run automated tests, and make local commits to source control until you're ready to push your changes to your shared source control repository.</span></span>

#### <a name="step-2-application-code-repository"></a><span data-ttu-id="6011a-161">Passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="6011a-161">Step 2.</span></span> <span data-ttu-id="6011a-162">Repository di codice dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="6011a-162">Application Code Repository</span></span>

<span data-ttu-id="6011a-163">Ogni volta che si è pronti per condividere il codice con il team, è necessario il push delle modifiche dal repository del codice sorgente locale al repository di origine condivisa del team.</span><span class="sxs-lookup"><span data-stu-id="6011a-163">Whenever you're ready to share your code with your team, you should push your changes from your local source repository to your team's shared source repository.</span></span> <span data-ttu-id="6011a-164">Se si è collaborato in un ramo personalizzato, questo passaggio prevede in genere l'unione di codice in un branch condiviso (ad esempio per mezzo di un [richiesta pull](https://www.visualstudio.com/docs/git/pull-requests)).</span><span class="sxs-lookup"><span data-stu-id="6011a-164">If you've been working in a custom branch, this step usually involves merging your code into a shared branch (perhaps by means of a [pull request](https://www.visualstudio.com/docs/git/pull-requests)).</span></span>

#### <a name="step-3-build-server-continuous-integration-build-test-package"></a><span data-ttu-id="6011a-165">Passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="6011a-165">Step 3.</span></span> <span data-ttu-id="6011a-166">Server di compilazione: Integrazione continua.</span><span class="sxs-lookup"><span data-stu-id="6011a-166">Build Server: Continuous Integration.</span></span> <span data-ttu-id="6011a-167">Pacchetto di compilazione, Test,</span><span class="sxs-lookup"><span data-stu-id="6011a-167">Build, Test, Package</span></span>

<span data-ttu-id="6011a-168">Ogni volta che viene eseguito il commit di una nuova nel repository di codice di applicazione condivisa, nel server di compilazione viene attivata una nuova compilazione.</span><span class="sxs-lookup"><span data-stu-id="6011a-168">A new build is triggered on the build server whenever a new commit is made to the shared application code repository.</span></span> <span data-ttu-id="6011a-169">Come parte del processo di integrazione continua, la compilazione deve compilare l'applicazione completamente ed eseguire test automatizzati per verificare che funzionino come previsto.</span><span class="sxs-lookup"><span data-stu-id="6011a-169">As part of the CI process, this build should fully compile the application and run automated tests to confirm everything is working as expected.</span></span> <span data-ttu-id="6011a-170">Il risultato finale del processo di CI deve essere una versione nel pacchetto dell'app web, pronto per la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="6011a-170">The end result of the CI process should be a packaged version of the web app, ready for deployment.</span></span>

#### <a name="step-4-build-server-continuous-delivery"></a><span data-ttu-id="6011a-171">Passaggio 4.</span><span class="sxs-lookup"><span data-stu-id="6011a-171">Step 4.</span></span> <span data-ttu-id="6011a-172">Server di compilazione: Il recapito continuo</span><span class="sxs-lookup"><span data-stu-id="6011a-172">Build Server: Continuous Delivery</span></span>

<span data-ttu-id="6011a-173">Una volta una compilazione come ha avuto esito positivo, il processo di CD selezionerà i prodotto degli artefatti di compilazione.</span><span class="sxs-lookup"><span data-stu-id="6011a-173">Once a build as succeeded, the CD process will pick up the build artifacts produced.</span></span> <span data-ttu-id="6011a-174">Ciò comprende una web distribuire il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="6011a-174">This will include a web deploy package.</span></span> <span data-ttu-id="6011a-175">Il server di compilazione verrà distribuito il pacchetto di servizio App di Azure, sostituendo qualsiasi servizio esistente con quella appena creata.</span><span class="sxs-lookup"><span data-stu-id="6011a-175">The build server will deploy this package to Azure App Service, replacing any existing service with the newly created one.</span></span> <span data-ttu-id="6011a-176">In genere questo passaggio è destinato a un ambiente di gestione temporanea, ma alcune applicazioni distribuire direttamente nell'ambiente di produzione tramite un processo del CD.</span><span class="sxs-lookup"><span data-stu-id="6011a-176">Typically this step targets a staging environment, but some applications deploy directly to production through a CD process.</span></span>

#### <a name="step-5-azure-app-service-web-app"></a><span data-ttu-id="6011a-177">Passaggio 5.</span><span class="sxs-lookup"><span data-stu-id="6011a-177">Step 5.</span></span> <span data-ttu-id="6011a-178">Servizio App di Azure.</span><span class="sxs-lookup"><span data-stu-id="6011a-178">Azure App Service.</span></span> <span data-ttu-id="6011a-179">App Web.</span><span class="sxs-lookup"><span data-stu-id="6011a-179">Web App.</span></span>

<span data-ttu-id="6011a-180">Una volta distribuito, l'applicazione ASP.NET Core viene eseguita all'interno del contesto di un'App Web di Azure App Service.</span><span class="sxs-lookup"><span data-stu-id="6011a-180">Once deployed, the ASP.NET Core application runs within the context of an Azure App Service Web App.</span></span> <span data-ttu-id="6011a-181">L'App Web può essere monitorata e ulteriormente configurate tramite il portale di Azure.</span><span class="sxs-lookup"><span data-stu-id="6011a-181">This Web App can be monitored and further configured using the Azure Portal.</span></span>

#### <a name="step-6-production-monitoring-and-diagnostics"></a><span data-ttu-id="6011a-182">Passaggio 6.</span><span class="sxs-lookup"><span data-stu-id="6011a-182">Step 6.</span></span> <span data-ttu-id="6011a-183">Monitoraggio di produzione e di diagnostica</span><span class="sxs-lookup"><span data-stu-id="6011a-183">Production Monitoring and Diagnostics</span></span>

<span data-ttu-id="6011a-184">Mentre l'App Web è in esecuzione, è possibile monitorare l'integrità dell'applicazione e raccogliere dati sul comportamento di utente e di diagnostica.</span><span class="sxs-lookup"><span data-stu-id="6011a-184">While the Web App is running, you can monitor the health of the application and collect diagnostics and user behavior data.</span></span> <span data-ttu-id="6011a-185">Application Insights è incluso in Visual Studio e offre strumentazione automatica per le applicazioni ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="6011a-185">Application Insights is included in Visual Studio, and offers automatic instrumentation for ASP.NET apps.</span></span> <span data-ttu-id="6011a-186">Può fornire informazioni sull'utilizzo, eccezioni, le richieste, prestazioni e log.</span><span class="sxs-lookup"><span data-stu-id="6011a-186">It can provide you with information on usage, exceptions, requests, performance, and logs.</span></span>

## <a name="references"></a><span data-ttu-id="6011a-187">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="6011a-187">References</span></span>

<span data-ttu-id="6011a-188">**Compilare e distribuire l'applicazione ASP.NET di base in Azure**</span><span class="sxs-lookup"><span data-stu-id="6011a-188">**Build and Deploy Your ASP.NET Core App to Azure**</span></span>  
<span data-ttu-id="6011a-189"><https://www.VisualStudio.com/docs/build/Apps/ASPNET/aspnetcore-to-Azure></span><span class="sxs-lookup"><span data-stu-id="6011a-189"><https://www.visualstudio.com/docs/build/apps/aspnet/aspnetcore-to-azure></span></span>


>[!div class="step-by-step"]
<span data-ttu-id="6011a-190">[Precedente] [Avanti] (azure-hosting-recommendations-for-asp-net-web-apps.md) (test-asp-net-core-mvc-apps.md)</span><span class="sxs-lookup"><span data-stu-id="6011a-190">[Previous] (test-asp-net-core-mvc-apps.md) [Next] (azure-hosting-recommendations-for-asp-net-web-apps.md)</span></span>