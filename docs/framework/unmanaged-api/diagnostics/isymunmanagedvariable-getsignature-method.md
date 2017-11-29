---
title: Metodo ISymUnmanagedVariable::GetSignature
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedVariable.GetSignature
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedVariable::GetSignature
helpviewer_keywords:
- GetSignature method, ISymUnmanagedVariable interface [.NET Framework debugging]
- ISymUnmanagedVariable::GetSignature method [.NET Framework debugging]
ms.assetid: 78c1ba28-a410-4360-805c-23a95408964a
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 1e29cd4a38e9abbe380b51b81fc2849b833d87e9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedvariablegetsignature-method"></a><span data-ttu-id="fb78d-102">Metodo ISymUnmanagedVariable::GetSignature</span><span class="sxs-lookup"><span data-stu-id="fb78d-102">ISymUnmanagedVariable::GetSignature Method</span></span>
<span data-ttu-id="fb78d-103">Ottiene la firma di questa variabile.</span><span class="sxs-lookup"><span data-stu-id="fb78d-103">Gets the signature of this variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb78d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fb78d-104">Syntax</span></span>  
  
```  
HRESULT GetSignature(  
    [in]  ULONG32  cSig,  
    [out] ULONG32  *pcSig,  
    [out, size_is(cSig),  
        length_is(*pcSig)] BYTE sig[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fb78d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="fb78d-105">Parameters</span></span>  
 `cSig`  
 <span data-ttu-id="fb78d-106">[in] La lunghezza del buffer a cui punta il `sig` parametro.</span><span class="sxs-lookup"><span data-stu-id="fb78d-106">[in] The length of the buffer pointed to by the `sig` parameter.</span></span>  
  
 `pcSig`  
 <span data-ttu-id="fb78d-107">[out] Un puntatore a un `ULONG32` che riceve le dimensioni, in caratteri, del buffer necessaria per contenere la firma.</span><span class="sxs-lookup"><span data-stu-id="fb78d-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the signature.</span></span>  
  
 `sig`  
 <span data-ttu-id="fb78d-108">[out] Buffer che archivia la firma.</span><span class="sxs-lookup"><span data-stu-id="fb78d-108">[out] The buffer that stores the signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fb78d-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="fb78d-109">Return Value</span></span>  
 <span data-ttu-id="fb78d-110">S_OK se il metodo ha esito positivo. in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="fb78d-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fb78d-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="fb78d-111">Requirements</span></span>  
 <span data-ttu-id="fb78d-112">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="fb78d-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb78d-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fb78d-113">See Also</span></span>  
 [<span data-ttu-id="fb78d-114">ISymUnmanagedVariable (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="fb78d-114">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)