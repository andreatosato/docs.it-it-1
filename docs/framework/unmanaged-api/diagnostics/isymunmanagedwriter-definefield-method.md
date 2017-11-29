---
title: Metodo ISymUnmanagedWriter::DefineField
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedWriter.DefineField
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedWriter::DefineField
helpviewer_keywords:
- ISymUnmanagedWriter::DefineField method [.NET Framework debugging]
- DefineField method, ISymUnmanagedWriter interface [.NET Framework debugging]
ms.assetid: c6a1f797-dbf4-40f5-ab99-d9b4bfb26148
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c44c4ba4a2fd8959299bce6c9f3b4dc361174922
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedwriterdefinefield-method"></a><span data-ttu-id="00f19-102">Metodo ISymUnmanagedWriter::DefineField</span><span class="sxs-lookup"><span data-stu-id="00f19-102">ISymUnmanagedWriter::DefineField Method</span></span>
<span data-ttu-id="00f19-103">Definisce una singola variabile che non è presente all'interno di un metodo.</span><span class="sxs-lookup"><span data-stu-id="00f19-103">Defines a single variable that is not within a method.</span></span> <span data-ttu-id="00f19-104">Questo metodo è usato per alcuni campi nelle classi, i campi di bit e così via.</span><span class="sxs-lookup"><span data-stu-id="00f19-104">This method is used for certain fields in classes, bit fields, and so on.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00f19-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="00f19-105">Syntax</span></span>  
  
```  
HRESULT DefineField(  
    [in] mdTypeDef    parent,  
    [in] const WCHAR  *name,  
    [in] ULONG32      attributes,  
    [in] ULONG32      cSig,  
    [in, size_is(cSig)] unsigned char signature[],  
    [in] ULONG32      addrKind,  
    [in] ULONG32      addr1,  
    [in] ULONG32      addr2,  
    [in] ULONG32      addr3);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="00f19-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="00f19-106">Parameters</span></span>  
 `parent`  
 <span data-ttu-id="00f19-107">[in] Il tipo di metadati o il metodo token.</span><span class="sxs-lookup"><span data-stu-id="00f19-107">[in] The metadata type or method token.</span></span>  
  
 `name`  
 <span data-ttu-id="00f19-108">[in] Il nome del campo.</span><span class="sxs-lookup"><span data-stu-id="00f19-108">[in] The field name.</span></span>  
  
 `attributes`  
 <span data-ttu-id="00f19-109">[in] Gli attributi di campo.</span><span class="sxs-lookup"><span data-stu-id="00f19-109">[in] The field attributes.</span></span>  
  
 `cSig`  
 <span data-ttu-id="00f19-110">[in] Oggetto `ULONG32` che rappresenta la dimensione, in caratteri, del buffer necessaria per contenere la firma del campo.</span><span class="sxs-lookup"><span data-stu-id="00f19-110">[in] A `ULONG32` that is the size, in characters, of the buffer required to contain the field signature.</span></span>  
  
 `signature`  
 <span data-ttu-id="00f19-111">[in] Matrice di firme di campo.</span><span class="sxs-lookup"><span data-stu-id="00f19-111">[in] The array of field signatures.</span></span>  
  
 `addrKind`  
 <span data-ttu-id="00f19-112">[in] Il tipo di indirizzo.</span><span class="sxs-lookup"><span data-stu-id="00f19-112">[in] The address type.</span></span>  
  
 `addr1`  
 <span data-ttu-id="00f19-113">[in] Il primo indirizzo relativo al campo specificato.</span><span class="sxs-lookup"><span data-stu-id="00f19-113">[in] The first address for the field specification.</span></span>  
  
 `addr2`  
 <span data-ttu-id="00f19-114">[in] Il secondo indirizzo per la specifica del campo.</span><span class="sxs-lookup"><span data-stu-id="00f19-114">[in] The second address for the field specification.</span></span>  
  
 `addr3`  
 <span data-ttu-id="00f19-115">[in] Terzo indirizzo relativo al campo specificato.</span><span class="sxs-lookup"><span data-stu-id="00f19-115">[in] The third address for the field specification.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="00f19-116">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="00f19-116">Return Value</span></span>  
 <span data-ttu-id="00f19-117">S_OK se il metodo ha esito positivo. in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="00f19-117">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="00f19-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="00f19-118">Requirements</span></span>  
 <span data-ttu-id="00f19-119">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="00f19-119">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00f19-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="00f19-120">See Also</span></span>  
 [<span data-ttu-id="00f19-121">ISymUnmanagedWriter (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="00f19-121">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)