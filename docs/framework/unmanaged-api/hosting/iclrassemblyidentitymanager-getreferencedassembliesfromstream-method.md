---
title: Metodo ICLRAssemblyIdentityManager::GetReferencedAssembliesFromStream
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRAssemblyIdentityManager.GetReferencedAssembliesFromStream
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRAssemblyIdentityManager::GetReferencedAssembliesFromStream
helpviewer_keywords:
- ICLRAssemblyIdentityManager::GetReferencedAssembliesFromStream method [.NET Framework hosting]
- GetReferencedAssembliesFromStream method [.NET Framework hosting]
ms.assetid: fe9849c1-c3fc-477b-a31f-e8619f5516f5
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 64a43640d08acbab0bcf505cc8a5850784ff18ca
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="iclrassemblyidentitymanagergetreferencedassembliesfromstream-method"></a><span data-ttu-id="b3188-102">Metodo ICLRAssemblyIdentityManager::GetReferencedAssembliesFromStream</span><span class="sxs-lookup"><span data-stu-id="b3188-102">ICLRAssemblyIdentityManager::GetReferencedAssembliesFromStream Method</span></span>
<span data-ttu-id="b3188-103">Ottiene un puntatore a un [ICLRReferenceAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md) oggetto che contiene i dati di identità di assembly per gli assembly a cui fa riferimento l'assembly nel flusso specificato.</span><span class="sxs-lookup"><span data-stu-id="b3188-103">Gets a pointer to an [ICLRReferenceAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md) object that contains assembly identity data for the assemblies referenced by the assembly in the specified stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b3188-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b3188-104">Syntax</span></span>  
  
```  
HRESULT GetReferencedAssembliesFromStream (  
    [in]  IStream *pStream,  
    [in]  DWORD    dwFlags,  
    [in]  ICLRAssemblyReferenceList  *pExcludeAssembliesList,  
    [out] ICLRReferenceAssemblyEnum **ppReferenceEnum  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b3188-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b3188-105">Parameters</span></span>  
 `pStream`  
 <span data-ttu-id="b3188-106">[in] Puntatore a interfaccia a un `IStream` contenente l'assembly da valutare.</span><span class="sxs-lookup"><span data-stu-id="b3188-106">[in] An interface pointer to an `IStream` containing the assembly to be evaluated.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="b3188-107">[in] Fornito per l'estensibilità futura.</span><span class="sxs-lookup"><span data-stu-id="b3188-107">[in] Provided for future extensibility.</span></span> <span data-ttu-id="b3188-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT è l'unico valore che supporta la versione corrente di common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="b3188-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT is the only value that the current version of the common language runtime (CLR) supports.</span></span>  
  
 `pExcludeAssembliesList`  
 <span data-ttu-id="b3188-109">[in] Un puntatore a un [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) oggetto che contiene dati di identità di assembly per gli assembly da escludere dal `ppReferenceEnum`.</span><span class="sxs-lookup"><span data-stu-id="b3188-109">[in] A pointer to an [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) object that contains assembly identity data for the assemblies to be excluded from `ppReferenceEnum`.</span></span>  
  
 `ppReferenceEnum`  
 <span data-ttu-id="b3188-110">[out] Un puntatore all'indirizzo di un `ICLRReferenceAssemblyEnum` oggetto che contiene i dati di identità di assembly per gli assembly a cui fa riferimento l'assembly in `pStream`, esclusi gli assembly in `pExcludeAssembliesList`.</span><span class="sxs-lookup"><span data-stu-id="b3188-110">[out] A pointer to the address of an `ICLRReferenceAssemblyEnum` object that contains assembly identity data for the assemblies referenced by the assembly in `pStream`, excluding the assemblies in `pExcludeAssembliesList`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b3188-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="b3188-111">Return Value</span></span>  
  
|<span data-ttu-id="b3188-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b3188-112">HRESULT</span></span>|<span data-ttu-id="b3188-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b3188-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b3188-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="b3188-114">S_OK</span></span>|<span data-ttu-id="b3188-115">Il metodo è stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="b3188-115">The method returned successfully.</span></span>|  
|<span data-ttu-id="b3188-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b3188-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b3188-117">CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="b3188-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b3188-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b3188-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b3188-119">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="b3188-119">The call timed out.</span></span>|  
|<span data-ttu-id="b3188-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b3188-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b3188-121">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="b3188-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b3188-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b3188-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b3188-123">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="b3188-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b3188-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b3188-124">E_FAIL</span></span>|<span data-ttu-id="b3188-125">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="b3188-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b3188-126">Se un metodo restituisce E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="b3188-126">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b3188-127">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="b3188-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b3188-128">Note</span><span class="sxs-lookup"><span data-stu-id="b3188-128">Remarks</span></span>  
 <span data-ttu-id="b3188-129">Il chiamante è possibile scegliere di escludere un insieme di riferimenti ad assembly noti nell'elenco restituito.</span><span class="sxs-lookup"><span data-stu-id="b3188-129">The caller can choose to exclude a set of known assembly references from the returned list.</span></span> <span data-ttu-id="b3188-130">Questo set è definito da `pExcludeAssembliesList`.</span><span class="sxs-lookup"><span data-stu-id="b3188-130">This set is defined by `pExcludeAssembliesList`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b3188-131">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b3188-131">Requirements</span></span>  
 <span data-ttu-id="b3188-132">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b3188-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b3188-133">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="b3188-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b3188-134">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b3188-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b3188-135">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b3188-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3188-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b3188-136">See Also</span></span>  
 [<span data-ttu-id="b3188-137">ICLRAssemblyIdentityManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="b3188-137">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)  
 [<span data-ttu-id="b3188-138">ICLRAssemblyReferenceList (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="b3188-138">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 [<span data-ttu-id="b3188-139">ICLRReferenceAssemblyEnum (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="b3188-139">ICLRReferenceAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md)