---
title: "Personalización de fuentes (Data Services de WCF)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, feeds
- WCF Data Services, Atom protocol
- Atom Publishing Protocol [WCF Data Services]
- WCF Data Services, customizing feeds
ms.assetid: 0d1a39bc-6462-4683-bd7d-e74e0fd28a85
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2c5e33490a94346880986fdf66a4c5907084c8cd
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2018
---
# <a name="feed-customization-wcf-data-services"></a>Personalización de fuentes (Data Services de WCF)
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]utiliza el [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] para exponer los datos como una fuente de distribución. [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]admite los formatos Atom y JavaScript Object Notation (JSON) para las fuentes de datos. Cuando se usa una fuente Atom, [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] proporciona un método estándar para serializar los datos, como entidades y relaciones en un formato XML que puede incluirse en el cuerpo del mensaje HTTP. [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]define una asignación de entidad-propiedad predeterminada entre los datos que se encuentra en las entidades y elementos Atom. Para obtener más información, consulte [OData: formato Atom](http://go.microsoft.com/fwlink/?LinkID=185794).  
  
 Quizá tenga un escenario de aplicación que requiera que los datos de la propiedad devueltos por el servicio de datos se serialicen de forma personalizada en vez de hacerlo con el formato de fuente estándar. Con [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)], puede personalizar la serialización de una fuente de datos para que las propiedades de una entidad se puedan asignar a los elementos y atributos de una entrada o a los elementos personalizados de una entrada en la fuente.  
  
> [!NOTE]
>  La personalización de fuentes solo se admite en las fuentes Atom. No se devuelven fuentes personalizadas cuando se solicita el formato JSON para la fuente devuelta.  
  
 Con [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)], puede definir una asignación de entidad-propiedad alternativa para una carga Atom aplicando manualmente los atributos a los tipos de entidad del modelo de datos. El proveedor del origen de datos del servicio de datos determina cómo debería aplicar estos atributos.  
  
> [!IMPORTANT]
>  Cuando defina las fuentes personalizadas, debe asegurarse de que se incluyan todas las propiedades de entidad con asignaciones personalizadas en la proyección. Cuando no se incluya ninguna propiedad de entidad asignada en la proyección, se puede producir la pérdida de datos. Para obtener más información, consulte [proyecciones de consulta](../../../../docs/framework/data/wcf/query-projections-wcf-data-services.md).  
  
## <a name="customizing-feeds-with-the-entity-framework-provider"></a>Personalizar fuentes con el proveedor de Entity Framework  
 El modelo de datos usado con el proveedor de [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] se representa como XML en el archivo .edmx. En este caso, los atributos que definen las fuentes personalizadas se agregan a los elementos `EntityType` y `Property`, que representan tipos de entidad y propiedades en el modelo de datos. Estos atributos de personalización de fuentes no estén definidos en [ \[MC-CSDL\]: formato de archivo de definición de esquemas conceptuales](http://go.microsoft.com/fwlink/?LinkId=159072), que es el formato que el [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] proveedor utiliza para definir el modelo de datos. Por consiguiente, debe declarar los atributos de personalización de fuentes en un espacio de nombres de esquema concreto, que se define como `m="http://schemas.microsoft.com/ado/2007/08/dataservices/metadata"`. El fragmento XML siguiente muestra los atributos de personalización de la fuente aplicados a los elementos `Property` del tipo de entidad `Products` que definen las propiedades `ProductName`, `ReorderLevel` y `UnitsInStock`.  
  
 [!code-xml[Astoria Custom Feeds#EdmFeedAttributes](../../../../samples/snippets/xml/VS_Snippets_Misc/astoria custom feeds/xml/northwind.csdl#edmfeedattributes)]  
  
 Estos atributos generan la fuente de distribución de datos personalizada siguiente para el conjunto de entidades `Products`. En la fuente de distribución de datos personalizada, el valor de propiedad `ProductName` se muestra tanto en el elemento `author` como en el elemento de propiedad `ProductName` y la propiedad `UnitsInStock` se muestra en un elemento personalizado que tiene su propio espacio de nombres único y con la propiedad `ReorderLevel` como atributo:  
  
 [!code-xml[Astoria Custom Feeds#EdmFeedResultProduct](../../../../samples/snippets/xml/VS_Snippets_Misc/astoria custom feeds/xml/edmfeedresult.xml#edmfeedresultproduct)]  
  
 Para obtener más información, consulte [Cómo: personalizar fuentes con el proveedor de Entity Framework](../../../../docs/framework/data/wcf/how-to-customize-feeds-with-ef-provider-wcf-data-services.md).  
  
> [!NOTE]
>  Dado que Entity Designer no admite las extensiones al modelo de datos, debe modificar manualmente el archivo XML que contiene el modelo de datos. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]el archivo .edmx generado por la [!INCLUDE[adonet_edm](../../../../includes/adonet-edm-md.md)] tools, vea [información general sobre archivo .edmx](http://msdn.microsoft.com/library/f4c8e7ce-1db6-417e-9759-15f8b55155d4).  
  
### <a name="custom-feed-attributes"></a>Atributos de fuentes personalizadas  
 En la tabla siguiente se muestran los atributos XML que personalizan fuentes y que puede agregar al lenguaje de definición de esquemas conceptuales (CSDL) que define el modelo de datos. Estos atributos son equivalentes a las propiedades de la clase <xref:System.Data.Services.Common.EntityPropertyMappingAttribute> usada con el proveedor de reflexión.  
  
|Nombre del atributo|Descripción|  
|--------------------|-----------------|  
|`FC_ContentKind`|Indica el tipo de contenido. Las palabras clave siguientes definen los tipos de contenido de distribución:<br /><br /> `text:`El valor de propiedad se muestra en la fuente como texto.<br /><br /> `html:`El valor de propiedad se muestra en la fuente como HTML.<br /><br /> `xhtml:`El valor de propiedad se muestra en la fuente como HTML con formato XML.<br /><br /> Estas palabras clave son equivalentes a los valores de la enumeración <xref:System.Data.Services.Common.SyndicationTextContentKind> usada con el proveedor de reflexión.<br /><br /> No se admite este atributo cuando se usan los atributos `FC_NsPrefix` y `FC_NsUri`.<br /><br /> Cuando especifique un valor de `xhtml` para el atributo `FC_ContentKind`, debe asegurarse de que el valor de propiedad contenga XML con el formato correcto. El servicio de datos devuelve el valor sin realizar transformaciones. Además, debe asegurarse de que cualquier prefijo de elemento XML del XML devuelto tenga un URI de espacio de nombres definido en la fuente asignada.|  
|`FC_KeepInContent`|Indica que el valor de propiedad a la que se hace referencia debería estar incluido tanto en la sección de contenido de la fuente como en la ubicación asignada. Los valores válidos son `true` y `false`. Para realizar la fuente resultante compatible con versiones anteriores de [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)], especifique un valor de `true` para asegurarse de que el valor se incluye en la sección de contenido de la fuente.|  
|`FC_NsPrefix`|El prefijo del espacio de nombres del elemento XML de una asignación sin distribución. Este atributo debe usarse con el atributo `FC_NsUri` y no se puede usar con el atributo `FC_ContentKind`.|  
|`FC_NsUri`|El URI del espacio de nombres del elemento XML de una asignación sin distribución. Este atributo debe usarse con el atributo `FC_NsPrefix` y no se puede usar con el atributo `FC_ContentKind`.|  
|`FC_SourcePath`|La ruta de acceso de la propiedad de la entidad a la que se aplica esta regla de asignación de fuentes. Este atributo solo se admite cuando se usa en un elemento `EntityType`.<br /><br /> La propiedad <xref:System.Data.Services.Common.EntityPropertyMappingAttribute.SourcePath%2A> no puede hacer referencia directamente a un tipo complejo. Para los tipos complejos, debe usar una expresión de ruta cuyos nombres de propiedad estén separados por un carácter de barra diagonal (`/`). Por ejemplo, se permiten los siguientes valores para un tipo de entidad `Person` con una propiedad de entero `Age` y una propiedad compleja<br /><br /> `Address`:<br /><br /> `Age`<br /><br /> `Address/Street`<br /><br /> La propiedad <xref:System.Data.Services.Common.EntityPropertyMappingAttribute.SourcePath%2A> no puede establecerse en un valor que contenga un espacio ni en ningún otro carácter que no sea válido para un nombre de propiedad.|  
|`FC_TargetPath`|El nombre del elemento de destino de la fuente resultante que debe asignarse a la propiedad. Este elemento puede ser un elemento definido por la especificación Atom o un elemento personalizado.<br /><br /> Las siguientes palabras clave son los valores predefinidos de la ruta de acceso de destino de distribución que señalan a una ubicación concreta de una fuente [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)].<br /><br /> `SyndicationAuthorEmail:`El `atom:email` elemento secundario de la `atom:author` elemento.<br /><br /> `SyndicationAuthorName:`El `atom:name` elemento secundario de la `atom:author` elemento.<br /><br /> `SyndicationAuthorUri:`El `atom:uri` elemento secundario de la `atom:author` elemento.<br /><br /> `SyndicationContributorEmail:`El `atom:email` elemento secundario de la `atom:contributor` elemento.<br /><br /> `SyndicationContributorName:`El `atom:name` elemento secundario de la `atom:contributor` elemento.<br /><br /> `SyndicationContributorUri:`El `atom:uri` elemento secundario de la `atom:contributor` elemento.<br /><br /> `SyndicationCustomProperty:`Un elemento de la propiedad personalizada. Cuando se realiza la asignación a un elemento personalizado, el destino debe ser una expresión de ruta de acceso cuyos elementos anidados estén separados mediante una barra diagonal (`/`) y cuyos atributos se especifiquen mediante una arroba (`@`). En el ejemplo siguiente, la cadena `UnitsInStock/@ReorderLevel` asigna un valor de propiedad a un atributo denominado `ReorderLevel` en un elemento secundario denominado `UnitsInStock` del elemento de entrada raíz.<br /><br /> `<Property Name="ReorderLevel" Type="Int16"               m:FC_TargetPath="UnitsInStock/@ReorderLevel"               m:FC_NsPrefix="Northwind"               m:FC_NsUri="http://schemas.examples.microsoft.com/dataservices"               m:FC_KeepInContent="false"               />`<br /><br /> Cuando el destino es un nombre de elemento personalizado, también se deben especificar los atributos `FC_NsPrefix` y `FC_NsUri`.<br /><br /> `SyndicationPublished:`El `atom:published` elemento.<br /><br /> `SyndicationRights:`El `atom:rights` elemento.<br /><br /> `SyndicationSummary:`El `atom:summary` elemento.<br /><br /> `SyndicationTitle:`El `atom:title` elemento.<br /><br /> `SyndicationUpdated:`El `atom:updated` elemento.<br /><br /> Estas palabras clave son equivalentes a los valores de la enumeración <xref:System.Data.Services.Common.SyndicationItemProperty> usada con el proveedor de reflexión.|  
  
> [!NOTE]
>  Los nombres y los valores de los atributos distinguen mayúsculas de minúsculas. Los atributos se pueden aplicar al elemento `EntityType` o a uno o varios elementos `Property`, pero no a ambos.  
  
## <a name="customizing-feeds-with-the-reflection-provider"></a>Personalizar fuentes con el proveedor de reflexión  
 Para personalizar fuentes para un modelo de datos que se implementó usando el proveedor de reflexión, agregue una o varias instancias del atributo <xref:System.Data.Services.Common.EntityPropertyMappingAttribute> a las clases que representan los tipos de entidad del modelo de datos. Las propiedades de la clase <xref:System.Data.Services.Common.EntityPropertyMappingAttribute> corresponden a los atributos de personalización de fuentes que se describen en la sección anterior. A continuación se muestra un ejemplo de la declaración del tipo `Order`, con asignación de la fuente personalizada definida para ambas propiedades.  
  
> [!NOTE]
>  El modelo de datos en este ejemplo se define en el tema [Cómo: crear un servicio de datos mediante el proveedor de reflexión](../../../../docs/framework/data/wcf/create-a-data-service-using-rp-wcf-data-services.md).  
  
 [!code-csharp[Astoria Custom Feeds#CustomOrderFeed](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria custom feeds/cs/orderitems.svc.cs#customorderfeed)]
 [!code-vb[Astoria Custom Feeds#CustomOrderFeed](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria custom feeds/vb/orderitems.svc.vb#customorderfeed)]  
  
 Estos atributos generan la fuente de distribución de datos personalizada siguiente para el conjunto de entidades `Orders`. En este personalizar fuente, la `OrderId` valor de propiedad se muestra en el `title` elemento de la `entry` y la `Customer` valor de propiedad muestra en el `author` elemento y como el `Customer` elemento property:  
  
 [!code-xml[Astoria Custom Feeds#IQueryableFeedResult](../../../../samples/snippets/xml/VS_Snippets_Misc/astoria custom feeds/xml/iqueryablefeedresult.xml#iqueryablefeedresult)]  
  
 Para obtener más información, consulte [Cómo: personalizar fuentes con el proveedor de reflexión](../../../../docs/framework/data/wcf/how-to-customize-feeds-with-the-reflection-provider-wcf-data-services.md).  
  
## <a name="customizing-feeds-with-a-custom-data-service-provider"></a>Personalizar fuentes con un proveedor de servicios de datos personalizado  
 La personalización de fuentes para un modelo de datos definido utilizando un proveedor de servicios de datos personalizado se define para un tipo de recurso llamando al método <xref:System.Data.Services.Providers.ResourceType.AddEntityPropertyMappingAttribute%2A> en el objeto <xref:System.Data.Services.Providers.ResourceType> que representa un tipo de entidad en el modelo de datos. Para obtener más información, consulte [proveedores de servicios de datos personalizados](../../../../docs/framework/data/wcf/custom-data-service-providers-wcf-data-services.md).  
  
## <a name="consuming-custom-feeds"></a>Usar fuentes personalizadas  
 Cuando una aplicación usa directamente una [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] fuentes de distribución, debe ser capaz de procesar los elementos y atributos personalizados en la fuente devuelta. Cuando se han implementado fuentes personalizadas en un modelo de datos, sea cual sea el proveedor del servicio de datos, el extremo `$metadata` devuelve la información de la fuente personalizada como atributos de fuente personalizados en el CSDL devuelto por el servicio de datos. Cuando se usa el **Agregar referencia de servicio** diálogo o [datasvcutil.exe](../../../../docs/framework/data/wcf/wcf-data-service-client-utility-datasvcutil-exe.md) herramienta para generar clases de servicio de datos de cliente, la fuente personalizada atributos se usan para garantizar que las solicitudes y respuestas el servicio de datos se controlen correctamente.  
  
## <a name="feed-customization-considerations"></a>Consideraciones sobre personalización de fuentes  
 Debe considerar lo siguiente cuando defina asignaciones de fuentes personalizadas.  
  
-   El cliente de [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] trata los elementos asignados en una fuente como vacíos cuando contengan solo espacio en blanco. Es por ello que los elementos asignados que contengan solo espacio en blanco no se materializan en el cliente con el mismo espacio en blanco. Para conservar este espacio en blanco en el cliente, debe establecer el valor de `KeepInContext` en `true` en el atributo de asignación de fuente.  
  
## <a name="versioning-requirements"></a>Requisitos de control de versiones  
 La personalización de fuentes tiene los siguientes requisitos de control de versiones de [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]:  
  
-   La personalización de fuente requiere que tanto el cliente como el servicio de datos admitan la versión 2.0 del protocolo de [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] y versiones posteriores.  
  
 Para obtener más información, consulte [versiones del servicio de datos](../../../../docs/framework/data/wcf/data-service-versioning-wcf-data-services.md).  
  
## <a name="see-also"></a>Vea también  
 [Proveedor de reflexión](../../../../docs/framework/data/wcf/reflection-provider-wcf-data-services.md)  
 [Proveedor de Entity Framework](../../../../docs/framework/data/wcf/entity-framework-provider-wcf-data-services.md)
