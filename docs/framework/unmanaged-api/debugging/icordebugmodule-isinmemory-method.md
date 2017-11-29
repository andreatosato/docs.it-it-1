---
title: Metodo ICorDebugModule::IsInMemory
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugModule.IsInMemory
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugModule::IsInMemory
helpviewer_keywords:
- IsInMemory method [.NET Framework debugging]
- ICorDebugModule::IsInMemory method [.NET Framework debugging]
ms.assetid: 89940711-98e7-4aa6-bffc-5e39e91e1b7d
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 58f7964faee19f85c83d1b9b1c3e176354ae9588
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugmoduleisinmemory-method"></a><span data-ttu-id="145a0-102">Metodo ICorDebugModule::IsInMemory</span><span class="sxs-lookup"><span data-stu-id="145a0-102">ICorDebugModule::IsInMemory Method</span></span>
<span data-ttu-id="145a0-103">Ottiene un valore che indica se questo modulo esiste solo in memoria.</span><span class="sxs-lookup"><span data-stu-id="145a0-103">Gets a value that indicates whether this module exists only in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="145a0-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="145a0-104">Syntax</span></span>  
  
```  
HRESULT IsInMemory(  
    [out] BOOL *pInMemory  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="145a0-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="145a0-105">Parameters</span></span>  
 `pInMemory`  
 <span data-ttu-id="145a0-106">[out] `true` se questo modulo è presente solo in memoria; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="145a0-106">[out] `true` if this module exists only in memory; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="145a0-107">Note</span><span class="sxs-lookup"><span data-stu-id="145a0-107">Remarks</span></span>  
 <span data-ttu-id="145a0-108">Common language runtime (CLR) supporta il caricamento di moduli da flussi di byte non elaborati.</span><span class="sxs-lookup"><span data-stu-id="145a0-108">The common language runtime (CLR) supports the loading of modules from raw streams of bytes.</span></span> <span data-ttu-id="145a0-109">Questi moduli sono denominati *moduli in memoria* e non sono presenti sul disco.</span><span class="sxs-lookup"><span data-stu-id="145a0-109">Such modules are called *in-memory modules* and do not exist on disk.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="145a0-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="145a0-110">Requirements</span></span>  
 <span data-ttu-id="145a0-111">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="145a0-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="145a0-112">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="145a0-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="145a0-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="145a0-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="145a0-114">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="145a0-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="145a0-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="145a0-115">See Also</span></span>  
    
 