---
title: Metodo ICorDebugHeapValue3::GetThreadOwningMonitorLock
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugHeapValue3.GetThreadOwningMonitorLock
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugHeapValue3::GetThreadOwningMonitorLock
helpviewer_keywords:
- GetThreadOwningMonitorLock method [.NET Framework debugging]
- ICorDebugHeapValue3::GetThreadOwningMonitorLock method [.NET Framework debugging]
ms.assetid: e06fc19d-2cf4-4cad-81a3-137a68af8969
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3571f546f71515a980c5415e568ae85eb0863d42
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugheapvalue3getthreadowningmonitorlock-method"></a><span data-ttu-id="50318-102">Metodo ICorDebugHeapValue3::GetThreadOwningMonitorLock</span><span class="sxs-lookup"><span data-stu-id="50318-102">ICorDebugHeapValue3::GetThreadOwningMonitorLock Method</span></span>
<span data-ttu-id="50318-103">Restituisce il thread gestito che possiede il blocco di monitoraggio per questo oggetto.</span><span class="sxs-lookup"><span data-stu-id="50318-103">Returns the managed thread that owns the monitor lock on this object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="50318-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="50318-104">Syntax</span></span>  
  
```  
HRESULT GetThreadOwningMonitorLock (  
    [out] ICorDebugThread   **ppThread,  
    [out] DWORD              *pAcquisitionCount  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="50318-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="50318-105">Parameters</span></span>  
 `ppThread`  
 <span data-ttu-id="50318-106">[out] Il thread gestito che possiede il blocco di monitoraggio per questo oggetto.</span><span class="sxs-lookup"><span data-stu-id="50318-106">[out] The managed thread that owns the monitor lock on this object.</span></span>  
  
 `pAcquisitionCount`  
 <span data-ttu-id="50318-107">[out] Il numero di volte in cui che il thread sarebbe necessario rilasciare il blocco prima di restituire a essere senza proprietario.</span><span class="sxs-lookup"><span data-stu-id="50318-107">[out] The number of times this thread would have to release the lock before it returns to being unowned.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="50318-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="50318-108">Return Value</span></span>  
 <span data-ttu-id="50318-109">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="50318-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="50318-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="50318-110">HRESULT</span></span>|<span data-ttu-id="50318-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="50318-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="50318-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="50318-112">S_OK</span></span>|<span data-ttu-id="50318-113">Metodo completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="50318-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="50318-114">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="50318-114">S_FALSE</span></span>|<span data-ttu-id="50318-115">Nessun thread gestito possiede il blocco di monitoraggio su questo oggetto.</span><span class="sxs-lookup"><span data-stu-id="50318-115">No managed thread owns the monitor lock on this object.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="50318-116">Eccezioni</span><span class="sxs-lookup"><span data-stu-id="50318-116">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="50318-117">Note</span><span class="sxs-lookup"><span data-stu-id="50318-117">Remarks</span></span>  
 <span data-ttu-id="50318-118">Se un thread gestito possiede il blocco di monitoraggio per questo oggetto:</span><span class="sxs-lookup"><span data-stu-id="50318-118">If a managed thread owns the monitor lock on this object:</span></span>  
  
-   <span data-ttu-id="50318-119">Il metodo restituisce S_OK.</span><span class="sxs-lookup"><span data-stu-id="50318-119">The method returns S_OK.</span></span>  
  
-   <span data-ttu-id="50318-120">L'oggetto thread è valido fino a quando non si esce dal thread.</span><span class="sxs-lookup"><span data-stu-id="50318-120">The thread object is valid until the thread exits.</span></span>  
  
 <span data-ttu-id="50318-121">Se nessun thread gestito possiede il blocco di monitoraggio su questo oggetto `ppThread` e `pAcquisitionCount` sono identiche, e il metodo restituisce S_FALSE.</span><span class="sxs-lookup"><span data-stu-id="50318-121">If no managed thread owns the monitor lock on this object, `ppThread` and `pAcquisitionCount` are unchanged, and the method returns S_FALSE.</span></span>  
  
 <span data-ttu-id="50318-122">Se `ppThread` o `pAcquisitionCount` non è un puntatore valido, il risultato è indefinito.</span><span class="sxs-lookup"><span data-stu-id="50318-122">If `ppThread` or `pAcquisitionCount` is not a valid pointer, the result is undefined.</span></span>  
  
 <span data-ttu-id="50318-123">Se si verifica un errore che non è possibile determinare che, se presente, thread proprietario del blocco di monitoraggio per questo oggetto, il metodo restituisce un HRESULT che indica un errore.</span><span class="sxs-lookup"><span data-stu-id="50318-123">If an error occurs such that it cannot be determined which, if any, thread owns the monitor lock on this object, the method returns an HRESULT that indicates failure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="50318-124">Requisiti</span><span class="sxs-lookup"><span data-stu-id="50318-124">Requirements</span></span>  
 <span data-ttu-id="50318-125">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="50318-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="50318-126">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="50318-126">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="50318-127">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="50318-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="50318-128">**Versioni di .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="50318-128">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50318-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="50318-129">See Also</span></span>  
 [<span data-ttu-id="50318-130">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="50318-130">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="50318-131">Debug</span><span class="sxs-lookup"><span data-stu-id="50318-131">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)