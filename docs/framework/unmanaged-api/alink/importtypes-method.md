---
title: Metodo ImportTypes
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IALink.ImportTypes
api_location: alink.dll
api_type: COM
f1_keywords: ImportTypes
helpviewer_keywords: ImportTypes method
ms.assetid: 351d4b4c-c939-486d-9471-51914a55f471
topic_type: apiref
caps.latest.revision: "5"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: b8fb83d4e3244010550cb21fedbc6c3b1c5d60d5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="importtypes-method"></a><span data-ttu-id="ccb9b-102">Metodo ImportTypes</span><span class="sxs-lookup"><span data-stu-id="ccb9b-102">ImportTypes Method</span></span>
<span data-ttu-id="ccb9b-103">Avvia l'importazione di tipi da ogni ambito importato tramite [metodo ImportFile](../../../../docs/framework/unmanaged-api/alink/importfile-method.md).</span><span class="sxs-lookup"><span data-stu-id="ccb9b-103">Initiates the importing of types from each scope imported via [ImportFile Method](../../../../docs/framework/unmanaged-api/alink/importfile-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ccb9b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ccb9b-104">Syntax</span></span>  
  
```  
HRESULT ImportTypes(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    HALINKENUM* phEnum,  
    IMetaDataImport** ppImportScope,  
    DWORD* pdwCountOfTypes  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ccb9b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ccb9b-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="ccb9b-106">ID dell'assembly da importare.</span><span class="sxs-lookup"><span data-stu-id="ccb9b-106">ID of the assembly to import to.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="ccb9b-107">ID del file da importare.</span><span class="sxs-lookup"><span data-stu-id="ccb9b-107">ID of the file to import from.</span></span>  
  
 `dwScope`  
 <span data-ttu-id="ccb9b-108">Ambito in base zero da importare.</span><span class="sxs-lookup"><span data-stu-id="ccb9b-108">Zero-based scope to import.</span></span>  
  
 `phEnum`  
 <span data-ttu-id="ccb9b-109">Riceve l'handle dell'enumeratore per i tipi in questo ambito.</span><span class="sxs-lookup"><span data-stu-id="ccb9b-109">Receives enumerator handle for the types in this scope.</span></span>  
  
 `ppImportScope`  
 <span data-ttu-id="ccb9b-110">Facoltativamente riceve [interfaccia IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interfaccia.</span><span class="sxs-lookup"><span data-stu-id="ccb9b-110">Optionally receives [IMetaDataImport Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interface.</span></span>  
  
 `pdwCountOfTypes`  
 <span data-ttu-id="ccb9b-111">Facoltativamente, riceve il numero dei tipi nell'ambito specificato.</span><span class="sxs-lookup"><span data-stu-id="ccb9b-111">Optionally receives count of types in the indicated scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ccb9b-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="ccb9b-112">Return Value</span></span>  
 <span data-ttu-id="ccb9b-113">Se il metodo ha esito positivo, restituisce S_OK.</span><span class="sxs-lookup"><span data-stu-id="ccb9b-113">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ccb9b-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ccb9b-114">Requirements</span></span>  
 <span data-ttu-id="ccb9b-115">Richiede alink.h</span><span class="sxs-lookup"><span data-stu-id="ccb9b-115">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ccb9b-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ccb9b-116">See Also</span></span>  
 [<span data-ttu-id="ccb9b-117">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="ccb9b-117">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="ccb9b-118">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="ccb9b-118">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="ccb9b-119">ALink (API)</span><span class="sxs-lookup"><span data-stu-id="ccb9b-119">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)