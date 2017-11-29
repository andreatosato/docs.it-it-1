---
title: "Testing unità di librerie F# in .NET Core usando il test dotnet e xUnit"
description: Informazioni sui concetti relativi agli unit test in .NET Core tramite un'esperienza interattiva per la creazione passo-passo di una soluzione di esempio con test dotnet e xUnit.
author: billwagner
ms.author: wiwagn
ms.date: 08/30/2017
ms.topic: article
dev_langs: fsharp
ms.prod: .net-core
ms.openlocfilehash: b4612b2b1a218f2bd126240db564258e07ba5231
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="unit-testing-f-libraries-in-net-core-using-dotnet-test-and-xunit"></a><span data-ttu-id="8c9bd-103">Testing unità di librerie F# in .NET Core usando il test dotnet e xUnit</span><span class="sxs-lookup"><span data-stu-id="8c9bd-103">Unit testing F# libraries in .NET Core using dotnet test and xUnit</span></span>

<span data-ttu-id="8c9bd-104">In questa esercitazione viene illustrata un'esperienza interattiva di compilazione passo passo di una soluzione di esempio finalizzata all'apprendimento dei concetti base del testing unità.</span><span class="sxs-lookup"><span data-stu-id="8c9bd-104">This tutorial takes you through an interactive experience building a sample solution step-by-step to learn unit testing concepts.</span></span> <span data-ttu-id="8c9bd-105">Se si preferisce seguire l'esercitazione usando una soluzione preesistente, [visualizzare o scaricare il codice di esempio](https://github.com/dotnet/docs/tree/master/samples/core/getting-started/unit-testing-with-fsharp/) prima di iniziare.</span><span class="sxs-lookup"><span data-stu-id="8c9bd-105">If you prefer to follow the tutorial using a pre-built solution, [view or download the sample code](https://github.com/dotnet/docs/tree/master/samples/core/getting-started/unit-testing-with-fsharp/) before you begin.</span></span> <span data-ttu-id="8c9bd-106">Per istruzioni sul download, vedere [Esempi ed esercitazioni](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="8c9bd-106">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

## <a name="creating-the-source-project"></a><span data-ttu-id="8c9bd-107">Creazione del progetto di origine</span><span class="sxs-lookup"><span data-stu-id="8c9bd-107">Creating the source project</span></span>

<span data-ttu-id="8c9bd-108">Aprire una finestra della shell.</span><span class="sxs-lookup"><span data-stu-id="8c9bd-108">Open a shell window.</span></span> <span data-ttu-id="8c9bd-109">Creare una directory denominata *unit-testing-with-fsharp* in cui archiviare la soluzione.</span><span class="sxs-lookup"><span data-stu-id="8c9bd-109">Create a directory called *unit-testing-with-fsharp* to hold the solution.</span></span>
<span data-ttu-id="8c9bd-110">In questa nuova directory eseguire [`dotnet new sln`](../tools/dotnet-new.md) per creare una nuova soluzione.</span><span class="sxs-lookup"><span data-stu-id="8c9bd-110">Inside this new directory, run [`dotnet new sln`](../tools/dotnet-new.md) to create a new solution.</span></span> <span data-ttu-id="8c9bd-111">Questo rende più semplice gestire sia la libreria di classi che il progetto di unit test.</span><span class="sxs-lookup"><span data-stu-id="8c9bd-111">This makes it easier to manage both the class library and the unit test project.</span></span>
<span data-ttu-id="8c9bd-112">All'interno della directory della soluzione creare una directory *MathService*.</span><span class="sxs-lookup"><span data-stu-id="8c9bd-112">Inside the solution directory, create a *MathService* directory.</span></span> <span data-ttu-id="8c9bd-113">La struttura della directory e dei file fino a questo momento è la seguente:</span><span class="sxs-lookup"><span data-stu-id="8c9bd-113">The directory and file structure thus far is shown below:</span></span>

```
/unit-testing-with-fsharp
    unit-testing-with-fsharp.sln
    /MathService
```

<span data-ttu-id="8c9bd-114">Impostare *MathService* come directory corrente ed eseguire [`dotnet new classlib -lang F#`](../tools/dotnet-new.md) per creare il progetto di origine.</span><span class="sxs-lookup"><span data-stu-id="8c9bd-114">Make *MathService* the current directory and run [`dotnet new classlib -lang F#`](../tools/dotnet-new.md) to create the source project.</span></span>  <span data-ttu-id="8c9bd-115">Per usare lo sviluppo basato su test (TDD) si creerà un'implementazione non funzionante del servizio matematico:</span><span class="sxs-lookup"><span data-stu-id="8c9bd-115">To use test-driven development (TDD), you'll create a failing implementation of the math service:</span></span>

```fsharp
module MyMath =
    let sumOfSquares xs = raise (System.NotImplementedException("You haven't written a test yet!"))
```

<span data-ttu-id="8c9bd-116">Tornare alla directory *unit-test-con-fsharp*.</span><span class="sxs-lookup"><span data-stu-id="8c9bd-116">Change the directory back to the *unit-testing-with-fsharp* directory.</span></span> <span data-ttu-id="8c9bd-117">Eseguire [`dotnet sln add .\MathService\MathService.fsproj`](../tools/dotnet-sln.md) per aggiungere il progetto di libreria di classi alla soluzione.</span><span class="sxs-lookup"><span data-stu-id="8c9bd-117">Run [`dotnet sln add .\MathService\MathService.fsproj`](../tools/dotnet-sln.md) to add the class library project to the solution.</span></span>

## <a name="creating-the-test-project"></a><span data-ttu-id="8c9bd-118">Creazione del progetto di test</span><span class="sxs-lookup"><span data-stu-id="8c9bd-118">Creating the test project</span></span>

<span data-ttu-id="8c9bd-119">Creare quindi la directory *MathService.Tests*.</span><span class="sxs-lookup"><span data-stu-id="8c9bd-119">Next, create the *MathService.Tests* directory.</span></span> <span data-ttu-id="8c9bd-120">Di seguito è illustrata la struttura di directory:</span><span class="sxs-lookup"><span data-stu-id="8c9bd-120">The following outline shows the directory structure:</span></span>

```
/unit-testing-with-fsharp
    unit-testing-with-fsharp.sln
    /MathService
        Source Files
        MathService.fsproj
    /MathService.Tests
```

<span data-ttu-id="8c9bd-121">Impostare *MathService.Tests* come directory corrente e creare un nuovo progetto usando [`dotnet new xunit -lang F#`](../tools/dotnet-new.md).</span><span class="sxs-lookup"><span data-stu-id="8c9bd-121">Make the *MathService.Tests* directory the current directory and create a new project using [`dotnet new xunit -lang F#`](../tools/dotnet-new.md).</span></span> <span data-ttu-id="8c9bd-122">In questo modo viene creato un progetto di test che usa xUnit come libreria di test.</span><span class="sxs-lookup"><span data-stu-id="8c9bd-122">This creates a test project that uses xUnit as the test library.</span></span> <span data-ttu-id="8c9bd-123">Il modello generato configura il Test Runner nel file *MathServiceTests.fsproj*:</span><span class="sxs-lookup"><span data-stu-id="8c9bd-123">The generated template configures the test runner in the *MathServiceTests.fsproj*:</span></span>

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.NET.Test.Sdk" Version="15.3.0-preview-20170628-02" />
  <PackageReference Include="xunit" Version="2.2.0" />
  <PackageReference Include="xunit.runner.visualstudio" Version="2.2.0" />
</ItemGroup>
```

<span data-ttu-id="8c9bd-124">Per creare ed eseguire unit test, il progetto di test richiede altri pacchetti.</span><span class="sxs-lookup"><span data-stu-id="8c9bd-124">The test project requires other packages to create and run unit tests.</span></span> <span data-ttu-id="8c9bd-125">Nel passaggio precedente `dotnet new` ha aggiunto xUnit e il Runner di xUnit.</span><span class="sxs-lookup"><span data-stu-id="8c9bd-125">`dotnet new` in the previous step added xUnit and the xUnit runner.</span></span> <span data-ttu-id="8c9bd-126">Aggiungere ora la libreria di classi `MathService` come un'altra dipendenza del progetto.</span><span class="sxs-lookup"><span data-stu-id="8c9bd-126">Now, add the `MathService` class library as another dependency to the project.</span></span> <span data-ttu-id="8c9bd-127">Usare il comando [`dotnet add reference`](../tools/dotnet-add-reference.md):</span><span class="sxs-lookup"><span data-stu-id="8c9bd-127">Use the [`dotnet add reference`](../tools/dotnet-add-reference.md) command:</span></span>

```
dotnet add reference ../MathService/MathService.fsproj
```

<span data-ttu-id="8c9bd-128">È possibile visualizzare l'intero file nel [repository degli esempi](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-with-fsharp/MathService.Tests/MathService.Tests.fsproj) su GitHub.</span><span class="sxs-lookup"><span data-stu-id="8c9bd-128">You can see the entire file in the [samples repository](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-with-fsharp/MathService.Tests/MathService.Tests.fsproj) on GitHub.</span></span>

<span data-ttu-id="8c9bd-129">Il layout della soluzione finale è il seguente:</span><span class="sxs-lookup"><span data-stu-id="8c9bd-129">You have the following final solution layout:</span></span>

```
/unit-testing-with-fsharp
    unit-testing-with-fsharp.sln
    /MathService
        Source Files
        MathService.fsproj
    /MathService.Tests
        Test Source Files
        MathServiceTests.fsproj
```

<span data-ttu-id="8c9bd-130">Eseguire [`dotnet sln add .\MathService.Tests\MathService.Tests.fsproj`](../tools/dotnet-sln.md) nella directory *unit-testing-with-fsharp*.</span><span class="sxs-lookup"><span data-stu-id="8c9bd-130">Execute [`dotnet sln add .\MathService.Tests\MathService.Tests.fsproj`](../tools/dotnet-sln.md) in the *unit-testing-with-fsharp* directory.</span></span> 

## <a name="creating-the-first-test"></a><span data-ttu-id="8c9bd-131">Creazione del primo test</span><span class="sxs-lookup"><span data-stu-id="8c9bd-131">Creating the first test</span></span>

<span data-ttu-id="8c9bd-132">L'approccio di sviluppo basato su test richiede la creazione di un test con esito negativo. È quindi necessario che il test venga superato e che il processo venga ripetuto.</span><span class="sxs-lookup"><span data-stu-id="8c9bd-132">The TDD approach calls for writing one failing test, making it pass, then repeating the process.</span></span> <span data-ttu-id="8c9bd-133">Aprire *Tests.fs* e aggiungere il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="8c9bd-133">Open *Tests.fs* and add the following code:</span></span>

```fsharp
[<Fact>]
let ``My test`` () =
    Assert.True(true)

[<Fact>]
let ``Fail every time`` () = Assert.True(false)
```

<span data-ttu-id="8c9bd-134">L'attributo `[<Fact>]` indica un metodo di test eseguito dal Test Runner.</span><span class="sxs-lookup"><span data-stu-id="8c9bd-134">The `[<Fact>]` attribute denotes a test method that is run by the test runner.</span></span> <span data-ttu-id="8c9bd-135">Da *unit-test-con-fsharp* eseguire [`dotnet test`](../tools/dotnet-test.md) per compilare i test e la libreria di classi, quindi eseguire i test.</span><span class="sxs-lookup"><span data-stu-id="8c9bd-135">From the *unit-testing-with-fsharp*, execute [`dotnet test`](../tools/dotnet-test.md) to build the tests and the class library and then run the tests.</span></span> <span data-ttu-id="8c9bd-136">Il Test Runner di xUnit include il punto d'ingresso del programma per l'esecuzione dei test.</span><span class="sxs-lookup"><span data-stu-id="8c9bd-136">The xUnit test runner contains the program entry point to run your tests.</span></span> <span data-ttu-id="8c9bd-137">`dotnet test` avvia il Test Runner usando il progetto di unit test creato.</span><span class="sxs-lookup"><span data-stu-id="8c9bd-137">`dotnet test` starts the test runner using the unit test project you've created.</span></span>

<span data-ttu-id="8c9bd-138">Questi due test mostrano i test più semplici superati e non superati.</span><span class="sxs-lookup"><span data-stu-id="8c9bd-138">These two tests show the most basic passing and failing tests.</span></span> <span data-ttu-id="8c9bd-139">`My test` viene superato e `Fail every time` non viene superato.</span><span class="sxs-lookup"><span data-stu-id="8c9bd-139">`My test` passes, and `Fail every time` fails.</span></span> <span data-ttu-id="8c9bd-140">A questo punto, creare un test per il metodo `sumOfSquares`.</span><span class="sxs-lookup"><span data-stu-id="8c9bd-140">Now, create a test for the `sumOfSquares` method.</span></span> <span data-ttu-id="8c9bd-141">Il metodo `sumOfSquares` restituisce la somma dei quadrati di tutti i valori interi dispari che fanno parte della sequenza di input.</span><span class="sxs-lookup"><span data-stu-id="8c9bd-141">The `sumOfSquares` method returns the sum of the squares of all odd integer values that are part of the input sequence.</span></span> <span data-ttu-id="8c9bd-142">Anziché tentare di scrivere tutte queste funzioni in una sola volta, è possibile creare in modo iterativo test per la convalida della funzionalità.</span><span class="sxs-lookup"><span data-stu-id="8c9bd-142">Rather than trying to write all of those functions at once, you can iteratively create tests that validate the functionality.</span></span> <span data-ttu-id="8c9bd-143">Fare in modo che ogni test venga superato significa creare le funzionalità necessarie per il metodo.</span><span class="sxs-lookup"><span data-stu-id="8c9bd-143">Making each test pass means creating the necessary functionality for the method.</span></span>

<span data-ttu-id="8c9bd-144">Il test più semplice che si può scrivere consiste nel chiamare `sumOfSquares` con tutti i numeri pari. In questo caso il risultato dovrebbe essere una sequenza vuota di numeri interi.</span><span class="sxs-lookup"><span data-stu-id="8c9bd-144">The simplest test we can write is to call `sumOfSquares` with all even numbers, where the result should be an empty sequence of integers.</span></span>  <span data-ttu-id="8c9bd-145">Ecco questo test:</span><span class="sxs-lookup"><span data-stu-id="8c9bd-145">Here's that test:</span></span>

```fsharp
[<Fact>]
let ``Sum of evens returns empty collection`` () =
    let expected = Seq.empty<int>
    let actual = MyMath.sumOfSquares [2; 4; 6; 8; 10]
    Assert.Equal<Collections.Generic.IEnumerable<int>>(expected, actual)
```

<span data-ttu-id="8c9bd-146">Il test ha esito negativo.</span><span class="sxs-lookup"><span data-stu-id="8c9bd-146">Your test fails.</span></span> <span data-ttu-id="8c9bd-147">Non è stata ancora creata l'implementazione.</span><span class="sxs-lookup"><span data-stu-id="8c9bd-147">You haven't created the implementation yet.</span></span> <span data-ttu-id="8c9bd-148">Fare in modo che questo test venga superato scrivendo il codice più semplice e funzionante nella classe `MathService`:</span><span class="sxs-lookup"><span data-stu-id="8c9bd-148">Make this test by writing the simplest code in the `MathService` class that works:</span></span>

```csharp
let sumOfSquares xs =
    Seq.empty<int>
```

<span data-ttu-id="8c9bd-149">Nella directory *unit-test-con-fsharp* eseguire di nuovo `dotnet test`.</span><span class="sxs-lookup"><span data-stu-id="8c9bd-149">In the *unit-testing-with-fsharp* directory, run `dotnet test` again.</span></span> <span data-ttu-id="8c9bd-150">Il comando `dotnet test` esegue prima una compilazione del progetto `MathService` e quindi del progetto `MathService.Tests`.</span><span class="sxs-lookup"><span data-stu-id="8c9bd-150">The `dotnet test` command runs a build for the `MathService` project and then for the `MathService.Tests` project.</span></span> <span data-ttu-id="8c9bd-151">Dopo la compilazione di entrambi i progetti, verrà eseguito il test singolo,</span><span class="sxs-lookup"><span data-stu-id="8c9bd-151">After building both projects, it runs this single test.</span></span> <span data-ttu-id="8c9bd-152">che viene superato.</span><span class="sxs-lookup"><span data-stu-id="8c9bd-152">It passes.</span></span>

## <a name="completing-the-requirements"></a><span data-ttu-id="8c9bd-153">Completamento dei requisiti</span><span class="sxs-lookup"><span data-stu-id="8c9bd-153">Completing the requirements</span></span>

<span data-ttu-id="8c9bd-154">Ora che il test è stato superato, è necessario scriverne altri.</span><span class="sxs-lookup"><span data-stu-id="8c9bd-154">Now that you've made one test pass, it's time to write more.</span></span> <span data-ttu-id="8c9bd-155">Il prossimo test case semplice opera su una sequenza in cui l'unico numero dispari è `1`.</span><span class="sxs-lookup"><span data-stu-id="8c9bd-155">The next simple case works with a sequence whose only odd number is `1`.</span></span> <span data-ttu-id="8c9bd-156">Il numero 1 è più semplice perché il quadrato di 1 è 1.</span><span class="sxs-lookup"><span data-stu-id="8c9bd-156">The number 1 is easier because the square of 1 is 1.</span></span> <span data-ttu-id="8c9bd-157">Ecco questo test:</span><span class="sxs-lookup"><span data-stu-id="8c9bd-157">Here's that next test:</span></span>

```fsharp
[<Fact>]
let ``Sum of sequences of Ones and Evens`` () =
    let expected = [1; 1; 1; 1]
    let actual = MyMath.sumOfSquares [2; 1; 4; 1; 6; 1; 8; 1; 10]
    Assert.Equal<Collections.Generic.IEnumerable<int>>(expected, actual)
```

<span data-ttu-id="8c9bd-158">L'esecuzione di `dotnet test` esegue i test e mostra che il nuovo test non viene superato.</span><span class="sxs-lookup"><span data-stu-id="8c9bd-158">Executing `dotnet test` runs your tests and shows you that the new test fails.</span></span> <span data-ttu-id="8c9bd-159">A questo punto, aggiornare il metodo `sumOfSquares` per gestire il nuovo test.</span><span class="sxs-lookup"><span data-stu-id="8c9bd-159">Now, update the `sumOfSquares` method to handle this new test.</span></span> <span data-ttu-id="8c9bd-160">Filtrare tutti i numeri pari fuori sequenza per fare in modo che il test venga superato.</span><span class="sxs-lookup"><span data-stu-id="8c9bd-160">You filter all the even numbers out of the sequence to make this test pass.</span></span> <span data-ttu-id="8c9bd-161">È possibile farlo scrivendo una breve funzione di filtro e usando `Seq.filter`:</span><span class="sxs-lookup"><span data-stu-id="8c9bd-161">You can do that by writing a small filter function and using `Seq.filter`:</span></span>

```fsharp
let private isOdd x = x % 2 <> 0

let sumOfSquares xs =
    xs
    |> Seq.filter isOdd
```

<span data-ttu-id="8c9bd-162">Manca un altro passaggio: elevare al quadrato ciascuno dei numeri di dispari.</span><span class="sxs-lookup"><span data-stu-id="8c9bd-162">There's one more step to go: square each of the odd numbers.</span></span> <span data-ttu-id="8c9bd-163">Per iniziare, scrivere un nuovo test:</span><span class="sxs-lookup"><span data-stu-id="8c9bd-163">Start by writing a new test:</span></span>

```fsharp
[<Fact>]
let ``SquaresOfOdds works`` () =
    let expected = [1; 9; 25; 49; 81]
    let actual = MyMath.sumOfSquares [1; 2; 3; 4; 5; 6; 7; 8; 9; 10]
    Assert.Equal(expected, actual)
```

<span data-ttu-id="8c9bd-164">È possibile correggere il test tramite il piping della sequenza filtrata attraverso un'operazione di mapping per calcolare il quadrato di ogni numero dispari:</span><span class="sxs-lookup"><span data-stu-id="8c9bd-164">You can fix the test by piping the filtered sequence through a map operation to compute the square of each odd number:</span></span>

```fsharp
let private square x = x * x
let private isOdd x = x % 2 <> 0

let sumOfSquares xs = 
    xs 
    |> Seq.filter isOdd 
    |> Seq.map square
```

<span data-ttu-id="8c9bd-165">È stata compilata una piccola libreria e un set di unit test per tale libreria.</span><span class="sxs-lookup"><span data-stu-id="8c9bd-165">You've built a small library and a set of unit tests for that library.</span></span> <span data-ttu-id="8c9bd-166">La soluzione è stata strutturata in modo che l'aggiunta di nuovi pacchetti e test faccia parte del normale flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="8c9bd-166">You've structured the solution so that adding new packages and tests is part of the normal workflow.</span></span> <span data-ttu-id="8c9bd-167">La maggior parte del tempo e dell'impegno è dedicata alla soluzione degli obiettivi dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="8c9bd-167">You've concentrated most of your time and effort on solving the goals of the application.</span></span>