---
title: "ICorConfiguration::SetDebuggerThreadControl (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorConfiguration.SetDebuggerThreadControl
api_location: mscoree.dll
api_type: COM
f1_keywords: SetDebuggerThreadControl
helpviewer_keywords:
- SetDebuggerThreadControl method [.NET Framework hosting]
- ICorConfiguration::SetDebuggerThreadControl method [.NET Framework hosting]
ms.assetid: 1ded7639-dacb-4db1-961c-d1ceaec01959
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4716e814c352fceacd8b949c2670058cf8a03bf1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="icorconfigurationsetdebuggerthreadcontrol-method"></a><span data-ttu-id="83210-102">ICorConfiguration::SetDebuggerThreadControl (Método)</span><span class="sxs-lookup"><span data-stu-id="83210-102">ICorConfiguration::SetDebuggerThreadControl Method</span></span>
<span data-ttu-id="83210-103">Establece la interfaz de devolución de llamada que llamará a los servicios de depuración como CLR subprocesos (CLR) se bloquea y desbloquea para la depuración.</span><span class="sxs-lookup"><span data-stu-id="83210-103">Sets the callback interface that the debugging services will call as common language runtime (CLR) threads are blocked and unblocked for debugging.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83210-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="83210-104">Syntax</span></span>  
  
```  
HRESULT SetDebuggerThreadControl (  
    [in] IDebuggerThreadControl* pDebuggerThreadControl  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="83210-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="83210-105">Parameters</span></span>  
 `pDebuggerThreadControl`  
 <span data-ttu-id="83210-106">[in] Un puntero a un [IDebuggerThreadControl](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-interface.md) objeto que notifica al host el bloqueo y desbloqueo de subprocesos por los servicios de depuración.</span><span class="sxs-lookup"><span data-stu-id="83210-106">[in] A pointer to an [IDebuggerThreadControl](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-interface.md) object that notifies the host about the blocking and unblocking of threads by the debugging services.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="83210-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="83210-107">Requirements</span></span>  
 <span data-ttu-id="83210-108">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="83210-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="83210-109">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="83210-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="83210-110">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="83210-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="83210-111">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="83210-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83210-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="83210-112">See Also</span></span>  
 [<span data-ttu-id="83210-113">ICorConfiguration (interfaz)</span><span class="sxs-lookup"><span data-stu-id="83210-113">ICorConfiguration Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)