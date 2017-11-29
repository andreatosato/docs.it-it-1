---
title: 'Procedura: utilizzare lo strumento XML Schema Definition per generare classi e documenti di XML Schema.'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- generating XML classes using XML Schema Definition tool
- generating XML Schema Document using XML Schema Definition tool
- XML Schema Definition tool, using to generate classes that conform to specific schema
- XML Schema Definition tool, using to generate XML Schema Document
ms.assetid: 51f0edc3-993d-4051-b7f2-77753694d3d1
caps.latest.revision: 5
author: Erikre
ms.author: erikre
manager: erikre
ms.translationtype: HT
ms.sourcegitcommit: 717bcb6f9f72a728d77e2847096ea558a9c50902
ms.openlocfilehash: 3d0d7a6fa5f8b6108567de02cfaec6f1fea71796
ms.contentlocale: it-it
ms.lasthandoff: 08/21/2017

---
# <a name="how-to-use-the-xml-schema-definition-tool-to-generate-classes-and-xml-schema-documents"></a>Procedura: utilizzare lo strumento XML Schema Definition per generare classi e documenti di XML Schema.
Lo strumento XML Schema Definition (Xsd.exe) consente di generare un XML Schema che descrive una classe o di generare la classe definita da un XML Schema. Le procedure descritte di seguito mostrano come eseguire queste operazioni.  
  
### <a name="to-generate-classes-that-conform-to-a-specific-schema"></a>Per generare classi conformi a uno schema specifico  
  
1.  Aprire un prompt dei comandi.  
  
2.  Passare lo schema XML come argomento allo strumento XML Schema Definition, che crea un set di classi esattamente corrispondenti allo schema XML, ad esempio:  
  
    ```  
    xsd mySchema.xsd  
    ```  
  
     Lo strumento è in grado di elaborare solo schemi che fanno riferimento alla specifica XML del World Wide Web Consortium del 16 marzo 2001. In altri termini, lo spazio dei nomi XML Schema deve essere "http://www.w3.org/2001/XMLSchema", come mostrato nell'esempio seguente.  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8"?>  
    <xs:schema attributeFormDefault="qualified" elementFormDefault="qualified" targetNamespace="" xmlns:xs="http://www.w3.org/2001/XMLSchema">  
    ```  
  
3.  Modificare le classi con metodi, proprietà o campi, in base alle necessità. Per altre informazioni sulla modifica di una classe con attributi, vedere [Controllo della serializzazione XML mediante attributi](../../../docs/standard/serialization/controlling-xml-serialization-using-attributes.md) e [Attributi per il controllo della serializzazione SOAP codificata](../../../docs/standard/serialization/attributes-that-control-encoded-soap-serialization.md).  
  
 Spesso risulta utile esaminare lo schema del flusso XML generato quando vengono serializzate istanze di una classe (o di più classi). Ad esempio, è possibile pubblicare lo schema affinché venga utilizzato da altri o è possibile confrontarlo a uno schema con il quale si sta cercando di ottenere la compatibilità.  
  
#### <a name="to-generate-an-xml-schema-document-from-a-set-of-classes"></a>Per generare un documento XML Schema da un set di classi  
  
1.  Compilare la classe o le classi in una DLL.  
  
2.  Aprire un prompt dei comandi.  
  
3.  Passare la DLL come argomento a Xsd.exe, ad esempio:  
  
    ```  
    xsd MyFile.dll  
    ```  
  
     Lo schema (o gli schemi) sarà scritto, a partire dal nome "schema0.xsd."  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Data.DataSet>   
 [Strumento XML Schema Definition e serializzazione XML](../../../docs/standard/serialization/the-xml-schema-definition-tool-and-xml-serialization.md)   
 [Introduzione alla serializzazione XML](../../../docs/standard/serialization/introducing-xml-serialization.md)   
 [Strumento XML Schema Definition (Xsd.exe)](../../../docs/standard/serialization/xml-schema-definition-tool-xsd-exe.md)   
 <xref:System.Xml.Serialization.XmlSerializer>   
 [Procedura: Serializzare un oggetto](../../../docs/standard/serialization/how-to-serialize-an-object.md)   
 [Procedura: Deserializzare un oggetto](../../../docs/standard/serialization/how-to-deserialize-an-object.md)
