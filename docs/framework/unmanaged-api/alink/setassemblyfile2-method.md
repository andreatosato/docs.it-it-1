---
title: Metodo SetAssemblyFile2
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IALink2.SetAssemblyFile2
api_location: alink.dll
api_type: COM
f1_keywords: SetAssemblyFile2
helpviewer_keywords: SetAssemblyFile2 method
ms.assetid: eedb9125-1ef1-4000-abfc-7de86e5a1f17
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 7363a8f633d5f447f72e27ba03055f589564bdd2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="setassemblyfile2-method"></a><span data-ttu-id="b13df-102">Metodo SetAssemblyFile2</span><span class="sxs-lookup"><span data-stu-id="b13df-102">SetAssemblyFile2 Method</span></span>
<span data-ttu-id="b13df-103">Imposta il nome e le opzioni per un nuovo assembly.</span><span class="sxs-lookup"><span data-stu-id="b13df-103">Sets the name of and options for a new assembly.</span></span> <span data-ttu-id="b13df-104">Non chiamare questo metodo quando si creano moduli non associati.</span><span class="sxs-lookup"><span data-stu-id="b13df-104">Do not call this method when you produce unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b13df-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b13df-105">Syntax</span></span>  
  
```  
HRESULT SetAssemblyFile2(  
    LPCWSTR pszFilename,  
    IMetaDataEmit2* pEmitter,  
    AssemblyFlags   afFlags,  
    mdAssembly* pAssemblyID  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b13df-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="b13df-106">Parameters</span></span>  
 `pszFilename`  
 <span data-ttu-id="b13df-107">Nome del file manifesto.</span><span class="sxs-lookup"><span data-stu-id="b13df-107">Name of manifest file.</span></span>  
  
 `pEmitter`  
 <span data-ttu-id="b13df-108">[Interfaccia IMetaDataEmit2](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md) interfaccia per il file.</span><span class="sxs-lookup"><span data-stu-id="b13df-108">[IMetaDataEmit2 Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md) interface for this file.</span></span>  
  
 `afFlags`  
 <span data-ttu-id="b13df-109">Opzioni rappresentate da [enumerazione AssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/assemblyflags-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="b13df-109">Options represented by [AssemblyFlags Enumeration](../../../../docs/framework/unmanaged-api/metadata/assemblyflags-enumeration.md).</span></span>  
  
 `pAssemblyID`  
 <span data-ttu-id="b13df-110">Riceve l'ID univoco per l'assembly viene costruito.</span><span class="sxs-lookup"><span data-stu-id="b13df-110">Receives unique ID for the assembly being constructed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b13df-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="b13df-111">Return Value</span></span>  
 <span data-ttu-id="b13df-112">Se il metodo ha esito positivo, restituisce S_OK.</span><span class="sxs-lookup"><span data-stu-id="b13df-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b13df-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b13df-113">Requirements</span></span>  
 <span data-ttu-id="b13df-114">Richiede alink.h.</span><span class="sxs-lookup"><span data-stu-id="b13df-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b13df-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b13df-115">See Also</span></span>  
 [<span data-ttu-id="b13df-116">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="b13df-116">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="b13df-117">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="b13df-117">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="b13df-118">ALink (API)</span><span class="sxs-lookup"><span data-stu-id="b13df-118">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)