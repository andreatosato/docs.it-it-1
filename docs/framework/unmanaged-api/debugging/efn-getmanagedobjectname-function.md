---
title: Funzione _EFN_GetManagedObjectName
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: _EFN_GetManagedObjectName
api_location: mscordbi.dll
api_type: COM
f1_keywords: _EFN_GetManagedObjectName
helpviewer_keywords: _EFN_GetManagedObjectName function [.NET Framework debugging]
ms.assetid: 6e7c6bee-7ced-495f-bf6c-2a5f0c716f7e
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 80e36f6c60c4c305cad9176cd7f185d8b6d2fdf2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="efngetmanagedobjectname-function"></a><span data-ttu-id="4657f-102">Funzione _EFN_GetManagedObjectName</span><span class="sxs-lookup"><span data-stu-id="4657f-102">_EFN_GetManagedObjectName Function</span></span>
<span data-ttu-id="4657f-103">Ottiene il nome di un tipo utilizzando il puntatore all'oggetto gestito fornito.</span><span class="sxs-lookup"><span data-stu-id="4657f-103">Gets the name of a type using the provided managed object pointer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4657f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4657f-104">Syntax</span></span>  
  
```  
HRESULT _EFN_GetManagedObjectName(  
    [in]  PDEBUG_CLIENT  Client,  
    [in]  ULONG64        objAddr,  
    [out] __out_ecount(cbName) PSTR szName,  
    [out] ULONG          cbName  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4657f-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="4657f-105">Parameters</span></span>  
 `Client`  
 <span data-ttu-id="4657f-106">[in] Puntatore al client di debug.</span><span class="sxs-lookup"><span data-stu-id="4657f-106">[in] A pointer to the debug client.</span></span>  
  
 `objAddr`  
 <span data-ttu-id="4657f-107">[in] Puntatore a un oggetto gestito.</span><span class="sxs-lookup"><span data-stu-id="4657f-107">[in] A managed object pointer.</span></span>  
  
 <span data-ttu-id="4657f-108">szName</span><span class="sxs-lookup"><span data-stu-id="4657f-108">szName</span></span>  
 <span data-ttu-id="4657f-109">[out] Il nome del tipo.</span><span class="sxs-lookup"><span data-stu-id="4657f-109">[out] The name of the type.</span></span>  
  
 `cbName`  
 <span data-ttu-id="4657f-110">[out] Il numero di caratteri disponibili nel buffer di stringa.</span><span class="sxs-lookup"><span data-stu-id="4657f-110">[out] The number of characters available in the string buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4657f-111">Note</span><span class="sxs-lookup"><span data-stu-id="4657f-111">Remarks</span></span>  
 <span data-ttu-id="4657f-112">Se non è presente nessun codice gestito sul thread attualmente in contesto, la funzione restituisce HRESULT SOS_E_NOMANAGEDCODE con un valore funzionalità 0xa0 e un codice di errore di 0x1000.</span><span class="sxs-lookup"><span data-stu-id="4657f-112">If there is no managed code on the thread currently in context, the function returns HRESULT SOS_E_NOMANAGEDCODE with a facility value of 0xa0 and an error code of 0x1000.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4657f-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4657f-113">Requirements</span></span>  
 <span data-ttu-id="4657f-114">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4657f-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4657f-115">**Intestazione:** SOS_Stacktrace. h</span><span class="sxs-lookup"><span data-stu-id="4657f-115">**Header:** SOS_Stacktrace.h</span></span>  
  
 <span data-ttu-id="4657f-116">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4657f-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4657f-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4657f-117">See Also</span></span>  
 [<span data-ttu-id="4657f-118">Funzioni statiche globali di debug</span><span class="sxs-lookup"><span data-stu-id="4657f-118">Debugging Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)