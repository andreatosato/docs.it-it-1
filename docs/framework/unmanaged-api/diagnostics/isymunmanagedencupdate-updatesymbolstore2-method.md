---
title: Metodo ISymUnmanagedENCUpdate::UpdateSymbolStore2
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedENCUpdate.UpdateSymbolStore2
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedENCUpdate::UpdateSymbolStore2
helpviewer_keywords:
- ISymUnmanagedENCUpdate::UpdateSymbolStore2 method [.NET Framework debugging]
- UpdateSymbolStore2 method [.NET Framework debugging]
ms.assetid: 35588317-6184-485c-ab41-4b15fc1765d9
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 1c0ff6d48bc749b1d8850f94fb1dc1adf3de8e37
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedencupdateupdatesymbolstore2-method"></a><span data-ttu-id="f6aee-102">Metodo ISymUnmanagedENCUpdate::UpdateSymbolStore2</span><span class="sxs-lookup"><span data-stu-id="f6aee-102">ISymUnmanagedENCUpdate::UpdateSymbolStore2 Method</span></span>
<span data-ttu-id="f6aee-103">Consente a un compilatore di omettere le funzioni che non sono state modificate dal flusso di programma (PDB) di database, purché le informazioni sulla riga soddisfa i requisiti.</span><span class="sxs-lookup"><span data-stu-id="f6aee-103">Allows a compiler to omit functions that have not been modified from the program database (PDB) stream, provided the line information meets the requirements.</span></span> <span data-ttu-id="f6aee-104">Le informazioni sulla riga corretto può essere determinati con le informazioni sulla riga PDB precedente e un delta per tutte le righe nella funzione.</span><span class="sxs-lookup"><span data-stu-id="f6aee-104">The correct line information can be determined with the old PDB line information and one delta for all lines in the function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6aee-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f6aee-105">Syntax</span></span>  
  
```  
HRESULT UpdateSymbolStore2(  
    [in]  IStream      *pIStream,  
    [in]  SYMLINEDELTA* pDeltaLines,  
    [in]  ULONG         cDeltaLines);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f6aee-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="f6aee-106">Parameters</span></span>  
 `pIStream`  
 <span data-ttu-id="f6aee-107">[in] Un puntatore a un <xref:IStream> che contiene le informazioni sulla riga.</span><span class="sxs-lookup"><span data-stu-id="f6aee-107">[in] A pointer to an <xref:IStream> that contains the line information.</span></span>  
  
 `pDeltaLines`  
 <span data-ttu-id="f6aee-108">[in] Un puntatore a un [SYMLINEDELTA](../../../../docs/framework/unmanaged-api/diagnostics/symlinedelta-structure.md) struttura che contiene le righe che sono stati modificati.</span><span class="sxs-lookup"><span data-stu-id="f6aee-108">[in] A pointer to a [SYMLINEDELTA](../../../../docs/framework/unmanaged-api/diagnostics/symlinedelta-structure.md) structure that contains the lines that have changed.</span></span>  
  
 `cDeltaLines`  
 <span data-ttu-id="f6aee-109">[in] Oggetto `ULONG` che rappresenta il numero di righe che sono stati modificati.</span><span class="sxs-lookup"><span data-stu-id="f6aee-109">[in] A `ULONG` that represents the number of lines that have changed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f6aee-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="f6aee-110">Return Value</span></span>  
 <span data-ttu-id="f6aee-111">S_OK se il metodo ha esito positivo. in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="f6aee-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f6aee-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f6aee-112">Requirements</span></span>  
 <span data-ttu-id="f6aee-113">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="f6aee-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6aee-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f6aee-114">See Also</span></span>  
 [<span data-ttu-id="f6aee-115">ISymUnmanagedENCUpdate (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="f6aee-115">ISymUnmanagedENCUpdate Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-interface.md)