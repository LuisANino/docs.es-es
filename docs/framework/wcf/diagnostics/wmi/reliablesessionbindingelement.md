---
title: ReliableSessionBindingElement
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: effda125-b8d3-4de6-8c0e-f59f5ea8f6eb
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 61c7f98fe0ac7bfa37d48cfc578444bb3dc10779
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="reliablesessionbindingelement"></a>ReliableSessionBindingElement
ReliableSessionBindingElement  
  
## <a name="syntax"></a>Sintaxis  
  
```  
class ReliableSessionBindingElement : BindingElement  
{  
  datetime AcknowledgementInterval;  
  boolean FlowControlEnabled;  
  datetime InactivityTimeout;  
  sint32 MaxPendingChannels;  
  sint32 MaxRetryCount;  
  sint32 MaxTransferWindowSize;  
  boolean Ordered;  
  integer ReliableMessagingVersion;  
};  
```  
  
## <a name="methods"></a>Métodos  
 La clase ReliableSessionBindingElement no define ningún método.  
  
## <a name="properties"></a>Propiedades  
 La clase ReliableSessionBindingElement posee las siguientes propiedades:  
  
### <a name="acknowledgementinterval"></a>AcknowledgementInterval  
 Tipo de datos: datetime  
  
 Tipo de acceso: solo lectura  
  
 Intervalo de tiempo que un destino espera antes de enviar una confirmación al origen del mensaje en canales de confianza creados por el que generador.  
  
### <a name="flowcontrolenabled"></a>FlowControlEnabled  
 Tipo de datos: booleano  
  
 Tipo de acceso: solo lectura  
  
 Valor booleano que especifica si el control de flujo está habilitado.  
  
### <a name="inactivitytimeout"></a>InactivityTimeout  
 Tipo de datos: datetime  
  
 Tipo de acceso: solo lectura  
  
 Especifica la duración máxima durante la cual el canal permite a la otra parte de la comunicación no enviar ningún mensaje antes de que se produzca un error.  
  
### <a name="maxpendingchannels"></a>MaxPendingChannels  
 Tipo de datos: sint32  
  
 Tipo de acceso: solo lectura  
  
 Número máximo de canales que pueden esperar a ser aceptados en el agente de escucha.  
  
### <a name="maxretrycount"></a>MaxRetryCount  
 Tipo de datos: sint32  
  
 Tipo de acceso: solo lectura  
  
 Número máximo de veces que un canal de confianza intenta retransmitir un mensaje, para él que no ha recibido una confirmación, llamando a `Send` en su canal subyacente.  
  
### <a name="maxtransferwindowsize"></a>MaxTransferWindowSize  
 Tipo de datos: sint32  
  
 Tipo de acceso: solo lectura  
  
 El tamaño máximo de la ventana de transferencia para la sesión de confianza.  
  
### <a name="ordered"></a>Por orden   
 Tipo de datos: booleano  
  
 Tipo de acceso: solo lectura  
  
 Un valor booleano que especifica si se garantiza que los mensajes lleguen en el orden en el que fueron enviados.  
  
### <a name="reliablemessagingversion"></a>ReliableMessagingVersion  
 Tipo de datos: enteros  
  
 Tipo de acceso: solo lectura  
  
 Entero que especifica la versión de protocolo de WS-ReliableMessaging utilizado en la sesión de confianza.  
  
## <a name="requirements"></a>Requisitos  
  
|MOF|Se declara en Servicemodel.mof.|  
|---------|-----------------------------------|  
|Espacio de nombres|Se define en root\ServiceModel|  
  
## <a name="see-also"></a>Vea también  
 <xref:System.ServiceModel.Channels.ReliableSessionBindingElement>
