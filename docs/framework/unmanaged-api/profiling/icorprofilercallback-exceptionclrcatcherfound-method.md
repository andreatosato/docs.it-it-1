---
title: Metodo ICorProfilerCallback::ExceptionCLRCatcherFound
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.ExceptionCLRCatcherFound
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::ExceptionCLRCatcherFound
helpviewer_keywords:
- ICorProfilerCallback::ExceptionCLRCatcherFound method [.NET Framework profiling]
- ExceptionCLRCatcherFound method [.NET Framework profiling]
ms.assetid: 73fe8b4b-8f9a-4ba5-a10c-b26521396a66
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: ebb1779ca9f09089a071673f92810ea7a9e76b3d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallbackexceptionclrcatcherfound-method"></a><span data-ttu-id="97acd-102">Metodo ICorProfilerCallback::ExceptionCLRCatcherFound</span><span class="sxs-lookup"><span data-stu-id="97acd-102">ICorProfilerCallback::ExceptionCLRCatcherFound Method</span></span>
<span data-ttu-id="97acd-103">Chiamato quando un `catch` bloccare per l'eccezione si trova all'interno di common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="97acd-103">Called when a `catch` block for an exception is found inside the common language runtime (CLR) itself.</span></span> <span data-ttu-id="97acd-104">Questo metodo è obsoleto in .NET Framework versione 2.0.</span><span class="sxs-lookup"><span data-stu-id="97acd-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97acd-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="97acd-105">Syntax</span></span>  
  
```  
HRESULT ExceptionCLRCatcherFound();  
```  
  
## <a name="requirements"></a><span data-ttu-id="97acd-106">Requisiti</span><span class="sxs-lookup"><span data-stu-id="97acd-106">Requirements</span></span>  
 <span data-ttu-id="97acd-107">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="97acd-107">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="97acd-108">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="97acd-108">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="97acd-109">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="97acd-109">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="97acd-110">**Versione di .NET framework:** 1.0</span><span class="sxs-lookup"><span data-stu-id="97acd-110">**.NET Framework Version:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97acd-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="97acd-111">See Also</span></span>  
 [<span data-ttu-id="97acd-112">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="97acd-112">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="97acd-113">ExceptionCLRCatcherExecute (metodo)</span><span class="sxs-lookup"><span data-stu-id="97acd-113">ExceptionCLRCatcherExecute Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionclrcatcherexecute-method.md)