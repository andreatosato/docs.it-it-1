---
title: Metodo ICorDebugObjectValue::GetFieldValue
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugObjectValue.GetFieldValue
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugObjectValue::GetFieldValue
helpviewer_keywords:
- ICorDebugObjectValue::GetFieldValue method [.NET Framework debugging]
- GetFieldValue method [.NET Framework debugging]
ms.assetid: c96770b0-3e09-47bb-bd29-20353b043459
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 33c3f368d9b78b899f54c989427ea1f660346487
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugobjectvaluegetfieldvalue-method"></a><span data-ttu-id="bf483-102">Metodo ICorDebugObjectValue::GetFieldValue</span><span class="sxs-lookup"><span data-stu-id="bf483-102">ICorDebugObjectValue::GetFieldValue Method</span></span>
<span data-ttu-id="bf483-103">Ottiene il valore del campo specificato della classe specificata per il valore dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="bf483-103">Gets the value of the specified field of the specified class for this object value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf483-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bf483-104">Syntax</span></span>  
  
```  
HRESULT GetFieldValue (  
    [in]  ICorDebugClass     *pClass,  
    [in]  mdFieldDef         fieldDef,  
    [out] ICorDebugValue     **ppValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bf483-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="bf483-105">Parameters</span></span>  
 `pClass`  
 <span data-ttu-id="bf483-106">[in] Un puntatore a un oggetto "ICorDebugClass" che rappresenta la classe per cui ottenere il valore del campo.</span><span class="sxs-lookup"><span data-stu-id="bf483-106">[in] A pointer to an "ICorDebugClass" object that represents the class for which to get the field value.</span></span>  
  
 `fieldDef`  
 <span data-ttu-id="bf483-107">[in] Un `mdFieldDef` token che fa riferimento ai metadati che descrivono il campo.</span><span class="sxs-lookup"><span data-stu-id="bf483-107">[in] An `mdFieldDef` token that references the metadata describing the field.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="bf483-108">[out] Un puntatore a un oggetto "ICorDebugValue" che rappresenta il valore del campo specificato.</span><span class="sxs-lookup"><span data-stu-id="bf483-108">[out] A pointer to an "ICorDebugValue" object that represents the value of the specified field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bf483-109">Note</span><span class="sxs-lookup"><span data-stu-id="bf483-109">Remarks</span></span>  
 <span data-ttu-id="bf483-110">La classe, specificata nel `pClass` parametro deve essere nella gerarchia di classe del valore dell'oggetto e il campo deve essere un campo di tale classe.</span><span class="sxs-lookup"><span data-stu-id="bf483-110">The class, specified in the `pClass` parameter, must be in the hierarchy of the object value's class, and the field must be a field of that class.</span></span>  
  
 <span data-ttu-id="bf483-111">Il `GetFieldValue` metodo avrà comunque esito positivo per oggetti e le classi generiche.</span><span class="sxs-lookup"><span data-stu-id="bf483-111">The `GetFieldValue` method will still succeed for generic objects and generic classes.</span></span> <span data-ttu-id="bf483-112">Ad esempio, se MyDictionary\<V > eredita dal dizionario\<stringa, V >, e il valore dell'oggetto è di tipo MyDictionary\<int32 >, passando il `ICorDebugClass` oggetto per il dizionario\<K, V > verrà ottenere correttamente un campo del dizionario\<string, int32 >.</span><span class="sxs-lookup"><span data-stu-id="bf483-112">For example, if MyDictionary\<V> inherits from Dictionary\<string,V>, and the object value is of type MyDictionary\<int32>, passing the `ICorDebugClass` object for Dictionary\<K,V> will successfully get a field of Dictionary\<string,int32>.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bf483-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="bf483-113">Requirements</span></span>  
 <span data-ttu-id="bf483-114">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bf483-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bf483-115">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="bf483-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bf483-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bf483-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bf483-117">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bf483-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf483-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bf483-118">See Also</span></span>  
    
 