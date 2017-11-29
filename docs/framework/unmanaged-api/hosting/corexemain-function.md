---
title: Funzione _CorExeMain
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: _CorExeMain
api_location:
- mscoree.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
api_type: DLLExport
f1_keywords: _CorExeMain
helpviewer_keywords: _CorExeMain function [.NET Framework hosting]
ms.assetid: 898f76e2-16f4-4a63-b7d9-dad2d3824d8a
topic_type: apiref
caps.latest.revision: "17"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 8c341d578a45d72804d9ac33e2aefe513fd33922
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="corexemain-function"></a><span data-ttu-id="18704-102">Funzione _CorExeMain</span><span class="sxs-lookup"><span data-stu-id="18704-102">_CorExeMain Function</span></span>
<span data-ttu-id="18704-103">Consente di inizializzare common language runtime (CLR), individua il punto di ingresso gestito nell'intestazione CLR dell'assembly eseguibile e inizia l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="18704-103">Initializes the common language runtime (CLR), locates the managed entry point in the executable assembly's CLR header, and begins execution.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18704-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="18704-104">Syntax</span></span>  
  
```  
__int32 STDMETHODCALLTYPE _CorExeMain ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="18704-105">Note</span><span class="sxs-lookup"><span data-stu-id="18704-105">Remarks</span></span>  
 <span data-ttu-id="18704-106">Questa funzione viene chiamata dal caricatore in processi creati dagli assembly eseguibile gestito.</span><span class="sxs-lookup"><span data-stu-id="18704-106">This function is called by the loader in processes created from managed executable assemblies.</span></span> <span data-ttu-id="18704-107">Per gli assembly DLL, il caricatore chiama la [CorDllMain](../../../../docs/framework/unmanaged-api/hosting/cordllmain-function.md) funzione alternativa.</span><span class="sxs-lookup"><span data-stu-id="18704-107">For DLL assemblies, the loader calls the [_CorDllMain](../../../../docs/framework/unmanaged-api/hosting/cordllmain-function.md) function instead.</span></span>  
  
 <span data-ttu-id="18704-108">Il caricatore del sistema operativo chiama questo metodo indipendentemente dal punto di ingresso specificato nel file di immagine.</span><span class="sxs-lookup"><span data-stu-id="18704-108">The operating system loader calls this method regardless of the entry point specified in the image file.</span></span>  
  
 <span data-ttu-id="18704-109">In Windows 98, Windows ME, Windows NT e Windows 2000, la `_CorExeMain` funzione viene chiamata indirettamente tramite una correzione nel caricatore del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="18704-109">In Windows 98, Windows ME, Windows NT, and Windows 2000, the `_CorExeMain` function is called indirectly through a fixup in the operating system loader.</span></span> <span data-ttu-id="18704-110">In tutte le altre versioni di Windows, viene chiamato direttamente dal caricatore del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="18704-110">In all other versions of Windows, it is called directly by the operating system loader.</span></span>  
  
 <span data-ttu-id="18704-111">Per ulteriori informazioni, vedere la sezione osservazioni nel [CorValidateImage](../../../../docs/framework/unmanaged-api/hosting/corvalidateimage-function.md) argomento.</span><span class="sxs-lookup"><span data-stu-id="18704-111">For additional information, see the Remarks section in the [_CorValidateImage](../../../../docs/framework/unmanaged-api/hosting/corvalidateimage-function.md) topic.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="18704-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="18704-112">Requirements</span></span>  
 <span data-ttu-id="18704-113">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="18704-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="18704-114">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="18704-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="18704-115">**Libreria:** inclusa come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="18704-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="18704-116">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="18704-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18704-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="18704-117">See Also</span></span>  
 [<span data-ttu-id="18704-118">Funzioni statiche globali dei metadati</span><span class="sxs-lookup"><span data-stu-id="18704-118">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)