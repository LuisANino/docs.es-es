---
title: "ICLRMetaHost::EnumerateInstalledRuntimes (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRMetaHost.EnumerateInstalledRuntimes
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRMetaHost::EnumerateInstalledRuntimes
helpviewer_keywords:
- ICLRMetaHost::EnumerateInstalledRuntimes method [.NET Framework hosting]
- EnumerateInstalledRuntimes method [.NET Framework hosting]
ms.assetid: 9e359384-0d3d-451c-807e-5d7fcebf2be7
topic_type: apiref
caps.latest.revision: "18"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 41e9b9de120154fe90eb3e73ada2ced4fa3e4544
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="iclrmetahostenumerateinstalledruntimes-method"></a>ICLRMetaHost::EnumerateInstalledRuntimes (Método)
Devuelve una enumeración que contiene un válido [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interfaz para cada versión de common language runtime (CLR) que se instala en un equipo.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT EnumerateInstalledRuntimes (  
    [out, retval] IEnumUnknown **ppEnumerator);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `ppEnumerator`  
 [out] Una enumeración de [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interfaces correspondientes a cada versión de CLR que está instalado en el equipo.  
  
## <a name="return-value"></a>Valor devuelto  
 Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|El método se completó correctamente.|  
|E_POINTER|`ppEnumerator` es null.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MetaHost.h  
  
 **Biblioteca:** incluye como recurso en MSCorEE.dll  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [ICLRMetaHost (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)  
 [Hospedar aplicaciones de WPF](../../../../docs/framework/unmanaged-api/hosting/index.md)
