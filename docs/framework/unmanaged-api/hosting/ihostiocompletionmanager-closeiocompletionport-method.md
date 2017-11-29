---
title: Metodo IHostIoCompletionManager::CloseIoCompletionPort
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostIoCompletionManager.CloseIoCompletionPort
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostIoCompletionManager::CloseIoCompletionPort
helpviewer_keywords:
- IHostIoCompletionManager::CloseIoCompletionPort method [.NET Framework hosting]
- CloseIoCompletionPort method [.NET Framework hosting]
ms.assetid: e86ad7be-3758-498a-a972-5522d69dfbb3
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 066d51c821cf86522ffaca4c15db360ce96ed773
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ihostiocompletionmanagercloseiocompletionport-method"></a><span data-ttu-id="f1977-102">Metodo IHostIoCompletionManager::CloseIoCompletionPort</span><span class="sxs-lookup"><span data-stu-id="f1977-102">IHostIoCompletionManager::CloseIoCompletionPort Method</span></span>
<span data-ttu-id="f1977-103">Richiede che l'host chiuda una porta che è stato aperto tramite una chiamata precedente a [CreateIoCompletionPort](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-createiocompletionport-method.md).</span><span class="sxs-lookup"><span data-stu-id="f1977-103">Requests that the host close a port that was opened through an earlier call to [CreateIoCompletionPort](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-createiocompletionport-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1977-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f1977-104">Syntax</span></span>  
  
```  
HRESULT CloseIoCompletionPort (  
    [in] HANDLE hPort  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f1977-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f1977-105">Parameters</span></span>  
 `hPort`  
 <span data-ttu-id="f1977-106">[in] Handle della porta da chiudere.</span><span class="sxs-lookup"><span data-stu-id="f1977-106">[in] The handle of the port to close.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f1977-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="f1977-107">Return Value</span></span>  
  
|<span data-ttu-id="f1977-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f1977-108">HRESULT</span></span>|<span data-ttu-id="f1977-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f1977-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f1977-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="f1977-110">S_OK</span></span>|<span data-ttu-id="f1977-111">`CloseIoCompletionPort`stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="f1977-111">`CloseIoCompletionPort` returned successfully.</span></span>|  
|<span data-ttu-id="f1977-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f1977-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f1977-113">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="f1977-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f1977-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f1977-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f1977-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="f1977-115">The call timed out.</span></span>|  
|<span data-ttu-id="f1977-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f1977-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f1977-117">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="f1977-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f1977-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f1977-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f1977-119">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="f1977-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f1977-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f1977-120">E_FAIL</span></span>|<span data-ttu-id="f1977-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="f1977-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f1977-122">Quando un metodo viene restituito E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="f1977-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f1977-123">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="f1977-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="f1977-124">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="f1977-124">E_INVALIDARG</span></span>|<span data-ttu-id="f1977-125">È stato passato un handle di porta non valido.</span><span class="sxs-lookup"><span data-stu-id="f1977-125">An invalid port handle was passed.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f1977-126">Note</span><span class="sxs-lookup"><span data-stu-id="f1977-126">Remarks</span></span>  
 <span data-ttu-id="f1977-127">`hPort`deve essere un handle a una porta che è stato creato da una precedente chiamata a `CreateIoCompletionPort`.</span><span class="sxs-lookup"><span data-stu-id="f1977-127">`hPort` must be a handle to a port that was created by an earlier call to `CreateIoCompletionPort`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f1977-128">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f1977-128">Requirements</span></span>  
 <span data-ttu-id="f1977-129">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f1977-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f1977-130">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="f1977-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f1977-131">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f1977-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f1977-132">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f1977-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1977-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f1977-133">See Also</span></span>  
 [<span data-ttu-id="f1977-134">ICLRIoCompletionManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="f1977-134">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)  
 [<span data-ttu-id="f1977-135">IHostIoCompletionManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="f1977-135">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)