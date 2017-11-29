---
title: "IHostTaskManager::EnterRuntime (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostTaskManager.EnterRuntime
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostTaskManager::EnterRuntime
helpviewer_keywords:
- IHostTaskManager::EnterRuntime method [.NET Framework hosting]
- EnterRuntime method [.NET Framework hosting]
ms.assetid: 1aa7a4b1-636a-4f5e-b834-b406d72f7120
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2a4c0304047246c912be965d80a26b26ec2344ad
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ihosttaskmanagerenterruntime-method"></a><span data-ttu-id="69580-102">IHostTaskManager::EnterRuntime (Método)</span><span class="sxs-lookup"><span data-stu-id="69580-102">IHostTaskManager::EnterRuntime Method</span></span>
<span data-ttu-id="69580-103">Notifica al host que una llamada a un método no administrado, como una plataforma de invocación de método, devuelve el control de la ejecución a common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="69580-103">Notifies the host that a call to an unmanaged method, such as a platform invoke method, is returning execution control to the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69580-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="69580-104">Syntax</span></span>  
  
```  
HRESULT EnterRuntime ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="69580-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="69580-105">Return Value</span></span>  
  
|<span data-ttu-id="69580-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="69580-106">HRESULT</span></span>|<span data-ttu-id="69580-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="69580-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="69580-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="69580-108">S_OK</span></span>|<span data-ttu-id="69580-109">`EnterRuntime`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="69580-109">`EnterRuntime` returned successfully.</span></span>|  
|<span data-ttu-id="69580-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="69580-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="69580-111">El CLR no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="69580-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="69580-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="69580-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="69580-113">La llamada agotó el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="69580-113">The call timed out.</span></span>|  
|<span data-ttu-id="69580-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="69580-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="69580-115">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="69580-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="69580-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="69580-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="69580-117">Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.</span><span class="sxs-lookup"><span data-stu-id="69580-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="69580-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="69580-118">E_FAIL</span></span>|<span data-ttu-id="69580-119">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="69580-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="69580-120">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="69580-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="69580-121">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="69580-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="69580-122">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="69580-122">E_OUTOFMEMORY</span></span>|<span data-ttu-id="69580-123">No había suficiente memoria disponible para completar la asignación solicitada.</span><span class="sxs-lookup"><span data-stu-id="69580-123">Not enough memory was available to complete the requested allocation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="69580-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="69580-124">Remarks</span></span>  
 <span data-ttu-id="69580-125">`EnterRuntime`se llama para notificar al host que una función no administrada, para que una llamada anterior a la [LeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md) método se realizó, ha terminado de ejecutarse y está devolviendo el control de ejecución al tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="69580-125">`EnterRuntime` is called to notify the host that an unmanaged function, for which an earlier call to the [LeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md) method was made, has finished executing, and is returning execution control to the runtime.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="69580-126">[ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md) se llama para notificar al host que una función no administrada, para que una llamada anterior a `LeaveRuntime` se realizó, realiza una llamada a código administrado.</span><span class="sxs-lookup"><span data-stu-id="69580-126">[ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md) is called to notify the host that an unmanaged function, for which an earlier call to `LeaveRuntime` was made, is making a call into managed code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="69580-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="69580-127">Requirements</span></span>  
 <span data-ttu-id="69580-128">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="69580-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="69580-129">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="69580-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="69580-130">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="69580-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="69580-131">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="69580-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69580-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="69580-132">See Also</span></span>  
 [<span data-ttu-id="69580-133">Interoperabilidad COM avanzada</span><span class="sxs-lookup"><span data-stu-id="69580-133">Advanced COM Interoperability</span></span>](http://msdn.microsoft.com/en-us/3ada36e5-2390-4d70-b490-6ad8de92f2fb)  
 [<span data-ttu-id="69580-134">Cómo: Llamar a archivos DLL nativos desde el código administrado mediante PInvoke</span><span class="sxs-lookup"><span data-stu-id="69580-134">How to: Call Native DLLs from Managed Code Using PInvoke</span></span>](/cpp/dotnet/how-to-call-native-dlls-from-managed-code-using-pinvoke)  
 [<span data-ttu-id="69580-135">ICLRTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="69580-135">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="69580-136">ICLRTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="69580-136">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="69580-137">IHostTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="69580-137">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="69580-138">IHostTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="69580-138">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [<span data-ttu-id="69580-139">LeaveRuntime (método)</span><span class="sxs-lookup"><span data-stu-id="69580-139">LeaveRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md)