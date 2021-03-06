---
title: ICLRTaskManager (Interfaz)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRTaskManager
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRTaskManager
helpviewer_keywords: ICLRTaskManager interface [.NET Framework hosting]
ms.assetid: 2bd55e0c-001b-41fd-b29d-f01670fe8216
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 342d7b82802fcfbe9e179d85d6d692205f19e382
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="iclrtaskmanager-interface"></a>ICLRTaskManager (Interfaz)
Proporciona métodos que permiten al host solicitar explícitamente que common language runtime (CLR) crean una nueva tarea, obtención la tarea que se está ejecuta actualmente y establecer el idioma geográfico y la referencia cultural para la tarea.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[CreateTask (método)](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-createtask-method.md)|Solicita explícitamente que CLR cree una nueva [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instancia.|  
|[GetCurrentTask (método)](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-getcurrenttask-method.md)|Obtiene el `ICLRTask` instancia que representa la tarea que se está ejecutando actualmente.|  
|[GetCurrentTaskType (método)](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-getcurrenttasktype-method.md)|Obtiene el tipo de la tarea que se está ejecutando actualmente.|  
|[SetLocale (método)](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-setlocale-method.md)|Notifica a CLR que el host ha modificado el identificador de configuración regional en la tarea que se ejecuta actualmente.|  
|[SetUILocale (método)](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-setuilocale-method.md)|Notifica a common language runtime que el host ha modificado el identificador de configuración regional de la interfaz de usuario en la tarea que se ejecuta actualmente.|  
  
## <a name="remarks"></a>Comentarios  
 Cada tarea que se ejecuta en un entorno hospedado tiene representaciones tanto en el lado del host (una instancia de [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)) y en el lado CLR (una instancia de [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)). El host o el CLR puede iniciar la creación de una tarea, pero la representación del lado del host debe estar asociada con una representación de lado de CLR correspondiente para garantizar una comunicación correcta entre el host y CLR con respecto a la tarea. Los dos objetos deben ser creados y crea una instancia antes de que el código administrado puede ejecutar en un subproceso del sistema operativo.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE.h  
  
 **Biblioteca:** incluye como recurso en MSCorEE.dll  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [ICLRTask (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [IHostTask (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [IHostTaskManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [Interfaces de hospedaje](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
