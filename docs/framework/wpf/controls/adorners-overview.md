---
title: "Información general sobre adornos"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: adorners [WPF], about adorners
ms.assetid: 33d4c5c2-2daf-4e45-ba9a-5b673e2b8280
caps.latest.revision: "35"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 47b43b1b9848f91e77448d41609d8be5d60ecda5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="adorners-overview"></a>Información general sobre adornos
Los adornos son un tipo especial de <xref:System.Windows.FrameworkElement>, que se usa para proporcionar indicaciones visuales a un usuario. Entre otros usos, los Adorners se pueden utilizar para agregar controladores funcionales a los elementos o proporcionar información de estado sobre un control.  
  
  
  
<a name="about_Adorners"></a>   
## <a name="about-adorners"></a>Acerca de Adorners  
 Un <xref:System.Windows.Documents.Adorner> es un personalizado <xref:System.Windows.FrameworkElement> que está enlazado a un <xref:System.Windows.UIElement>. Los adornos se representan en un <xref:System.Windows.Documents.AdornerLayer>, que es una superficie de representación que siempre está encima del elemento con adornos o una colección de elementos con adornos. Representación de un adorno es independiente de la representación de la <xref:System.Windows.UIElement> que está enlazado el adorno. Un adorno se suele colocar respecto al elemento al que se enlaza, utilizando el origen de coordenadas 2D estándar situado en la parte superior izquierda del elemento adornado.  
  
 Algunas aplicaciones comunes de adornos son:  
  
-   Agregar controladores funcionales a un <xref:System.Windows.UIElement> que permiten al usuario manipular el elemento de alguna manera (cambio de tamaño, girar, cambiar de posición, etcetera).  
  
-   Proporcionar comentarios visuales para indicar diversos estados, o en respuesta a distintos eventos.  
  
-   Superponer etiquetas contextuales visuales en un <xref:System.Windows.UIElement>.  
  
-   Invalidar parcial o totalmente o enmascarar visualmente una <xref:System.Windows.UIElement>.  
  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] proporciona un marco básico para adornar elementos visuales. En la tabla siguiente se muestra una lista de los tipos principales utilizados al adornar objetos y su finalidad. A continuación se presentan varios ejemplos de uso.  
  
|||  
|-|-|  
|<xref:System.Windows.Documents.Adorner>|Una clase base abstracta de la que heredan todas las implementaciones de adornos contextuales concretas.|  
|<xref:System.Windows.Documents.AdornerLayer>|Una clase que representa una capa de representación para los adornos de uno o más elementos adornados.|  
|<xref:System.Windows.Documents.AdornerDecorator>|Una clase que permite asociar una capa de adornos a una colección de elementos.|  
  
<a name="implement_custom_Adorner"></a>   
## <a name="implementing-a-custom-adorner"></a>Implementación de un adorno personalizado  
 El marco de adornos que proporciona [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] está diseñado principalmente para admitir la creación de adornos personalizados. Un adorno personalizado se crea implementando una clase que hereda de la clase abstracta <xref:System.Windows.Documents.Adorner> clase.  
  
> [!NOTE]
>  El elemento primario de un <xref:System.Windows.Documents.Adorner> es el <xref:System.Windows.Documents.AdornerLayer> que representa el <xref:System.Windows.Documents.Adorner>, no el elemento que se adorna.  
  
 En el ejemplo siguiente se muestra una clase que implementa un adorno simple. El adorno del ejemplo simplemente adorna las esquinas de una <xref:System.Windows.UIElement> con un círculo.  
  
 [!code-csharp[Adorners_SimpleCircleAdorner#_SimpleCircleAdornerBody](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_simplecircleadornerbody)]
 [!code-vb[Adorners_SimpleCircleAdorner#_SimpleCircleAdornerBody](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_simplecircleadornerbody)]  
  
 La siguiente imagen muestra la etiqueta contextual SimpleCircleAdorner aplicada a un <xref:System.Windows.Controls.TextBox>.  
  
 ![Ejemplo de adornos: Cuadro de texto con adornos](../../../../docs/framework/wpf/controls/media/adornedtextbox.png "AdornedTextBox")  
  
<a name="rendering_behavior_for_Adorners"></a>   
## <a name="rendering-behavior-for-adorners"></a>Comportamiento de representación de los adornos  
 Es importante tener en cuenta que los adornos no incluyen ningún comportamiento de representación inherente; asegurarse de que un adorno se representa es responsabilidad del implementador del adorno.   Una manera común de implementar el comportamiento de representación es invalidar la <xref:System.Windows.UIElement.OnRender%2A> método y el uso de uno o más <xref:System.Windows.Media.DrawingContext> objetos para representar objetos visuales del adorno según sea necesario (como se muestra en el ejemplo anterior).  
  
> [!NOTE]
>  Todo aquello que se coloca en la capa de los adornos se representa encima del resto de estilos que se han establecido. En otras palabras, los adornos siempre están visualmente encima y no pueden invalidar utilizando el orden z.  
  
<a name="adorner_events_hittest"></a>   
## <a name="events-and-hit-testing"></a>Eventos y pruebas de posicionamiento  
 Adornos de reciban eventos de entrada como cualquier otro <xref:System.Windows.FrameworkElement>.  Dado que un adorno siempre tiene un orden z más alto que el elemento que adorna, el adorno recibe eventos de entrada (como <xref:System.Windows.UIElement.Drop> o <xref:System.Windows.UIElement.MouseMove>) que puede ser intencionado para subyacente complementados elemento.  Un adorno puede realizar escuchas para ciertos eventos de entrada y pasárselos al elemento adornado subyacente volviendo a provocar el evento.  
  
 Para habilitar la prueba de posicionamiento paso a través de los elementos en un adorno, establezca la prueba de posicionamiento <xref:System.Windows.UIElement.IsHitTestVisible%2A> propiedad **false** en el adorno.  Para más información sobre pruebas de posicionamiento, consulte  
  
 [Realizar pruebas de posicionamiento en la capa visual](../../../../docs/framework/wpf/graphics-multimedia/hit-testing-in-the-visual-layer.md).  
  
<a name="adorn_single_element"></a>   
## <a name="adorning-a-single-uielement"></a>Adorno de un solo elemento de la interfaz de usuario  
 Para enlazar un adorno a un determinado <xref:System.Windows.UIElement>, siga estos pasos:  
  
1.  Llame al método estático <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> para obtener un <xref:System.Windows.Documents.AdornerLayer> de objeto para el <xref:System.Windows.UIElement> que se va a adornar. <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A>recorre el árbol visual, empezando en el índice especificado <xref:System.Windows.UIElement>y devuelve la primera capa de adornos que encuentra. (Si no se encuentra ninguna capa de adornos, el método devuelve null).  
  
2.  Llame a la <xref:System.Windows.Documents.AdornerLayer.Add%2A> método para enlazar el adorno al destino <xref:System.Windows.UIElement>.  
  
 En el ejemplo siguiente se enlaza la etiqueta contextual SimpleCircleAdorner (mostrada anteriormente) a un <xref:System.Windows.Controls.TextBox> denominado *myTextBox*.  
  
 [!code-csharp[Adorners_SimpleCircleAdorner#_AdornSingleElement](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_adornsingleelement)]
 [!code-vb[Adorners_SimpleCircleAdorner#_AdornSingleElement](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_adornsingleelement)]  
  
> [!NOTE]
>  En la actualidad, no se admite el uso de [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] para enlazar un adorno a otro elemento.  
  
<a name="adorn_children_panel"></a>   
## <a name="adorning-the-children-of-a-panel"></a>Adornamiento de elementos secundarios de un panel  
 Para enlazar un adorno a los elementos secundarios de un <xref:System.Windows.Controls.Panel>, siga estos pasos:  
  
1.  Llame a la `static` método <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> para buscar una capa de adornos para el elemento cuyos elementos secundarios se van a etiquetar.  
  
2.  Enumerar los elementos secundarios del elemento primario y llamada la <xref:System.Windows.Documents.AdornerLayer.Add%2A> método para enlazar un adorno a cada elemento secundario.  
  
 En el ejemplo siguiente se enlaza la etiqueta contextual SimpleCircleAdorner (mostrada anteriormente) a los elementos secundarios de un <xref:System.Windows.Controls.StackPanel> denominado *myStackPanel*.  
  
 [!code-csharp[Adorners_SimpleCircleAdorner#_AdornChildren](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_adornchildren)]
 [!code-vb[Adorners_SimpleCircleAdorner#_AdornChildren](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_adornchildren)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Media.AdornerHitTestResult>  
 [Información general sobre formas y dibujo básico en WPF](../../../../docs/framework/wpf/graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md)  
 [Pintar con imágenes, dibujos y elementos visuales](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)  
 [Información general sobre objetos Drawing](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)  
 [Temas "Cómo..."](../../../../docs/framework/wpf/controls/adorners-how-to-topics.md)
