---
title: "Envío y recepción de errores"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: handling faults [WCF], sending
ms.assetid: 7be6fb96-ce2a-450b-aebe-f932c6a4bc5d
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 248202e07d3b74f5d71b40155ae8f617f7ed15ce
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="sending-and-receiving-faults"></a>Envío y recepción de errores
Los errores de SOAP transportan información de condición de errores desde un servicio a un cliente y, en caso de comunicación dúplex, desde un cliente a un servicio de manera interoperable. Normalmente, un servicio define el contenido del error personalizado y especifica qué operaciones pueden devolverlos. (Para obtener más información, consulte [definir y especificar los errores](../../../docs/framework/wcf/defining-and-specifying-faults.md).) Este tema discute cómo un servicio o cliente dúplex puede enviar esos errores cuando la condición de error correspondiente se ha producido y cómo una aplicación de cliente o servicio administra estos errores. Para obtener información general de control de errores en [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] las aplicaciones, vea [especificar y control de errores en contactos y servicios](../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md).  
  
## <a name="sending-soap-faults"></a>Envío de errores SOAP  
 Los errores de SOAP declarados son aquéllos en los que una operación tiene <xref:System.ServiceModel.FaultContractAttribute?displayProperty=nameWithType> que especifica un tipo de error de SOAP personalizado. Los errores de SOAP no declarados son aquéllos que no se especifican en el contrato para una operación.  
  
### <a name="sending-declared-faults"></a>Envío de errores declarados  
 Para enviar un error de SOAP declarado, detecte la condición de error para la que el error de SOAP es adecuado y genere una nueva <xref:System.ServiceModel.FaultException%601?displayProperty=nameWithType>, donde el parámetro de tipo es un nuevo objeto del tipo especificado en <xref:System.ServiceModel.FaultContractAttribute> para esa operación. El ejemplo de código siguiente muestra el uso de <xref:System.ServiceModel.FaultContractAttribute> para especificar que la operación `SampleMethod` puede devolver un error de SOAP con el tipo de detalle de `GreetingFault`.  
  
 [!code-csharp[FaultContractAttribute#4](../../../samples/snippets/csharp/VS_Snippets_CFX/faultcontractattribute/cs/services.cs#4)]
 [!code-vb[FaultContractAttribute#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/faultcontractattribute/vb/services.vb#4)]  
  
 Para transportar la información de error `GreetingFault` al cliente, detecte la condición de error adecuada y genere una nueva <xref:System.ServiceModel.FaultException%601?displayProperty=nameWithType> de tipo `GreetingFault` con un nuevo objeto `GreetingFault` como el argumento, como en el ejemplo de código siguiente. Si el cliente es una aplicación cliente de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)], experimenta esto como una excepción administrada donde el tipo es <xref:System.ServiceModel.FaultException%601?displayProperty=nameWithType> de tipo `GreetingFault`.  
  
 [!code-csharp[FaultContractAttribute#5](../../../samples/snippets/csharp/VS_Snippets_CFX/faultcontractattribute/cs/services.cs#5)]
 [!code-vb[FaultContractAttribute#5](../../../samples/snippets/visualbasic/VS_Snippets_CFX/faultcontractattribute/vb/services.vb#5)]  
  
### <a name="sending-undeclared-faults"></a>Envío de errores no declarados  
 Enviar errores no declarados puede ser muy útil para diagnosticar y depurar rápidamente los problemas en las aplicaciones de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)], pero su utilidad como herramienta de depuración es limitada. Más generalmente, se recomienda al depurar que utilice la propiedad <xref:System.ServiceModel.Description.ServiceDebugBehavior.IncludeExceptionDetailInFaults%2A?displayProperty=nameWithType>. Al establecer este valor en true, los clientes experimentan tales errores como excepciones <xref:System.ServiceModel.FaultException%601> de tipo <xref:System.ServiceModel.ExceptionDetail>.  
  
> [!IMPORTANT]
>  Dado que las excepciones administradas pueden exponer información interna de la aplicación, establecer <xref:System.ServiceModel.ServiceBehaviorAttribute.IncludeExceptionDetailInFaults%2A?displayProperty=nameWithType> o <xref:System.ServiceModel.Description.ServiceDebugBehavior.IncludeExceptionDetailInFaults%2A?displayProperty=nameWithType> en `true` puede permitir que los clientes [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] obtengan información sobre las excepciones de operaciones de servicio internas, incluida la información de identificación personal u otro tipo de información confidencial.  
>   
>  Por consiguiente, establecer <xref:System.ServiceModel.ServiceBehaviorAttribute.IncludeExceptionDetailInFaults%2A?displayProperty=nameWithType> o <xref:System.ServiceModel.Description.ServiceDebugBehavior.IncludeExceptionDetailInFaults%2A?displayProperty=nameWithType> en `true` solo está recomendado como una manera de depurar temporalmente una aplicación de servicio. Además, el WSDL de un método que devuelve excepciones administradas no controladas de esta manera no contiene el contrato para la <xref:System.ServiceModel.FaultException%601> de tipo <xref:System.ServiceModel.ExceptionDetail>. Los clientes deben contar con la posibilidad de que se produzca un error SOAP desconocido (devuelto a los clientes [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] como objetos <xref:System.ServiceModel.FaultException?displayProperty=nameWithType>) para obtener correctamente la información de depuración.  
  
 Para enviar un error de SOAP no declarado, genere un objeto de <xref:System.ServiceModel.FaultException?displayProperty=nameWithType> (esto es, no del tipo genérico <xref:System.ServiceModel.FaultException%601>) y pase la cadena al constructor. Esto se expone a las aplicaciones cliente de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] como una excepción <xref:System.ServiceModel.FaultException?displayProperty=nameWithType> generada donde la cadena está disponible llamando al método <xref:System.ServiceModel.FaultException%601.ToString%2A?displayProperty=nameWithType>.  
  
> [!NOTE]
>  Si declara un error de SOAP de tipo cadena y, a continuación, lo genera en su servicio como una <xref:System.ServiceModel.FaultException%601> donde el tipo del parámetro es una <xref:System.String?displayProperty=nameWithType>, el valor de la cadena está asignado a la propiedad <xref:System.ServiceModel.FaultException%601.Detail%2A?displayProperty=nameWithType>, y no está disponible desde <xref:System.ServiceModel.FaultException%601.ToString%2A?displayProperty=nameWithType>.  
  
## <a name="handling-faults"></a>Control de errores  
 En clientes [!INCLUDE[indigo2](../../../includes/indigo2-md.md)], los errores de SOAP que se producen durante la comunicación que son de interés para las aplicaciones cliente se elevan como excepciones administradas. Aunque hay muchas excepciones que pueden producirse durante la ejecución de cualquier programa, las aplicaciones que usan el modelo de programación de cliente de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] pueden esperar administrar excepciones de uno de los dos tipos siguientes como resultado de la comunicación.  
  
-   <xref:System.TimeoutException>  
  
-   <xref:System.ServiceModel.CommunicationException>  
  
 Los objetos <xref:System.TimeoutException> se producen cuando una operación supera el período de tiempo de espera especificado.  
  
 Los objetos <xref:System.ServiceModel.CommunicationException> se producen cuando hay alguna condición de error de comunicación recuperable en el servicio o el cliente.  
  
 La clase <xref:System.ServiceModel.CommunicationException> tiene dos tipos derivados importantes: <xref:System.ServiceModel.FaultException> y el tipo <xref:System.ServiceModel.FaultException%601> genérico  
  
 Las excepciones <xref:System.ServiceModel.FaultException> se producen cuando un agente de escucha recibe un error que no se espera o especifica en el contrato de operación; normalmente esto sucede cuando se depura la aplicación y el servicio tiene la propiedad <xref:System.ServiceModel.Description.ServiceDebugBehavior.IncludeExceptionDetailInFaults%2A?displayProperty=nameWithType> establecida en `true`.  
  
 Las excepciones <xref:System.ServiceModel.FaultException%601> se producen en el cliente cuando se recibe un error de SOAP especificado en el contrato de la operación en respuesta a una operación bidireccional (es decir, un método con un atributo <xref:System.ServiceModel.OperationContractAttribute> con <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A> establecido en `false`).  
  
> [!NOTE]
>  Cuando un servicio de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] tiene la propiedad <xref:System.ServiceModel.ServiceBehaviorAttribute.IncludeExceptionDetailInFaults%2A?displayProperty=nameWithType> o <xref:System.ServiceModel.Description.ServiceDebugBehavior.IncludeExceptionDetailInFaults%2A?displayProperty=nameWithType> establecida en `true`, el cliente experimenta esto como una <xref:System.ServiceModel.FaultException%601> no declarada de tipo <xref:System.ServiceModel.ExceptionDetail>. Los clientes pueden detectar este error concreto o administrar el error en un bloque de detección de <xref:System.ServiceModel.FaultException>.  
  
 Normalmente, solo las excepciones <xref:System.ServiceModel.FaultException%601>, <xref:System.TimeoutException> y <xref:System.ServiceModel.CommunicationException> son de interés para los clientes y servicios.  
  
> [!NOTE]
>  Por supuesto, se producen otras excepciones. Entre las excepciones no esperadas se incluyen errores catastróficos como <xref:System.OutOfMemoryException?displayProperty=nameWithType>; normalmente las aplicaciones no deberían detectar ese tipo de métodos.  
  
### <a name="catch-fault-exceptions-in-the-correct-order"></a>Detectar excepciones de errores en el orden correcto  
 Puesto que <xref:System.ServiceModel.FaultException%601> deriva de <xref:System.ServiceModel.FaultException>, y <xref:System.ServiceModel.FaultException> deriva de <xref:System.ServiceModel.CommunicationException>, es importante detectar estas excepciones en el orden apropiado. Por ejemplo, si tiene un bloque de intento/detección en el que primero detecta <xref:System.ServiceModel.CommunicationException>, todos los errores SOAP especificados y no especificados se administran ahí; los bloques de detección posteriores para administrar una excepción <xref:System.ServiceModel.FaultException%601> personalizada nunca se invocan.  
  
 Recuerde que una operación puede devolver un número indefinido de errores especificados. Cada error es de un tipo único y se ha de administrar separadamente.  
  
### <a name="handle-exceptions-when-closing-the-channel"></a>Administre las excepciones al cerrar el canal  
 La mayor parte de la discusión anterior tiene que ver con los errores enviados en el curso del procesamiento de mensajes de aplicaciones, es decir, mensajes enviados explícitamente por el cliente cuando la aplicación de cliente llama a las operaciones en el objeto de cliente de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].  
  
 Incluso con la disposición de objetos locales, el objeto puede elevar o enmascara excepciones que tienen lugar durante el proceso de reciclaje. Algo similar puede producirse al utilizar objetos de cliente de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]. Al llamar a operaciones, está enviando mensajes a través de una conexión establecida. Cerrar el canal puede producir excepciones si la conexión no se puede cerrar limpiamente o ya está cerrada, aun cuando todas las operaciones hayan devuelto correctamente.  
  
 Normalmente, los canales de objeto de cliente se cierran de una de las siguientes maneras:  
  
-   Cuando se recicla el objeto de cliente de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].  
  
-   Cuando la aplicación de cliente llama <xref:System.ServiceModel.ClientBase%601.Close%2A?displayProperty=nameWithType>.  
  
-   Cuando la aplicación de cliente llama <xref:System.ServiceModel.ICommunicationObject.Close%2A?displayProperty=nameWithType>.  
  
-   Cuando la aplicación de cliente llama a una operación que es una operación de finalización para una sesión.  
  
 En todos los casos, cerrar el canal indica al canal que comience a cerrar todos los canales subyacentes que puedan estar enviando mensajes para admitir una funcionalidad compleja en el nivel de la aplicación. Por ejemplo, cuando un contrato requiere sesiones, un enlace intenta establecer una sesión mediante el intercambio de mensajes con el canal del servicio hasta que se establezca una sesión. Cuando se cierre el canal, el canal de la sesión subyacente notifica al servicio que la sesión se ha terminado. En este caso, si el canal ya se ha anulado, cerrado o es inutilizable (por ejemplo, cuando se desconecta un cable de red), el canal de cliente no puede informar al canal del servicio que se finaliza la sesión y es posible que se produzca una excepción.  
  
### <a name="abort-the-channel-if-necessary"></a>Anule el canal si fuese necesario  
 Dado que cerrar el canal también puede producir excepciones, se recomienda que además de detectar las excepciones de error en el orden correcto, es importante anular el canal que se utilizó para realizar la llamada en el bloque de detección.  
  
 Si el error transporta información de error específica de una operación y sigue siendo posible que otros puedan utilizarla, no hay ninguna necesidad de anular el canal (aunque estos casos son aislados). En el resto de casos, se recomienda que anule el canal. Para obtener un ejemplo que muestra todos estos aspectos, vea [espera excepciones](../../../docs/framework/wcf/samples/expected-exceptions.md).  
  
 El siguiente ejemplo de código muestra cómo administrar las excepciones de errores de SOAP en una aplicación de cliente básica, incluyendo un error declarado y uno no declarado.  
  
> [!NOTE]
>  Este código de ejemplo no utiliza la construcción `using`. Dado que el cierre de canales puede producir excepciones, se recomienda que las aplicaciones creen primero un cliente de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)], y, a continuación, abran, utilicen y cierren el cliente de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] en el mismo bloque de intento. Para obtener más información, consulte [información general sobre el cliente de WCF](../../../docs/framework/wcf/wcf-client-overview.md) y [evitar problemas con la instrucción Using](../../../docs/framework/wcf/samples/avoiding-problems-with-the-using-statement.md).  
  
 [!code-csharp[FaultContractAttribute#3](../../../samples/snippets/csharp/VS_Snippets_CFX/faultcontractattribute/cs/client.cs#3)]
 [!code-vb[FaultContractAttribute#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/faultcontractattribute/vb/client.vb#3)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.ServiceModel.FaultException>  
 <xref:System.ServiceModel.FaultException%601>  
 <xref:System.ServiceModel.CommunicationException?displayProperty=nameWithType>  
 [Excepciones esperadas](../../../docs/framework/wcf/samples/expected-exceptions.md)  
 [Evitar problemas mediante una declaración de instrucción](../../../docs/framework/wcf/samples/avoiding-problems-with-the-using-statement.md)
