---
title: Metodo ICLRTask::Abort
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRTask.Abort
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRTask::Abort
helpviewer_keywords:
- ICLRTask::Abort method [.NET Framework hosting]
- Abort method, ICLRTask interface [.NET Framework hosting]
ms.assetid: b3594b5f-2e41-4e36-9096-3586276a138c
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e789afc8f570d647fd44f8f43c23c2cc33ba8f70
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="iclrtaskabort-method"></a><span data-ttu-id="db159-102">Metodo ICLRTask::Abort</span><span class="sxs-lookup"><span data-stu-id="db159-102">ICLRTask::Abort Method</span></span>
<span data-ttu-id="db159-103">Richiede che common language runtime (CLR) di interrompere l'attività che corrente [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) istanza.</span><span class="sxs-lookup"><span data-stu-id="db159-103">Requests that the common language runtime (CLR) abort the task that the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db159-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="db159-104">Syntax</span></span>  
  
```  
HRESULT Abort ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="db159-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="db159-105">Return Value</span></span>  
  
|<span data-ttu-id="db159-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="db159-106">HRESULT</span></span>|<span data-ttu-id="db159-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="db159-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="db159-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="db159-108">S_OK</span></span>|<span data-ttu-id="db159-109">`Abort`stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="db159-109">`Abort` returned successfully.</span></span>|  
|<span data-ttu-id="db159-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="db159-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="db159-111">CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="db159-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="db159-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="db159-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="db159-113">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="db159-113">The call timed out.</span></span>|  
|<span data-ttu-id="db159-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="db159-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="db159-115">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="db159-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="db159-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="db159-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="db159-117">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="db159-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="db159-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="db159-118">E_FAIL</span></span>|<span data-ttu-id="db159-119">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="db159-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="db159-120">Quando un metodo viene restituito E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="db159-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="db159-121">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="db159-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="db159-122">Note</span><span class="sxs-lookup"><span data-stu-id="db159-122">Remarks</span></span>  
 <span data-ttu-id="db159-123">Il Common Language Runtime genera un <xref:System.Threading.ThreadAbortException> quando l'host chiama `Abort`.</span><span class="sxs-lookup"><span data-stu-id="db159-123">The CLR raises a <xref:System.Threading.ThreadAbortException> when the host calls `Abort`.</span></span> <span data-ttu-id="db159-124">Viene restituito immediatamente dopo le informazioni sull'eccezione viene inizializzati, senza attendere che il codice utente, ad esempio i finalizzatori o i meccanismi di gestione delle eccezioni per l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="db159-124">It returns immediately after the exception information is initialized, without waiting for user code, such as finalizers or exception handling mechanisms, to execute.</span></span> <span data-ttu-id="db159-125">Le chiamate a `Abort` vengono quindi eseguite rapidamente.</span><span class="sxs-lookup"><span data-stu-id="db159-125">Calls to `Abort` thus return quickly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="db159-126">Requisiti</span><span class="sxs-lookup"><span data-stu-id="db159-126">Requirements</span></span>  
 <span data-ttu-id="db159-127">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="db159-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="db159-128">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="db159-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="db159-129">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="db159-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="db159-130">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="db159-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db159-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="db159-131">See Also</span></span>  
 [<span data-ttu-id="db159-132">ICLRTask (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="db159-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="db159-133">ICLRTaskManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="db159-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="db159-134">IHostTask (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="db159-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="db159-135">IHostTaskManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="db159-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)