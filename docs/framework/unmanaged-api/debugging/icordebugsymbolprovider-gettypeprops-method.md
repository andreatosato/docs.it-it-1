---
title: Metodo ICorDebugSymbolProvider::GetTypeProps
ms.date: 03/30/2017
ms.assetid: 35ac4140-91ea-4c77-b1c4-1daf41986ca5
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3398e01912309c057cd1e01e8fc0af6c62f976bf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33421600"
---
# <a name="icordebugsymbolprovidergettypeprops-method"></a>Metodo ICorDebugSymbolProvider::GetTypeProps
Restituisce informazioni sulle proprietà di un tipo, ad esempio il numero di firma dei parametri generici, dato un indirizzo RVA (Relative Virtual Address) in un oggetto vtable.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetTypeProps(  
   [in]  ULONG32 vtableRva,  
   [in]  ULONG32 cbSignature,  
   [out] ULONG32 *pcbSignature,  
   [out, size_is(cbSignature), length_is(*pcbSignature)] BYTE signature[]  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `tableRva`  
 [in] Indirizzo RVA (Relative Virtual Address) in un oggetto vtable  
  
 `cbSignature`  
 [in] Dimensione della matrice `signature`. Vedere la sezione Osservazioni.  
  
 `pcbSignature`  
 [out] [out] Puntatore alla dimensione della matrice `signature` restituita.  
  
 `signature`  
 [out] Buffer contenente le firme typespec di tutti i parametri generici.  
  
## <a name="remarks"></a>Note  
 Per ottenere la dimensione del tipo richiesta `signature` matrice, impostare il `cbSignature` argomento su 0 e `signature` a **null**. Quando il metodo viene restituito, `pcbSignature` conterrà il numero di byte necessari per la matrice `signature`.  
  
> [!NOTE]
>  Questo metodo è disponibile solo con .NET Native.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cordebug. idl, Cordebug. H  
  
 **Libreria:** CorGuids. lib  
  
 **Versioni di .NET framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Metodo GetMethodProps](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getmethodprops-method.md)  
 [Interfaccia ICorDebugSymbolProvider](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)  
 [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
