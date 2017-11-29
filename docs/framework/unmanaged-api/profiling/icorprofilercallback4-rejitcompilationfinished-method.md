---
title: Metodo ICorProfilerCallback4::ReJITCompilationFinished
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback4.ReJITCompilationFinished
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback4::ReJITCompilationFinished
helpviewer_keywords:
- ICorProfilerCallback4::ReJITCompilationFinished method [.NET Framework profiling]
- ReJITCompilationFinished method, ICorProfilerCallback4 interface [.NET Framework profiling]
ms.assetid: 3b5cff02-2005-44eb-a2bc-50214c4b0e1d
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 768c77a91c072cadc2975d9dde704c134e719220
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallback4rejitcompilationfinished-method"></a><span data-ttu-id="951b6-102">Metodo ICorProfilerCallback4::ReJITCompilationFinished</span><span class="sxs-lookup"><span data-stu-id="951b6-102">ICorProfilerCallback4::ReJITCompilationFinished Method</span></span>
<span data-ttu-id="951b6-103">Notifica al profiler che il compilatore di just-in-time (JIT) ha terminato la ricompilazione di una funzione.</span><span class="sxs-lookup"><span data-stu-id="951b6-103">Notifies the profiler that the just-in-time (JIT) compiler has finished recompiling a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="951b6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="951b6-104">Syntax</span></span>  
  
```  
HRESULT ReJITCompilationFinished(  
    [in] FunctionID functionId,    [in] ReJITID rejitId,  
    [in] HRESULT    hrStatus,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="951b6-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="951b6-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="951b6-106">[in] L'ID della funzione ricompilata.</span><span class="sxs-lookup"><span data-stu-id="951b6-106">[in] The ID of the function that was recompiled.</span></span>  
  
 `rejitId`  
 <span data-ttu-id="951b6-107">[in] Identità della funzione ricompilata in JIT.</span><span class="sxs-lookup"><span data-stu-id="951b6-107">[in] The identity of the JIT-recompiled function.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="951b6-108">[in] Un valore che indica se è stata completata la ricompilazione JIT.</span><span class="sxs-lookup"><span data-stu-id="951b6-108">[in] A value that indicates whether the JIT recompilation was successful.</span></span>  
  
 `fIsSafeToBlock`  
 <span data-ttu-id="951b6-109">[in] `true` per indicare che il blocco può causare il runtime di attesa per il thread chiamante da questo callback; `false` per indicare che il blocco non avranno effetto l'operazione di runtime.</span><span class="sxs-lookup"><span data-stu-id="951b6-109">[in] `true` to indicate that blocking may cause the runtime to wait for the calling thread to return from this callback; `false` to indicate that blocking will not affect the operation of the runtime.</span></span>  
  
 <span data-ttu-id="951b6-110">Il valore `true` non influisce sul runtime, ma possono influenzare i risultati di profilatura.</span><span class="sxs-lookup"><span data-stu-id="951b6-110">A value of `true` does not harm the runtime, but can affect the profiling results.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="951b6-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="951b6-111">Requirements</span></span>  
 <span data-ttu-id="951b6-112">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="951b6-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="951b6-113">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="951b6-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="951b6-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="951b6-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="951b6-115">**Versioni di .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="951b6-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="951b6-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="951b6-116">See Also</span></span>  
 [<span data-ttu-id="951b6-117">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="951b6-117">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="951b6-118">ICorProfilerCallback4 (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="951b6-118">ICorProfilerCallback4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)  
 [<span data-ttu-id="951b6-119">JITCompilationStarted (metodo)</span><span class="sxs-lookup"><span data-stu-id="951b6-119">JITCompilationStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md)  
 [<span data-ttu-id="951b6-120">ReJITCompilationStarted (metodo)</span><span class="sxs-lookup"><span data-stu-id="951b6-120">ReJITCompilationStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationstarted-method.md)