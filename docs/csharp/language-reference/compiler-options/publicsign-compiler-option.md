---
title: -publicsign (opzioni del compilatore C#)
ms.date: 05/15/2018
f1_keywords:
- /publicsign
helpviewer_keywords:
- -publicsign compiler option [C#]
- publicsign compiler option [C#]
- /publicsign compiler option [C#]
ms.openlocfilehash: ec25f9c1f2ef943db41bcfa20c8efd1d05866acd
ms.sourcegitcommit: 77d9a94dac4c05827ed0663d95e0f9ad35d6682e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/24/2018
ms.locfileid: "34472824"
---
# <a name="-publicsign-c-compiler-options"></a><span data-ttu-id="d8baf-102">-publicsign (opzioni del compilatore C#)</span><span class="sxs-lookup"><span data-stu-id="d8baf-102">-publicsign (C# Compiler Options)</span></span>

<span data-ttu-id="d8baf-103">Questa opzione indica al compilatore di applicare una chiave pubblica ma non firma effettivamente l'assembly.</span><span class="sxs-lookup"><span data-stu-id="d8baf-103">This option causes the compiler to apply a public key but does not actually sign the assembly.</span></span> <span data-ttu-id="d8baf-104">L'opzione **-publicsign** imposta anche un bit nell'assembly che indica al runtime che il file è effettivamente firmato.</span><span class="sxs-lookup"><span data-stu-id="d8baf-104">The **-publicsign** option also sets a bit in the assembly that tells the runtime that the file is actually signed.</span></span>

## <a name="syntax"></a><span data-ttu-id="d8baf-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d8baf-105">Syntax</span></span>

```console
-publicsign
```

## <a name="arguments"></a><span data-ttu-id="d8baf-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="d8baf-106">Arguments</span></span>

<span data-ttu-id="d8baf-107">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="d8baf-107">None.</span></span>

## <a name="remarks"></a><span data-ttu-id="d8baf-108">Note</span><span class="sxs-lookup"><span data-stu-id="d8baf-108">Remarks</span></span>

<span data-ttu-id="d8baf-109">L'opzione **-publicsign** richiede l'uso di [-keyfile](keyfile-compiler-option.md) o [-keycontainer](keycontainer-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="d8baf-109">The **-publicsign** option requires the use of the [-keyfile](keyfile-compiler-option.md) or [-keycontainer](keycontainer-compiler-option.md).</span></span> <span data-ttu-id="d8baf-110">Le opzioni **keyfile** o **keycontainer** specificano la chiave pubblica.</span><span class="sxs-lookup"><span data-stu-id="d8baf-110">The **keyfile** or **keycontainer** options specify the public key.</span></span>

<span data-ttu-id="d8baf-111">Le opzioni **-publicsign** e **-delaysign** si escludono a vicenda.</span><span class="sxs-lookup"><span data-stu-id="d8baf-111">The **-publicsign** and **-delaysign** options are mutually exclusive.</span></span>

<span data-ttu-id="d8baf-112">Talvolta denominata "firma falsa" o "firma OSS", la firma pubblica include la chiave pubblica in un assembly di output e imposta il flag "firmato", ma non firma effettivamente l'assembly con una chiave privata.</span><span class="sxs-lookup"><span data-stu-id="d8baf-112">Sometimes called "fake sign" or "OSS sign", public signing includes the public key in an output assembly and sets the "signed" flag, but doesn't actually sign the assembly with a private key.</span></span> <span data-ttu-id="d8baf-113">Ciò è utile per progetti open source in cui le persone devono poter compilare assembly compatibili con gli assembly rilasciati con "firma completa", ma non hanno accesso alla chiave privata usata per firmare gli assembly.</span><span class="sxs-lookup"><span data-stu-id="d8baf-113">This is useful for open source projects where people want to build assemblies which are compatible with the released "fully signed" assemblies, but don't have access to the private key used to sign the assemblies.</span></span> <span data-ttu-id="d8baf-114">Dato che praticamente nessun consumer ha effettivamente la necessità di verificare se l'assembly è firmato completamente, questi assembly compilati pubblicamente sono utilizzabili in quasi tutti gli scenari in cui verrebbe usato un assembly con firma completa.</span><span class="sxs-lookup"><span data-stu-id="d8baf-114">Since almost no consumers actually need to check if the assembly is fully signed, these publicly built assemblies are useable in almost every scenario where the fully signed one would be used.</span></span>

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="d8baf-115">Per impostare l'opzione del compilatore nell'ambiente di sviluppo di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="d8baf-115">To set this compiler option in the Visual Studio development environment</span></span>

1. <span data-ttu-id="d8baf-116">Aprire la pagina **Proprietà** del progetto.</span><span class="sxs-lookup"><span data-stu-id="d8baf-116">Open the **Properties** page for the project.</span></span>
1. <span data-ttu-id="d8baf-117">Modificare la proprietà **Solo firma ritardata**.</span><span class="sxs-lookup"><span data-stu-id="d8baf-117">Modify the **Delay sign only** property.</span></span>

## <a name="see-also"></a><span data-ttu-id="d8baf-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d8baf-118">See Also</span></span>
 [<span data-ttu-id="d8baf-119">Opzione -delaysign del compilatore C#</span><span class="sxs-lookup"><span data-stu-id="d8baf-119">C# Compiler -delaysign option</span></span>](delaysign-compiler-option.md)  
 [<span data-ttu-id="d8baf-120">Opzione - keyfile del compilatore C#</span><span class="sxs-lookup"><span data-stu-id="d8baf-120">C# Compiler -keyfile option</span></span>](keyfile-compiler-option.md)  
 [<span data-ttu-id="d8baf-121">Opzione -keycontainer del compilatore C#</span><span class="sxs-lookup"><span data-stu-id="d8baf-121">C# Compiler -keycontainer option</span></span>](keycontainer-compiler-option.md)  
 [<span data-ttu-id="d8baf-122">Opzioni del compilatore C#</span><span class="sxs-lookup"><span data-stu-id="d8baf-122">C# Compiler Options</span></span>](index.md)  
 [<span data-ttu-id="d8baf-123">Gestione delle proprietà di progetti e soluzioni</span><span class="sxs-lookup"><span data-stu-id="d8baf-123">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)