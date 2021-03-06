---
title: Scelta della versione di .NET Core
description: Informazioni su come .NET Core ricerca e sceglie le versioni runtime per un programma.
author: billwagner
ms.author: wiwagn
ms.date: 06/27/2018
ms.openlocfilehash: 28a76cc17346c40517a21e8dc902bd6c2a84597f
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2018
ms.locfileid: "47233202"
---
# <a name="net-core-version-selection"></a>Scelta della versione di .NET Core

[!INCLUDE [topic-appliesto-net-core-2plus](../../../includes/topic-appliesto-net-core-2plus.md)]

Questo articolo illustra i criteri usati dagli strumenti di .NET Core, dall'SDK e dal Common Language Runtime per selezionare le versioni. Questi criteri consentono di bilanciare tra l'esecuzione di applicazioni con le versioni specificate e la possibilità di aggiornare i computer sia degli sviluppatori che degli utenti finali. Questi criteri consentono le azioni seguenti:

- Distribuzione facile e veloce di .NET Core, inclusi gli aggiornamenti alla sicurezza e all'affidabilità.
- Utilizzo degli strumenti e dei comandi più recenti indipendentemente dal runtime di destinazione.

La selezione della versione si verifica nei seguenti casi:

- Quando si esegue un comando SDK, [l'SDK usa la versione installata più recente](#the-sdk-uses-the-latest-installed-version).
- Quando si compila un assembly, [i moniker del framework di destinazione definiscono le API della fase di compilazione](#target-framework-monikers-define-build-time-apis).
- Quando si esegue un'applicazione .NET Core, [le app che dipendono dal framework di destinazione eseguono il roll forward](#framework-dependent-apps-roll-forward).
- Quando si pubblica un'applicazione autonoma, [le distribuzioni autonome includono il runtime selezionato](#self-contained-deployments-include-the-selected-runtime).

Il resto di questo documento esamina questi quattro scenari.

## <a name="the-sdk-uses-the-latest-installed-version"></a>L'SDK usa la versione installata più recente

I comandi dell'SDK includono `dotnet new` e `dotnet run`. L'interfaccia della riga di comando `dotnet` deve scegliere una versione dell'SDK per ogni comando .NET. Per impostazione predefinita, l'interfaccia della riga di comando .NET Core usa l'SDK più recente installato nel computer, anche se:

* Il progetto è destinato a una versione precedente.
* La versione più recente è una versione di anteprima.

Le app possono usufruire delle funzionalità e dei miglioramenti più recenti dell'SDK anche quando si scelgono come destinazione versioni meno recenti di .NET Core Runtime. È possibile assegnare più versioni di runtime di .NET Core a progetti diversi, usando gli stessi strumenti dell'SDK per tutti i progetti.

In casi rari potrebbe essere necessario usare una versione meno recente dell'SDK. La versione deve essere specificata in un file [*global.json*](../tools/global-json.md). I criteri dell'"uso della versione più recente" indicano che si usa solo il file *global.json* per specificare una versione di .NET Core SDK antecedente a quella installata, che è la più recente.

Il file *global.json* può essere memorizzato in un punto qualsiasi della gerarchia di file. L'interfaccia della riga di comando cerca a ritroso il primo file *global.json* che trova partendo dalla directory di progetto. Si controlla a quali progetti si applica un determinato file *global.json* in base alla sua posizione nel file system. L'interfaccia della riga di comando .NET cerca ripetutamente un file *global.json* esplorando il percorso a ritroso partendo dalla directory di lavoro corrente. Il primo file *global.json* trovato specifica la versione usata. Se tale versione è installata, sarà questa a essere usata. Se l'SDK specificato nel file *global.json* non viene trovato, l'interfaccia della riga di comando .NET esegue il roll forward all'SDK installato più recente. Il roll-forward è analogo al comportamento predefinito quando non viene individuato alcun file *global.json*.

L'esempio seguente mostra la sintassi del file *global.json*:

``` json
{
  "sdk": {
    "version": "2.0.0"
  }
}
```

Il processo per la selezione di una versione dell'SDK è il seguente:

1. `dotnet` cerca ripetutamente un file *global.json* risalendo il percorso a partire dalla directory di lavoro corrente.
1. `dotnet` usa l'SDK specificato nel file *global.json* trovato.
1. `dotnet` usa l'SDK installato più recente se non viene trovato alcun file *global.json*.

Altre informazioni sulla selezione di una versione dell'SDK sono disponibili nella sezione sulle [regole di corrispondenza](../tools/global-json.md#matching-rules) nell'articolo relativo a *global.json*.

## <a name="target-framework-monikers-define-build-time-apis"></a>Definizione delle API della fase di compilazione tramite i moniker del framework di destinazione

Il progetto viene compilato con le API definite in un **moniker del framework di destinazione** (TFM). Il [framework di destinazione](../../standard/frameworks.md) deve essere specificato nel file di progetto. Impostare l'elemento `TargetFramework` nel file di progetto come illustrato nell'esempio seguente:

``` xml
<TargetFramework>netcoreapp2.0</TargetFramework>
```

È possibile compilare il progetto usando più TFM. L'impostazione di più framework di destinazione è una pratica più comune per le librerie, ma può essere usata anche con le applicazioni. Occorre specificare una proprietà `TargetFrameworks` (plurale di `TargetFramework`). I framework di destinazione sono delimitati da punto e virgola come illustrato nell'esempio seguente:

``` xml
<TargetFrameworks>netcoreapp2.0;net47</TargetFrameworks>
```

Una determinata versione di SDK supporta un set fisso di framework, inclusivo del framework di destinazione del runtime con cui viene offerto. .NET Core 2.0 SDK, ad esempio, include il runtime .NET Core 2.0, che è un'implementazione del framework di destinazione `netcoreapp2.0`. .NET Core 2.0 SDK supporta `netcoreapp1.0`, `netcoreapp1.1` e `netcoreapp2.0` ma non `netcoreapp2.1` (o versione superiore). Occorre installare .NET Core 2.1 SDK per compilare `netcoreapp2.1`.

I framework di destinazione .NET Standard sono anche limitati al framework di destinazione del runtime fornito con SDK. .NET Core 2.0 SDK è limitato a `netstandard2.0`.

## <a name="framework-dependent-apps-roll-forward"></a>Roll forward delle app dipendenti dal framework

Si esegue un'applicazione dall'origine con [`dotnet run`](../tools/dotnet-run.md). `dotnet run` compila ed esegue un'applicazione. Il file eseguibile `dotnet` è l'**host** per l'applicazione negli ambienti di sviluppo.

L'host sceglie la versione di patch più recente installata nel computer. Se ad esempio è stato specificato `netcoreapp2.0` nel file di progetto e `2.0.4` è il runtime .NET più recente installato, viene usato il runtime `2.0.4`.

Se non viene trovata alcuna versione `2.0.*` accettabile, viene usata una nuova versione `2.*`. Se ad esempio è stato specificato `netcoreapp2.0` ed è installata solo la versione `2.1.0`, l'applicazione viene eseguita usando il runtime `2.1.0`. Questo comportamento è detto "roll forward della versione secondaria". Le versioni minori non verranno prese in considerazione. Se non è installato alcun runtime accettabile, l'applicazione non viene eseguita.

Alcuni esempi di utilizzo dimostrano il comportamento:

- È richiesta la versione 2.0.4. 2.0.5 è la versione di patch più recente installata. Viene usata la versione 2.0.5.
- È richiesta la versione 2.0.4. Non è installata alcuna versione 2.0.*. 1.1.1 è il runtime più recente installato. Viene visualizzato un messaggio di errore.
- È richiesta la versione 2.0.4. 2.0.0 è la versione più recente installata. Viene visualizzato un messaggio di errore.
- È richiesta la versione 2.0.4. Non è installata alcuna versione 2.0.*. 2.2.2 è la versione di runtime 2.x più recente installata. Viene usata la versione 2.2.2.
- È richiesta la versione 2.0.4. Non è installata alcuna versione 2.x. Viene installata la versione 3.0.0 (non una versione attualmente disponibile). Viene visualizzato un messaggio di errore.

Il roll forward della versione secondaria presenta un effetto collaterale che può interessare gli utenti finali. Si consideri lo scenario seguente:

- È richiesta la versione 2.0.4. Non è installata alcuna versione 2.0.*. Viene installata la versione 2.2.2. Viene usata la versione 2.2.2.
- In un momento successivo viene installata la versione 2.0.5. Per i successivi avvii dell'applicazione verrà usata la versione 2.0.5, non la 2.2.2. La patch più recente della versione secondaria richiesta viene preferita a una versione secondaria più recente.
- È possibile che le versioni 2.0.5 e 2.2.2 si comportino diversamente, in particolare per gli scenari come la serializzazione dei dati binari.

## <a name="self-contained-deployments-include-the-selected-runtime"></a>Distribuzioni autonome con runtime selezionato

È possibile pubblicare un'applicazione come [**distribuzione autonoma**](../deploying/index.md#self-contained-deployments-scd). Questo approccio raggruppa il runtime e le librerie di .NET Core con l'applicazione. Le distribuzioni autonome non hanno dipendenze dagli ambienti di runtime. La scelta della versione di runtime avviene al momento della pubblicazione non in base di esecuzione.

Il processo di pubblicazione seleziona la versione di patch più recente della famiglia di runtime specificata. Il comando `dotnet publish` ad esempio selezionerà .NET Core 2.0.4 se è la versione di patch più recente nella famiglia di runtime .NET Core 2.0. Il framework di destinazione (incluse le patch di sicurezza più recenti) viene fornito con l'applicazione.

Se la versione minima specificata per un'applicazione non viene soddisfatta, si verifica un errore. `dotnet publish` esegue l'associazione alla versione di patch di runtime più recente (nella famiglia di versioni principale.secondaria specificata). `dotnet publish` non supporta la semantica del roll forward di `dotnet run`. Per altre informazioni su patch e distribuzioni autonome, vedere l'articolo sulla [selezione della patch di runtime](../deploying/runtime-patch-selection.md) nella distribuzione di applicazioni .NET Core.

Le distribuzioni autonome potrebbero richiedere una versione di patch specifica. È possibile sostituire la versione di patch di runtime minima (per versioni superiori o inferiori) nel file di progetto, come illustrato nell'esempio seguente:

``` xml
<RuntimeFrameworkVersion>2.0.4</RuntimeFrameworkVersion>
```

L'elemento `RuntimeFrameworkVersion` sostituisce i criteri di versione predefiniti. Per le distribuzioni autonome, l'elemento `RuntimeFrameworkVersion` specifica l'*esatta* versione del framework di runtime. Per le applicazioni dipendenti dal framework, l'elemento `RuntimeFrameworkVersion` specifica la versione di framework di runtime *minima* richiesta.
