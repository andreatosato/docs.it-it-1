---
title: "Testing unità con Visual Basic in .NET Core usando il test dotnet e xUnit"
description: Informazioni sui concetti relativi agli unit test in .NET Core tramite un'esperienza interattiva per la creazione passo-passo di una soluzione di Visual Basic di esempio con test dotnet e xUnit.
author: billwagner
ms.author: wiwagn
ms.date: 09/01/2017
ms.topic: article
dev_langs: vb
ms.prod: .net-core
ms.openlocfilehash: 3aa6e11ae14eecef1d291f7edc1fb9a27b49861e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="unit-testing-visual-basic-net-core-libraries-using-dotnet-test-and-xunit"></a><span data-ttu-id="75b2a-103">Testing unità di librerie .NET Core di Visual Basic usando il test dotnet e xUnit</span><span class="sxs-lookup"><span data-stu-id="75b2a-103">Unit testing Visual Basic .NET Core libraries using dotnet test and xUnit</span></span>

<span data-ttu-id="75b2a-104">In questa esercitazione viene illustrata un'esperienza interattiva di compilazione passo passo di una soluzione di esempio finalizzata all'apprendimento dei concetti base del testing unità.</span><span class="sxs-lookup"><span data-stu-id="75b2a-104">This tutorial takes you through an interactive experience building a sample solution step-by-step to learn unit testing concepts.</span></span> <span data-ttu-id="75b2a-105">Se si preferisce seguire l'esercitazione usando una soluzione preesistente, [visualizzare o scaricare il codice di esempio](https://github.com/dotnet/docs/tree/master/samples/core/getting-started/unit-testing-using-dotnet-test/) prima di iniziare.</span><span class="sxs-lookup"><span data-stu-id="75b2a-105">If you prefer to follow the tutorial using a pre-built solution, [view or download the sample code](https://github.com/dotnet/docs/tree/master/samples/core/getting-started/unit-testing-using-dotnet-test/) before you begin.</span></span> <span data-ttu-id="75b2a-106">Per istruzioni sul download, vedere [Esempi ed esercitazioni](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="75b2a-106">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

## <a name="creating-the-source-project"></a><span data-ttu-id="75b2a-107">Creazione del progetto di origine</span><span class="sxs-lookup"><span data-stu-id="75b2a-107">Creating the source project</span></span>

<span data-ttu-id="75b2a-108">Aprire una finestra della shell.</span><span class="sxs-lookup"><span data-stu-id="75b2a-108">Open a shell window.</span></span> <span data-ttu-id="75b2a-109">Creare una directory denominata *unit-testing-vb-using-dotnet-test* in cui archiviare la soluzione.</span><span class="sxs-lookup"><span data-stu-id="75b2a-109">Create a directory called *unit-testing-vb-using-dotnet-test* to hold the solution.</span></span>
<span data-ttu-id="75b2a-110">In questa nuova directory eseguire [`dotnet new sln`](../tools/dotnet-new.md) per creare una nuova soluzione.</span><span class="sxs-lookup"><span data-stu-id="75b2a-110">Inside this new directory, run [`dotnet new sln`](../tools/dotnet-new.md) to create a new solution.</span></span> <span data-ttu-id="75b2a-111">Questa procedura semplifica la gestione sia della libreria di classi che del progetto di unit test.</span><span class="sxs-lookup"><span data-stu-id="75b2a-111">This practice makes it easier to manage both the class library and the unit test project.</span></span>
<span data-ttu-id="75b2a-112">All'interno della directory della soluzione creare una directory *PrimeService*.</span><span class="sxs-lookup"><span data-stu-id="75b2a-112">Inside the solution directory, create a *PrimeService* directory.</span></span> <span data-ttu-id="75b2a-113">Finora è stata creata la struttura di directory e file seguente:</span><span class="sxs-lookup"><span data-stu-id="75b2a-113">You have the following directory and file structure thus far:</span></span>

```
/unit-testing-using-dotnet-test
    unit-testing-using-dotnet-test.sln
    /PrimeService
```

<span data-ttu-id="75b2a-114">Impostare *PrimeService* come directory corrente ed eseguire [`dotnet new classlib -lang VB`](../tools/dotnet-new.md) per creare il progetto di origine.</span><span class="sxs-lookup"><span data-stu-id="75b2a-114">Make *PrimeService* the current directory and run [`dotnet new classlib -lang VB`](../tools/dotnet-new.md) to create the source project.</span></span> <span data-ttu-id="75b2a-115">Rinominare *Class1.VB* in *PrimeService.VB*.</span><span class="sxs-lookup"><span data-stu-id="75b2a-115">Rename *Class1.VB* to *PrimeService.VB*.</span></span> <span data-ttu-id="75b2a-116">Per usare lo sviluppo basato su test (TDD), si creerà un'implementazione non corretta della classe `PrimeService`:</span><span class="sxs-lookup"><span data-stu-id="75b2a-116">To use test-driven development (TDD), you create a failing implementation of the `PrimeService` class:</span></span>

```vb
Namespace Prime.Services
    Public Class PrimeService
        Public Function IsPrime(candidate As Integer) As Boolean
            Throw New NotImplementedException("Please create a test first")
        End Function
    End Class
End Namespace
```

<span data-ttu-id="75b2a-117">Tornare alla directory *unit-testing-vb-using-dotnet-test*.</span><span class="sxs-lookup"><span data-stu-id="75b2a-117">Change the directory back to the *unit-testing-vb-using-dotnet-test* directory.</span></span> <span data-ttu-id="75b2a-118">Eseguire [`dotnet sln add .\PrimeService\PrimeService.vbproj`](../tools/dotnet-sln.md) per aggiungere il progetto di libreria di classi alla soluzione.</span><span class="sxs-lookup"><span data-stu-id="75b2a-118">Run [`dotnet sln add .\PrimeService\PrimeService.vbproj`](../tools/dotnet-sln.md) to add the class library project to the solution.</span></span>

## <a name="creating-the-test-project"></a><span data-ttu-id="75b2a-119">Creazione del progetto di test</span><span class="sxs-lookup"><span data-stu-id="75b2a-119">Creating the test project</span></span>

<span data-ttu-id="75b2a-120">Creare quindi la directory *PrimeService.Tests*.</span><span class="sxs-lookup"><span data-stu-id="75b2a-120">Next, create the *PrimeService.Tests* directory.</span></span> <span data-ttu-id="75b2a-121">Di seguito è illustrata la struttura di directory:</span><span class="sxs-lookup"><span data-stu-id="75b2a-121">The following outline shows the directory structure:</span></span>

```
/unit-testing-vb-using-dotnet-test
    unit-testing-vb-using-dotnet-test.sln
    /PrimeService
        Source Files
        PrimeService.vbproj
    /PrimeService.Tests
```

<span data-ttu-id="75b2a-122">Impostare *PrimeService.Tests* come directory corrente e creare un nuovo progetto usando [`dotnet new xunit -lang VB`](../tools/dotnet-new.md).</span><span class="sxs-lookup"><span data-stu-id="75b2a-122">Make the *PrimeService.Tests* directory the current directory and create a new project using [`dotnet new xunit -lang VB`](../tools/dotnet-new.md).</span></span> <span data-ttu-id="75b2a-123">Questo comando crea un progetto di test che usa xUnit come libreria di test.</span><span class="sxs-lookup"><span data-stu-id="75b2a-123">This command creates a test project that uses xUnit as the test library.</span></span> <span data-ttu-id="75b2a-124">Il modello generato configura il Test Runner nel file *PrimeServiceTests.vbproj*:</span><span class="sxs-lookup"><span data-stu-id="75b2a-124">The generated template configures the test runner in the *PrimeServiceTests.vbproj*:</span></span>

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.NET.Test.Sdk" Version="15.3.0-preview-20170628-02" />
  <PackageReference Include="xunit" Version="2.2.0" />
  <PackageReference Include="xunit.runner.visualstudio" Version="2.2.0" />
</ItemGroup>
```

<span data-ttu-id="75b2a-125">Per creare ed eseguire unit test, il progetto di test richiede altri pacchetti.</span><span class="sxs-lookup"><span data-stu-id="75b2a-125">The test project requires other packages to create and run unit tests.</span></span> <span data-ttu-id="75b2a-126">Nel passaggio precedente `dotnet new` ha aggiunto xUnit e il Runner di xUnit.</span><span class="sxs-lookup"><span data-stu-id="75b2a-126">`dotnet new` in the previous step added xUnit and the xUnit runner.</span></span> <span data-ttu-id="75b2a-127">Aggiungere ora la libreria di classi `PrimeService` come un'altra dipendenza del progetto.</span><span class="sxs-lookup"><span data-stu-id="75b2a-127">Now, add the `PrimeService` class library as another dependency to the project.</span></span> <span data-ttu-id="75b2a-128">Usare il comando [`dotnet add reference`](../tools/dotnet-add-reference.md):</span><span class="sxs-lookup"><span data-stu-id="75b2a-128">Use the [`dotnet add reference`](../tools/dotnet-add-reference.md) command:</span></span>

```
dotnet add reference ../PrimeService/PrimeService.vbproj
```

<span data-ttu-id="75b2a-129">È possibile visualizzare l'intero file nel [repository degli esempi](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-vb-using-dotnet-test/PrimeService.Tests/PrimeService.Tests.vbproj) su GitHub.</span><span class="sxs-lookup"><span data-stu-id="75b2a-129">You can see the entire file in the [samples repository](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-vb-using-dotnet-test/PrimeService.Tests/PrimeService.Tests.vbproj) on GitHub.</span></span>

<span data-ttu-id="75b2a-130">Il layout della cartella finale è il seguente:</span><span class="sxs-lookup"><span data-stu-id="75b2a-130">You have the following final folder layout:</span></span>

```
/unit-testing-using-dotnet-test
    unit-testing-using-dotnet-test.sln
    /PrimeService
        Source Files
        PrimeService.vbproj
    /PrimeService.Tests
        Test Source Files
        PrimeServiceTests.vbproj
```

<span data-ttu-id="75b2a-131">Eseguire [`dotnet sln add .\PrimeService.Tests\PrimeService.Tests.vbproj`](../tools/dotnet-sln.md) nella directory *unit-testing-vb-using-dotnet-test*.</span><span class="sxs-lookup"><span data-stu-id="75b2a-131">Execute [`dotnet sln add .\PrimeService.Tests\PrimeService.Tests.vbproj`](../tools/dotnet-sln.md) in the *unit-testing-vb-using-dotnet-test* directory.</span></span> 

## <a name="creating-the-first-test"></a><span data-ttu-id="75b2a-132">Creazione del primo test</span><span class="sxs-lookup"><span data-stu-id="75b2a-132">Creating the first test</span></span>

<span data-ttu-id="75b2a-133">L'approccio di sviluppo basato su test richiede la creazione di un test con esito negativo. È quindi necessario che il test venga superato e che il processo venga ripetuto.</span><span class="sxs-lookup"><span data-stu-id="75b2a-133">The TDD approach calls for writing one failing test, making it pass, then repeating the process.</span></span> <span data-ttu-id="75b2a-134">Rimuovere *UnitTest1.vb* dalla directory *PrimeService.Tests* e creare un nuovo file di Visual Basic denominato *PrimeService_IsPrimeShould.VB*.</span><span class="sxs-lookup"><span data-stu-id="75b2a-134">Remove *UnitTest1.vb* from the *PrimeService.Tests* directory and create a new Visual Basic file named *PrimeService_IsPrimeShould.VB*.</span></span> <span data-ttu-id="75b2a-135">Aggiungere il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="75b2a-135">Add the following code:</span></span>

```vb
Imports Xunit

Namespace PrimeService.Tests
    Public Class PrimeService_IsPrimeShould
        Private _primeService As Prime.Services.PrimeService = New Prime.Services.PrimeService()

        <Fact>
        Sub ReturnFalseGivenValueOf1()
            Dim result As Boolean = _primeService.IsPrime(1)

            Assert.False(result, "1 should not be prime")
        End Sub

    End Class
End Namespace
```

<span data-ttu-id="75b2a-136">L'attributo `<Fact>` indica un metodo di test eseguito dal Test Runner.</span><span class="sxs-lookup"><span data-stu-id="75b2a-136">The `<Fact>` attribute denotes a test method that is run by the test runner.</span></span> <span data-ttu-id="75b2a-137">Da *unit-testing-using-dotnet-test* eseguire [`dotnet test`](../tools/dotnet-test.md) per compilare i test e la libreria di classi, quindi eseguire i test.</span><span class="sxs-lookup"><span data-stu-id="75b2a-137">From the *unit-testing-using-dotnet-test*, execute [`dotnet test`](../tools/dotnet-test.md) to build the tests and the class library and then run the tests.</span></span> <span data-ttu-id="75b2a-138">Il Test Runner di xUnit include il punto d'ingresso del programma per l'esecuzione dei test.</span><span class="sxs-lookup"><span data-stu-id="75b2a-138">The xUnit test runner contains the program entry point to run your tests.</span></span> <span data-ttu-id="75b2a-139">`dotnet test` avvia il Test Runner usando il progetto di unit test creato.</span><span class="sxs-lookup"><span data-stu-id="75b2a-139">`dotnet test` starts the test runner using the unit test project you've created.</span></span>

<span data-ttu-id="75b2a-140">Il test ha esito negativo.</span><span class="sxs-lookup"><span data-stu-id="75b2a-140">Your test fails.</span></span> <span data-ttu-id="75b2a-141">Non è stata ancora creata l'implementazione.</span><span class="sxs-lookup"><span data-stu-id="75b2a-141">You haven't created the implementation yet.</span></span> <span data-ttu-id="75b2a-142">Fare in modo che questo test venga superato scrivendo il codice più semplice e funzionante nella classe `PrimeService`:</span><span class="sxs-lookup"><span data-stu-id="75b2a-142">Make this test by writing the simplest code in the `PrimeService` class that works:</span></span>

```vb
Public Function IsPrime(candidate As Integer) As Boolean
    If candidate = 1 Then
        Return False
    End If
    Throw New NotImplementedException("Please create a test first")
End Function
```

<span data-ttu-id="75b2a-143">Eseguire di nuovo `dotnet test` nella directory *unit-testing-vb-using-dotnet-test*.</span><span class="sxs-lookup"><span data-stu-id="75b2a-143">In the *unit-testing-vb-using-dotnet-test* directory, run `dotnet test` again.</span></span> <span data-ttu-id="75b2a-144">Il comando `dotnet test` esegue prima una compilazione del progetto `PrimeService` e quindi del progetto `PrimeService.Tests`.</span><span class="sxs-lookup"><span data-stu-id="75b2a-144">The `dotnet test` command runs a build for the `PrimeService` project and then for the `PrimeService.Tests` project.</span></span> <span data-ttu-id="75b2a-145">Dopo la compilazione di entrambi i progetti, verrà eseguito il test singolo,</span><span class="sxs-lookup"><span data-stu-id="75b2a-145">After building both projects, it runs this single test.</span></span> <span data-ttu-id="75b2a-146">che viene superato.</span><span class="sxs-lookup"><span data-stu-id="75b2a-146">It passes.</span></span>

## <a name="adding-more-features"></a><span data-ttu-id="75b2a-147">Aggiunta di altre funzionalità</span><span class="sxs-lookup"><span data-stu-id="75b2a-147">Adding more features</span></span>

<span data-ttu-id="75b2a-148">Ora che il test è stato superato, è necessario scriverne altri.</span><span class="sxs-lookup"><span data-stu-id="75b2a-148">Now that you've made one test pass, it's time to write more.</span></span> <span data-ttu-id="75b2a-149">Esistono alcuni altri casi semplici per i numeri primi: 0, -1.</span><span class="sxs-lookup"><span data-stu-id="75b2a-149">There are a few other simple cases for prime numbers: 0, -1.</span></span> <span data-ttu-id="75b2a-150">È possibile aggiungerli come nuovi test, con l'attributo `<Fact>`, ma questa operazione risulta rapidamente noiosa.</span><span class="sxs-lookup"><span data-stu-id="75b2a-150">You could add those cases as new tests with the `<Fact>` attribute, but that quickly becomes tedious.</span></span> <span data-ttu-id="75b2a-151">Sono disponibili altri attributi xUnit che consentono di scrivere una suite di test analoghi.</span><span class="sxs-lookup"><span data-stu-id="75b2a-151">There are other xUnit attributes that enable you to write a suite of similar tests.</span></span>  <span data-ttu-id="75b2a-152">Un attributo `<Theory>` rappresenta una suite di test che eseguono lo stesso codice, ma hanno argomenti di input diversi.</span><span class="sxs-lookup"><span data-stu-id="75b2a-152">A `<Theory>` attribute represents a suite of tests that execute the same code but have different input arguments.</span></span> <span data-ttu-id="75b2a-153">È possibile usare l'attributo `<InlineData>` per specificare i valori per tali input.</span><span class="sxs-lookup"><span data-stu-id="75b2a-153">You can use the `<InlineData>` attribute to specify values for those inputs.</span></span>

<span data-ttu-id="75b2a-154">Anziché creare nuovi test, applicare questi due attributi per creare una singola teoria.</span><span class="sxs-lookup"><span data-stu-id="75b2a-154">Instead of creating new tests, apply these two attributes to create a single theory.</span></span> <span data-ttu-id="75b2a-155">La teoria è un metodo che verifica vari valori minori di due, ovvero il numero primo più piccolo:</span><span class="sxs-lookup"><span data-stu-id="75b2a-155">The theory is a method that tests several values less than two, which is the lowest prime number:</span></span>

[!code-vb[Sample_TestCode](../../../samples/core/getting-started/unit-testing-vb-dotnet-test/PrimeService.Tests/PrimeService_IsPrimeShould.vb?name=Sample_TestCode)]

<span data-ttu-id="75b2a-156">Eseguire `dotnet test`. Due test hanno esito negativo.</span><span class="sxs-lookup"><span data-stu-id="75b2a-156">Run `dotnet test`, and two of these tests fail.</span></span> <span data-ttu-id="75b2a-157">Per assicurare che tutti i test vengano superati, modificare la clausola `if` all'inizio del metodo:</span><span class="sxs-lookup"><span data-stu-id="75b2a-157">To make all of the tests pass, change the `if` clause at the beginning of the method:</span></span>

```vb
if candidate < 2
```

<span data-ttu-id="75b2a-158">Continuare a eseguire l'iterazione aggiungendo altri test, altre teorie e altro codice nella libreria principale.</span><span class="sxs-lookup"><span data-stu-id="75b2a-158">Continue to iterate by adding more tests, more theories, and more code in the main library.</span></span> <span data-ttu-id="75b2a-159">Si ottiene la [versione completa dei test](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-vb-using-dotnet-test/PrimeService.Tests/PrimeService_IsPrimeShould.vb) e l'[implementazione completa della libreria](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-vb-using-dotnet-test/PrimeService/PrimeService.vb).</span><span class="sxs-lookup"><span data-stu-id="75b2a-159">You have the [finished version of the tests](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-vb-using-dotnet-test/PrimeService.Tests/PrimeService_IsPrimeShould.vb) and the [complete implementation of the library](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-vb-using-dotnet-test/PrimeService/PrimeService.vb).</span></span>

<span data-ttu-id="75b2a-160">È stata compilata una piccola libreria e un set di unit test per tale libreria.</span><span class="sxs-lookup"><span data-stu-id="75b2a-160">You've built a small library and a set of unit tests for that library.</span></span> <span data-ttu-id="75b2a-161">La soluzione è stata strutturata in modo che l'aggiunta di nuovi pacchetti e test faccia parte del normale flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="75b2a-161">You've structured the solution so that adding new packages and tests is part of the normal workflow.</span></span> <span data-ttu-id="75b2a-162">La maggior parte del tempo e dell'impegno è dedicata alla soluzione degli obiettivi dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="75b2a-162">You've concentrated most of your time and effort on solving the goals of the application.</span></span>