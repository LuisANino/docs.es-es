---
title: "ICorProfilerInfo::GetInprocInspectionInterface (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo.GetInprocInspectionInterface
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo::GetInprocInspectionInterface
helpviewer_keywords:
- GetInprocInspectionInterface method [.NET Framework profiling]
- ICorProfilerInfo::GetInprocInspectionInterface method [.NET Framework profiling]
ms.assetid: 22a92d1d-8849-4af6-8304-ecc53dd1d289
topic_type: apiref
caps.latest.revision: "19"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: be114784b0003e5f1540520fdbbef751b369f1da
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilerinfogetinprocinspectioninterface-method"></a><span data-ttu-id="480fd-102">ICorProfilerInfo::GetInprocInspectionInterface (Método)</span><span class="sxs-lookup"><span data-stu-id="480fd-102">ICorProfilerInfo::GetInprocInspectionInterface Method</span></span>
<span data-ttu-id="480fd-103">Obtiene un objeto que se pueden consultar para una interfaz "ICorDebugProcess".</span><span class="sxs-lookup"><span data-stu-id="480fd-103">Gets an object that can be queried for an "ICorDebugProcess" interface.</span></span> <span data-ttu-id="480fd-104">Este método está obsoleto en la versión 2.0 de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="480fd-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="480fd-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="480fd-105">Syntax</span></span>  
  
```  
HRESULT GetInprocInspectionInterface(  
    [out] IUnknown **ppicd);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="480fd-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="480fd-106">Parameters</span></span>  
 `ppicd`  
 <span data-ttu-id="480fd-107">[out](/cpp/atl/iunknown) objeto que se puede consultar para un `ICorDebugProcess` interfaz.</span><span class="sxs-lookup"><span data-stu-id="480fd-107">[out](/cpp/atl/iunknown) object that can be queried for an `ICorDebugProcess` interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="480fd-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="480fd-108">Remarks</span></span>  
 <span data-ttu-id="480fd-109">API de depuración de common language runtime (CLR) admite la depuración en proceso de forma limitada en la versión 1.0 de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="480fd-109">The common language runtime (CLR) debugging API supported limited in-process debugging in the .NET Framework version 1.0.</span></span> <span data-ttu-id="480fd-110">Un generador de perfiles usar las partes de inspección de la API de depuración habilita la depuración en curso.</span><span class="sxs-lookup"><span data-stu-id="480fd-110">In-process debugging enabled a profiler to use the inspection portions of the debugging API.</span></span> <span data-ttu-id="480fd-111">Como resultado de los comentarios de clientes, la depuración en proceso tiene ha quitado de la versión 2.0 de .NET Framework y reemplaza con un conjunto de funciones que está más en línea con la API de generación de perfiles.</span><span class="sxs-lookup"><span data-stu-id="480fd-111">As a result of customer feedback, in-process debugging has been removed from the .NET Framework in version 2.0, and replaced with a set of functionality that is more in line with the profiling API.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="480fd-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="480fd-112">Requirements</span></span>  
 <span data-ttu-id="480fd-113">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="480fd-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="480fd-114">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="480fd-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="480fd-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="480fd-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="480fd-116">**Versión de .NET framework:** 1.0</span><span class="sxs-lookup"><span data-stu-id="480fd-116">**.NET Framework Version:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="480fd-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="480fd-117">See Also</span></span>  
 [<span data-ttu-id="480fd-118">ICorProfilerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="480fd-118">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)