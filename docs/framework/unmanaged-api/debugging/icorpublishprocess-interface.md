---
title: ICorPublishProcess (Interfaz)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorPublishProcess
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorPublishProcess
helpviewer_keywords: ICorPublishProcess interface [.NET Framework debugging]
ms.assetid: 6d1dc41b-8aa2-4889-bb00-1cbccc00c123
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: cb62da277ff13bea33969bb9c728cac5d5a15554
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="icorpublishprocess-interface"></a><span data-ttu-id="37eef-102">ICorPublishProcess (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="37eef-102">ICorPublishProcess Interface</span></span>
<span data-ttu-id="37eef-103">Proporciona métodos que tienen acceso a la información que se mostrará un proceso.</span><span class="sxs-lookup"><span data-stu-id="37eef-103">Provides methods that access information to be displayed about a process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="37eef-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="37eef-104">Methods</span></span>  
  
|<span data-ttu-id="37eef-105">Método</span><span class="sxs-lookup"><span data-stu-id="37eef-105">Method</span></span>|<span data-ttu-id="37eef-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="37eef-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="37eef-107">EnumAppDomains (método)</span><span class="sxs-lookup"><span data-stu-id="37eef-107">EnumAppDomains Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-enumappdomains-method.md)|<span data-ttu-id="37eef-108">Obtiene un [ICorPublishAppDomainEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md) instancia que contiene los dominios de aplicación en el proceso que hace referencia esta `ICorPublishProcess`.</span><span class="sxs-lookup"><span data-stu-id="37eef-108">Gets an [ICorPublishAppDomainEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md) instance that contains the application domains in the process referenced by this `ICorPublishProcess`.</span></span>|  
|[<span data-ttu-id="37eef-109">GetDisplayName (método)</span><span class="sxs-lookup"><span data-stu-id="37eef-109">GetDisplayName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-getdisplayname-method.md)|<span data-ttu-id="37eef-110">Obtiene la ruta de acceso completa del archivo ejecutable del proceso que hace referencia esta `ICorPublishProcess`.</span><span class="sxs-lookup"><span data-stu-id="37eef-110">Gets the full path of the executable for the process referenced by this `ICorPublishProcess`.</span></span>|  
|[<span data-ttu-id="37eef-111">GetProcessID (método)</span><span class="sxs-lookup"><span data-stu-id="37eef-111">GetProcessID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-getprocessid-method.md)|<span data-ttu-id="37eef-112">Obtiene el identificador de sistema operativo para el proceso que hace referencia esta `ICorPublishProcess`.</span><span class="sxs-lookup"><span data-stu-id="37eef-112">Gets the operating system identifier for the process referenced by this `ICorPublishProcess`.</span></span>|  
|[<span data-ttu-id="37eef-113">IsManaged (método)</span><span class="sxs-lookup"><span data-stu-id="37eef-113">IsManaged Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-ismanaged-method.md)|<span data-ttu-id="37eef-114">Obtiene un valor que indica si el proceso al que hace referencia este `ICorPublishProcess` se sabe que se ejecuta código administrado.</span><span class="sxs-lookup"><span data-stu-id="37eef-114">Gets a value that indicates whether the process referenced by this `ICorPublishProcess` is known to be running managed code.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="37eef-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="37eef-115">Requirements</span></span>  
 <span data-ttu-id="37eef-116">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="37eef-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="37eef-117">**Encabezado:** Cordebug.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="37eef-117">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="37eef-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="37eef-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="37eef-119">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="37eef-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37eef-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="37eef-120">See Also</span></span>  
 [<span data-ttu-id="37eef-121">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="37eef-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="37eef-122">CorpubPublish (Coclase)</span><span class="sxs-lookup"><span data-stu-id="37eef-122">CorpubPublish Coclass</span></span>](../../../../docs/framework/unmanaged-api/debugging/corpubpublish-coclass.md)