---
title: Metodo IMetaDataTables::GetRow
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataTables.GetRow
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataTables::GetRow
helpviewer_keywords:
- IMetaDataTables::GetRow method [.NET Framework metadata]
- GetRow method [.NET Framework metadata]
ms.assetid: a7408d51-0bce-45a2-b58f-da4660bbc039
topic_type: apiref
caps.latest.revision: "16"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 281824ace7696ab0fc6b3a96e0cdf307a9419313
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="imetadatatablesgetrow-method"></a><span data-ttu-id="57933-102">Metodo IMetaDataTables::GetRow</span><span class="sxs-lookup"><span data-stu-id="57933-102">IMetaDataTables::GetRow Method</span></span>
<span data-ttu-id="57933-103">Ottiene la riga in corrispondenza dell'indice di riga specificata, nella tabella in corrispondenza dell'indice di tabella specificata.</span><span class="sxs-lookup"><span data-stu-id="57933-103">Gets the row at the specified row index, in the table at the specified table index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="57933-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="57933-104">Syntax</span></span>  
  
```  
HRESULT GetRow (   
    [in]  ULONG   ixTbl,  
    [in]  ULONG   rid,  
    [out] void    **ppRow  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="57933-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="57933-105">Parameters</span></span>  
 `ixTbl`  
 <span data-ttu-id="57933-106">[in] Indice della tabella da cui verrà recuperata la riga.</span><span class="sxs-lookup"><span data-stu-id="57933-106">[in] The index of the table from which the row will be retrieved.</span></span>  
  
 `rid`  
 <span data-ttu-id="57933-107">[in] Indice della riga da ottenere.</span><span class="sxs-lookup"><span data-stu-id="57933-107">[in] The index of the row to get.</span></span>  
  
 `ppRow`  
 <span data-ttu-id="57933-108">[out] Un puntatore a un puntatore alla riga.</span><span class="sxs-lookup"><span data-stu-id="57933-108">[out] A pointer to a pointer to the row.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="57933-109">Note</span><span class="sxs-lookup"><span data-stu-id="57933-109">Remarks</span></span>  
 <span data-ttu-id="57933-110">Non è consigliabile l'utilizzo di questo metodo, perché non restituisce risultati coerenti.</span><span class="sxs-lookup"><span data-stu-id="57933-110">We do not recommend the use of this method, because it does not return consistent results.</span></span> <span data-ttu-id="57933-111">Per informazioni sulla tabella dei GUID, vedere la documentazione di Common Language Infrastructure (CLI), in particolare "partizione II: metadati definizione e la semantica".</span><span class="sxs-lookup"><span data-stu-id="57933-111">For information about the GUID table, see the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics".</span></span> <span data-ttu-id="57933-112">La documentazione è disponibile online; vedere [ECMA C# and Common Language Infrastructure Standards](http://go.microsoft.com/fwlink/?LinkID=99212) (ECMA C# e standard di Common Language Infrastructure) in MSDN e [Standard ECMA-335 - Common Language Infrastructure (CLI)](http://go.microsoft.com/fwlink/?LinkID=65552) nel sito Web internazionale Ecma.</span><span class="sxs-lookup"><span data-stu-id="57933-112">The documentation is available online; see [ECMA C# and Common Language Infrastructure Standards](http://go.microsoft.com/fwlink/?LinkID=99212) on MSDN and [Standard ECMA-335 - Common Language Infrastructure (CLI)](http://go.microsoft.com/fwlink/?LinkID=65552) on the Ecma International Web site.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="57933-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="57933-113">Requirements</span></span>  
 <span data-ttu-id="57933-114">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="57933-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="57933-115">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="57933-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="57933-116">**Libreria:** usata come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="57933-116">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="57933-117">**Versioni di .NET framework**  [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="57933-117">**.NET Framework Versions**  [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57933-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="57933-118">See Also</span></span>  
 [<span data-ttu-id="57933-119">IMetaDataTables (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="57933-119">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)  
 [<span data-ttu-id="57933-120">IMetaDataTables2 (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="57933-120">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)