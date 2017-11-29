---
title: Metodo ICorDebugProcess::ReadMemory
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess.ReadMemory
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess::ReadMemory
helpviewer_keywords:
- ReadMemory method [.NET Framework debugging]
- ICorDebugProcess::ReadMemory method [.NET Framework debugging]
ms.assetid: 28e4b2f6-9589-445c-be24-24a3306795e7
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 33345ada6606bc1a43a630340251d3ba1404b2f2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugprocessreadmemory-method"></a><span data-ttu-id="a0f78-102">Metodo ICorDebugProcess::ReadMemory</span><span class="sxs-lookup"><span data-stu-id="a0f78-102">ICorDebugProcess::ReadMemory Method</span></span>
<span data-ttu-id="a0f78-103">Legge un'area specificata di memoria per questo processo.</span><span class="sxs-lookup"><span data-stu-id="a0f78-103">Reads a specified area of memory for this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0f78-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a0f78-104">Syntax</span></span>  
  
```  
HRESULT ReadMemory(  
    [in]  CORDB_ADDRESS address,   
    [in]  DWORD size,  
    [out, size_is(size), length_is(size)] BYTE buffer[],  
    [out] SIZE_T *read);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a0f78-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a0f78-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="a0f78-106">[in] Oggetto `CORDB_ADDRESS` valore che specifica l'indirizzo di base della memoria da leggere.</span><span class="sxs-lookup"><span data-stu-id="a0f78-106">[in] A `CORDB_ADDRESS` value that specifies the base address of the memory to be read.</span></span>  
  
 `size`  
 <span data-ttu-id="a0f78-107">[in] Il numero di byte da leggere dalla memoria.</span><span class="sxs-lookup"><span data-stu-id="a0f78-107">[in] The number of bytes to be read from memory.</span></span>  
  
 `buffer`  
 <span data-ttu-id="a0f78-108">[out] Un buffer che riceve il contenuto della memoria.</span><span class="sxs-lookup"><span data-stu-id="a0f78-108">[out] A buffer that receives the contents of the memory.</span></span>  
  
 `read`  
 <span data-ttu-id="a0f78-109">[out] Un puntatore al numero di byte trasferiti nel buffer specificato.</span><span class="sxs-lookup"><span data-stu-id="a0f78-109">[out] A pointer to the number of bytes transferred into the specified buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a0f78-110">Note</span><span class="sxs-lookup"><span data-stu-id="a0f78-110">Remarks</span></span>  
 <span data-ttu-id="a0f78-111">Il `ReadMemory` metodo viene usata principalmente per essere utilizzato per il debug di interoperabilità per controllare le aree della memoria in uso da parte dell'oggetto del debug non gestita.</span><span class="sxs-lookup"><span data-stu-id="a0f78-111">The `ReadMemory` method is primarily intended to be used by interop debugging to inspect memory regions that are being used by the unmanaged portion of the debuggee.</span></span> <span data-ttu-id="a0f78-112">Questo metodo può anche essere utilizzato per leggere codice Microsoft intermediate language (MSIL) e codice nativo compilato tramite JIT.</span><span class="sxs-lookup"><span data-stu-id="a0f78-112">This method can also be used to read Microsoft intermediate language (MSIL) code and native JIT-compiled code.</span></span>  
  
 <span data-ttu-id="a0f78-113">I punti di interruzione gestiti verrà rimossa dal disco i dati restituiti nel `buffer` parametro.</span><span class="sxs-lookup"><span data-stu-id="a0f78-113">Any managed breakpoints will be removed from the data that is returned in the `buffer` parameter.</span></span> <span data-ttu-id="a0f78-114">Verrà eseguita alcuna modifica per i punti di interruzione nativi impostato dal [ICorDebugProcess2::](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md).</span><span class="sxs-lookup"><span data-stu-id="a0f78-114">No adjustments will be made for native breakpoints set by [ICorDebugProcess2::SetUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md).</span></span>  
  
 <span data-ttu-id="a0f78-115">Non viene eseguita nessuna memorizzazione nella cache della memoria del processo.</span><span class="sxs-lookup"><span data-stu-id="a0f78-115">No caching of process memory is performed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a0f78-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a0f78-116">Requirements</span></span>  
 <span data-ttu-id="a0f78-117">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a0f78-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a0f78-118">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="a0f78-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a0f78-119">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a0f78-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a0f78-120">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a0f78-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>