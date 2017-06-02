---
title: "Extensibilidad de host de servicio de flujo de trabajo | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c0e8f7bb-cb13-49ec-852f-b85d7c23972f
caps.latest.revision: 14
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 14
---
# Extensibilidad de host de servicio de flujo de trabajo
[!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] proporciona la clase <xref:System.ServiceModel.Activities.WorkflowServiceHost> para hospedar servicios de flujo de trabajo.  Esta clase se usa cuando auto\-hospeda un servicio de flujo de trabajo en una aplicación administrada o en un servicio Windows.  Esta clase también se usa al hospedar un servicio de flujo de trabajo con Internet Information Services \(IIS\) o el Servicio de activación de procesos de Windows \(WAS\).  La clase <xref:System.ServiceModel.Activities.WorkflowServiceHost> proporciona puntos de extensión que le permiten agregar extensiones personalizadas, cambiar el comportamiento inactivo y hospedar flujos de trabajo no pertenecientes al servicio \(flujos de trabajo que no usan actividades de mensajería\).  
  
## Extensiones del host de servicio de flujo de trabajo  
 <xref:System.ServiceModel.Activities.WorkflowServiceHost> contiene una propiedad <xref:System.ServiceModel.Activities.WorkflowServiceHost.WorkflowExtensions%2A> de tipo <xref:System.Activities.Hosting.WorkflowInstanceExtensionManager> que ofrece métodos para agregar extensiones a <xref:System.ServiceModel.Activities.WorkflowServiceHost>.  Use el método <xref:System.Activities.Hosting.WorkflowInstanceExtensionManager.Add%2A> para agregar una extensión para cada instancia de servicio de flujo de trabajo.  Se llama al delegado especificado para crear una nueva extensión cuando una instancia de servicio de flujo de trabajo se crea o se carga de un almacén de persistencia.  Use el método <xref:System.Activities.Hosting.WorkflowInstanceExtensionManager.Add%2A> para agregar una extensión para cada host de servicio de flujo de trabajo; se comparte una instancia de la extensión para todas las instancias de servicio de flujo de trabajo.  
  
## Reaccionar ante excepciones no controladas  
 <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior> permite especificar la acción que debe emprenderse cuando se produce una excepción no controlada dentro de un servicio de flujo de trabajo.  La propiedad <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior.Action%2A> especifica uno de los valores <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionAction>:  
  
-   <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionAction>. Anula la instancia de servicio de flujo de trabajo.  
  
-   <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionAction>. Deshace hasta el último estado guardado y suspende la instancia de servicio de flujo de trabajo.  Esto solo ocurre si ya se ha guardado el flujo de trabajo por lo menos una vez.  Si no es así, se anula la instancia de flujo de trabajo.  
  
-   <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionAction>. Cancela la instancia.  
  
-   <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionAction>. Termina la instancia.  
  
 Este comportamiento se puede configurar en código, tal y como se muestra en el siguiente ejemplo.  
  
```csharp  
host.Description.Behaviors.Add(new WorkflowUnhandledExceptionBehavior { Action = WorkflowUnhandledExceptionAction.Abandon });  
  
```  
  
 También se puede configurar en un archivo de configuración, tal y como se muestra en el siguiente ejemplo.  
  
```vb-c#  
<behaviors>  
      <serviceBehaviors>  
        <behavior>  
          <serviceMetadata httpGetEnabled="True"/>  
          <serviceDebug includeExceptionDetailInFaults="False" />  
          <workflowUnhandledExceptionBehavior action="Abandon" />        
        </behavior>  
      </serviceBehaviors>  
  
```  
  
## Hospedar flujos de trabajo no pertenecientes al servicio  
 <xref:System.ServiceModel.Activities.WorkflowServiceHost> se puede utilizar para hospedar flujos de trabajo no pertenecientes al servicio, o flujos de trabajo que no comienzan con una actividad <xref:System.ServiceModel.Activities.Receive> o que no usan las actividades de mensajería.  Los servicios de flujo de trabajo suelen comenzar por una actividad <xref:System.ServiceModel.Activities.Receive>.  Cuando <xref:System.ServiceModel.Activities.WorkflowServiceHost> recibe un mensaje para un servicio de flujo de trabajo, se crea una nueva instancia de servicio de flujo de trabajo si aún no se está ejecutando \(o no se ha guardado\).  Si un flujo de trabajo no comienza con una actividad Receive, no se puede iniciar enviando un mensaje porque no hay ninguna actividad para recibir el mensaje.  Para hospedar un flujo de trabajo no perteneciente al servicio, derive una clase de <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> e invalide <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint.OnGetInstanceId%2A>, <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint.OnGetCreationContext%2A> y <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint.OnResolveBookmark%2A>.  Invalide <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint.OnGetInstanceId%2A> si desea proporcionar un identificador de instancia preferido.  Invalide <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint.OnGetCreationContext%2A> para crear un contexto de creación de flujo de trabajo personalizado o rellene una instancia de la clase <xref:System.ServiceModel.Activities.WorkflowCreationContext> existente.  Invalide <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint.OnResolveBookmark%2A> para extraer manualmente el marcador del mensaje entrante.  Si invalida este método, debe invocar el método <xref:System.ServiceModel.Activities.WorkflowHostingResponseContext.SendResponse%2A> en su cuerpo igual que al responder al mensaje enviado al WorkflowHostingEndpoint.  Si no lo hace, puede que a la larga se supere un límite <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentCalls%2A>.  En contratos bidireccionales, es posible que pueda detectar que no se puede invocar al método <xref:System.ServiceModel.Activities.WorkflowHostingResponseContext.SendResponse%2A> debido a que el cliente no puede recibir una respuesta.  En los contratos unidireccionales, puede que no reconozca el error que se produce cuando no se puede llamar al método <xref:System.ServiceModel.Activities.WorkflowHostingResponseContext.SendResponse%2A> hasta que sea demasiado tarde, después de que se supere el límite de la propiedad <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentCalls%2A>.  Para obtener más información, vea el [Reanudar marcador WorkflowHostingEndpoint](../../../../docs/framework/windows-workflow-foundation/samples/workflowhostingendpoint-resume-bookmark.md)Para crear una nueva instancia de un flujo de trabajo que no sea de servicio, declare un contrato de árbol que defina una operación que cree una nueva instancia.  La operación de creación debería tomar IDictionary\<cadena, objeto\> para pasar los parámetros de flujo de trabajo necesarios.  Este contrato está implícitamente implementado por la case derivada de <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint>.  Al hospedar el flujo de trabajo, agregue una instancia de la clase derivada de <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> al host llamando a <xref:System.ServiceModel.Activities.WorkflowServiceHost.AddServiceEndpoint%2A> y llame a <xref:System.ServiceModel.Activities.WorkflowServiceHost.Open%2A>.  Para crear una instancia del flujo de trabajo, cree una clase <xref:System.ServiceModel.ChannelFactory%601> de su tipo de contrato de servicios y llame e <xref:System.ServiceModel.ChannelFactory%601.CreateChannel%2A>.  A continuación, puede llamar a la operación de creación definida en el contrato de servicios.  
  
## Vea también  
 [Servicios de flujo de trabajo](../../../../docs/framework/wcf/feature-details/workflow-services.md)   
 [Actividades de mensajería](../../../../docs/framework/wcf/feature-details/messaging-activities.md)