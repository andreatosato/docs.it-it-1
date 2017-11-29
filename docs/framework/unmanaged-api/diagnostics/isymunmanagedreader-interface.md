---
title: Interfaccia ISymUnmanagedReader
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedReader
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedReader
helpviewer_keywords: ISymUnmanagedReader interface [.NET Framework debugging]
ms.assetid: aa3cc15d-058e-4e6f-b03e-39569646ba47
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 56e0012ae1412c0fb5b434d3b4c0221831296c60
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="isymunmanagedreader-interface"></a><span data-ttu-id="4616a-102">Interfaccia ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="4616a-102">ISymUnmanagedReader Interface</span></span>
<span data-ttu-id="4616a-103">Rappresenta un lettore di simboli che fornisce l'accesso a documenti, metodi e variabili all'interno di un archivio dei simboli.</span><span class="sxs-lookup"><span data-stu-id="4616a-103">Represents a symbol reader that provides access to documents, methods, and variables within a symbol store.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4616a-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="4616a-104">Methods</span></span>  
  
|<span data-ttu-id="4616a-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="4616a-105">Method</span></span>|<span data-ttu-id="4616a-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4616a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4616a-107">GetDocument (metodo)</span><span class="sxs-lookup"><span data-stu-id="4616a-107">GetDocument Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getdocument-method.md)|<span data-ttu-id="4616a-108">Trova un documento.</span><span class="sxs-lookup"><span data-stu-id="4616a-108">Finds a document.</span></span>|  
|[<span data-ttu-id="4616a-109">GetDocuments (metodo)</span><span class="sxs-lookup"><span data-stu-id="4616a-109">GetDocuments Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getdocuments-method.md)|<span data-ttu-id="4616a-110">Restituisce una matrice di tutti i documenti definiti nell'archivio simboli.</span><span class="sxs-lookup"><span data-stu-id="4616a-110">Returns an array of all the documents defined in the symbol store.</span></span>|  
|[<span data-ttu-id="4616a-111">GetDocumentVersion (metodo)</span><span class="sxs-lookup"><span data-stu-id="4616a-111">GetDocumentVersion Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getdocumentversion-method.md)|<span data-ttu-id="4616a-112">Ottiene la versione specificata del documento specificato.</span><span class="sxs-lookup"><span data-stu-id="4616a-112">Gets the specified version of the specified document.</span></span>|  
|[<span data-ttu-id="4616a-113">GetGlobalVariables (metodo)</span><span class="sxs-lookup"><span data-stu-id="4616a-113">GetGlobalVariables Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getglobalvariables-method.md)|<span data-ttu-id="4616a-114">Restituisce tutte le variabili globali.</span><span class="sxs-lookup"><span data-stu-id="4616a-114">Returns all global variables.</span></span>|  
|[<span data-ttu-id="4616a-115">GetMethod (metodo)</span><span class="sxs-lookup"><span data-stu-id="4616a-115">GetMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getmethod-method.md)|<span data-ttu-id="4616a-116">Ottiene un metodo del lettore di simboli, dato un token di metodo.</span><span class="sxs-lookup"><span data-stu-id="4616a-116">Gets a symbol reader method, given a method token.</span></span>|  
|[<span data-ttu-id="4616a-117">GetMethodByVersion (metodo)</span><span class="sxs-lookup"><span data-stu-id="4616a-117">GetMethodByVersion Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getmethodbyversion-method.md)|<span data-ttu-id="4616a-118">Ottiene un metodo del lettore di simboli, dato un token di metodo e un numero di versione di modifica e copia.</span><span class="sxs-lookup"><span data-stu-id="4616a-118">Gets a symbol reader method, given a method token and an edit-and-copy version number.</span></span>|  
|[<span data-ttu-id="4616a-119">GetMethodFromDocumentPosition (metodo)</span><span class="sxs-lookup"><span data-stu-id="4616a-119">GetMethodFromDocumentPosition Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getmethodfromdocumentposition-method.md)|<span data-ttu-id="4616a-120">Restituisce il metodo che contiene il punto di interruzione in corrispondenza della posizione specificata in un documento.</span><span class="sxs-lookup"><span data-stu-id="4616a-120">Returns the method that contains the breakpoint at the given position in a document.</span></span>|  
|[<span data-ttu-id="4616a-121">GetMethodsFromDocumentPosition (metodo)</span><span class="sxs-lookup"><span data-stu-id="4616a-121">GetMethodsFromDocumentPosition Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getmethodsfromdocumentposition-method.md)|<span data-ttu-id="4616a-122">Restituisce una matrice di metodi, ognuno dei quali contiene il punto di interruzione in corrispondenza della posizione specificata in un documento.</span><span class="sxs-lookup"><span data-stu-id="4616a-122">Returns an array of methods, each of which contains the breakpoint at the given position in a document.</span></span>|  
|[<span data-ttu-id="4616a-123">GetMethodVersion (metodo)</span><span class="sxs-lookup"><span data-stu-id="4616a-123">GetMethodVersion Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getmethodversion-method.md)|<span data-ttu-id="4616a-124">Ottiene la versione del metodo.</span><span class="sxs-lookup"><span data-stu-id="4616a-124">Gets the method version.</span></span>|  
|[<span data-ttu-id="4616a-125">GetNamespaces (metodo)</span><span class="sxs-lookup"><span data-stu-id="4616a-125">GetNamespaces Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getnamespaces-method.md)|<span data-ttu-id="4616a-126">Ottiene gli spazi dei nomi definiti in ambito globale all'interno dell'archivio simboli.</span><span class="sxs-lookup"><span data-stu-id="4616a-126">Gets the namespaces defined at global scope within this symbol store.</span></span>|  
|[<span data-ttu-id="4616a-127">GetSymAttribute (metodo)</span><span class="sxs-lookup"><span data-stu-id="4616a-127">GetSymAttribute Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getsymattribute-method.md)|<span data-ttu-id="4616a-128">Ottiene un attributo personalizzato in base al relativo nome.</span><span class="sxs-lookup"><span data-stu-id="4616a-128">Gets a custom attribute based upon its name.</span></span>|  
|[<span data-ttu-id="4616a-129">GetSymbolStoreFileName (metodo)</span><span class="sxs-lookup"><span data-stu-id="4616a-129">GetSymbolStoreFileName Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getsymbolstorefilename-method.md)|<span data-ttu-id="4616a-130">Fornisce il nome di file su disco dell'archivio di simboli.</span><span class="sxs-lookup"><span data-stu-id="4616a-130">Provides the on-disk file name of the symbol store.</span></span>|  
|[<span data-ttu-id="4616a-131">GetUserEntryPoint (metodo)</span><span class="sxs-lookup"><span data-stu-id="4616a-131">GetUserEntryPoint Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getuserentrypoint-method.md)|<span data-ttu-id="4616a-132">Restituisce il metodo che è stato specificato come punto di ingresso utente per il modulo, se presente.</span><span class="sxs-lookup"><span data-stu-id="4616a-132">Returns the method that was specified as the user entry point for the module, if any.</span></span>|  
|[<span data-ttu-id="4616a-133">GetVariables (metodo)</span><span class="sxs-lookup"><span data-stu-id="4616a-133">GetVariables Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getvariables-method.md)|<span data-ttu-id="4616a-134">Restituisce una variabile non locale, padre e al nome.</span><span class="sxs-lookup"><span data-stu-id="4616a-134">Return a non-local variable, given its parent and name.</span></span>|  
|[<span data-ttu-id="4616a-135">Initialize (metodo)</span><span class="sxs-lookup"><span data-stu-id="4616a-135">Initialize Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-initialize-method.md)|<span data-ttu-id="4616a-136">Inizializza il lettore di simboli con l'interfaccia dell'utilità di importazione dei metadati che il lettore verrà associato, insieme al nome file del modulo.</span><span class="sxs-lookup"><span data-stu-id="4616a-136">Initializes the symbol reader with the metadata importer interface that this reader will be associated with, along with the file name of the module.</span></span>|  
|[<span data-ttu-id="4616a-137">ReplaceSymbolStore (metodo)</span><span class="sxs-lookup"><span data-stu-id="4616a-137">ReplaceSymbolStore Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-replacesymbolstore-method.md)|<span data-ttu-id="4616a-138">Sostituisce l'archivio dei simboli esistente con un archivio dei simboli delta.</span><span class="sxs-lookup"><span data-stu-id="4616a-138">Replaces the existing symbol store with a delta symbol store.</span></span>|  
|[<span data-ttu-id="4616a-139">UpdateSymbolStore (metodo)</span><span class="sxs-lookup"><span data-stu-id="4616a-139">UpdateSymbolStore Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md)|<span data-ttu-id="4616a-140">Aggiorna l'archivio dei simboli esistente con un archivio dei simboli delta.</span><span class="sxs-lookup"><span data-stu-id="4616a-140">Updates the existing symbol store with a delta symbol store.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4616a-141">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4616a-141">Requirements</span></span>  
 <span data-ttu-id="4616a-142">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="4616a-142">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4616a-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4616a-143">See Also</span></span>  
 [<span data-ttu-id="4616a-144">Interfacce dell'archivio dei simboli di diagnostica</span><span class="sxs-lookup"><span data-stu-id="4616a-144">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)  
 [<span data-ttu-id="4616a-145">ISymUnmanagedReader2 (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="4616a-145">ISymUnmanagedReader2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-interface.md)