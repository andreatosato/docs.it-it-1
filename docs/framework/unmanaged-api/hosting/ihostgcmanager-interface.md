---
title: Interfaccia IHostGCManager
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostGCManager
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostGCManager
helpviewer_keywords: IHostGCManager interface [.NET Framework hosting]
ms.assetid: 820330a4-244c-4f67-ab5e-f24b0b3c2080
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0927b236af094b964261a9b2a49a33d1ea2b9391
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ihostgcmanager-interface"></a><span data-ttu-id="1d348-102">Interfaccia IHostGCManager</span><span class="sxs-lookup"><span data-stu-id="1d348-102">IHostGCManager Interface</span></span>
<span data-ttu-id="1d348-103">Fornisce metodi per notificare all'host gli eventi nel meccanismo di garbage collection implementato da common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="1d348-103">Provides methods that notify the host of events in the garbage collection mechanism implemented by the common language runtime (CLR).</span></span>  
  
## <a name="members"></a><span data-ttu-id="1d348-104">Membri</span><span class="sxs-lookup"><span data-stu-id="1d348-104">Members</span></span>  
  
|<span data-ttu-id="1d348-105">Membro</span><span class="sxs-lookup"><span data-stu-id="1d348-105">Member</span></span>|<span data-ttu-id="1d348-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1d348-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1d348-107">SuspensionEnding (metodo)</span><span class="sxs-lookup"><span data-stu-id="1d348-107">SuspensionEnding Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-suspensionending-method.md)|<span data-ttu-id="1d348-108">Notifica all'host che Common Language Runtime viene ripresa l'esecuzione di attività nel thread che era stato sospeso per una garbage collection.</span><span class="sxs-lookup"><span data-stu-id="1d348-108">Notifies the host that the CLR is resuming execution of tasks on threads that had been suspended for a garbage collection.</span></span>|  
|[<span data-ttu-id="1d348-109">SuspensionStarting (metodo)</span><span class="sxs-lookup"><span data-stu-id="1d348-109">SuspensionStarting Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-suspensionstarting-method.md)|<span data-ttu-id="1d348-110">Notifica all'host che Common Language Runtime sta sospendendo l'esecuzione delle attività, per eseguire un'operazione di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="1d348-110">Notifies the host that the CLR is suspending execution of tasks, to perform a garbage collection.</span></span>|  
|[<span data-ttu-id="1d348-111">ThreadIsBlockingForSuspension (metodo)</span><span class="sxs-lookup"><span data-stu-id="1d348-111">ThreadIsBlockingForSuspension Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-threadisblockingforsuspension-method.md)|<span data-ttu-id="1d348-112">Notifica all'host che il thread da cui è stata effettuata la chiamata al metodo per essere bloccato per una garbage collection.</span><span class="sxs-lookup"><span data-stu-id="1d348-112">Notifies the host that the thread from which the method call was made is about to block for a garbage collection.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1d348-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1d348-113">Requirements</span></span>  
 <span data-ttu-id="1d348-114">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1d348-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1d348-115">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="1d348-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1d348-116">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1d348-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1d348-117">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1d348-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d348-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1d348-118">See Also</span></span>  
 [<span data-ttu-id="1d348-119">ICLRTask (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="1d348-119">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="1d348-120">ICLRTaskManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="1d348-120">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="1d348-121">IHostTask (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="1d348-121">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="1d348-122">IHostTaskManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="1d348-122">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [<span data-ttu-id="1d348-123">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="1d348-123">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)