---
title: Funzione _CorDllMain
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: _CorDllMain
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: _CorDllMain
helpviewer_keywords: _CorDllMain function [.NET Framework hosting]
ms.assetid: bc7b51cf-39d3-48ec-a5cb-2f179fbefff8
topic_type: apiref
caps.latest.revision: "23"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d2e4188f8b95141118e4bbb2df2a702ff04c2adf
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="cordllmain-function"></a><span data-ttu-id="30e36-102">Funzione _CorDllMain</span><span class="sxs-lookup"><span data-stu-id="30e36-102">_CorDllMain Function</span></span>
<span data-ttu-id="30e36-103">Consente di inizializzare common language runtime (CLR), individua il punto di ingresso gestito nell'intestazione CLR dell'assembly DLL e inizia l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="30e36-103">Initializes the common language runtime (CLR), locates the managed entry point in the DLL assembly's CLR header, and begins execution.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30e36-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="30e36-104">Syntax</span></span>  
  
```  
BOOL STDMETHODCALLTYPE _CorDllMain (  
   [in] HINSTANCE hInst,  
   [in] DWORD     dwReason,  
   [in] LPVOID    lpReserved  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="30e36-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="30e36-105">Parameters</span></span>  
 `hInst`  
 <span data-ttu-id="30e36-106">[in] L'handle dell'istanza del modulo caricato.</span><span class="sxs-lookup"><span data-stu-id="30e36-106">[in] The instance handle of the loaded module.</span></span>  
  
 `dwReason`  
 <span data-ttu-id="30e36-107">[in] Indica i motivi per cui viene richiamata la funzione di punto di ingresso DLL.</span><span class="sxs-lookup"><span data-stu-id="30e36-107">[in]Indicates why the DLL entry-point function is being called.</span></span> <span data-ttu-id="30e36-108">Questo parametro può essere uno dei seguenti valori: DLL_PROCESS_ATTACH, DLL_THREAD_ATTACH, DLL_THREAD_ATTACH o DLL_PROCESS_DETACH.</span><span class="sxs-lookup"><span data-stu-id="30e36-108">This parameter can be one of the following values: DLL_PROCESS_ATTACH, DLL_THREAD_ATTACH, DLL_THREAD_ATTACH, or DLL_PROCESS_DETACH.</span></span> <span data-ttu-id="30e36-109">Per una descrizione di questi valori, vedere il `DllMain` documentazione di Platform SDK.</span><span class="sxs-lookup"><span data-stu-id="30e36-109">For descriptions of these values, see the `DllMain` documentation in the Platform SDK.</span></span>  
  
 `lpReserved`  
 <span data-ttu-id="30e36-110">[in] Non usato.</span><span class="sxs-lookup"><span data-stu-id="30e36-110">[in] Unused.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="30e36-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="30e36-111">Return Value</span></span>  
 <span data-ttu-id="30e36-112">Questo metodo restituisce `true` per l'esito positivo e `false` se si verifica un errore.</span><span class="sxs-lookup"><span data-stu-id="30e36-112">This method returns `true` for success and `false` if an error occurs.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="30e36-113">Note</span><span class="sxs-lookup"><span data-stu-id="30e36-113">Remarks</span></span>  
 <span data-ttu-id="30e36-114">Questa funzione viene chiamata dal caricatore del sistema operativo per gli assembly DLL.</span><span class="sxs-lookup"><span data-stu-id="30e36-114">This function is called by the operating system loader for DLL assemblies.</span></span> <span data-ttu-id="30e36-115">Per gli assembly eseguibili, il caricatore chiama la [CorExeMain](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md) funzione alternativa.</span><span class="sxs-lookup"><span data-stu-id="30e36-115">For executable assemblies, the loader calls the [_CorExeMain](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md) function instead.</span></span>  
  
 <span data-ttu-id="30e36-116">Il caricatore del sistema operativo chiama questo metodo indipendentemente dal punto di ingresso specificato nel file DLL.</span><span class="sxs-lookup"><span data-stu-id="30e36-116">The operating system loader calls this method regardless of the entry point specified in the DLL file.</span></span>  
  
 <span data-ttu-id="30e36-117">In Windows 98, Windows ME, Windows NT e Windows 2000, la `_CorDllMain` funzione viene chiamata indirettamente tramite una fixupin caricatore del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="30e36-117">In Windows 98, Windows ME, Windows NT, and Windows 2000, the `_CorDllMain` function is called indirectly through a fixupin the operating system loader.</span></span> <span data-ttu-id="30e36-118">In tutte le altre versioni di Windows, viene chiamato direttamente dal caricatore del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="30e36-118">In all other versions of Windows, it is called directly by the operating system loader.</span></span>  
  
 <span data-ttu-id="30e36-119">Per ulteriori informazioni, vedere la sezione osservazioni nel [CorValidateImage](../../../../docs/framework/unmanaged-api/hosting/corvalidateimage-function.md) argomento.</span><span class="sxs-lookup"><span data-stu-id="30e36-119">For additional information, see the Remarks section in the [_CorValidateImage](../../../../docs/framework/unmanaged-api/hosting/corvalidateimage-function.md) topic.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="30e36-120">Requisiti</span><span class="sxs-lookup"><span data-stu-id="30e36-120">Requirements</span></span>  
 <span data-ttu-id="30e36-121">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="30e36-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="30e36-122">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="30e36-122">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="30e36-123">**Libreria:** inclusa come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="30e36-123">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="30e36-124">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="30e36-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30e36-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="30e36-125">See Also</span></span>  
 [<span data-ttu-id="30e36-126">Funzioni statiche globali dei metadati</span><span class="sxs-lookup"><span data-stu-id="30e36-126">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)