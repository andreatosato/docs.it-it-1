---
title: Glossario .NET
description: Significato di termini selezionati usati nella documentazione di .NET.
keywords: Glossario .NET, dizionario .NET, terminologia .NET, piattaforma .NET, .NET Framework, runtime .NET
author: tdykstra
ms.author: tdykstra
ms.date: 07/08/2017
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.translationtype: HT
ms.sourcegitcommit: 33b22ab80f9b4d42975f2c41c880543c615a3e01
ms.openlocfilehash: c66f1b2b85d377c84712c0ad73682cdeeb7249fd
ms.contentlocale: it-it
ms.lasthandoff: 08/31/2017

---

# <a name="net-glossary"></a><span data-ttu-id="3a40f-104">Glossario .NET</span><span class="sxs-lookup"><span data-stu-id="3a40f-104">.NET Glossary</span></span>

<span data-ttu-id="3a40f-105">Scopo principale di questo glossario è quello di chiarire il significato di acronimi e termini selezionati usati frequentemente nella documentazione di .NET senza definizioni.</span><span class="sxs-lookup"><span data-stu-id="3a40f-105">The primary goal of this glossary is to clarify meanings of selected terms and acronyms that appear frequently in the .NET documentation without definitions.</span></span>

## <a name="aot"></a><span data-ttu-id="3a40f-106">AOT</span><span class="sxs-lookup"><span data-stu-id="3a40f-106">AOT</span></span>

<span data-ttu-id="3a40f-107">Compilatore Ahead Of Time.</span><span class="sxs-lookup"><span data-stu-id="3a40f-107">Ahead-of-time compiler.</span></span>

<span data-ttu-id="3a40f-108">Simile a [JIT](#jit), questo compilatore esegue anche la conversione del linguaggio [IL](#il) in codice macchina.</span><span class="sxs-lookup"><span data-stu-id="3a40f-108">Similar to [JIT](#jit), this compiler also translates [IL](#il) to machine code.</span></span> <span data-ttu-id="3a40f-109">A differenza della compilazione JIT, la compilazione AOT viene eseguita prima dell'esecuzione dell'applicazione, generalmente in un computer diverso.</span><span class="sxs-lookup"><span data-stu-id="3a40f-109">In contrast to JIT compilation, AOT compilation happens before the application is executed and is usually performed on a different machine.</span></span> <span data-ttu-id="3a40f-110">Dal momento che le toolchain AOT non eseguono compilazioni in fase di esecuzione, non devono ridurre al minimo il tempo impiegato per la compilazione</span><span class="sxs-lookup"><span data-stu-id="3a40f-110">Because AOT tool chains don't compile at runtime, they don't have to minimize time spent compiling.</span></span> <span data-ttu-id="3a40f-111">e possono dedicare più tempo all'ottimizzazione.</span><span class="sxs-lookup"><span data-stu-id="3a40f-111">That means they can spend more time optimizing.</span></span> <span data-ttu-id="3a40f-112">Il contesto di AOT è l'intera applicazione, pertanto il compilatore AOT esegue anche il collegamento tra i moduli e l'analisi dell'intero programma, di conseguenza vengono seguiti tutti i riferimenti e viene generato un unico file eseguibile.</span><span class="sxs-lookup"><span data-stu-id="3a40f-112">Since the context of AOT is the entire application, the AOT compiler also performs cross-module linking and whole-program analysis, which means that all references are followed and a single executable is produced.</span></span>

## <a name="aspnet"></a><span data-ttu-id="3a40f-113">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="3a40f-113">ASP.NET</span></span> 

<span data-ttu-id="3a40f-114">Implementazione originale di ASP.NET inclusa con .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3a40f-114">The original ASP.NET implementation that ships with the .NET Framework.</span></span>

<span data-ttu-id="3a40f-115">In alcuni casi ASP.NET è un termine generico che fa riferimento a entrambe le implementazioni di ASP.NET, inclusa ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="3a40f-115">Sometimes ASP.NET is an umbrella term that refers to both ASP.NET implementations including ASP.NET Core.</span></span> <span data-ttu-id="3a40f-116">Il significato assunto dal termine in una specifica istanza è determinato dal contesto.</span><span class="sxs-lookup"><span data-stu-id="3a40f-116">The meaning that the term carries in any given instance is determined by context.</span></span> 

<span data-ttu-id="3a40f-117">Vedere [ASP.NET](/aspnet/#pivot=aspnet).</span><span class="sxs-lookup"><span data-stu-id="3a40f-117">See [ASP.NET](/aspnet/#pivot=aspnet).</span></span>

## <a name="aspnet-core"></a><span data-ttu-id="3a40f-118">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="3a40f-118">ASP.NET Core</span></span>

<span data-ttu-id="3a40f-119">Implementazione open source, ad alte prestazioni e multi-piattaforma di ASP.NET basata su .NET Core.</span><span class="sxs-lookup"><span data-stu-id="3a40f-119">A cross-platform, high-performance, open source implementation of ASP.NET built on .NET Core.</span></span>

<span data-ttu-id="3a40f-120">Vedere [ASP.NET Core](/aspnet/#pivot=core).</span><span class="sxs-lookup"><span data-stu-id="3a40f-120">See [ASP.NET Core](/aspnet/#pivot=core).</span></span>

## <a name="assembly"></a><span data-ttu-id="3a40f-121">assembly</span><span class="sxs-lookup"><span data-stu-id="3a40f-121">assembly</span></span>

<span data-ttu-id="3a40f-122">File *DLL* contenente una raccolta di API che possono essere chiamate da app o altri assembly.</span><span class="sxs-lookup"><span data-stu-id="3a40f-122">A *.dll* file that contains a collection of APIs that can be called by apps or other assemblies.</span></span>

<span data-ttu-id="3a40f-123">Un assembly .NET è una raccolta di tipi.</span><span class="sxs-lookup"><span data-stu-id="3a40f-123">A .NET assembly is a collection of types.</span></span> <span data-ttu-id="3a40f-124">Un assembly include interfacce, classi, strutture, enumerazioni e delegati.</span><span class="sxs-lookup"><span data-stu-id="3a40f-124">An assembly includes interfaces, classes, structures, enumerations, and delegates.</span></span>  <span data-ttu-id="3a40f-125">Gli assembly presenti nella cartella *bin* di un progetto sono anche denominati *binari*.</span><span class="sxs-lookup"><span data-stu-id="3a40f-125">Assemblies in a project's *bin* folder are sometimes referred to as *binaries*.</span></span> <span data-ttu-id="3a40f-126">Vedere anche [libreria](#library).</span><span class="sxs-lookup"><span data-stu-id="3a40f-126">See also [library](#library).</span></span>

## <a name="clr"></a><span data-ttu-id="3a40f-127">CLR</span><span class="sxs-lookup"><span data-stu-id="3a40f-127">CLR</span></span>

<span data-ttu-id="3a40f-128">Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="3a40f-128">Common Language Runtime.</span></span>

<span data-ttu-id="3a40f-129">Il significato esatto dipende dal contesto, ma questo in genere si riferisce al runtime di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3a40f-129">The exact meaning depends on the context, but this usually refers to the runtime of the .NET Framework.</span></span> <span data-ttu-id="3a40f-130">CLR gestisce allocazione e gestione della memoria.</span><span class="sxs-lookup"><span data-stu-id="3a40f-130">The CLR handles memory allocation and management.</span></span> <span data-ttu-id="3a40f-131">È inoltre una macchina virtuale che non solo esegue app, ma genera e compila codice al volo usando un compilatore JIT.</span><span class="sxs-lookup"><span data-stu-id="3a40f-131">The CLR is also a virtual machine that not only executes apps but also generates and compiles code on-the-fly using a JIT compiler.</span></span> <span data-ttu-id="3a40f-132">L'implementazione corrente di Microsoft CLR è solo Windows.</span><span class="sxs-lookup"><span data-stu-id="3a40f-132">The current Microsoft CLR implementation is Windows only.</span></span>

## <a name="coreclr"></a><span data-ttu-id="3a40f-133">CoreCLR</span><span class="sxs-lookup"><span data-stu-id="3a40f-133">CoreCLR</span></span>

<span data-ttu-id="3a40f-134">.NET Core Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="3a40f-134">.NET Core Common Language Runtime.</span></span>

<span data-ttu-id="3a40f-135">Questo tipo di CLR viene creato dalla stessa base di codice di CLR.</span><span class="sxs-lookup"><span data-stu-id="3a40f-135">This CLR is built from the same code base as the CLR.</span></span> <span data-ttu-id="3a40f-136">In origine, CoreCLR era il runtime di Silverlight ed è stato progettato per l'esecuzione su più piattaforme, in particolare Windows e OS X. CoreCLR è ora incluso in .NET Core e rappresenta una versione semplificata di CLR.</span><span class="sxs-lookup"><span data-stu-id="3a40f-136">Originally, CoreCLR was the runtime of Silverlight and was designed to run on multiple platforms, specifically Windows and OS X. CoreCLR is now part of .NET Core and represents a simplified version of the CLR.</span></span> <span data-ttu-id="3a40f-137">È comunque un runtime multipiattaforma, che ora include il supporto per molte distribuzioni di Linux.</span><span class="sxs-lookup"><span data-stu-id="3a40f-137">It's still a cross platform runtime, now including support for many Linux distributions.</span></span> <span data-ttu-id="3a40f-138">CoreCLR è anche una macchina virtuale con funzionalità JIT e di esecuzione del codice.</span><span class="sxs-lookup"><span data-stu-id="3a40f-138">CoreCLR is also a virtual machine with JIT and code execution capabilities.</span></span>

## <a name="corefx"></a><span data-ttu-id="3a40f-139">CoreFX</span><span class="sxs-lookup"><span data-stu-id="3a40f-139">CoreFX</span></span>

<span data-ttu-id="3a40f-140">Libreria di classi base .NET Core (BCL)</span><span class="sxs-lookup"><span data-stu-id="3a40f-140">.NET Core Base Class Library (BCL)</span></span>

<span data-ttu-id="3a40f-141">Set di librerie che comprende gli spazi dei nomi System.* (e in modo limitato quelli Microsoft.*.</span><span class="sxs-lookup"><span data-stu-id="3a40f-141">A set of libraries that comprise the System.* (and to a limited extent  Microsoft.*) namespaces.</span></span> <span data-ttu-id="3a40f-142">La libreria di classi base è un framework generico di livello inferiore su cui si basano framework applicazione di livello superiore, ad esempio ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="3a40f-142">The BCL is a general purpose, lower-level framework that higher-level application frameworks, such as ASP.NET Core, build on.</span></span> <span data-ttu-id="3a40f-143">Il codice sorgente della libreria di classi base .NET Core è incluso reperibile nel [repository CoreFX](https://github.com/dotnet/corefx).</span><span class="sxs-lookup"><span data-stu-id="3a40f-143">The source code of the .NET Core BCL is contained in the [CoreFX repository](https://github.com/dotnet/corefx).</span></span> <span data-ttu-id="3a40f-144">La maggior parte delle API .NET Core sono però anche disponibili in .NET Framework, di conseguenza è possibile considerare CoreFX come un fork della libreria di classi base .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3a40f-144">However, the majority of the .NET Core APIs are also available in the .NET Framework, so you can think of CoreFX as a fork of the .NET Framework BCL.</span></span>

## <a name="corert"></a><span data-ttu-id="3a40f-145">CoreRT</span><span class="sxs-lookup"><span data-stu-id="3a40f-145">CoreRT</span></span>

<span data-ttu-id="3a40f-146">Runtime di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="3a40f-146">.NET Core runtime.</span></span>

<span data-ttu-id="3a40f-147">A differenza di CLR/CoreCLR, CoreRT non è una macchina virtuale, ovvero non include le funzionalità per generare ed eseguire codice al volo perché non include un [JIT](#jit).</span><span class="sxs-lookup"><span data-stu-id="3a40f-147">In contrast to the CLR/CoreCLR, CoreRT is not a virtual machine, which means it doesn't include the facilities to generate and run code on-the-fly because it doesn't include a [JIT](#jit).</span></span> <span data-ttu-id="3a40f-148">Include invece la [Garbage Collection](#gc) e la funzionalità per l'identificazione del tipo di runtime (RTTI) e la reflection.</span><span class="sxs-lookup"><span data-stu-id="3a40f-148">It does, however, include the [GC](#gc) and the ability for runtime type identification (RTTI) and reflection.</span></span> <span data-ttu-id="3a40f-149">Tuttavia, il sistema di tipi di questo runtime è progettato in modo tale da rendere superflui i metadati per la reflection.</span><span class="sxs-lookup"><span data-stu-id="3a40f-149">However, its type system is designed so that metadata for reflection isn't required.</span></span> <span data-ttu-id="3a40f-150">Si ottiene pertanto una toolchain [AOT](#aot) in grado di scollegare i metadati superflui e, più importante, identificare il codice non usato dall'app.</span><span class="sxs-lookup"><span data-stu-id="3a40f-150">This enables having an [AOT](#aot) tool chain that can link away superfluous metadata and (more importantly) identify code that the app doesn't use.</span></span> <span data-ttu-id="3a40f-151">CoreRT è in fase di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="3a40f-151">CoreRT is in development.</span></span>

<span data-ttu-id="3a40f-152">Vedere [Intro to .NET Native and CoreRT](https://github.com/dotnet/corert/blob/master/Documentation/intro-to-corert.md) (Introduzione a .NET Native e CoreRT).</span><span class="sxs-lookup"><span data-stu-id="3a40f-152">See [Intro to .NET Native and CoreRT](https://github.com/dotnet/corert/blob/master/Documentation/intro-to-corert.md)</span></span>

## <a name="ecosystem"></a><span data-ttu-id="3a40f-153">ecosistema</span><span class="sxs-lookup"><span data-stu-id="3a40f-153">ecosystem</span></span>

<span data-ttu-id="3a40f-154">Tutto il software di runtime, gli strumenti di sviluppo e le risorse della community usati per creare ed eseguire applicazioni per una determinata tecnologia.</span><span class="sxs-lookup"><span data-stu-id="3a40f-154">All of the runtime software, development tools, and community resources that are used to build and run applications for a given technology.</span></span>

<span data-ttu-id="3a40f-155">Il termine "ecosistema .NET" è diverso da termini simili, quali "stack .NET", quando è inserito in app e librerie di terze parti.</span><span class="sxs-lookup"><span data-stu-id="3a40f-155">The term ".NET ecosystem" differs from similar terms such as ".NET stack" in its inclusion of third-party apps and libraries.</span></span> <span data-ttu-id="3a40f-156">Eccone un esempio in una frase:</span><span class="sxs-lookup"><span data-stu-id="3a40f-156">Here's an example in a sentence:</span></span>

- <span data-ttu-id="3a40f-157">"La motivazione alla base di [.NET Standard](#net-standard) è l'esigenza di creare maggiore uniformità nell'ecosistema .NET".</span><span class="sxs-lookup"><span data-stu-id="3a40f-157">"The motivation behind the [.NET Standard](#net-standard) is to establish greater uniformity in the .NET ecosystem."</span></span> 

## <a name="framework"></a><span data-ttu-id="3a40f-158">framework</span><span class="sxs-lookup"><span data-stu-id="3a40f-158">framework</span></span>

<span data-ttu-id="3a40f-159">In termini generali, una raccolta completa di API che consente di semplificare lo sviluppo e la distribuzione di applicazioni basate su una particolare tecnologia.</span><span class="sxs-lookup"><span data-stu-id="3a40f-159">In general, a comprehensive collection of APIs that facilitates development and deployment of applications that are based on a particular technology.</span></span> <span data-ttu-id="3a40f-160">In tal senso, ASP.NET Core e Windows Form sono esempi di framework applicazione.</span><span class="sxs-lookup"><span data-stu-id="3a40f-160">In this general sense, ASP.NET Core and Windows Forms are examples of application frameworks.</span></span> <span data-ttu-id="3a40f-161">Vedere anche [libreria](#library).</span><span class="sxs-lookup"><span data-stu-id="3a40f-161">See also [library](#library).</span></span>

<span data-ttu-id="3a40f-162">La parola "framework" presenta un significato tecnico più specifico nei termini seguenti:</span><span class="sxs-lookup"><span data-stu-id="3a40f-162">The word "framework" has a more specific technical meaning in the following terms:</span></span>
* [<span data-ttu-id="3a40f-163">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="3a40f-163">.NET Framework</span></span>](#net-framework)
* [<span data-ttu-id="3a40f-164">framework di destinazione</span><span class="sxs-lookup"><span data-stu-id="3a40f-164">target framework</span></span>](#target-framework)
* [<span data-ttu-id="3a40f-165">TFM (moniker framework di destinazione)</span><span class="sxs-lookup"><span data-stu-id="3a40f-165">TFM (target framework moniker)</span></span>](#tfm)

<span data-ttu-id="3a40f-166">Nella documentazione esistente il termine "framework" si riferisce talvolta a un'[implementazione di .NET](#implementation-of-net).</span><span class="sxs-lookup"><span data-stu-id="3a40f-166">In the existing documentation, "framework" sometimes refers to an [implementation of .NET](#implementation-of-net).</span></span> <span data-ttu-id="3a40f-167">In un articolo, ad esempio, è possibile che .NET Core venga considerato un framework.</span><span class="sxs-lookup"><span data-stu-id="3a40f-167">For example, an article may call .NET Core a framework.</span></span> <span data-ttu-id="3a40f-168">È intenzione di Microsoft chiarire il significato di questo termine nella documentazione.</span><span class="sxs-lookup"><span data-stu-id="3a40f-168">We plan to eliminate this confusing usage from the documentation.</span></span>

## <a name="gc"></a><span data-ttu-id="3a40f-169">GC</span><span class="sxs-lookup"><span data-stu-id="3a40f-169">GC</span></span>

<span data-ttu-id="3a40f-170">Garbage Collector.</span><span class="sxs-lookup"><span data-stu-id="3a40f-170">Garbage collector.</span></span>

<span data-ttu-id="3a40f-171">Il Garbage Collector è un'implementazione di un sistema di gestione automatica della memoria.</span><span class="sxs-lookup"><span data-stu-id="3a40f-171">The garbage collector is an implementation of automatic memory management.</span></span>  <span data-ttu-id="3a40f-172">Libera infatti la memoria occupata da oggetti che non vengono più usati.</span><span class="sxs-lookup"><span data-stu-id="3a40f-172">The GC frees memory occupied by objects that are no longer in use.</span></span> 

<span data-ttu-id="3a40f-173">Vedere [Garbage Collection](garbage-collection/index.md).</span><span class="sxs-lookup"><span data-stu-id="3a40f-173">See [Garbage Collection](garbage-collection/index.md).</span></span>

## <a name="il"></a><span data-ttu-id="3a40f-174">IL</span><span class="sxs-lookup"><span data-stu-id="3a40f-174">IL</span></span>

<span data-ttu-id="3a40f-175">Linguaggio intermedio.</span><span class="sxs-lookup"><span data-stu-id="3a40f-175">Intermediate language.</span></span>

<span data-ttu-id="3a40f-176">Con i linguaggi .NET di livello superiore, ad esempio C#, la compilazione viene eseguita fino a un set di istruzioni indipendente dall'hardware, che viene chiamato linguaggio intermedio (IL).</span><span class="sxs-lookup"><span data-stu-id="3a40f-176">Higher-level .NET languages, such as C#, compile down to a hardware-agnostic instruction set, which is called Intermediate Language (IL).</span></span> <span data-ttu-id="3a40f-177">Tale linguaggio intermedio è noto anche come MSIL (Microsoft IL) o CIL (Common IL).</span><span class="sxs-lookup"><span data-stu-id="3a40f-177">IL is sometimes referred to as MSIL (Microsoft IL) or CIL (Common IL).</span></span>

## <a name="jit"></a><span data-ttu-id="3a40f-178">JIT</span><span class="sxs-lookup"><span data-stu-id="3a40f-178">JIT</span></span>

<span data-ttu-id="3a40f-179">Compilatore JIT.</span><span class="sxs-lookup"><span data-stu-id="3a40f-179">Just-in-time compiler.</span></span>

<span data-ttu-id="3a40f-180">Simile a [AOT](#aot), questo compilatore esegue la conversione del linguaggio [IL](#il) in codice macchina riconosciuto dal processore.</span><span class="sxs-lookup"><span data-stu-id="3a40f-180">Similar to [AOT](#aot), this compiler translates [IL](#il) to machine code that the processor understands.</span></span> <span data-ttu-id="3a40f-181">A differenza di AOT, la compilazione JIT viene eseguita su richiesta e nello stesso computer in cui deve essere eseguito il codice.</span><span class="sxs-lookup"><span data-stu-id="3a40f-181">Unlike AOT, JIT compilation happens on demand and is performed on the same machine that the code needs to run on.</span></span> <span data-ttu-id="3a40f-182">La compilazione JIT viene eseguita durante l'esecuzione dell'applicazione, di conseguenza la fase di compilazione fa parte del runtime.</span><span class="sxs-lookup"><span data-stu-id="3a40f-182">Since JIT compilation occurs during execution of the application, compile time is part of the run time.</span></span> <span data-ttu-id="3a40f-183">I compilatori JIT devono quindi bilanciare il tempo impiegato per l'ottimizzazione del tempo con i possibili risparmi ottenuti dal codice risultante.</span><span class="sxs-lookup"><span data-stu-id="3a40f-183">Thus, JIT compilers have to balance time spent optimizing code against the savings that the resulting code can produce.</span></span> <span data-ttu-id="3a40f-184">Ma dal momento che un compilatore JIT riconosce l'hardware effettivamente in uso, gli sviluppatori non devono più fornire implementazioni diverse.</span><span class="sxs-lookup"><span data-stu-id="3a40f-184">But a JIT knows the actual hardware and can free developers from having to ship different implementations.</span></span>

## <a name="implementation-of-net"></a><span data-ttu-id="3a40f-185">implementazione di .NET</span><span class="sxs-lookup"><span data-stu-id="3a40f-185">implementation of .NET</span></span>

<span data-ttu-id="3a40f-186">Un'implementazione di .NET include i componenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="3a40f-186">An implementation of .NET includes the following:</span></span>

- <span data-ttu-id="3a40f-187">Uno o più runtime.</span><span class="sxs-lookup"><span data-stu-id="3a40f-187">One or more runtimes.</span></span> <span data-ttu-id="3a40f-188">Esempi: CLR, CoreCLR, CoreRT.</span><span class="sxs-lookup"><span data-stu-id="3a40f-188">Examples: CLR, CoreCLR, CoreRT.</span></span>
- <span data-ttu-id="3a40f-189">Una libreria di classi che implementa una versione di .NET Standard e può includere API aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="3a40f-189">A class library that implements a version of the .NET Standard and may include additional APIs.</span></span> <span data-ttu-id="3a40f-190">Esempi: libreria di classi base .NET Framework, libreria di classi base .NET Core.</span><span class="sxs-lookup"><span data-stu-id="3a40f-190">Examples: .NET Framework Base Class Library, .NET Core Base Class Library.</span></span>
- <span data-ttu-id="3a40f-191">Facoltativamente, uno o più framework applicazione.</span><span class="sxs-lookup"><span data-stu-id="3a40f-191">Optionally, one or more application frameworks.</span></span> <span data-ttu-id="3a40f-192">Esempi: ASP.NET, Windows Forms e WPF sono inclusi in .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3a40f-192">Examples: ASP.NET, Windows Forms, and WPF are included in the .NET Framework.</span></span>
- <span data-ttu-id="3a40f-193">Facoltativamente, strumenti di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="3a40f-193">Optionally, development tools.</span></span> <span data-ttu-id="3a40f-194">Alcuni strumenti di sviluppo sono condivisi tra più implementazioni.</span><span class="sxs-lookup"><span data-stu-id="3a40f-194">Some development tools are shared among multiple implementations.</span></span>

<span data-ttu-id="3a40f-195">Esempi di implementazioni di .NET:</span><span class="sxs-lookup"><span data-stu-id="3a40f-195">Examples of .NET implementations:</span></span>

- [<span data-ttu-id="3a40f-196">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="3a40f-196">.NET Framework</span></span>](#net-framework)
- [<span data-ttu-id="3a40f-197">.NET Core</span><span class="sxs-lookup"><span data-stu-id="3a40f-197">.NET Core</span></span>](#net-core)
- [<span data-ttu-id="3a40f-198">Piattaforma UWP (Universal Windows Platform)</span><span class="sxs-lookup"><span data-stu-id="3a40f-198">Universal Windows Platform (UWP)</span></span>](#uwp)

## <a name="library"></a><span data-ttu-id="3a40f-199">libreria</span><span class="sxs-lookup"><span data-stu-id="3a40f-199">library</span></span>

<span data-ttu-id="3a40f-200">Raccolta di API che possono essere chiamate da app o altre librerie.</span><span class="sxs-lookup"><span data-stu-id="3a40f-200">A collection of APIs that can be called by apps or other libraries.</span></span> <span data-ttu-id="3a40f-201">Una libreria .NET è composta da uno o più [assembly](#assembly).</span><span class="sxs-lookup"><span data-stu-id="3a40f-201">A .NET library is composed of one or more [assemblies](#assembly).</span></span>

<span data-ttu-id="3a40f-202">Le parole libreria e [framework](#framework) vengono spesso usate come sinonimi.</span><span class="sxs-lookup"><span data-stu-id="3a40f-202">The words library and [framework](#framework) are often used synonymously.</span></span>

## <a name="metapackage"></a><span data-ttu-id="3a40f-203">metapacchetto</span><span class="sxs-lookup"><span data-stu-id="3a40f-203">metapackage</span></span>

<span data-ttu-id="3a40f-204">Pacchetto NuGet che non contiene una propria libreria, ma è costituito da un elenco di dipendenze.</span><span class="sxs-lookup"><span data-stu-id="3a40f-204">A NuGet package that has no library of its own but is only a list of dependencies.</span></span> <span data-ttu-id="3a40f-205">Facoltativamente, i pacchetti inclusi possono stabilire l'API per un framework di destinazione.</span><span class="sxs-lookup"><span data-stu-id="3a40f-205">The included packages can optionally establish the API for a target framework.</span></span>

<span data-ttu-id="3a40f-206">Vedere [Pacchetti, metapacchetti e framework](../core/packages.md)</span><span class="sxs-lookup"><span data-stu-id="3a40f-206">See [Packages, Metapackages and Frameworks](../core/packages.md)</span></span>

## <a name="mono"></a><span data-ttu-id="3a40f-207">Mono</span><span class="sxs-lookup"><span data-stu-id="3a40f-207">Mono</span></span>

<span data-ttu-id="3a40f-208">Mono è un'implementazione di .NET usata principalmente quando è necessario un runtime di dimensioni ridotte.</span><span class="sxs-lookup"><span data-stu-id="3a40f-208">Mono is a .NET implementation that is mainly used when a small runtime is required.</span></span> <span data-ttu-id="3a40f-209">Si tratta del runtime su cui si basano le applicazioni Xamarin in Android, Mac, iOS, tvOS e watchOS ed è incentrato principalmente su app che richiedono un footprint ridotto.</span><span class="sxs-lookup"><span data-stu-id="3a40f-209">It is the runtime that powers Xamarin applications on Android, Mac, iOS, tvOS and watchOS and is focused primarily on apps that require a small footprint.</span></span>

<span data-ttu-id="3a40f-210">Supporta tutte le versioni attualmente pubblicate di .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="3a40f-210">It supports all of the currently published .NET Standard versions.</span></span>

<span data-ttu-id="3a40f-211">In precedenza, Mono implementava le API di dimensioni maggiori di .NET Framework ed emulava alcune delle funzionalità più diffuse su Unix.</span><span class="sxs-lookup"><span data-stu-id="3a40f-211">Historically, Mono implemented the larger API of the .NET Framework and emulated some of the most popular capabilities on Unix.</span></span> <span data-ttu-id="3a40f-212">Viene a volte usato per eseguire applicazioni .NET che si basano su tali funzionalità in Unix.</span><span class="sxs-lookup"><span data-stu-id="3a40f-212">It is sometimes used to run .NET applications that rely on those capabilities on Unix.</span></span>

<span data-ttu-id="3a40f-213">Mono viene in genere usato con un compilatore JIT, ma include anche un compilatore statico completo (compilazione Ahead Of Time), usato in piattaforme quali iOS.</span><span class="sxs-lookup"><span data-stu-id="3a40f-213">Mono is typically used with a just-in-time compiler, but it also features a full static compiler (ahead-of-time compilation) that is used on platforms like iOS.</span></span>

<span data-ttu-id="3a40f-214">Per altre informazioni su Mono, vedere la [documentazione Mono](http://www.mono-project.com/docs/).</span><span class="sxs-lookup"><span data-stu-id="3a40f-214">To learn more about Mono, see the [Mono documentation](http://www.mono-project.com/docs/).</span></span>

## <a name="net"></a><span data-ttu-id="3a40f-215">.NET</span><span class="sxs-lookup"><span data-stu-id="3a40f-215">.NET</span></span>

<span data-ttu-id="3a40f-216">Termine generico per riferirsi a [.NET Standard](#net-standard) e a tutti i carichi di lavoro e le [implementazioni di .NET](#implementation-of-net).</span><span class="sxs-lookup"><span data-stu-id="3a40f-216">The umbrella term for [.NET Standard](#net-standard) and all [.NET implementations](#implementation-of-net) and workloads.</span></span> <span data-ttu-id="3a40f-217">Questo termine è sempre scritto in lettere maiuscole, pertanto la grafia ".Net" è errata.</span><span class="sxs-lookup"><span data-stu-id="3a40f-217">Always capitalized, never ".Net".</span></span>

<span data-ttu-id="3a40f-218">Vedere [Guida alla piattaforma .NET](index.md).</span><span class="sxs-lookup"><span data-stu-id="3a40f-218">See the [.NET Guide](index.md)</span></span>

## <a name="net-core"></a><span data-ttu-id="3a40f-219">.NET Core</span><span class="sxs-lookup"><span data-stu-id="3a40f-219">.NET Core</span></span> 

<span data-ttu-id="3a40f-220">Implementazione open source, ad alte prestazioni e multi-piattaforma di .NET.</span><span class="sxs-lookup"><span data-stu-id="3a40f-220">A cross-platform, high-performance, open source implementation of .NET.</span></span> <span data-ttu-id="3a40f-221">Include Core Common Language Runtime (CoreCLR), il runtime Core AOT (CoreRT, in fase di sviluppo), la libreria di classi base Core e Core SDK.</span><span class="sxs-lookup"><span data-stu-id="3a40f-221">Includes the Core Common Language Runtime (CoreCLR), the Core AOT Runtime (CoreRT, in development), the Core Base Class Library, and the Core SDK.</span></span>

<span data-ttu-id="3a40f-222">Vedere [.NET Core](../core/index.md).</span><span class="sxs-lookup"><span data-stu-id="3a40f-222">See [.NET Core](../core/index.md).</span></span>

## <a name="net-core-cli"></a><span data-ttu-id="3a40f-223">Interfaccia della riga di comando di .NET Core</span><span class="sxs-lookup"><span data-stu-id="3a40f-223">.NET Core CLI</span></span>

<span data-ttu-id="3a40f-224">Toolchain multipiattaforma per lo sviluppo di applicazioni .NET Core.</span><span class="sxs-lookup"><span data-stu-id="3a40f-224">A cross-platform toolchain for developing .NET Core applications.</span></span>

<span data-ttu-id="3a40f-225">Vedere [Strumenti dell'interfaccia della riga di comando di .NET Core](../core/tools/index.md).</span><span class="sxs-lookup"><span data-stu-id="3a40f-225">See [.NET Core command-line interface (CLI) tools](../core/tools/index.md).</span></span>

## <a name="net-core-sdk"></a><span data-ttu-id="3a40f-226">.NET Core SDK</span><span class="sxs-lookup"><span data-stu-id="3a40f-226">.NET Core SDK</span></span>

<span data-ttu-id="3a40f-227">Set di librerie e strumenti che consente agli sviluppatori di creare applicazioni e librerie .NET Core.</span><span class="sxs-lookup"><span data-stu-id="3a40f-227">A set of libraries and tools that allow developers to create .NET Core applications and libraries.</span></span> <span data-ttu-id="3a40f-228">Include l'[interfaccia della riga di comando di .NET Core](#net-core-cli) per la creazione di app, le librerie e il runtime .NET Core per la compilazione e l'esecuzione di app e l'eseguibile dotnet (*dotnet.exe*) per l'esecuzione delle applicazioni e dei comandi dell'interfaccia della riga di comando.</span><span class="sxs-lookup"><span data-stu-id="3a40f-228">Includes the [.NET Core CLI](#net-core-cli) for building apps, .NET Core libraries and runtime for building and running apps, and the dotnet executable (*dotnet.exe*) that runs CLI commands and runs applications.</span></span>

<span data-ttu-id="3a40f-229">Vedere [Panoramica di .NET Core SDK](../core/sdk.md).</span><span class="sxs-lookup"><span data-stu-id="3a40f-229">See [.NET Core SDK Overview](../core/sdk.md).</span></span>

## <a name="net-framework"></a><span data-ttu-id="3a40f-230">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="3a40f-230">.NET Framework</span></span>

<span data-ttu-id="3a40f-231">Implementazione di .NET che viene eseguita solo in Windows.</span><span class="sxs-lookup"><span data-stu-id="3a40f-231">An implementation of .NET that runs only on Windows.</span></span> <span data-ttu-id="3a40f-232">Include Common Language Runtime (CLR), la libreria di classi base e le librerie del framework applicazione, quali ASP.NET, Windows Form e WPF.</span><span class="sxs-lookup"><span data-stu-id="3a40f-232">Includes the Common Language Runtime (CLR), the Base Class Library, and application framework libraries such as ASP.NET, Windows Forms, and WPF.</span></span>

<span data-ttu-id="3a40f-233">Vedere [Guida a .NET Framework](../framework/index.md).</span><span class="sxs-lookup"><span data-stu-id="3a40f-233">See [.NET Framework Guide](../framework/index.md).</span></span>

## <a name="net-native"></a><span data-ttu-id="3a40f-234">.NET Native</span><span class="sxs-lookup"><span data-stu-id="3a40f-234">.NET Native</span></span>

<span data-ttu-id="3a40f-235">Toolchain del compilatore che produce codice nativo Ahead Of Time (AOT), in contrapposizione a quello JIT.</span><span class="sxs-lookup"><span data-stu-id="3a40f-235">A compiler tool chain that produces native code ahead-of-time (AOT), as opposed to just-in-time (JIT).</span></span>

<span data-ttu-id="3a40f-236">La compilazione viene eseguita nel computer dello sviluppatore in modo analogo al funzionamento di un compilatore e un linker C++.</span><span class="sxs-lookup"><span data-stu-id="3a40f-236">Compilation happens on the developer's machine similar to the way a C++ compiler and linker works.</span></span> <span data-ttu-id="3a40f-237">Il codice inutilizzato viene rimosso e viene dedicato più tempo all'ottimizzazione.</span><span class="sxs-lookup"><span data-stu-id="3a40f-237">It removes unused code and spends more time optimizing it.</span></span> <span data-ttu-id="3a40f-238">Il codice viene estratto dalle librerie e unito nel file eseguibile.</span><span class="sxs-lookup"><span data-stu-id="3a40f-238">It extracts code from libraries and merges them into the executable.</span></span> <span data-ttu-id="3a40f-239">Il risultato è un singolo modulo che rappresenta l'intera app.</span><span class="sxs-lookup"><span data-stu-id="3a40f-239">The result is a single module that represents the entire app.</span></span>

<span data-ttu-id="3a40f-240">Il primo framework applicazione supportato da .NET Native è stata la piattaforma UWP.</span><span class="sxs-lookup"><span data-stu-id="3a40f-240">UWP was the first application framework supported by .NET Native.</span></span> <span data-ttu-id="3a40f-241">Ora è supportata la compilazione di app console native per Windows, macOS e Linux.</span><span class="sxs-lookup"><span data-stu-id="3a40f-241">Now, we support building native console apps for Windows, macOS, and Linux.</span></span>

<span data-ttu-id="3a40f-242">Vedere [Intro to .NET Native and CoreRT](https://github.com/dotnet/corert/blob/master/Documentation/intro-to-corert.md) (Introduzione a .NET Native e CoreRT).</span><span class="sxs-lookup"><span data-stu-id="3a40f-242">See [Intro to .NET Native and CoreRT](https://github.com/dotnet/corert/blob/master/Documentation/intro-to-corert.md)</span></span>

## <a name="net-standard"></a><span data-ttu-id="3a40f-243">.NET Standard</span><span class="sxs-lookup"><span data-stu-id="3a40f-243">.NET Standard</span></span>

<span data-ttu-id="3a40f-244">Specifica formale delle API .NET che sono disponibili in tutte le implementazioni di .NET.</span><span class="sxs-lookup"><span data-stu-id="3a40f-244">A formal specification of .NET APIs that are available in each .NET implementation.</span></span>

<span data-ttu-id="3a40f-245">La specifica .NET Standard è talvolta indicata come libreria nella documentazione.</span><span class="sxs-lookup"><span data-stu-id="3a40f-245">The .NET Standard specification is sometimes called a library in the documentation.</span></span> <span data-ttu-id="3a40f-246">Dal momento che una libreria include le implementazioni delle API e non solo di specifiche (interfacce), è fuorviante usare il termine "libreria" in riferimento a .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="3a40f-246">Because a library includes API implementations, not only specifications (interfaces), it's misleading to call .NET Standard a "library."</span></span> <span data-ttu-id="3a40f-247">È intenzione di Microsoft chiarire il significato di questo termine nella documentazione, ad eccezione dei casi in cui viene fatto riferimento al nome del metapacchetto .NET Standard (`NETStandard.Library`).</span><span class="sxs-lookup"><span data-stu-id="3a40f-247">We plan to eliminate that usage from the documentation, except in reference to the name of the .NET Standard metapackage (`NETStandard.Library`).</span></span>

<span data-ttu-id="3a40f-248">Vedere [.NET Standard](net-standard.md).</span><span class="sxs-lookup"><span data-stu-id="3a40f-248">See [.NET Standard](net-standard.md).</span></span>

## <a name="ngen"></a><span data-ttu-id="3a40f-249">NGEN</span><span class="sxs-lookup"><span data-stu-id="3a40f-249">NGEN</span></span>

<span data-ttu-id="3a40f-250">Generazione di immagini native.</span><span class="sxs-lookup"><span data-stu-id="3a40f-250">Native (image) generation.</span></span>

<span data-ttu-id="3a40f-251">È possibile considerare questa tecnologia come un compilatore JIT permanente.</span><span class="sxs-lookup"><span data-stu-id="3a40f-251">You can think of this technology as a persistent JIT compiler.</span></span> <span data-ttu-id="3a40f-252">Il codice viene in genere compilato nel computer stesso in cui viene eseguito il codice, ma la compilazione viene eseguita di solito durante l'installazione.</span><span class="sxs-lookup"><span data-stu-id="3a40f-252">It usually compiles code on the machine where the code is executed, but compilation typically occurs at install time.</span></span>

## <a name="package"></a><span data-ttu-id="3a40f-253">pacchetto</span><span class="sxs-lookup"><span data-stu-id="3a40f-253">package</span></span>

<span data-ttu-id="3a40f-254">Un pacchetto NuGet &mdash; o semplicemente un pacchetto &mdash; è un file *ZIP* contenente uno o più assembly con lo stesso nome, unitamente a metadati aggiuntivi, quali il nome dell'autore.</span><span class="sxs-lookup"><span data-stu-id="3a40f-254">A NuGet package &mdash; or just a package &mdash; is a *.zip* file with one or more assemblies of the same name along with additional metadata such as the author name.</span></span>

<span data-ttu-id="3a40f-255">Il file *ZIP* è caratterizzato dall'estensione *nupkg* e può contenere asset, quali file *DLL* e *XML*, da usare con più framework e versioni.</span><span class="sxs-lookup"><span data-stu-id="3a40f-255">The *.zip* file has a *.nupkg* extension and may contain assets, such as *.dll* files and *.xml* files, for use with multiple frameworks and versions.</span></span> <span data-ttu-id="3a40f-256">Quando vengono installati in un'app o una libreria, gli asset appropriati vengono selezionati in base al framework di destinazione specificato dall'app o dalla libreria.</span><span class="sxs-lookup"><span data-stu-id="3a40f-256">When installed in an app or library, the appropriate assets are selected based on the target framework specified by the app or library.</span></span> <span data-ttu-id="3a40f-257">Gli asset che definiscono l'interfaccia si trovano nella cartella *ref*, mentre quelli che definiscono l'implementazione si trovano nella cartella *lib*.</span><span class="sxs-lookup"><span data-stu-id="3a40f-257">The assets that define the interface are in the *ref* folder, and the assets that define the implementation are in the *lib* folder.</span></span>

## <a name="platform"></a><span data-ttu-id="3a40f-258">platform</span><span class="sxs-lookup"><span data-stu-id="3a40f-258">platform</span></span>

<span data-ttu-id="3a40f-259">Sistema operativo e hardware in cui viene eseguito, ad esempio Windows, macOS, Linux, iOS e Android.</span><span class="sxs-lookup"><span data-stu-id="3a40f-259">An operating system and the hardware it runs on, such as Windows, macOS, Linux, iOS, and Android.</span></span>

<span data-ttu-id="3a40f-260">Ecco alcuni esempio di utilizzo nelle frasi:</span><span class="sxs-lookup"><span data-stu-id="3a40f-260">Here are examples of usage in sentences:</span></span>

- <span data-ttu-id="3a40f-261">".NET Core è un'implementazione multipiattaforma di .NET".</span><span class="sxs-lookup"><span data-stu-id="3a40f-261">".NET Core is a cross-platform implementation of .NET."</span></span> 
- <span data-ttu-id="3a40f-262">"I profili delle librerie di classi portabili rappresentano piattaforme Microsoft, mentre .NET Standard è indipendente dalla piattaforma".</span><span class="sxs-lookup"><span data-stu-id="3a40f-262">"PCL profiles represent Microsoft platforms, while the .NET Standard is agnostic to platform."</span></span>

<span data-ttu-id="3a40f-263">Nella documentazione di .NET si usa spesso "piattaforma .NET" per indicare un'implementazione di .NET o lo stack .NET che include tutte le implementazioni.</span><span class="sxs-lookup"><span data-stu-id="3a40f-263">The .NET documentation frequently uses ".NET platform" to mean either an implementation of .NET or the .NET stack including all implementations.</span></span> <span data-ttu-id="3a40f-264">Entrambe queste accezioni generano confusione con il significato primario (sistema operativo/hardware), di conseguenza Microsoft intende eliminarle dalla documentazione.</span><span class="sxs-lookup"><span data-stu-id="3a40f-264">Both of these usages tend to get confused with the primary (OS/hardware) meaning, so we plan to eliminate these usages from the documentation.</span></span>

## <a name="runtime"></a><span data-ttu-id="3a40f-265">runtime</span><span class="sxs-lookup"><span data-stu-id="3a40f-265">runtime</span></span>

<span data-ttu-id="3a40f-266">Ambiente di esecuzione per un programma gestito.</span><span class="sxs-lookup"><span data-stu-id="3a40f-266">The execution environment for a managed program.</span></span>

<span data-ttu-id="3a40f-267">Il sistema operativo è parte dell'ambiente di runtime, ma non del runtime .NET.</span><span class="sxs-lookup"><span data-stu-id="3a40f-267">The OS is part of the runtime environment but is not part of the .NET runtime.</span></span> <span data-ttu-id="3a40f-268">Ecco alcuni esempi di runtime .NET:</span><span class="sxs-lookup"><span data-stu-id="3a40f-268">Here are some examples of .NET runtimes:</span></span>

- <span data-ttu-id="3a40f-269">Common Language Runtime (CLR)</span><span class="sxs-lookup"><span data-stu-id="3a40f-269">Common Language Runtime (CLR)</span></span>
- <span data-ttu-id="3a40f-270">Core Common Language Runtime (CoreCLR)</span><span class="sxs-lookup"><span data-stu-id="3a40f-270">Core Common Language Runtime (CoreCLR)</span></span>
- <span data-ttu-id="3a40f-271">.NET Native (per la piattaforma UWP)</span><span class="sxs-lookup"><span data-stu-id="3a40f-271">.NET Native (for UWP)</span></span>
- <span data-ttu-id="3a40f-272">Runtime di Mono</span><span class="sxs-lookup"><span data-stu-id="3a40f-272">Mono runtime</span></span>

<span data-ttu-id="3a40f-273">Nella documentazione di .NET si usa talvolta "runtime" per indicare un'implementazione di .NET.</span><span class="sxs-lookup"><span data-stu-id="3a40f-273">The .NET documentation sometimes uses "runtime" to mean an implementation of .NET.</span></span> <span data-ttu-id="3a40f-274">Ad esempio, nelle frasi seguenti "runtime" deve essere sostituito da "implementazione":</span><span class="sxs-lookup"><span data-stu-id="3a40f-274">For example, in the following sentences "runtime" should be replaced with "implementation":</span></span>

- <span data-ttu-id="3a40f-275">"I diversi runtime .NET implementano versioni specifiche di .NET Standard".</span><span class="sxs-lookup"><span data-stu-id="3a40f-275">"The various .NET runtimes implement specific versions of .NET Standard."</span></span>
- <span data-ttu-id="3a40f-276">"Le librerie da eseguire su più runtime devono avere come destinazione questo framework"</span><span class="sxs-lookup"><span data-stu-id="3a40f-276">"Libraries that are intended to run on multiple runtimes should target this framework."</span></span> <span data-ttu-id="3a40f-277">(in riferimento a .NET Standard).</span><span class="sxs-lookup"><span data-stu-id="3a40f-277">(referring to .NET Standard)</span></span>
- <span data-ttu-id="3a40f-278">"I diversi runtime .NET implementano versioni specifiche di .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="3a40f-278">"The various .NET runtimes implement specific versions of .NET Standard.</span></span> <span data-ttu-id="3a40f-279">…</span><span class="sxs-lookup"><span data-stu-id="3a40f-279">…</span></span> <span data-ttu-id="3a40f-280">Ciascuna versione del runtime .NET annuncia la versione .NET Standard più recente supportata...".</span><span class="sxs-lookup"><span data-stu-id="3a40f-280">Each .NET runtime version advertises the highest .NET Standard version it supports …"</span></span>

<span data-ttu-id="3a40f-281">Microsoft intende eliminare questa incoerenza.</span><span class="sxs-lookup"><span data-stu-id="3a40f-281">We plan to eliminate this inconsistent usage.</span></span> 

## <a name="stack"></a><span data-ttu-id="3a40f-282">stack</span><span class="sxs-lookup"><span data-stu-id="3a40f-282">stack</span></span>

<span data-ttu-id="3a40f-283">Set di tecnologie di programmazione che vengono usate in combinazione per compilare ed eseguire applicazioni.</span><span class="sxs-lookup"><span data-stu-id="3a40f-283">A set of programming technologies that are used together to build and run applications.</span></span>

<span data-ttu-id="3a40f-284">Il termine "stack .NET" si riferisce a .NET Standard e a tutte le implementazioni di .NET.</span><span class="sxs-lookup"><span data-stu-id="3a40f-284">"The .NET stack" refers to the .NET Standard and all .NET implementations.</span></span> <span data-ttu-id="3a40f-285">L'espressione "uno stack .NET" può fare riferimento a una singola implementazione di .NET.</span><span class="sxs-lookup"><span data-stu-id="3a40f-285">The phrase "a .NET stack" may refer to one implementation of .NET.</span></span> 

## <a name="target-framework"></a><span data-ttu-id="3a40f-286">framework di destinazione</span><span class="sxs-lookup"><span data-stu-id="3a40f-286">target framework</span></span>

<span data-ttu-id="3a40f-287">Raccolta di API su cui si basa un'app o una libreria .NET.</span><span class="sxs-lookup"><span data-stu-id="3a40f-287">The collection of APIs that a .NET app or library relies on.</span></span>

<span data-ttu-id="3a40f-288">Un'app o una libreria può essere destinata a una versione di .NET Standard (ad esempio .NET Standard 2.0), che è la specifica di un set standardizzato di API in tutte le implementazioni di .NET.</span><span class="sxs-lookup"><span data-stu-id="3a40f-288">An app or library can target a version of .NET Standard (for example, .NET Standard 2.0), which is specification for a standardized set of APIs across all .NET implementations.</span></span> <span data-ttu-id="3a40f-289">Un'app o una libreria può anche essere destinata a una versione di un'implementazione specifica di .NET. In tal caso, ottiene l'accesso ad API specifiche dell'implementazione.</span><span class="sxs-lookup"><span data-stu-id="3a40f-289">An app or library can also target a version of a specific .NET implementation, in which case it gets access to implementation-specific APIs.</span></span> <span data-ttu-id="3a40f-290">Ad esempio, un'app destinata a Xamarin.iOS ottiene l'accesso ai wrapper di API iOS forniti da Xamarin.</span><span class="sxs-lookup"><span data-stu-id="3a40f-290">For example, an app that targets Xamarin.iOS gets access to Xamarin-provided iOS API wrappers.</span></span>

<span data-ttu-id="3a40f-291">Per alcuni framework di destinazione, ad esempio .NET Framework, le API disponibili vengono definite dagli assembly installati da un framework .NET in un sistema e potrebbero includere API del framework applicazione, ad esempio, ASP.NET e WinForms.</span><span class="sxs-lookup"><span data-stu-id="3a40f-291">For some target frameworks (for example, the .NET Framework) the available APIs are defined by the assemblies that a .NET implementation installs on a system, which may include application framework APIs (for example, ASP.NET, WinForms).</span></span> <span data-ttu-id="3a40f-292">Per i framework di destinazione basati su pacchetti, ad esempio .NET Standard e .NET Core, le API del framework vengono definite dai pacchetti installati nell'app o nella libreria.</span><span class="sxs-lookup"><span data-stu-id="3a40f-292">For package-based target frameworks (such as .NET Standard and .NET Core), the framework APIs are defined by the packages installed in the app or library.</span></span> <span data-ttu-id="3a40f-293">In tal caso, il framework di destinazione specifica in modo implicito un metapacchetto che fa riferimento a tutti i pacchetti che costituiscono complessivamente il framework.</span><span class="sxs-lookup"><span data-stu-id="3a40f-293">In that case, the target framework implicitly specifies a metapackage that references all the packages that together make up the framework.</span></span>

<span data-ttu-id="3a40f-294">Vedere [Framework di destinazione](frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="3a40f-294">See [Target Frameworks](frameworks.md).</span></span>

## <a name="tfm"></a><span data-ttu-id="3a40f-295">TFM</span><span class="sxs-lookup"><span data-stu-id="3a40f-295">TFM</span></span>

<span data-ttu-id="3a40f-296">Moniker framework di destinazione.</span><span class="sxs-lookup"><span data-stu-id="3a40f-296">Target framework moniker.</span></span>

<span data-ttu-id="3a40f-297">Formato di token standardizzato per specificare il framework di destinazione di un'app o di una libreria .NET.</span><span class="sxs-lookup"><span data-stu-id="3a40f-297">A standardized token format for specifying the target framework of a .NET app or library.</span></span> <span data-ttu-id="3a40f-298">In genere, per fare riferimento ai framework di destinazione si usa un nome breve, ad esempio `net462`.</span><span class="sxs-lookup"><span data-stu-id="3a40f-298">Target frameworks are typically referenced by a short name, such as `net462`.</span></span> <span data-ttu-id="3a40f-299">Sono presenti anche moniker framework di destinazione in formato lungo (ad esempio .NETFramework,Version=4.6.2), che però non vengono in genere usati per specificare un framework di destinazione.</span><span class="sxs-lookup"><span data-stu-id="3a40f-299">Long-form TFMs (such as .NETFramework,Version=4.6.2) exist but are not generally used to specify a target framework.</span></span>

<span data-ttu-id="3a40f-300">Vedere [Framework di destinazione](frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="3a40f-300">See [Target Frameworks](frameworks.md).</span></span>

## <a name="uwp"></a><span data-ttu-id="3a40f-301">Piattaforma UWP</span><span class="sxs-lookup"><span data-stu-id="3a40f-301">UWP</span></span>

<span data-ttu-id="3a40f-302">Piattaforma UWP (Universal Windows Platform).</span><span class="sxs-lookup"><span data-stu-id="3a40f-302">Universal Windows Platform.</span></span>

<span data-ttu-id="3a40f-303">Implementazione di .NET usata per la creazione di applicazioni Windows moderne e abilitate per il tocco e di software per Internet delle cose.</span><span class="sxs-lookup"><span data-stu-id="3a40f-303">An implementation of .NET that is used for building modern, touch-enabled Windows applications and software for the Internet of Things (IoT).</span></span> <span data-ttu-id="3a40f-304">È stata progettata per unificare i diversi tipi di dispositivi da specificare come destinazione, ad esempio computer, tablet, phablet, telefoni e anche Xbox.</span><span class="sxs-lookup"><span data-stu-id="3a40f-304">It's designed to unify the different types of devices that you may want to target, including PCs, tablets, phablets, phones, and even the Xbox.</span></span> <span data-ttu-id="3a40f-305">La piattaforma UWP offre molti servizi, ad esempio un App Store centralizzato, un ambiente di esecuzione (AppContainer) e un set di API di Windows da usare invece di Win32 (WinRT).</span><span class="sxs-lookup"><span data-stu-id="3a40f-305">UWP provides many services, such as a centralized app store, an execution environment (AppContainer), and a set of Windows APIs to use instead of Win32 (WinRT).</span></span> <span data-ttu-id="3a40f-306">Le app possono essere scritte in C++, C#, VB.NET e JavaScript.</span><span class="sxs-lookup"><span data-stu-id="3a40f-306">Apps can be written in C++, C#, VB.NET, and JavaScript.</span></span> <span data-ttu-id="3a40f-307">Quando si usano C# e VB.NET, le API .NET vengono fornite da .NET Core.</span><span class="sxs-lookup"><span data-stu-id="3a40f-307">When using C# and VB.NET, the .NET APIs are provided by .NET Core.</span></span>

## <a name="see-also"></a><span data-ttu-id="3a40f-308">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3a40f-308">See also</span></span>

[<span data-ttu-id="3a40f-309">Guida di .NET</span><span class="sxs-lookup"><span data-stu-id="3a40f-309">.NET Guide</span></span>](index.md)  
[<span data-ttu-id="3a40f-310">Guida a .NET Framework</span><span class="sxs-lookup"><span data-stu-id="3a40f-310">.NET Framework Guide</span></span>](../framework/index.md)  
[<span data-ttu-id="3a40f-311">.NET Core</span><span class="sxs-lookup"><span data-stu-id="3a40f-311">.NET Core</span></span>](../core/index.md)  
[<span data-ttu-id="3a40f-312">Panoramica di ASP.NET</span><span class="sxs-lookup"><span data-stu-id="3a40f-312">ASP.NET Overview</span></span>](/aspnet/index#pivot=aspnet)  
[<span data-ttu-id="3a40f-313">Panoramica di ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="3a40f-313">ASP.NET Core Overview</span></span>](/aspnet/index#pivot=core)  

