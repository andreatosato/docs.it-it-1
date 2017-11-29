---
title: ICorDebugType Interface1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugType
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugType
helpviewer_keywords: ICorDebugType interface [.NET Framework debugging]
ms.assetid: 94e02e31-67ea-4b00-8148-a46740a4571d
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9a25e72766e6647f820c9871e989d4b24db0bf26
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugtype-interface1"></a><span data-ttu-id="cd1c5-102">ICorDebugType Interface1</span><span class="sxs-lookup"><span data-stu-id="cd1c5-102">ICorDebugType Interface1</span></span>
<span data-ttu-id="cd1c5-103">Rappresenta un tipo di base o complesso (è definito dall'utente).</span><span class="sxs-lookup"><span data-stu-id="cd1c5-103">Represents a type, either basic or complex (that is, user-defined).</span></span> <span data-ttu-id="cd1c5-104">Se il tipo è generico, `ICorDebugType` rappresenta il tipo generico di cui è stata creata un'istanza.</span><span class="sxs-lookup"><span data-stu-id="cd1c5-104">If the type is generic, `ICorDebugType` represents the instantiated generic type.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="cd1c5-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="cd1c5-105">Methods</span></span>  
  
|<span data-ttu-id="cd1c5-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="cd1c5-106">Method</span></span>|<span data-ttu-id="cd1c5-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cd1c5-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="cd1c5-108">EnumerateTypeParameters (metodo)</span><span class="sxs-lookup"><span data-stu-id="cd1c5-108">EnumerateTypeParameters Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-enumeratetypeparameters-method.md)|<span data-ttu-id="cd1c5-109">Ottiene un puntatore a interfaccia a un'interfaccia ICorDebugTypeEnum che fa riferimento il tipo generico <xref:System.Type> parametri della classe a cui fa riferimento questo `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="cd1c5-109">Gets an interface pointer to an ICorDebugTypeEnum that references the generic <xref:System.Type> parameters of the class referenced by this `ICorDebugType`.</span></span>|  
|[<span data-ttu-id="cd1c5-110">GetBase (metodo)</span><span class="sxs-lookup"><span data-stu-id="cd1c5-110">GetBase Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getbase-method.md)|<span data-ttu-id="cd1c5-111">Ottiene un puntatore a interfaccia a un `ICorDebugType` che fa riferimento alla classe di base della classe a cui fa riferimento questo `ICorDebugType`, se presente.</span><span class="sxs-lookup"><span data-stu-id="cd1c5-111">Gets an interface pointer to an `ICorDebugType` that references the base class of the class referenced by this `ICorDebugType`, if one exists.</span></span>|  
|[<span data-ttu-id="cd1c5-112">GetClass (metodo)</span><span class="sxs-lookup"><span data-stu-id="cd1c5-112">GetClass Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getclass-method.md)|<span data-ttu-id="cd1c5-113">Ottiene un puntatore a interfaccia ICorDebugClass che fa riferimento al costruttore tipizzato di `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="cd1c5-113">Gets an interface pointer to an ICorDebugClass that references the typed constructor of this `ICorDebugType`.</span></span>|  
|[<span data-ttu-id="cd1c5-114">GetFirstTypeParameter (metodo)</span><span class="sxs-lookup"><span data-stu-id="cd1c5-114">GetFirstTypeParameter Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getfirsttypeparameter-method.md)|<span data-ttu-id="cd1c5-115">Ottiene un puntatore a interfaccia a un `ICorDebugType` che fa riferimento il primo generico <xref:System.Type> parametro del costruttore della classe a cui fa riferimento questo `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="cd1c5-115">Gets an interface pointer to an `ICorDebugType` that references the first generic <xref:System.Type> parameter for the constructor of the class referenced by this `ICorDebugType`.</span></span>|  
|[<span data-ttu-id="cd1c5-116">GetRank (metodo)</span><span class="sxs-lookup"><span data-stu-id="cd1c5-116">GetRank Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getrank-method.md)|<span data-ttu-id="cd1c5-117">Ottiene il numero di dimensioni in un tipo di matrice.</span><span class="sxs-lookup"><span data-stu-id="cd1c5-117">Gets the number of dimensions in an array type.</span></span>|  
|[<span data-ttu-id="cd1c5-118">GetStaticFieldValue (metodo)</span><span class="sxs-lookup"><span data-stu-id="cd1c5-118">GetStaticFieldValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getstaticfieldvalue-method.md)|<span data-ttu-id="cd1c5-119">Ottiene un puntatore a interfaccia a un oggetto ICorDebugValue che contiene il valore del campo statico a cui fa riferimento il campo specificato token stack frame specificato.</span><span class="sxs-lookup"><span data-stu-id="cd1c5-119">Gets an interface pointer to an ICorDebugValue that contains the value of the static field referenced by the specified field token in the specified stack frame.</span></span>|  
|[<span data-ttu-id="cd1c5-120">GetType (metodo)</span><span class="sxs-lookup"><span data-stu-id="cd1c5-120">GetType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md)|<span data-ttu-id="cd1c5-121">Ottiene un valore CorElementType che descrive il tipo nativo di common language runtime <xref:System.Type> a cui fa riferimento questo `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="cd1c5-121">Gets a CorElementType value that describes the native type of the common language runtime <xref:System.Type> referenced by this `ICorDebugType`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cd1c5-122">Note</span><span class="sxs-lookup"><span data-stu-id="cd1c5-122">Remarks</span></span>  
 <span data-ttu-id="cd1c5-123">Se il tipo è generico, `ICorDebugClass` rappresenta il tipo privo di istanze.</span><span class="sxs-lookup"><span data-stu-id="cd1c5-123">If the type is generic, `ICorDebugClass` represents the uninstantiated type.</span></span> <span data-ttu-id="cd1c5-124">Il `ICorDebugType` interfaccia rappresenta un tipo generico istanziato.</span><span class="sxs-lookup"><span data-stu-id="cd1c5-124">The `ICorDebugType` interface represents an instantiated generic type.</span></span> <span data-ttu-id="cd1c5-125">Ad esempio, Hashtable\<K, V > viene rappresentato da `ICorDebugClass`, mentre Hashtable\<Int32, String > viene rappresentato da `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="cd1c5-125">For example, Hashtable\<K, V> would be represented by `ICorDebugClass`, whereas Hashtable\<Int32, String> would be represented by `ICorDebugType`.</span></span>  
  
 <span data-ttu-id="cd1c5-126">I tipi non generici sono rappresentati da `ICorDebugClass` e `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="cd1c5-126">Non-generic types are represented by both `ICorDebugClass` and `ICorDebugType`.</span></span> <span data-ttu-id="cd1c5-127">L'interfaccia di quest'ultima è stato introdotto in .NET Framework versione 2.0 per gestire la creazione di istanze di tipo.</span><span class="sxs-lookup"><span data-stu-id="cd1c5-127">The latter interface was introduced in the .NET Framework version 2.0 to deal with type instantiation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cd1c5-128">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="cd1c5-128">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cd1c5-129">Requisiti</span><span class="sxs-lookup"><span data-stu-id="cd1c5-129">Requirements</span></span>  
 <span data-ttu-id="cd1c5-130">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cd1c5-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cd1c5-131">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="cd1c5-131">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cd1c5-132">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cd1c5-132">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cd1c5-133">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cd1c5-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd1c5-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cd1c5-134">See Also</span></span>  
 [<span data-ttu-id="cd1c5-135">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="cd1c5-135">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)