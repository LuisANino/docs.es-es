---
title: ICorDebugILCode2 (Interfaz)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugILCode2
api_location: mscordbi.dll
api_type: COM
ms.assetid: f9dc2afd-df8a-464d-bdbf-5af0a1d4bf85
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2fd6b7b6b097010a307abbc260cda7c4b73e0f00
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugilcode2-interface"></a><span data-ttu-id="b4460-102">ICorDebugILCode2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b4460-102">ICorDebugILCode2 Interface</span></span>
<span data-ttu-id="b4460-103">[Compatible con .NET Framework 4.5.2 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="b4460-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="b4460-104">Extiende lógicamente la [ICorDebugILCode](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md) interfaz para proporcionar métodos que devuelven el token de firma de variable local de una función e instrumentada un lenguaje intermedio del generador de perfiles (IL) que asignan los desplazamientos al IL del método original desplazamientos.</span><span class="sxs-lookup"><span data-stu-id="b4460-104">Logically extends the [ICorDebugILCode](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md) interface to provide methods that return the token for a function's local variable signature, and that map a profiler's instrumented intermediate language (IL) offsets to original method IL offsets.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b4460-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="b4460-105">Methods</span></span>  
  
|<span data-ttu-id="b4460-106">Método</span><span class="sxs-lookup"><span data-stu-id="b4460-106">Method</span></span>|<span data-ttu-id="b4460-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="b4460-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b4460-108">Método GetInstrumentedILMap</span><span class="sxs-lookup"><span data-stu-id="b4460-108">GetInstrumentedILMap Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode2-getinstrumentedilmap-method.md)|<span data-ttu-id="b4460-109">Devuelve la correspondencia entre los desplazamientos del IL instrumentado del generador de perfiles y los desplazamientos del IL del método original para esta instancia.</span><span class="sxs-lookup"><span data-stu-id="b4460-109">Returns a map from profiler instrumented IL offsets to original method IL offsets for this instance.</span></span>|  
|[<span data-ttu-id="b4460-110">GetLocalVarSigToken (método)</span><span class="sxs-lookup"><span data-stu-id="b4460-110">GetLocalVarSigToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode2-getlocalvarsigtoken-method.md)|<span data-ttu-id="b4460-111">Obtiene el token de metadatos de la firma de variable local para la función que esta instancia representa.</span><span class="sxs-lookup"><span data-stu-id="b4460-111">Gets the metadata token for the local variable signature for the function that is represented by this instance.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b4460-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b4460-112">Requirements</span></span>  
 <span data-ttu-id="b4460-113">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b4460-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b4460-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b4460-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b4460-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b4460-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b4460-116">**Versiones de .NET framework:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b4460-116">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4460-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="b4460-117">See Also</span></span>  
 [<span data-ttu-id="b4460-118">ICorDebugILCode (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b4460-118">ICorDebugILCode Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md)  
 [<span data-ttu-id="b4460-119">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="b4460-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="b4460-120">Depuración</span><span class="sxs-lookup"><span data-stu-id="b4460-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)