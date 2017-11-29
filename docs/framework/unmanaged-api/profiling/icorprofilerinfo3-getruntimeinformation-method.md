---
title: Metodo ICorProfilerInfo3::GetRuntimeInformation
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo3.GetRuntimeInformation Method
api_location: Mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo3::GetRuntimeInformation
helpviewer_keywords:
- GetRuntimeInformation method [.NET Framework profiling]
- ICorProfilerInfo3::GetRuntimeInformation method [.NET Framework profiling]
ms.assetid: 4400fb8c-0407-4791-8557-f011fd2aee51
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: a18f0604b1585ffb1dd8230c289bcd95bfa3dfae
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerinfo3getruntimeinformation-method"></a><span data-ttu-id="c3f15-102">Metodo ICorProfilerInfo3::GetRuntimeInformation</span><span class="sxs-lookup"><span data-stu-id="c3f15-102">ICorProfilerInfo3::GetRuntimeInformation Method</span></span>
<span data-ttu-id="c3f15-103">Vengono fornite informazioni di versione di common language runtime (CLR) che si sta profilando.</span><span class="sxs-lookup"><span data-stu-id="c3f15-103">Provides version information about the common language runtime (CLR) that is being profiled.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3f15-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c3f15-104">Syntax</span></span>  
  
```  
HRESULT GetRuntimeInformation(  
       [out] USHORT *pClrInstanceId,  
       [out] COR_PRF_RUNTIME_TYPE *pRuntimeType,  
       [out] USHORT *pMajorVersion,  
       [out] USHORT *pMinorVersion,  
       [out] USHORT *pBuildNumber,  
       [out] USHORT *pQFEVersion,  
       [in]  ULONG  cchVersionString,  
       [out] ULONG  *pcchVersionString,  
       [out, size_is(cchVersionString), length_is(*pcchVersionString)]  
                   WCHAR  szVersionString[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c3f15-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="c3f15-105">Parameters</span></span>  
 `pClrInstanceId`  
 <span data-ttu-id="c3f15-106">[out] ID rappresentativo di un'istanza CLR in esecuzione in un processo.</span><span class="sxs-lookup"><span data-stu-id="c3f15-106">[out] The representative ID of a running CLR instance in a process.</span></span> <span data-ttu-id="c3f15-107">Questo è lo stesso come il `ClrInstanceID` che segnala la traccia eventi per l'evento di avvio di Windows (ETW).</span><span class="sxs-lookup"><span data-stu-id="c3f15-107">This is the same as the `ClrInstanceID` that the event tracing for Windows (ETW) startup event reports.</span></span>  
  
 `pRuntimeType`  
 <span data-ttu-id="c3f15-108">[out] Il tipo di runtime.</span><span class="sxs-lookup"><span data-stu-id="c3f15-108">[out] The runtime type.</span></span> <span data-ttu-id="c3f15-109">Questo parametro restituisce `COR_PRF_DESKTOP_CLR` per la versione desktop di CLR, o `COR_PRF_CORE_CLR` per la versione principale di CLR utilizzata in Silverlight.</span><span class="sxs-lookup"><span data-stu-id="c3f15-109">This parameter returns `COR_PRF_DESKTOP_CLR` for the desktop version of the CLR, or `COR_PRF_CORE_CLR` for the core version of the CLR used in Silverlight.</span></span>  
  
 `pMajorVersion`  
 <span data-ttu-id="c3f15-110">[out] Il numero di versione principale di CLR.</span><span class="sxs-lookup"><span data-stu-id="c3f15-110">[out] The major version number of the CLR.</span></span>  
  
 `pMinorVersion`  
 <span data-ttu-id="c3f15-111">[out] Il numero di versione secondaria di CLR.</span><span class="sxs-lookup"><span data-stu-id="c3f15-111">[out] The minor version number of the CLR.</span></span>  
  
 `pBuildVersion`  
 <span data-ttu-id="c3f15-112">[out] Il numero di versione di build di Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="c3f15-112">[out] The build version number of the CLR.</span></span>  
  
 `pQFEVersion`  
 <span data-ttu-id="c3f15-113">[out] Il numero di versione di CLR associato a un aggiornamento software.</span><span class="sxs-lookup"><span data-stu-id="c3f15-113">[out] The version number of the CLR that is associated with a software update.</span></span>  
  
 `cchVersionString`  
 <span data-ttu-id="c3f15-114">[in] Lunghezza, espressa in caratteri, del buffer che `szVersionString` punta a.</span><span class="sxs-lookup"><span data-stu-id="c3f15-114">[in] The length, in characters, of the buffer that `szVersionString` points to.</span></span>  
  
 `pcchVersionString`  
 <span data-ttu-id="c3f15-115">[out] Lunghezza, espressa in caratteri, di `szVersionString`.</span><span class="sxs-lookup"><span data-stu-id="c3f15-115">[out] The length, in characters, of `szVersionString`.</span></span>  
  
 `szVersionString`  
 <span data-ttu-id="c3f15-116">[out] La stringa di versione CLR.</span><span class="sxs-lookup"><span data-stu-id="c3f15-116">[out] The CLR version string.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c3f15-117">Note</span><span class="sxs-lookup"><span data-stu-id="c3f15-117">Remarks</span></span>  
 <span data-ttu-id="c3f15-118">È possibile passare null per qualsiasi parametro.</span><span class="sxs-lookup"><span data-stu-id="c3f15-118">You may pass null for any parameter.</span></span> <span data-ttu-id="c3f15-119">Tuttavia, `pcchVersionString` non può essere null a meno che non `szVersionString` è null.</span><span class="sxs-lookup"><span data-stu-id="c3f15-119">However, `pcchVersionString` cannot be null unless `szVersionString` is also null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c3f15-120">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c3f15-120">Requirements</span></span>  
 <span data-ttu-id="c3f15-121">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c3f15-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c3f15-122">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c3f15-122">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c3f15-123">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c3f15-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c3f15-124">**Versioni di .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c3f15-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3f15-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c3f15-125">See Also</span></span>  
 [<span data-ttu-id="c3f15-126">ICorProfilerInfo3 (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="c3f15-126">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)  
 [<span data-ttu-id="c3f15-127">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="c3f15-127">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="c3f15-128">Profilatura</span><span class="sxs-lookup"><span data-stu-id="c3f15-128">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)