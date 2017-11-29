---
title: "CorDebugInterfaceVersion (Enumeración)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorDebugInterfaceVersion
api_location: mscordbi.dll
api_type: COM
f1_keywords: CorDebugInterfaceVersion
helpviewer_keywords: CorDebugInterfaceVersion enumeration [.NET Framework debugging]
ms.assetid: 7d1e6cd9-2a15-41c6-9b68-008705a4ed90
topic_type: apiref
caps.latest.revision: "17"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3d579390dd54e746e700c6c571998648aefba74f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="cordebuginterfaceversion-enumeration"></a><span data-ttu-id="c80ee-102">CorDebugInterfaceVersion (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="c80ee-102">CorDebugInterfaceVersion Enumeration</span></span>
<span data-ttu-id="c80ee-103">Especifica una interfaz, una versión de .NET Framework, o la versión de .NET Framework en la que se incorporó una interfaz.</span><span class="sxs-lookup"><span data-stu-id="c80ee-103">Specifies an interface, a version of the .NET Framework, or a version of the .NET Framework in which an interface was introduced.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c80ee-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c80ee-104">Syntax</span></span>  
  
```  
typedef enum CorDebugInterfaceVersion {  
  
    CorDebugInvalidVersion            = 0,  
    CorDebugVersion_1_0               = CorDebugInvalidVersion + 1,  
  
    ver_ICorDebugManagedCallback      = CorDebugVersion_1_0,  
    ver_ICorDebugUnmanagedCallback    = CorDebugVersion_1_0,  
    ver_ICorDebug                     = CorDebugVersion_1_0,  
    ver_ICorDebugController           = CorDebugVersion_1_0,  
    ver_ICorDebugAppDomain            = CorDebugVersion_1_0,  
    ver_ICorDebugAssembly             = CorDebugVersion_1_0,  
    ver_ICorDebugProcess              = CorDebugVersion_1_0,  
    ver_ICorDebugBreakpoint           = CorDebugVersion_1_0,  
    ver_ICorDebugFunctionBreakpoint   = CorDebugVersion_1_0,  
    ver_ICorDebugModuleBreakpoint     = CorDebugVersion_1_0,  
    ver_ICorDebugValueBreakpoint      = CorDebugVersion_1_0,  
    ver_ICorDebugStepper              = CorDebugVersion_1_0,  
    ver_ICorDebugRegisterSet          = CorDebugVersion_1_0,  
    ver_ICorDebugThread               = CorDebugVersion_1_0,  
    ver_ICorDebugChain                = CorDebugVersion_1_0,  
    ver_ICorDebugFrame                = CorDebugVersion_1_0,  
    ver_ICorDebugILFrame              = CorDebugVersion_1_0,  
    ver_ICorDebugNativeFrame          = CorDebugVersion_1_0,  
    ver_ICorDebugModule               = CorDebugVersion_1_0,  
    ver_ICorDebugFunction             = CorDebugVersion_1_0,  
    ver_ICorDebugCode                 = CorDebugVersion_1_0,  
    ver_ICorDebugClass                = CorDebugVersion_1_0,  
    ver_ICorDebugEval                 = CorDebugVersion_1_0,  
    ver_ICorDebugValue                = CorDebugVersion_1_0,  
    ver_ICorDebugGenericValue         = CorDebugVersion_1_0,  
    ver_ICorDebugReferenceValue       = CorDebugVersion_1_0,  
    ver_ICorDebugHeapValue            = CorDebugVersion_1_0,  
    ver_ICorDebugObjectValue          = CorDebugVersion_1_0,  
    ver_ICorDebugBoxValue             = CorDebugVersion_1_0,  
    ver_ICorDebugStringValue          = CorDebugVersion_1_0,  
    ver_ICorDebugArrayValue           = CorDebugVersion_1_0,  
    ver_ICorDebugContext              = CorDebugVersion_1_0,  
    ver_ICorDebugEnum                 = CorDebugVersion_1_0,  
    ver_ICorDebugObjectEnum           = CorDebugVersion_1_0,  
    ver_ICorDebugBreakpointEnum       = CorDebugVersion_1_0,  
    ver_ICorDebugStepperEnum          = CorDebugVersion_1_0,  
    ver_ICorDebugProcessEnum          = CorDebugVersion_1_0,  
    ver_ICorDebugThreadEnum           = CorDebugVersion_1_0,  
    ver_ICorDebugFrameEnum            = CorDebugVersion_1_0,  
    ver_ICorDebugChainEnum            = CorDebugVersion_1_0,  
    ver_ICorDebugModuleEnum           = CorDebugVersion_1_0,  
    ver_ICorDebugValueEnum            = CorDebugVersion_1_0,  
    ver_ICorDebugCodeEnum             = CorDebugVersion_1_0,  
    ver_ICorDebugTypeEnum             = CorDebugVersion_1_0,  
    ver_ICorDebugErrorInfoEnum        = CorDebugVersion_1_0,  
    ver_ICorDebugAppDomainEnum        = CorDebugVersion_1_0,  
    ver_ICorDebugAssemblyEnum         = CorDebugVersion_1_0,  
    ver_ICorDebugEditAndContinueErrorInfo   
                                      = CorDebugVersion_1_0,  
    ver_ICorDebugEditAndContinueSnapshot   
                                      = CorDebugVersion_1_0,  
  
    CorDebugVersion_1_1               = CorDebugVersion_1_0 + 1,  
    // No interface definitions in version 1.1.  
  
    CorDebugVersion_2_0 = CorDebugVersion_1_1 + 1,  
  
    ver_ICorDebugManagedCallback2    = CorDebugVersion_2_0,  
    ver_ICorDebugAppDomain2          = CorDebugVersion_2_0,  
    ver_ICorDebugProcess2            = CorDebugVersion_2_0,  
    ver_ICorDebugStepper2            = CorDebugVersion_2_0,  
    ver_ICorDebugRegisterSet2        = CorDebugVersion_2_0,  
    ver_ICorDebugThread2             = CorDebugVersion_2_0,  
    ver_ICorDebugILFrame2            = CorDebugVersion_2_0,  
    ver_ICorDebugModule2             = CorDebugVersion_2_0,  
    ver_ICorDebugFunction2           = CorDebugVersion_2_0,  
    ver_ICorDebugCode2               = CorDebugVersion_2_0,  
    ver_ICorDebugClass2              = CorDebugVersion_2_0,  
    ver_ICorDebugValue2              = CorDebugVersion_2_0,  
    ver_ICorDebugEval2               = CorDebugVersion_2_0,  
    ver_ICorDebugObjectValue2        = CorDebugVersion_2_0,  
  
    // CLR v4 - next major CLR version after CLR v2  
    // Includes Silverlight 4  
    CorDebugVersion_4_0 = CorDebugVersion_2_0 + 1,  
  
    ver_ICorDebugThread3             = CorDebugVersion_4_0,  
    ver_ICorDebugThread4             = CorDebugVersion_4_0,  
    ver_ICorDebugStackWalk           = CorDebugVersion_4_0,  
    ver_ICorDebugNativeFrame2        = CorDebugVersion_4_0,  
    ver_ICorDebugInternalFrame2      = CorDebugVersion_4_0,  
    ver_ICorDebugRuntimeUnwindableFrame = CorDebugVersion_4_0,  
    ver_ICorDebugHeapValue3          = CorDebugVersion_4_0,  
    ver_ICorDebugBlockingObjectEnum  = CorDebugVersion_4_0,  
    ver_ICorDebugValue3 = CorDebugVersion_4_0,  
  
    CorDebugVersion_4_5 = CorDebugVersion_4_0 + 1,  
  
    ver_ICorDebugComObjectValue = CorDebugVersion_4_5,  
    ver_ICorDebugAppDomain3 = CorDebugVersion_4_5,  
    ver_ICorDebugCode3 = CorDebugVersion_4_5,  
    ver_ICorDebugILFrame3 = CorDebugVersion_4_5,  
  
    CorDebugLatestVersion = CorDebugVersion_4_5  
  
} CorDebugInterfaceVersion;  
```  
  
## <a name="members"></a><span data-ttu-id="c80ee-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="c80ee-105">Members</span></span>  
 <span data-ttu-id="c80ee-106">En la tabla siguiente se incluyen vínculos de cada valor de enumeración a la interfaz correspondiente.</span><span class="sxs-lookup"><span data-stu-id="c80ee-106">The following table provides links from each enumeration value to the corresponding interface.</span></span> <span data-ttu-id="c80ee-107">Además, la tabla indica la primera versión de .NET Framework en la que se admitía la interfaz.</span><span class="sxs-lookup"><span data-stu-id="c80ee-107">In addition, the table indicates the first version of the .NET Framework that the interface was supported in.</span></span>  
  
|<span data-ttu-id="c80ee-108">Miembro</span><span class="sxs-lookup"><span data-stu-id="c80ee-108">Member</span></span>|<span data-ttu-id="c80ee-109">Especifica</span><span class="sxs-lookup"><span data-stu-id="c80ee-109">Specifies</span></span>|<span data-ttu-id="c80ee-110">Versión de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="c80ee-110">.NET Framework version</span></span>|  
|------------|---------------|----------------------------|  
|`CorDebugInvalidVersion`|<span data-ttu-id="c80ee-111">La versión de .NET Framework no es válida.</span><span class="sxs-lookup"><span data-stu-id="c80ee-111">The version of the .NET Framework is invalid.</span></span>|-|  
|`CorDebugVersion_1_0`|<span data-ttu-id="c80ee-112">La versión de .NET Framework, incluidos todos sus Service Packs, es 1.0.</span><span class="sxs-lookup"><span data-stu-id="c80ee-112">The version of the .NET Framework, including all its service packs, is 1.0.</span></span>|<span data-ttu-id="c80ee-113">1.0</span><span class="sxs-lookup"><span data-stu-id="c80ee-113">1.0</span></span>|  
|`CorDebugVersion_1_1`|<span data-ttu-id="c80ee-114">La versión de .NET Framework, incluidos todos los Service Packs, es 1.1.</span><span class="sxs-lookup"><span data-stu-id="c80ee-114">The version of the .NET Framework, including all service packs, is 1.1.</span></span>|<span data-ttu-id="c80ee-115">1.1</span><span class="sxs-lookup"><span data-stu-id="c80ee-115">1.1</span></span>|  
|`CorDebugVersion_2_0`|<span data-ttu-id="c80ee-116">La versión de .NET Framework, incluidos todos los Service Packs, es 2,0.</span><span class="sxs-lookup"><span data-stu-id="c80ee-116">The version of the .NET Framework, including all service packs, is 2.0.</span></span>|<span data-ttu-id="c80ee-117">2.0</span><span class="sxs-lookup"><span data-stu-id="c80ee-117">2.0</span></span>|  
|`CorDebugVersion_4_0`|<span data-ttu-id="c80ee-118">La versión de .NET Framework, incluidos todos los Service Packs, es 4.</span><span class="sxs-lookup"><span data-stu-id="c80ee-118">The version of the .NET Framework, including all service packs, is 4.</span></span>|<span data-ttu-id="c80ee-119">4</span><span class="sxs-lookup"><span data-stu-id="c80ee-119">4</span></span>|  
|`CorDebugVersion_4_5`|<span data-ttu-id="c80ee-120">La versión de .NET Framework, incluidos todos los Service Packs, es 4,5.</span><span class="sxs-lookup"><span data-stu-id="c80ee-120">The version of the .NET Framework, including all service packs, is 4.5.</span></span>|<span data-ttu-id="c80ee-121">4.5</span><span class="sxs-lookup"><span data-stu-id="c80ee-121">4.5</span></span>|  
|`ver_ICorDebugManagedCallback`|[<span data-ttu-id="c80ee-122">ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="c80ee-122">ICorDebugManagedCallback</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)|<span data-ttu-id="c80ee-123">1.0</span><span class="sxs-lookup"><span data-stu-id="c80ee-123">1.0</span></span>|  
|`ver_ICorDebugUnmanagedCallback`|[<span data-ttu-id="c80ee-124">ICorDebugUnmanagedCallback</span><span class="sxs-lookup"><span data-stu-id="c80ee-124">ICorDebugUnmanagedCallback</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugunmanagedcallback-interface.md)|<span data-ttu-id="c80ee-125">1.0</span><span class="sxs-lookup"><span data-stu-id="c80ee-125">1.0</span></span>|  
|`ver_ICorDebug`|[<span data-ttu-id="c80ee-126">ICorDebug</span><span class="sxs-lookup"><span data-stu-id="c80ee-126">ICorDebug</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)|<span data-ttu-id="c80ee-127">1.0</span><span class="sxs-lookup"><span data-stu-id="c80ee-127">1.0</span></span>|  
|`ver_ICorDebugController`|[<span data-ttu-id="c80ee-128">ICorDebugController</span><span class="sxs-lookup"><span data-stu-id="c80ee-128">ICorDebugController</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-interface.md)|<span data-ttu-id="c80ee-129">1.0</span><span class="sxs-lookup"><span data-stu-id="c80ee-129">1.0</span></span>|  
|`ver_ICorDebugAppDomain`|[<span data-ttu-id="c80ee-130">ICorDebugAppDomain</span><span class="sxs-lookup"><span data-stu-id="c80ee-130">ICorDebugAppDomain</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-interface.md)|<span data-ttu-id="c80ee-131">1.0</span><span class="sxs-lookup"><span data-stu-id="c80ee-131">1.0</span></span>|  
|`ver_ICorDebugAssembly`|[<span data-ttu-id="c80ee-132">ICorDebugAssembly</span><span class="sxs-lookup"><span data-stu-id="c80ee-132">ICorDebugAssembly</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-interface.md)|<span data-ttu-id="c80ee-133">1.0</span><span class="sxs-lookup"><span data-stu-id="c80ee-133">1.0</span></span>|  
|`ver_ICorDebugProcess`|[<span data-ttu-id="c80ee-134">ICorDebugProcess</span><span class="sxs-lookup"><span data-stu-id="c80ee-134">ICorDebugProcess</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-interface.md)|<span data-ttu-id="c80ee-135">1.0</span><span class="sxs-lookup"><span data-stu-id="c80ee-135">1.0</span></span>|  
|`ver_ICorDebugBreakpoint`|[<span data-ttu-id="c80ee-136">ICorDebugBreakpoint</span><span class="sxs-lookup"><span data-stu-id="c80ee-136">ICorDebugBreakpoint</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugbreakpoint-interface.md)|<span data-ttu-id="c80ee-137">1.0</span><span class="sxs-lookup"><span data-stu-id="c80ee-137">1.0</span></span>|  
|`ver_ICorDebugFunctionBreakpoint`|[<span data-ttu-id="c80ee-138">ICorDebugFunctionBreakpoint</span><span class="sxs-lookup"><span data-stu-id="c80ee-138">ICorDebugFunctionBreakpoint</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunctionbreakpoint-interface.md)|<span data-ttu-id="c80ee-139">1.0</span><span class="sxs-lookup"><span data-stu-id="c80ee-139">1.0</span></span>|  
|`ver_ICorDebugModuleBreakpoint`|[<span data-ttu-id="c80ee-140">ICorDebugModuleBreakpoint</span><span class="sxs-lookup"><span data-stu-id="c80ee-140">ICorDebugModuleBreakpoint</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodulebreakpoint-interface.md)|<span data-ttu-id="c80ee-141">1.0</span><span class="sxs-lookup"><span data-stu-id="c80ee-141">1.0</span></span>|  
|`ver_ICorDebugValueBreakpoint`|[<span data-ttu-id="c80ee-142">ICorDebugValueBreakpoint</span><span class="sxs-lookup"><span data-stu-id="c80ee-142">ICorDebugValueBreakpoint</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvaluebreakpoint-interface.md)|<span data-ttu-id="c80ee-143">1.0</span><span class="sxs-lookup"><span data-stu-id="c80ee-143">1.0</span></span>|  
|`ver_ICorDebugStepper`|[<span data-ttu-id="c80ee-144">ICorDebugStepper</span><span class="sxs-lookup"><span data-stu-id="c80ee-144">ICorDebugStepper</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-interface.md)|<span data-ttu-id="c80ee-145">1.0</span><span class="sxs-lookup"><span data-stu-id="c80ee-145">1.0</span></span>|  
|`ver_ICorDebugRegisterSet`|[<span data-ttu-id="c80ee-146">ICorDebugRegisterSet</span><span class="sxs-lookup"><span data-stu-id="c80ee-146">ICorDebugRegisterSet</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)|<span data-ttu-id="c80ee-147">1.0</span><span class="sxs-lookup"><span data-stu-id="c80ee-147">1.0</span></span>|  
|`ver_ICorDebugThread`|[<span data-ttu-id="c80ee-148">ICorDebugThread</span><span class="sxs-lookup"><span data-stu-id="c80ee-148">ICorDebugThread</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-interface.md)|<span data-ttu-id="c80ee-149">1.0</span><span class="sxs-lookup"><span data-stu-id="c80ee-149">1.0</span></span>|  
|`ver_ICorDebugChain`|[<span data-ttu-id="c80ee-150">ICorDebugChain</span><span class="sxs-lookup"><span data-stu-id="c80ee-150">ICorDebugChain</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-interface.md)|<span data-ttu-id="c80ee-151">1.0</span><span class="sxs-lookup"><span data-stu-id="c80ee-151">1.0</span></span>|  
|`ver_ICorDebugFrame`|[<span data-ttu-id="c80ee-152">ICorDebugFrame</span><span class="sxs-lookup"><span data-stu-id="c80ee-152">ICorDebugFrame</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-interface.md)|<span data-ttu-id="c80ee-153">1.0</span><span class="sxs-lookup"><span data-stu-id="c80ee-153">1.0</span></span>|  
|`ver_ICorDebugILFrame`|[<span data-ttu-id="c80ee-154">ICorDebugILFrame</span><span class="sxs-lookup"><span data-stu-id="c80ee-154">ICorDebugILFrame</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-interface.md)|<span data-ttu-id="c80ee-155">1.0</span><span class="sxs-lookup"><span data-stu-id="c80ee-155">1.0</span></span>|  
|`ver_ICorDebugNativeFrame`|[<span data-ttu-id="c80ee-156">ICorDebugNativeFrame</span><span class="sxs-lookup"><span data-stu-id="c80ee-156">ICorDebugNativeFrame</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-interface.md)|<span data-ttu-id="c80ee-157">1.0</span><span class="sxs-lookup"><span data-stu-id="c80ee-157">1.0</span></span>|  
|`ver_ICorDebugModule`|[<span data-ttu-id="c80ee-158">ICorDebugModule</span><span class="sxs-lookup"><span data-stu-id="c80ee-158">ICorDebugModule</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-interface.md)|<span data-ttu-id="c80ee-159">1.0</span><span class="sxs-lookup"><span data-stu-id="c80ee-159">1.0</span></span>|  
|`ver_ICorDebugFunction`|[<span data-ttu-id="c80ee-160">ICorDebugFunction</span><span class="sxs-lookup"><span data-stu-id="c80ee-160">ICorDebugFunction</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-interface1.md)|<span data-ttu-id="c80ee-161">1.0</span><span class="sxs-lookup"><span data-stu-id="c80ee-161">1.0</span></span>|  
|`ver_ICorDebugCode`|[<span data-ttu-id="c80ee-162">ICorDebugCode</span><span class="sxs-lookup"><span data-stu-id="c80ee-162">ICorDebugCode</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-interface1.md)|<span data-ttu-id="c80ee-163">1.0</span><span class="sxs-lookup"><span data-stu-id="c80ee-163">1.0</span></span>|  
|`ver_ICorDebugClass`|[<span data-ttu-id="c80ee-164">ICorDebugClass</span><span class="sxs-lookup"><span data-stu-id="c80ee-164">ICorDebugClass</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-interface.md)|<span data-ttu-id="c80ee-165">1.0</span><span class="sxs-lookup"><span data-stu-id="c80ee-165">1.0</span></span>|  
|`ver_ICorDebugEval`|[<span data-ttu-id="c80ee-166">ICorDebugEval</span><span class="sxs-lookup"><span data-stu-id="c80ee-166">ICorDebugEval</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-interface.md)|<span data-ttu-id="c80ee-167">1.0</span><span class="sxs-lookup"><span data-stu-id="c80ee-167">1.0</span></span>|  
|`ver_ICorDebugValue`|[<span data-ttu-id="c80ee-168">ICorDebugValue</span><span class="sxs-lookup"><span data-stu-id="c80ee-168">ICorDebugValue</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-interface.md)|<span data-ttu-id="c80ee-169">1.0</span><span class="sxs-lookup"><span data-stu-id="c80ee-169">1.0</span></span>|  
|`ver_ICorDebugGenericValue`|[<span data-ttu-id="c80ee-170">ICorDebugGenericValue</span><span class="sxs-lookup"><span data-stu-id="c80ee-170">ICorDebugGenericValue</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuggenericvalue-interface.md)|<span data-ttu-id="c80ee-171">1.0</span><span class="sxs-lookup"><span data-stu-id="c80ee-171">1.0</span></span>|  
|`ver_ICorDebugReferenceValue`|[<span data-ttu-id="c80ee-172">ICorDebugReferenceValue</span><span class="sxs-lookup"><span data-stu-id="c80ee-172">ICorDebugReferenceValue</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-interface.md)|<span data-ttu-id="c80ee-173">1.0</span><span class="sxs-lookup"><span data-stu-id="c80ee-173">1.0</span></span>|  
|`ver_ICorDebugHeapValue`|[<span data-ttu-id="c80ee-174">ICorDebugHeapValue</span><span class="sxs-lookup"><span data-stu-id="c80ee-174">ICorDebugHeapValue</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue-interface.md)|<span data-ttu-id="c80ee-175">1.0</span><span class="sxs-lookup"><span data-stu-id="c80ee-175">1.0</span></span>|  
|`ver_ICorDebugObjectValue`|[<span data-ttu-id="c80ee-176">ICorDebugObjectValue</span><span class="sxs-lookup"><span data-stu-id="c80ee-176">ICorDebugObjectValue</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-interface.md)|<span data-ttu-id="c80ee-177">1.0</span><span class="sxs-lookup"><span data-stu-id="c80ee-177">1.0</span></span>|  
|`ver_ICorDebugBoxValue`|[<span data-ttu-id="c80ee-178">ICorDebugBoxValue</span><span class="sxs-lookup"><span data-stu-id="c80ee-178">ICorDebugBoxValue</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugboxvalue-interface.md)|<span data-ttu-id="c80ee-179">1.0</span><span class="sxs-lookup"><span data-stu-id="c80ee-179">1.0</span></span>|  
|`ver_ICorDebugStringValue`|[<span data-ttu-id="c80ee-180">ICorDebugStringValue</span><span class="sxs-lookup"><span data-stu-id="c80ee-180">ICorDebugStringValue</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstringvalue-interface.md)|<span data-ttu-id="c80ee-181">1.0</span><span class="sxs-lookup"><span data-stu-id="c80ee-181">1.0</span></span>|  
|`ver_ICorDebugArrayValue`|[<span data-ttu-id="c80ee-182">ICorDebugArrayValue</span><span class="sxs-lookup"><span data-stu-id="c80ee-182">ICorDebugArrayValue</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-interface.md)|<span data-ttu-id="c80ee-183">1.0</span><span class="sxs-lookup"><span data-stu-id="c80ee-183">1.0</span></span>|  
|`ver_ICorDebugContext`|[<span data-ttu-id="c80ee-184">ICorDebugContext</span><span class="sxs-lookup"><span data-stu-id="c80ee-184">ICorDebugContext</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontext-interface.md)|<span data-ttu-id="c80ee-185">1.0</span><span class="sxs-lookup"><span data-stu-id="c80ee-185">1.0</span></span>|  
|`ver_ICorDebugEnum`|[<span data-ttu-id="c80ee-186">ICorDebugEnum</span><span class="sxs-lookup"><span data-stu-id="c80ee-186">ICorDebugEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-interface1.md)|<span data-ttu-id="c80ee-187">1.0</span><span class="sxs-lookup"><span data-stu-id="c80ee-187">1.0</span></span>|  
|`ver_ICorDebugObjectEnum`|[<span data-ttu-id="c80ee-188">ICorDebugObjectEnum</span><span class="sxs-lookup"><span data-stu-id="c80ee-188">ICorDebugObjectEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectenum-interface.md)|<span data-ttu-id="c80ee-189">1.0</span><span class="sxs-lookup"><span data-stu-id="c80ee-189">1.0</span></span>|  
|`ver_ICorDebugBreakpointEnum`|[<span data-ttu-id="c80ee-190">ICorDebugBreakpointEnum</span><span class="sxs-lookup"><span data-stu-id="c80ee-190">ICorDebugBreakpointEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugbreakpointenum-interface.md)|<span data-ttu-id="c80ee-191">1.0</span><span class="sxs-lookup"><span data-stu-id="c80ee-191">1.0</span></span>|  
|`ver_ICorDebugStepperEnum`|[<span data-ttu-id="c80ee-192">ICorDebugStepperEnum</span><span class="sxs-lookup"><span data-stu-id="c80ee-192">ICorDebugStepperEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepperenum-interface.md)|<span data-ttu-id="c80ee-193">1.0</span><span class="sxs-lookup"><span data-stu-id="c80ee-193">1.0</span></span>|  
|`ver_ICorDebugProcessEnum`|[<span data-ttu-id="c80ee-194">ICorDebugProcessEnum</span><span class="sxs-lookup"><span data-stu-id="c80ee-194">ICorDebugProcessEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocessenum-interface.md)|<span data-ttu-id="c80ee-195">1.0</span><span class="sxs-lookup"><span data-stu-id="c80ee-195">1.0</span></span>|  
|`ver_ICorDebugThreadEnum`|[<span data-ttu-id="c80ee-196">ICorDebugThreadEnum</span><span class="sxs-lookup"><span data-stu-id="c80ee-196">ICorDebugThreadEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthreadenum-interface1.md)|<span data-ttu-id="c80ee-197">1.0</span><span class="sxs-lookup"><span data-stu-id="c80ee-197">1.0</span></span>|  
|`ver_ICorDebugFrameEnum`|[<span data-ttu-id="c80ee-198">ICorDebugFrameEnum</span><span class="sxs-lookup"><span data-stu-id="c80ee-198">ICorDebugFrameEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframeenum-interface.md)|<span data-ttu-id="c80ee-199">1.0</span><span class="sxs-lookup"><span data-stu-id="c80ee-199">1.0</span></span>|  
|`ver_ICorDebugChainEnum`|[<span data-ttu-id="c80ee-200">ICorDebugChainEnum</span><span class="sxs-lookup"><span data-stu-id="c80ee-200">ICorDebugChainEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchainenum-interface.md)|<span data-ttu-id="c80ee-201">1.0</span><span class="sxs-lookup"><span data-stu-id="c80ee-201">1.0</span></span>|  
|`ver_ICorDebugModuleEnum`|[<span data-ttu-id="c80ee-202">ICorDebugModuleEnum</span><span class="sxs-lookup"><span data-stu-id="c80ee-202">ICorDebugModuleEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmoduleenum-interface.md)|<span data-ttu-id="c80ee-203">1.0</span><span class="sxs-lookup"><span data-stu-id="c80ee-203">1.0</span></span>|  
|`ver_ICorDebugValueEnum`|[<span data-ttu-id="c80ee-204">ICorDebugValueEnum</span><span class="sxs-lookup"><span data-stu-id="c80ee-204">ICorDebugValueEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalueenum-interface.md)|<span data-ttu-id="c80ee-205">1.0</span><span class="sxs-lookup"><span data-stu-id="c80ee-205">1.0</span></span>|  
|`ver_ICorDebugCodeEnum`|[<span data-ttu-id="c80ee-206">ICorDebugCodeEnum</span><span class="sxs-lookup"><span data-stu-id="c80ee-206">ICorDebugCodeEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcodeenum-interface.md)|<span data-ttu-id="c80ee-207">1.0</span><span class="sxs-lookup"><span data-stu-id="c80ee-207">1.0</span></span>|  
|`ver_ICorDebugTypeEnum`|[<span data-ttu-id="c80ee-208">ICorDebugTypeEnum</span><span class="sxs-lookup"><span data-stu-id="c80ee-208">ICorDebugTypeEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtypeenum-interface.md)|<span data-ttu-id="c80ee-209">1.0</span><span class="sxs-lookup"><span data-stu-id="c80ee-209">1.0</span></span>|  
|`ver_ICorDebugErrorInfoEnum`|[<span data-ttu-id="c80ee-210">ICorDebugErrorInfoEnum</span><span class="sxs-lookup"><span data-stu-id="c80ee-210">ICorDebugErrorInfoEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugerrorinfoenum-interface.md)|<span data-ttu-id="c80ee-211">1.0</span><span class="sxs-lookup"><span data-stu-id="c80ee-211">1.0</span></span>|  
|`ver_ICorDebugAppDomainEnum`|[<span data-ttu-id="c80ee-212">ICorDebugAppDomainEnum</span><span class="sxs-lookup"><span data-stu-id="c80ee-212">ICorDebugAppDomainEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomainenum-interface.md)|<span data-ttu-id="c80ee-213">1.0</span><span class="sxs-lookup"><span data-stu-id="c80ee-213">1.0</span></span>|  
|`ver_ICorDebugAssemblyEnum`|[<span data-ttu-id="c80ee-214">ICorDebugAssemblyEnum</span><span class="sxs-lookup"><span data-stu-id="c80ee-214">ICorDebugAssemblyEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassemblyenum-interface.md)|<span data-ttu-id="c80ee-215">1.0</span><span class="sxs-lookup"><span data-stu-id="c80ee-215">1.0</span></span>|  
|`ver_ICorDebugEditAndContinueErrorInfo`|[<span data-ttu-id="c80ee-216">ICorDebugEditAndContinueErrorInfo</span><span class="sxs-lookup"><span data-stu-id="c80ee-216">ICorDebugEditAndContinueErrorInfo</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeditandcontinueerrorinfo-interface.md)|<span data-ttu-id="c80ee-217">1.0</span><span class="sxs-lookup"><span data-stu-id="c80ee-217">1.0</span></span>|  
|`ver_ICorDebugEditAndContinueSnapshot`|[<span data-ttu-id="c80ee-218">ICorDebugEditAndContinueSnapshot</span><span class="sxs-lookup"><span data-stu-id="c80ee-218">ICorDebugEditAndContinueSnapshot</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeditandcontinuesnapshot-interface.md)|<span data-ttu-id="c80ee-219">1.0</span><span class="sxs-lookup"><span data-stu-id="c80ee-219">1.0</span></span>|  
|`ver_ICorDebugManagedCallback2`|[<span data-ttu-id="c80ee-220">ICorDebugManagedCallback2</span><span class="sxs-lookup"><span data-stu-id="c80ee-220">ICorDebugManagedCallback2</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)|<span data-ttu-id="c80ee-221">2.0</span><span class="sxs-lookup"><span data-stu-id="c80ee-221">2.0</span></span>|  
|`ver_ICorDebugAppDomain2`|[<span data-ttu-id="c80ee-222">ICorDebugAppDomain2</span><span class="sxs-lookup"><span data-stu-id="c80ee-222">ICorDebugAppDomain2</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain2-interface.md)|<span data-ttu-id="c80ee-223">2.0</span><span class="sxs-lookup"><span data-stu-id="c80ee-223">2.0</span></span>|  
|`ver_ICorDebugProcess2`|[<span data-ttu-id="c80ee-224">ICorDebugProcess2</span><span class="sxs-lookup"><span data-stu-id="c80ee-224">ICorDebugProcess2</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-interface1.md)|<span data-ttu-id="c80ee-225">2.0</span><span class="sxs-lookup"><span data-stu-id="c80ee-225">2.0</span></span>|  
|`ver_ICorDebugStepper2`|[<span data-ttu-id="c80ee-226">ICorDebugStepper2</span><span class="sxs-lookup"><span data-stu-id="c80ee-226">ICorDebugStepper2</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper2-interface1.md)|<span data-ttu-id="c80ee-227">2.0</span><span class="sxs-lookup"><span data-stu-id="c80ee-227">2.0</span></span>|  
|`ver_ICorDebugRegisterSet2`|[<span data-ttu-id="c80ee-228">ICorDebugRegisterSet2</span><span class="sxs-lookup"><span data-stu-id="c80ee-228">ICorDebugRegisterSet2</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)|<span data-ttu-id="c80ee-229">2.0</span><span class="sxs-lookup"><span data-stu-id="c80ee-229">2.0</span></span>|  
|`ver_ICorDebugThread2`|[<span data-ttu-id="c80ee-230">ICorDebugThread2</span><span class="sxs-lookup"><span data-stu-id="c80ee-230">ICorDebugThread2</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-interface.md)|<span data-ttu-id="c80ee-231">2.0</span><span class="sxs-lookup"><span data-stu-id="c80ee-231">2.0</span></span>|  
|`ver_ICorDebugILFrame2`|[<span data-ttu-id="c80ee-232">ICorDebugILFrame2</span><span class="sxs-lookup"><span data-stu-id="c80ee-232">ICorDebugILFrame2</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-interface.md)|<span data-ttu-id="c80ee-233">2.0</span><span class="sxs-lookup"><span data-stu-id="c80ee-233">2.0</span></span>|  
|`ver_ICorDebugModule2`|[<span data-ttu-id="c80ee-234">ICorDebugModule2</span><span class="sxs-lookup"><span data-stu-id="c80ee-234">ICorDebugModule2</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-interface.md)|<span data-ttu-id="c80ee-235">2.0</span><span class="sxs-lookup"><span data-stu-id="c80ee-235">2.0</span></span>|  
|`ver_ICorDebugFunction2`|[<span data-ttu-id="c80ee-236">ICorDebugFunction2</span><span class="sxs-lookup"><span data-stu-id="c80ee-236">ICorDebugFunction2</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction2-interface.md)|<span data-ttu-id="c80ee-237">2.0</span><span class="sxs-lookup"><span data-stu-id="c80ee-237">2.0</span></span>|  
|`ver_ICorDebugCode2`|[<span data-ttu-id="c80ee-238">ICorDebugCode2</span><span class="sxs-lookup"><span data-stu-id="c80ee-238">ICorDebugCode2</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-interface.md)|<span data-ttu-id="c80ee-239">2.0</span><span class="sxs-lookup"><span data-stu-id="c80ee-239">2.0</span></span>|  
|`ver_ICorDebugClass2`|<span data-ttu-id="c80ee-240">"ICorDebugClass2"</span><span class="sxs-lookup"><span data-stu-id="c80ee-240">"ICorDebugClass2"</span></span>|<span data-ttu-id="c80ee-241">2.0</span><span class="sxs-lookup"><span data-stu-id="c80ee-241">2.0</span></span>|  
|`ver_ICorDebugValue2`|<span data-ttu-id="c80ee-242">"ICorDebugValue2"</span><span class="sxs-lookup"><span data-stu-id="c80ee-242">"ICorDebugValue2"</span></span>|<span data-ttu-id="c80ee-243">2.0</span><span class="sxs-lookup"><span data-stu-id="c80ee-243">2.0</span></span>|  
|`ver_ICorDebugEval2`|<span data-ttu-id="c80ee-244">El "ICorDebugEval2".</span><span class="sxs-lookup"><span data-stu-id="c80ee-244">The "ICorDebugEval2".</span></span>|<span data-ttu-id="c80ee-245">2.0</span><span class="sxs-lookup"><span data-stu-id="c80ee-245">2.0</span></span>|  
|`ver_ICorDebugObjectValue2`|<span data-ttu-id="c80ee-246">"ICorDebugObjectValue2"</span><span class="sxs-lookup"><span data-stu-id="c80ee-246">"ICorDebugObjectValue2"</span></span>|<span data-ttu-id="c80ee-247">2.0</span><span class="sxs-lookup"><span data-stu-id="c80ee-247">2.0</span></span>|  
|`ver_ICorDebugThread3`|[<span data-ttu-id="c80ee-248">ICorDebugThread3</span><span class="sxs-lookup"><span data-stu-id="c80ee-248">ICorDebugThread3</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread3-interface.md)|<span data-ttu-id="c80ee-249">4</span><span class="sxs-lookup"><span data-stu-id="c80ee-249">4</span></span>|  
|`ver_ICorDebugThread4`|[<span data-ttu-id="c80ee-250">ICorDebugThread4</span><span class="sxs-lookup"><span data-stu-id="c80ee-250">ICorDebugThread4</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-interface.md)|<span data-ttu-id="c80ee-251">4</span><span class="sxs-lookup"><span data-stu-id="c80ee-251">4</span></span>|  
|`ver_ICorDebugStackWalk`|[<span data-ttu-id="c80ee-252">ICorDebugStackWalk</span><span class="sxs-lookup"><span data-stu-id="c80ee-252">ICorDebugStackWalk</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md)|<span data-ttu-id="c80ee-253">4</span><span class="sxs-lookup"><span data-stu-id="c80ee-253">4</span></span>|  
|`ver_ICorDebugNativeFrame2`|[<span data-ttu-id="c80ee-254">ICorDebugNativeFrame2</span><span class="sxs-lookup"><span data-stu-id="c80ee-254">ICorDebugNativeFrame2</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-interface.md)|<span data-ttu-id="c80ee-255">4</span><span class="sxs-lookup"><span data-stu-id="c80ee-255">4</span></span>|  
|`ver_ICorDebugInternalFrame2`|[<span data-ttu-id="c80ee-256">ICorDebugInternalFrame2</span><span class="sxs-lookup"><span data-stu-id="c80ee-256">ICorDebugInternalFrame2</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md)|<span data-ttu-id="c80ee-257">4</span><span class="sxs-lookup"><span data-stu-id="c80ee-257">4</span></span>|  
|`ver_ICorDebugRuntimeUnwindableFrame`|[<span data-ttu-id="c80ee-258">ICorDebugRuntimeUnwindableFrame</span><span class="sxs-lookup"><span data-stu-id="c80ee-258">ICorDebugRuntimeUnwindableFrame</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugruntimeunwindableframe-interface.md)|<span data-ttu-id="c80ee-259">4</span><span class="sxs-lookup"><span data-stu-id="c80ee-259">4</span></span>|  
|`ver_ICorDebugHeapValue3`|[<span data-ttu-id="c80ee-260">ICorDebugHeapValue3 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c80ee-260">ICorDebugHeapValue3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue3-interface.md)|<span data-ttu-id="c80ee-261">4</span><span class="sxs-lookup"><span data-stu-id="c80ee-261">4</span></span>|  
|`ver_ICorDebugBlockingObjectEnum`|[<span data-ttu-id="c80ee-262">ICorDebugBlockingObjectEnum (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c80ee-262">ICorDebugBlockingObjectEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugblockingobjectenum-interface.md)|<span data-ttu-id="c80ee-263">4</span><span class="sxs-lookup"><span data-stu-id="c80ee-263">4</span></span>|  
|`ver_ICorDebugValue3`|[<span data-ttu-id="c80ee-264">ICorDebugValue3</span><span class="sxs-lookup"><span data-stu-id="c80ee-264">ICorDebugValue3</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md)|<span data-ttu-id="c80ee-265">4</span><span class="sxs-lookup"><span data-stu-id="c80ee-265">4</span></span>|  
|`ver_ICorDebugComObjectValue`|[<span data-ttu-id="c80ee-266">ICorDebugComObjectValue</span><span class="sxs-lookup"><span data-stu-id="c80ee-266">ICorDebugComObjectValue</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcomobjectvalue-interface.md)|<span data-ttu-id="c80ee-267">4.5</span><span class="sxs-lookup"><span data-stu-id="c80ee-267">4.5</span></span>|  
|`ver_ICorDebugAppDomain3`|[<span data-ttu-id="c80ee-268">ICorDebugAppDomain3</span><span class="sxs-lookup"><span data-stu-id="c80ee-268">ICorDebugAppDomain3</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-interface.md)|<span data-ttu-id="c80ee-269">4.5</span><span class="sxs-lookup"><span data-stu-id="c80ee-269">4.5</span></span>|  
|`ver_ICorDebugCode3`|[<span data-ttu-id="c80ee-270">ICorDebugCode3</span><span class="sxs-lookup"><span data-stu-id="c80ee-270">ICorDebugCode3</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-interface.md)|<span data-ttu-id="c80ee-271">4.5</span><span class="sxs-lookup"><span data-stu-id="c80ee-271">4.5</span></span>|  
|`ver_ICorDebugILFrame3`|[<span data-ttu-id="c80ee-272">ICorDebugILFrame3</span><span class="sxs-lookup"><span data-stu-id="c80ee-272">ICorDebugILFrame3</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-interface.md)|<span data-ttu-id="c80ee-273">4.5</span><span class="sxs-lookup"><span data-stu-id="c80ee-273">4.5</span></span>|  
|`CorDebugLatestVersion`|<span data-ttu-id="c80ee-274">La versión de .NET Framework, incluidos todos sus Service Packs, es la última versión.</span><span class="sxs-lookup"><span data-stu-id="c80ee-274">The version of the .NET Framework, including all of its service packs, is the latest version.</span></span>|-|  
  
## <a name="remarks"></a><span data-ttu-id="c80ee-275">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c80ee-275">Remarks</span></span>  
 <span data-ttu-id="c80ee-276">Puede usar un depurador el `CorDebugInterfaceVersion` en la enumeración de la [CreateDebuggingInterfaceFromVersion](../../../../docs/framework/unmanaged-api/hosting/createdebugginginterfacefromversion-function.md) función para especificar la versión más reciente de .NET Framework que admite el depurador.</span><span class="sxs-lookup"><span data-stu-id="c80ee-276">A debugger can use the `CorDebugInterfaceVersion` enumeration in the [CreateDebuggingInterfaceFromVersion](../../../../docs/framework/unmanaged-api/hosting/createdebugginginterfacefromversion-function.md) function to specify the highest version of the .NET Framework that the debugger supports.</span></span>  
  
## <a name="interface-names"></a><span data-ttu-id="c80ee-277">Nombres de interfaz</span><span class="sxs-lookup"><span data-stu-id="c80ee-277">Interface Names</span></span>  
 <span data-ttu-id="c80ee-278">El número que aparece al final de los nombres de interfaz en la API de depuración (por ejemplo, "3" en `ICorDebugThread3`) especifica la versión de la interfaz, no la versión de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c80ee-278">The number that appears at the end of the interface names in the debugging API (for example, the "3" in `ICorDebugThread3`) specifies the version of the interface, not the version of the .NET Framework.</span></span> <span data-ttu-id="c80ee-279">Todos los nombres de interfaz en la API de depuración incluyen números de versión, excepto las interfaces que se incorporaron en .NET Framework versión 1.</span><span class="sxs-lookup"><span data-stu-id="c80ee-279">All interface names in the debugging API include version numbers except for interfaces that were introduced in the .NET Framework version 1.</span></span> <span data-ttu-id="c80ee-280">Cualquier correspondencia entre los números de versión de las interfaces y los números de versión de .NET Framework es pura coincidencia.</span><span class="sxs-lookup"><span data-stu-id="c80ee-280">Any correspondence between interface version numbers and.NET Framework version numbers are coincidental.</span></span>  
  
-   <span data-ttu-id="c80ee-281">Las interfaces que se incorporaron en .NET Framework versión 1.0 no incluyen números, porque implícitamente son todas de la versión 1.</span><span class="sxs-lookup"><span data-stu-id="c80ee-281">Interfaces that were introduced in the .NET Framework version 1.0 do not include numbers, because they are all implicitly version 1.</span></span>  
  
-   <span data-ttu-id="c80ee-282">.NET Framework versión 1.1 usa las interfaces de la versión 1.0 y no incorpora ninguna interfaz de depuración nueva.</span><span class="sxs-lookup"><span data-stu-id="c80ee-282">The .NET Framework version 1.1 uses version 1.0 interfaces, and does not introduce any new debugging interfaces.</span></span>  
  
-   <span data-ttu-id="c80ee-283">Las 14 interfaces de depuración que se incorporaron en .NET Framework versión 2.0 son extensiones lógicas de sus homólogas de la versión 1, e incluyen el número "2" en sus nombres.</span><span class="sxs-lookup"><span data-stu-id="c80ee-283">The 14 debugging interfaces introduced in the .NET Framework version 2.0 are logical extensions of their version 1 counterparts and include the number "2" in their names.</span></span>  
  
-   <span data-ttu-id="c80ee-284">.NET Framework versión 3.0 y versión 3.5 usa las interfaces de .NET Framework 2.0 existentes y no incorpora ninguna interfaz nueva.</span><span class="sxs-lookup"><span data-stu-id="c80ee-284">The .NET Framework versions 3.0 and 3.5 use the existing .NET Framework 2.0 interfaces, and do not introduce any new interfaces.</span></span>  
  
-   <span data-ttu-id="c80ee-285">El [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] incorpora una mezcla de versiones de la interfaz.</span><span class="sxs-lookup"><span data-stu-id="c80ee-285">The [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] introduces a mix of interface versions.</span></span> <span data-ttu-id="c80ee-286">Por ejemplo, tanto `ICorDebugThread3` como `ICorDebugThread4` aparecen como la tercera y cuarta versión de la interfaz `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="c80ee-286">For example, both `ICorDebugThread3` and `ICorDebugThread4` appear as the third and fourth versions of the `ICorDebugThread` interface.</span></span> <span data-ttu-id="c80ee-287">El [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] también presenta la primera versión de la `ICorDebugStackWalk` interfaz y la segunda versión de la `ICorDebugNativeFrame` interfaz (`ICorDebugNativeFrame2`).</span><span class="sxs-lookup"><span data-stu-id="c80ee-287">The [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] also introduces the first version of the `ICorDebugStackWalk` interface and the second version of the `ICorDebugNativeFrame` interface (`ICorDebugNativeFrame2`).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c80ee-288">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c80ee-288">Requirements</span></span>  
 <span data-ttu-id="c80ee-289">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c80ee-289">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c80ee-290">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c80ee-290">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c80ee-291">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c80ee-291">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c80ee-292">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c80ee-292">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c80ee-293">Vea también</span><span class="sxs-lookup"><span data-stu-id="c80ee-293">See Also</span></span>  
 [<span data-ttu-id="c80ee-294">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="c80ee-294">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)