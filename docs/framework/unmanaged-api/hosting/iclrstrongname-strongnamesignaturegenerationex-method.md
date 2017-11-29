---
title: Metodo ICLRStrongName::StrongNameSignatureGenerationEx
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRStrongName.StrongNameSignatureGenerationEx
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRStrongName::StrongNameSignatureGenerationEx
helpviewer_keywords:
- ICLRStrongName::StrongNameSignatureGenerationEx method [.NET Framework hosting]
- StrongNameSignatureGenerationEx method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: c3f34584-c6e2-41fd-bb44-e44da8546309
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 80b0527be680ed755366f77593e4dc7e1dea830c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="iclrstrongnamestrongnamesignaturegenerationex-method"></a><span data-ttu-id="1a475-102">Metodo ICLRStrongName::StrongNameSignatureGenerationEx</span><span class="sxs-lookup"><span data-stu-id="1a475-102">ICLRStrongName::StrongNameSignatureGenerationEx Method</span></span>
<span data-ttu-id="1a475-103">Genera una firma nome sicuro per l'assembly specificato, in base ai flag specificati.</span><span class="sxs-lookup"><span data-stu-id="1a475-103">Generates a strong name signature for the specified assembly, according to the specified flags.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1a475-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1a475-104">Syntax</span></span>  
  
```  
HRESULT StrongNameSignatureGenerationEx (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbSignatureBlob,  
    [out] ULONG     *pcbSignatureBlob,  
    [in]  DWORD     dwFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1a475-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="1a475-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="1a475-106">[in] Il percorso del file che contiene il manifesto dell'assembly per il quale verrà generata la firma nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="1a475-106">[in] The path to the file that contains the manifest of the assembly for which the strong name signature will be generated.</span></span>  
  
 `wszKeyContainer`  
 <span data-ttu-id="1a475-107">[in] Il nome del contenitore di chiavi contenente la coppia di chiavi pubblica/privata.</span><span class="sxs-lookup"><span data-stu-id="1a475-107">[in] The name of the key container that contains the public/private key pair.</span></span>  
  
 <span data-ttu-id="1a475-108">Se `pbKeyBlob` è null, `wszKeyContainer` deve specificare un contenitore valido all'interno del provider del servizio di crittografia (CSP).</span><span class="sxs-lookup"><span data-stu-id="1a475-108">If `pbKeyBlob` is null, `wszKeyContainer` must specify a valid container within the cryptographic service provider (CSP).</span></span> <span data-ttu-id="1a475-109">In questo caso, la coppia di chiavi archiviata nel contenitore viene utilizzata per firmare il file.</span><span class="sxs-lookup"><span data-stu-id="1a475-109">In this case, the key pair stored in the container is used to sign the file.</span></span>  
  
 <span data-ttu-id="1a475-110">Se `pbKeyBlob` non è null, si presuppone che la coppia di chiavi deve contenere la chiave BLOB binary large object ().</span><span class="sxs-lookup"><span data-stu-id="1a475-110">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="1a475-111">[in] Un puntatore per la coppia di chiavi pubblica/privata.</span><span class="sxs-lookup"><span data-stu-id="1a475-111">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="1a475-112">Questa coppia è nel formato creato da Win32 `CryptExportKey` (funzione).</span><span class="sxs-lookup"><span data-stu-id="1a475-112">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="1a475-113">Se `pbKeyBlob` è null, il contenitore di chiavi specificato da `wszKeyContainer` si presuppone che la coppia di chiavi.</span><span class="sxs-lookup"><span data-stu-id="1a475-113">If `pbKeyBlob` is null, the key container specified by `wszKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="1a475-114">[in] Le dimensioni, in byte, di `pbKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="1a475-114">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbSignatureBlob`  
 <span data-ttu-id="1a475-115">[out] Puntatore alla posizione in cui common language runtime restituisce la firma.</span><span class="sxs-lookup"><span data-stu-id="1a475-115">[out] A pointer to the location to which the common language runtime returns the signature.</span></span> <span data-ttu-id="1a475-116">Se `ppbSignatureBlob` è null, il runtime archivia la firma nel file specificato da `wszFilePath`.</span><span class="sxs-lookup"><span data-stu-id="1a475-116">If `ppbSignatureBlob` is null, the runtime stores the signature in the file specified by `wszFilePath`.</span></span>  
  
 <span data-ttu-id="1a475-117">Se `ppbSignatureBlob` è non null, common language runtime consente di allocare spazio nel quale restituire la firma.</span><span class="sxs-lookup"><span data-stu-id="1a475-117">If `ppbSignatureBlob` is not null, the common language runtime allocates space in which to return the signature.</span></span> <span data-ttu-id="1a475-118">Il chiamante deve liberare questo spazio utilizzando il [ICLRStrongName:: StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) metodo.</span><span class="sxs-lookup"><span data-stu-id="1a475-118">The caller must free this space using the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method.</span></span>  
  
 `pcbSignatureBlob`  
 <span data-ttu-id="1a475-119">[out] Le dimensioni in byte, della firma restituita.</span><span class="sxs-lookup"><span data-stu-id="1a475-119">[out] The size, in bytes, of the returned signature.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="1a475-120">[in] Uno o più dei seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="1a475-120">[in] One or more of the following values:</span></span>  
  
-   <span data-ttu-id="1a475-121">`SN_SIGN_ALL_FILES`(0x00000001) - ricalcola tutti gli hash per i moduli collegati.</span><span class="sxs-lookup"><span data-stu-id="1a475-121">`SN_SIGN_ALL_FILES` (0x00000001) - Recompute all hashes for linked modules.</span></span>  
  
-   <span data-ttu-id="1a475-122">`SN_TEST_SIGN`(0x00000002) - la firma di test dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="1a475-122">`SN_TEST_SIGN` (0x00000002) - Test-sign the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1a475-123">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="1a475-123">Return Value</span></span>  
 <span data-ttu-id="1a475-124">`S_OK`Se il metodo viene completato correttamente. in caso contrario, un valore HRESULT indicante un errore (vedere [valori HRESULT comuni](http://go.microsoft.com/fwlink/?LinkId=213878) per un elenco).</span><span class="sxs-lookup"><span data-stu-id="1a475-124">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](http://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1a475-125">Note</span><span class="sxs-lookup"><span data-stu-id="1a475-125">Remarks</span></span>  
 <span data-ttu-id="1a475-126">Specificare null per `wszFilePath` per calcolare la dimensione della firma senza la creazione della firma.</span><span class="sxs-lookup"><span data-stu-id="1a475-126">Specify null for `wszFilePath` to calculate the size of the signature without creating the signature.</span></span>  
  
 <span data-ttu-id="1a475-127">La firma possa essere archiviata direttamente nel file o restituita al chiamante.</span><span class="sxs-lookup"><span data-stu-id="1a475-127">The signature can be either stored directly in the file, or returned to the caller.</span></span>  
  
 <span data-ttu-id="1a475-128">Se `SN_SIGN_ALL_FILES` è specificato, ma non è inclusa una chiave pubblica (entrambi `pbKeyBlob` e `wszFilePath` sono null), vengono ricalcolati gli hash per i moduli collegati, ma l'assembly non è firmato.</span><span class="sxs-lookup"><span data-stu-id="1a475-128">If `SN_SIGN_ALL_FILES` is specified but a public key is not included (both `pbKeyBlob` and `wszFilePath` are null), hashes for linked modules are recomputed, but the assembly is not re-signed.</span></span>  
  
 <span data-ttu-id="1a475-129">Se `SN_TEST_SIGN` viene specificato, l'intestazione di common language runtime non viene modificata per indicare che l'assembly è firmato con un nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="1a475-129">If `SN_TEST_SIGN` is specified, the common language runtime header is not modified to indicate that the assembly is signed with a strong name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1a475-130">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1a475-130">Requirements</span></span>  
 <span data-ttu-id="1a475-131">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1a475-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1a475-132">**Intestazione:** Metahost. H</span><span class="sxs-lookup"><span data-stu-id="1a475-132">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="1a475-133">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1a475-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1a475-134">**Versioni di .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1a475-134">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a475-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1a475-135">See Also</span></span>  
 [<span data-ttu-id="1a475-136">StrongNameSignatureGeneration (metodo)</span><span class="sxs-lookup"><span data-stu-id="1a475-136">StrongNameSignatureGeneration Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegeneration-method.md)  
 [<span data-ttu-id="1a475-137">ICLRStrongName (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="1a475-137">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)