---
title: OneWayBindingElement
ms.date: 03/30/2017
ms.assetid: 5c7e17c3-39b9-4214-ae08-9e6141734305
ms.openlocfilehash: ee7cfed20234175ba54dd25dbbbab4615c1ed7af
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="onewaybindingelement"></a>OneWayBindingElement
OneWayBindingElement  
  
## <a name="syntax"></a>Sintassi  
  
```  
class OneWayBindingElement : BindingElement  
{  
  ChannelPoolSettings ChannelPoolSettings;  
  sint32 MaxAcceptedChannels;  
  boolean PacketRoutable;  
};  
```  
  
## <a name="methods"></a>Metodi  
 La classe OneWayBindingElement non definisce metodi.  
  
## <a name="properties"></a>Proprietà  
 La classe OneWayBindingElement dispone delle proprietà seguenti:  
  
### <a name="channelpoolsettings"></a>ChannelPoolSettings  
 Tipo di dati: ChannelPoolSettings  
  
 Tipo di accesso: sola lettura  
  
 Impostazioni del pool di canali.  
  
### <a name="maxacceptedchannels"></a>MaxAcceptedChannels  
 Tipo di dati: sint32  
  
 Tipo di accesso: sola lettura  
  
 Numero massimo di canali accettati.  
  
### <a name="packetroutable"></a>PacketRoutable  
 Tipo di dati: booleano  
  
 Tipo di accesso: sola lettura  
  
 Valore che indica se il pacchetto è instradabile.  
  
## <a name="requirements"></a>Requisiti  
  
|MOF|Dichiarato in Servicemodel.mof.|  
|---------|-----------------------------------|  
|Spazio dei nomi|Definito in root\ServiceModel|  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.ServiceModel.Channels.OneWayBindingElement>
