---
title: 'Procedura: creare una forma tramite un oggetto PathGeometry'
ms.date: 03/30/2017
helpviewer_keywords:
- shapes [WPF], creating with PathGeometry class
- graphics [WPF], shapes
ms.assetid: 49a4a8b7-e738-45be-8dac-b54a6d8f5b21
ms.openlocfilehash: 4c9cd7a1af921a0a547c7dec3afc5f69b29e6aed
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2018
ms.locfileid: "43865665"
---
# <a name="how-to-create-a-shape-by-using-a-pathgeometry"></a>Procedura: creare una forma tramite un oggetto PathGeometry
Questo esempio viene illustrato come creare forme tramite il <xref:System.Windows.Media.PathGeometry> classe. <xref:System.Windows.Media.PathGeometry> gli oggetti sono costituiti da uno o più <xref:System.Windows.Media.PathFigure> oggetti, ognuna delle quali <xref:System.Windows.Media.PathFigure> rappresenta un "importo" diverso o una forma. Ciascuna <xref:System.Windows.Media.PathFigure> è composto di uno o più <xref:System.Windows.Media.PathSegment> oggetti, ognuno dei quali rappresenta una parte collegata della figura o forma. Tipi di segmento comprendono <xref:System.Windows.Media.LineSegment>, <xref:System.Windows.Media.ArcSegment>, e <xref:System.Windows.Media.BezierSegment>.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa un <xref:System.Windows.Media.PathGeometry> per creare un triangolo. Il <xref:System.Windows.Media.PathGeometry> viene visualizzato tramite un <xref:System.Windows.Shapes.Path> elemento.  
  
 [!code-xaml[GeometrySample#49](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#49)]  
  
 La figura seguente mostra la forma creata nell'esempio precedente.  
  
 ![Un oggetto PathGeometry](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-pathgeometry-triangle.gif "wcpsdk_graphicsmm_pathgeometry_triangle")  
Un triangolo creato con un oggetto PathGeometry  
  
 L'esempio precedente illustra come creare una forma relativamente semplice, un triangolo. Oggetto <xref:System.Windows.Media.PathGeometry> può anche essere utilizzato per creare forme più complesse, compresi archi e curve. Per esempi, vedere [creare un arco ellittico](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-an-elliptical-arc.md), [creare una curva di Bézier cubica](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-cubic-bezier-curve.md), e [creare una curva di Bézier quadratica](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-quadratic-bezier-curve.md).  
  
 Questo esempio fa parte di un esempio più esaustivo. Per l'esempio completo, vedere la pagina [Geometries Sample (esempio di geometrie)](https://go.microsoft.com/fwlink/?LinkID=159989).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Shapes.Path>  
 <xref:System.Windows.Media.GeometryDrawing>  
 [Cenni preliminari sulle classi Geometry](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)  
 [Esempio di geometrie](https://go.microsoft.com/fwlink/?LinkID=159989)
