---
title: Metodo ICLRDataTarget3::GetExceptionRecord
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: cpp
api_name: ICLRDataTarget3.GetExceptionRecord
api_location: mscordbi.dll
api_type: COM
ms.assetid: 6643c2af-2ee6-4789-aa25-1d8eaf500c94
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f8c9ac4ecc0cffda4038129b1244b81501e9a1f7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="iclrdatatarget3getexceptionrecord-method"></a><span data-ttu-id="11f04-102">Metodo ICLRDataTarget3::GetExceptionRecord</span><span class="sxs-lookup"><span data-stu-id="11f04-102">ICLRDataTarget3::GetExceptionRecord Method</span></span>
<span data-ttu-id="11f04-103">Chiamato dai servizi di accesso ai dati di Common Language Runtime (CLR) per recuperare il record di eccezione associato al processo destinazione.</span><span class="sxs-lookup"><span data-stu-id="11f04-103">Called by the common language runtime (CLR) data access services to retrieve the exception record associated with the target process.</span></span> <span data-ttu-id="11f04-104">Ad esempio, per una destinazione del dump, sarebbe equivalente al record di eccezione passato tramite la `ExceptionParam` argomento per il [MiniDumpWriteDump](http://msdn.microsoft.com/library/windows/desktop/ms680360.aspx) funzione nella libreria di Windows eseguire il Debug della Guida (DbgHelp).</span><span class="sxs-lookup"><span data-stu-id="11f04-104">For example, for a dump target, this would be equivalent to the exception record passed in via the `ExceptionParam` argument to the [MiniDumpWriteDump](http://msdn.microsoft.com/library/windows/desktop/ms680360.aspx) function in the Windows Debug Help Library (DbgHelp).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11f04-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="11f04-105">Syntax</span></span>  
  
```cpp  
HRESULT GetExceptionRecord(  
    [in] ULONG32 bufferSize,  
    [out] ULONG32* bufferUsed,  
    [out, size_is(bufferSize] BYTE* buffer  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="11f04-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="11f04-106">Parameters</span></span>  
 `bufferSize`  
 <span data-ttu-id="11f04-107">[in] La dimensione del buffer di input, in byte.</span><span class="sxs-lookup"><span data-stu-id="11f04-107">[in] The input buffer size, in bytes.</span></span> <span data-ttu-id="11f04-108">Deve essere uguale a `sizeof(` [MINIDUMP_EXCEPTION](http://msdn.microsoft.com/library/windows/desktop/ms680367.aspx)`)`.</span><span class="sxs-lookup"><span data-stu-id="11f04-108">This must be equal to `sizeof(`[MINIDUMP_EXCEPTION](http://msdn.microsoft.com/library/windows/desktop/ms680367.aspx)`)`.</span></span>  
  
 `bufferUsed`  
 <span data-ttu-id="11f04-109">[out] Un puntatore a un tipo `ULONG32` che riceve il numero di byte effettivamente scritti nel buffer.</span><span class="sxs-lookup"><span data-stu-id="11f04-109">[out] A pointer to a `ULONG32` type that receives the number of bytes actually written to the buffer.</span></span>  
  
 `buffer`  
 <span data-ttu-id="11f04-110">[out] Un puntatore a un buffer di memoria che riceve una copia del record di eccezione.</span><span class="sxs-lookup"><span data-stu-id="11f04-110">[out] A pointer to a memory buffer that receives a copy of the exception record.</span></span> <span data-ttu-id="11f04-111">Il record di eccezione viene restituito come un [MINIDUMP_EXCEPTION](http://msdn.microsoft.com/library/windows/desktop/ms680367.aspx) tipo.</span><span class="sxs-lookup"><span data-stu-id="11f04-111">The exception record is returned as a [MINIDUMP_EXCEPTION](http://msdn.microsoft.com/library/windows/desktop/ms680367.aspx) type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="11f04-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="11f04-112">Return Value</span></span>  
 <span data-ttu-id="11f04-113">Il valore restituito è `S_OK` in caso di esito positivo o un codice di errore `HRESULT` in caso di esito negativo.</span><span class="sxs-lookup"><span data-stu-id="11f04-113">The return value is `S_OK` on success, or a failure `HRESULT` code on failure.</span></span> <span data-ttu-id="11f04-114">I codici `HRESULT` possono includere, ma non sono limitati a, quanto segue:</span><span class="sxs-lookup"><span data-stu-id="11f04-114">The `HRESULT` codes can include but are not limited to the following:</span></span>  
  
|<span data-ttu-id="11f04-115">Codice restituito</span><span class="sxs-lookup"><span data-stu-id="11f04-115">Return code</span></span>|<span data-ttu-id="11f04-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="11f04-116">Description</span></span>|  
|-----------------|-----------------|  
|`S_OK`|<span data-ttu-id="11f04-117">Il metodo è riuscito.</span><span class="sxs-lookup"><span data-stu-id="11f04-117">Method succeeded.</span></span> <span data-ttu-id="11f04-118">Il record di eccezione è stato copiato nel buffer di output.</span><span class="sxs-lookup"><span data-stu-id="11f04-118">The exception record has been copied to the output buffer.</span></span>|  
|`HRESULT_FROM_WIN32(ERROR_NOT_FOUND)`|<span data-ttu-id="11f04-119">Nessun record di eccezione è associato alla destinazione.</span><span class="sxs-lookup"><span data-stu-id="11f04-119">No exception record is associated with the target.</span></span>|  
|`HRESULT_FROM_WIN32(ERROR_BAD_LENGTH)`|<span data-ttu-id="11f04-120">La dimensione del buffer di input non è uguale a `sizeof(MINIDUMP_EXCEPTION)`.</span><span class="sxs-lookup"><span data-stu-id="11f04-120">The input buffer size is not equal to `sizeof(MINIDUMP_EXCEPTION)`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="11f04-121">Note</span><span class="sxs-lookup"><span data-stu-id="11f04-121">Remarks</span></span>  
 <span data-ttu-id="11f04-122">[MINIDUMP_EXCEPTION](http://msdn.microsoft.com/library/windows/desktop/ms680367.aspx) è una struttura definita in dbghelp. h e Imagehlp in Windows SDK.</span><span class="sxs-lookup"><span data-stu-id="11f04-122">[MINIDUMP_EXCEPTION](http://msdn.microsoft.com/library/windows/desktop/ms680367.aspx) is a structure defined in dbghelp.h and imagehlp.h in the Windows SDK.</span></span>  
  
 <span data-ttu-id="11f04-123">Questo metodo è implementato dal writer dell'applicazione di debug.</span><span class="sxs-lookup"><span data-stu-id="11f04-123">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="11f04-124">Requisiti</span><span class="sxs-lookup"><span data-stu-id="11f04-124">Requirements</span></span>  
 <span data-ttu-id="11f04-125">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="11f04-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="11f04-126">**Intestazione:** ClrData.idl, Clrdata. H</span><span class="sxs-lookup"><span data-stu-id="11f04-126">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="11f04-127">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="11f04-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="11f04-128">**Versioni di .NET framework:**[!INCLUDE[v451_update](../../../../includes/v451-update-md.md)]</span><span class="sxs-lookup"><span data-stu-id="11f04-128">**.NET Framework Versions:** [!INCLUDE[v451_update](../../../../includes/v451-update-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11f04-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="11f04-129">See Also</span></span>  
 [<span data-ttu-id="11f04-130">Interfaccia ICLRDataTarget3</span><span class="sxs-lookup"><span data-stu-id="11f04-130">ICLRDataTarget3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-interface.md)  
 [<span data-ttu-id="11f04-131">Metodo GetExceptionContextRecord</span><span class="sxs-lookup"><span data-stu-id="11f04-131">GetExceptionContextRecord Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptioncontextrecord-method.md)  
 [<span data-ttu-id="11f04-132">Metodo GetExceptionThreadID</span><span class="sxs-lookup"><span data-stu-id="11f04-132">GetExceptionThreadID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptionthreadid-method.md)