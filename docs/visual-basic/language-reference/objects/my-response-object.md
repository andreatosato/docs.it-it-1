---
title: Oggetto My. Response (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- My.MyWebExtension.Response
- My.Response
helpviewer_keywords:
- My.Response object
ms.assetid: 626359bc-3165-40b4-bfaf-2c610e26eb5b
ms.openlocfilehash: d5f49529a2593093a234babc22f64b591ea3cc61
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2018
ms.locfileid: "47399807"
---
# <a name="myresponse-object"></a>Oggetto My.Response
Ottiene il <xref:System.Web.HttpResponse> oggetto associato di <xref:System.Web.UI.Page>. Questo oggetto consente di inviare dati di risposta HTTP a un client e contiene informazioni su tale risposta.  
  
## <a name="remarks"></a>Note  
 Il `My.Response` oggetto contiene l'oggetto corrente <xref:System.Web.HttpResponse> oggetto associato alla pagina.  
  
 Il `My.Response` oggetto è disponibile solo per [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] applicazioni.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente ottiene la raccolta di intestazioni dal `My.Request` oggetto e viene utilizzato il `My.Response` oggetto da scrivere la pagina ASP.NET.  
  
 [!code-vb[VbVbalrMyWeb#1](../../../visual-basic/language-reference/objects/codesnippet/VisualBasic/my-response-object_1.aspx)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Web.HttpResponse>  
 [Oggetto My.Request](../../../visual-basic/language-reference/objects/my-request-object.md)
