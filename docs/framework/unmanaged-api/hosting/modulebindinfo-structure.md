---
title: Struttura ModuleBindInfo
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ModuleBindInfo
api_location: mscoree.dll
api_type: COM
f1_keywords: ModuleBindInfo
helpviewer_keywords: ModuleBindInfo structure [.NET Framework hosting]
ms.assetid: 632d4adc-dbc9-4ce8-9397-abc3285c1c69
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 6488503e0300530b22c0c6f904e11db7f5d5b41c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="modulebindinfo-structure"></a><span data-ttu-id="e6775-102">Struttura ModuleBindInfo</span><span class="sxs-lookup"><span data-stu-id="e6775-102">ModuleBindInfo Structure</span></span>
<span data-ttu-id="e6775-103">Fornisce informazioni dettagliate sul modulo a cui fa riferimento e l'assembly che lo contiene.</span><span class="sxs-lookup"><span data-stu-id="e6775-103">Provides detailed information about the referenced module and the assembly that contains it.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6775-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e6775-104">Syntax</span></span>  
  
```  
typedef struct _ModuleBindInfo {  
    DWORD    dwAppDomainId;  
    LPCWSTR  lpAssemblyIdentity;  
    LPCWSTR  lpModuleName  
} ModuleBindInfo;  
```  
  
## <a name="members"></a><span data-ttu-id="e6775-105">Membri</span><span class="sxs-lookup"><span data-stu-id="e6775-105">Members</span></span>  
  
|<span data-ttu-id="e6775-106">Membro</span><span class="sxs-lookup"><span data-stu-id="e6775-106">Member</span></span>|<span data-ttu-id="e6775-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e6775-107">Description</span></span>|  
|------------|-----------------|  
|`dwAppDomainId`|<span data-ttu-id="e6775-108">Un identificatore univoco per il `IStream` restituito da una chiamata al [IHostAssemblyStore:: ProvideModule](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-providemodule-method.md) metodo da cui è possibile caricare il modulo a cui fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="e6775-108">A unique identifier for the `IStream` that is returned by a call to the [IHostAssemblyStore::ProvideModule](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-providemodule-method.md) method from which the referenced module is to be loaded.</span></span>|  
|`lpAssemblyIdentity`|<span data-ttu-id="e6775-109">Identificatore univoco per l'assembly che contiene il modulo a cui fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="e6775-109">A unique identifier for the assembly that contains the referenced module.</span></span>|  
|`lpModuleName`|<span data-ttu-id="e6775-110">Il nome del modulo a cui fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="e6775-110">The name of the referenced module.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e6775-111">Note</span><span class="sxs-lookup"><span data-stu-id="e6775-111">Remarks</span></span>  
 <span data-ttu-id="e6775-112">`ModuleBindInfo`viene passato come parametro a `IHostAssemblyStore::ProvideModule`.</span><span class="sxs-lookup"><span data-stu-id="e6775-112">`ModuleBindInfo` is passed as a parameter to `IHostAssemblyStore::ProvideModule`.</span></span> <span data-ttu-id="e6775-113">L'identificatore univoco viene fornito dall'host `dwAppDomainId` a common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="e6775-113">The host supplies the unique identifier `dwAppDomainId` to the common language runtime (CLR).</span></span> <span data-ttu-id="e6775-114">Dopo una chiamata al [IHostAssemblyStore::](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md) metodo viene restituito, il runtime usa l'identificatore per determinare se il contenuto del `IStream` è stato eseguito il mapping.</span><span class="sxs-lookup"><span data-stu-id="e6775-114">After a call to the [IHostAssemblyStore::ProvideAssembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md) method returns, the runtime uses the identifier to determine whether the contents of the `IStream` have been mapped.</span></span> <span data-ttu-id="e6775-115">In questo caso, il runtime carica la copia esistente anziché la modifica del flusso.</span><span class="sxs-lookup"><span data-stu-id="e6775-115">If so, the runtime loads the existing copy rather than remapping the stream.</span></span> <span data-ttu-id="e6775-116">Il runtime usa anche questo identificatore come chiave di ricerca per i flussi restituiti dalle chiamate al `IHostAssemblyStore::ProvideAssembly` metodo.</span><span class="sxs-lookup"><span data-stu-id="e6775-116">The runtime also uses this identifier as a lookup key for streams that are returned from calls to the `IHostAssemblyStore::ProvideAssembly` method.</span></span> <span data-ttu-id="e6775-117">Pertanto, l'identificatore deve essere univoco per richieste del modulo anche per le richieste di assembly.</span><span class="sxs-lookup"><span data-stu-id="e6775-117">Therefore, the identifier must be unique for module requests as well as for assembly requests.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e6775-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e6775-118">Requirements</span></span>  
 <span data-ttu-id="e6775-119">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e6775-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e6775-120">**Intestazione:** Mscoree</span><span class="sxs-lookup"><span data-stu-id="e6775-120">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="e6775-121">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e6775-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e6775-122">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e6775-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6775-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e6775-123">See Also</span></span>  
 [<span data-ttu-id="e6775-124">Strutture di hosting</span><span class="sxs-lookup"><span data-stu-id="e6775-124">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)  
 [<span data-ttu-id="e6775-125">AssemblyBindInfo (struttura)</span><span class="sxs-lookup"><span data-stu-id="e6775-125">AssemblyBindInfo Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/assemblybindinfo-structure.md)  
 [<span data-ttu-id="e6775-126">ICLRAssemblyIdentityManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="e6775-126">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)  
 [<span data-ttu-id="e6775-127">ICLRAssemblyReferenceList (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="e6775-127">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 [<span data-ttu-id="e6775-128">IHostAssemblyManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="e6775-128">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)