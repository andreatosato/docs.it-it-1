---
title: 114 - WorkflowInstanceRecordWithId
ms.date: 03/30/2017
ms.assetid: 2bd8b4a1-b210-4c07-8156-f19392318c08
ms.openlocfilehash: 739b86a0c7c64ebc17cbbc882576788fe0e4bb9d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33512792"
---
# <a name="114---workflowinstancerecordwithid"></a>114 - WorkflowInstanceRecordWithId
## <a name="properties"></a>Proprietà  
  
|||  
|-|-|  
|ID|114|  
|Parole chiave|HealthMonitoring, WFTracking|  
|Livello|Informazioni|  
|Canale|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Descrizione  
 Questo evento viene creato dal partecipante del rilevamento ETW quando un'istanza del flusso di lavoro crea l'oggetto WorkflowInstanceRecord per gli stati del flusso di lavoro: Started, Resumed, Persisted, Idle, Deleted, Completed, Canceled, Unloaded, Unsuspended.  
  
## <a name="message"></a>Messaggio  
 TrackRecord= WorkflowInstanceRecord, InstanceID = %1, RecordNumber = %2, EventTime = %3, ActivityDefinitionId = %4, State = %5, Annotations = %6, ProfileName = %7, WorkflowDefinitionIdentity = %8  
  
## <a name="details"></a>Dettagli  
  
|Nome elemento dati|Tipo elemento dati|Descrizione|  
|--------------------|--------------------|-----------------|  
|InstanceId|xs:GUID|ID istanza del flusso di lavoro.|  
|RecordNumber|xs:long|Numero di sequenza del record creato.|  
|EventTime|xs:dateTime|Ora di creazione dell'evento in UTC.|  
|ActivityDefinitionId|xs:string|Nome dell'attività radice nel flusso di lavoro.|  
|Stato|xs:string|Stato corrente del flusso di lavoro.|  
|Annotazioni|xs:string|Annotazioni aggiunte a questo evento. I valori vengono archiviati in un elemento xml nel formato \<elementi >\< nome elemento = "Nomeannotazione" Type = "> Valoreannotazione\</item > \< /items >. Se viene specificata alcuna annotazione, la stringa contiene \<elementi / >. La dimensione dell'evento ETW è limitata da quella del buffer ETW o dal payload massimo per un evento ETW. Se la dimensione dell'evento supera i limiti ETW, l'evento viene troncato eliminando le annotazioni e sostituendo il valore di annotazione con \<elementi >...  \< /items >.|  
|ProfileName|xs:string|Nome o profilo di rilevamento che ha determinato la creazione di questo evento.|  
|WorkflowDefinitionIdentity|xs:string|ID della definizione del flusso di lavoro|  
|AppDomain|xs:string|Stringa restituita da AppDomain.CurrentDomain.FriendlyName.|
