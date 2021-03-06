---
title: "Procedura: configurare un'associazione WS-Metadata Exchange personalizzata"
ms.date: 03/30/2017
helpviewer_keywords:
- WS-Metadata Exchange [WCF]
- WS-Metadata Exchange [WCF], configuring a custom binding
ms.assetid: cdba4d73-da64-4805-bc56-9822becfd1e4
ms.openlocfilehash: 0596e91204a2a9dbaed2fdbe85387ec3785fd3db
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33488699"
---
# <a name="how-to-configure-a-custom-ws-metadata-exchange-binding"></a>Procedura: configurare un'associazione WS-Metadata Exchange personalizzata
In questo argomento viene illustrato come configurare un'associazione WS-Metadata Exchange personalizzata. Windows Communication Foundation (WCF) include quattro associazioni di metadati definite dal sistema, ma è possibile pubblicare metadati usando qualsiasi associazione desiderata. In questo argomento viene illustrato come pubblicare metadati usando `wsHttpBinding`. Questa associazione offre la possibilità di esporre i metadati in modo sicuro. Il codice in questo articolo si basa sul [Introduzione](../../../../docs/framework/wcf/samples/getting-started-sample.md).  
  
### <a name="using-a-configuration-file"></a>Uso di un file di configurazione  
  
1.  Nel file di configurazione del servizio aggiungere un comportamento del servizio che contenga il tag `serviceMetadata`:  
  
    ```xml  
    <behaviors>  
       <serviceBehaviors>  
         <behavior name="CalculatorServiceBehavior">  
           <serviceMetadata httpGetEnabled="True"/>  
         </behavior>  
       </serviceBehaviors>  
    </behaviors>  
    ```  
  
2.  Aggiungere un attributo `behaviorConfiguration` al tag del servizio che fa riferimento a questo nuovo comportamento:  
  
    ```xml  
    <service        name="Microsoft.ServiceModel.Samples.CalculatorService"  
    behaviorConfiguration="CalculatorServiceBehavior">   
    ```  
  
3.  Aggiungere un endpoint dei metadati specificando mex come indirizzo, `wsHttpBinding` come associazione e <xref:System.ServiceModel.Description.IMetadataExchange> come contratto:  
  
    ```xml  
    <endpoint address="mex"  
              binding="wsHttpBinding"  
              contract="IMetadataExchange" />  
    ```  
  
4.  Per verificare che l'endpoint dello scambio di metadati stia funzionando correttamente, aggiungere un tag dell'endpoint nel file di configurazione client:  
  
    ```xml  
    <endpoint name="MyMexEndpoint"               address="http://localhost:8000/servicemodelsamples/service/mex"  
              binding="wsHttpBinding"  
              contract="IMetadataExchange"/>  
    ```  
  
5.  Nel metodo Main() del client creare una nuova istanza di <xref:System.ServiceModel.Description.MetadataExchangeClient>, impostare la proprietà <xref:System.ServiceModel.Description.MetadataExchangeClient.ResolveMetadataReferences%2A> su `true`, chiamare <xref:System.ServiceModel.Description.MetadataExchangeClient.GetMetadata%2A> e quindi eseguire un'iterazione nella raccolta di metadati restituita:  
  
    ```  
    string mexAddress = "http://localhost:8000/servicemodelsamples/service/mex";  
  
    MetadataExchangeClient mexClient = new MetadataExchangeClient("MyMexEndpoint");  
    mexClient.ResolveMetadataReferences = true;  
    MetadataSet mdSet = mexClient.GetMetadata(new EndpointAddress(mexAddress));  
    foreach (MetadataSection section in mdSet.MetadataSections)  
    Console.WriteLine("Metadata section: " + section.Dialect.ToString());  
    ```  
  
### <a name="configuring-by-code"></a>Configurazione mediante codice  
  
1.  Creare una <<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`> istanza di associazione:  
  
    ```  
    WSHttpBinding binding = new WSHttpBinding();  
    ```  
  
2.  Creare un'istanza di <xref:System.ServiceModel.ServiceHost>:  
  
    ```  
    ServiceHost serviceHost = new ServiceHost(typeof(CalculatorService), baseAddress);  
    ```  
  
3.  Aggiungere un endpoint di servizio e un'istanza di <xref:System.ServiceModel.Description.ServiceMetadataBehavior>:  
  
    ```  
    serviceHost.AddServiceEndpoint(typeof(ICalculator), binding, baseAddress);  
    ServiceMetadataBehavior smb = new ServiceMetadataBehavior();  
    smb.HttpGetEnabled = true;  
    serviceHost.Description.Behaviors.Add(smb);  
    ```  
  
4.  Aggiungere un endpoint di scambio di metadati, specificando il <<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`> creato in precedenza:  
  
    ```  
    serviceHost.AddServiceEndpoint(typeof(IMetadataExchange), binding, mexAddress);  
    ```  
  
5.  Per verificare che l'endpoint dello scambio di metadati stia funzionando correttamente, aggiungere un tag dell'endpoint nel file di configurazione client:  
  
    ```xml  
    <endpoint name="MyMexEndpoint"               address="http://localhost:8000/servicemodelsamples/service/mex"  
              binding="wsHttpBinding"  
              contract="IMetadataExchange"/>  
    ```  
  
6.  Nel metodo Main() del client creare una nuova istanza di <xref:System.ServiceModel.Description.MetadataExchangeClient>, impostare la proprietà <xref:System.ServiceModel.Description.MetadataExchangeClient.ResolveMetadataReferences%2A> su `true`, chiamare <xref:System.ServiceModel.Description.MetadataExchangeClient.GetMetadata%2A> e quindi eseguire un'iterazione nella raccolta di metadati restituita:  
  
    ```  
    string mexAddress = "http://localhost:8000/servicemodelsamples/service/mex";  
  
    MetadataExchangeClient mexClient = new MetadataExchangeClient("MyMexEndpoint");  
    mexClient.ResolveMetadataReferences = true;  
    MetadataSet mdSet = mexClient.GetMetadata(new EndpointAddress(mexAddress));  
    foreach (MetadataSection section in mdSet.MetadataSections)  
    Console.WriteLine("Metadata section: " + section.Dialect.ToString());  
    ```  
  
## <a name="see-also"></a>Vedere anche  
 [Comportamento di pubblicazione dei metadati](../../../../docs/framework/wcf/samples/metadata-publishing-behavior.md)  
 [Recupero di metadati](../../../../docs/framework/wcf/samples/retrieve-metadata.md)  
 [Metadati](../../../../docs/framework/wcf/feature-details/metadata.md)  
 [Pubblicazione di metadati](../../../../docs/framework/wcf/feature-details/publishing-metadata.md)  
 [Pubblicazione di endpoint dei metadati](../../../../docs/framework/wcf/publishing-metadata-endpoints.md)
