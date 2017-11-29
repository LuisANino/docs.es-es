---
title: "ICLRMetaHost::QueryLegacyV2RuntimeBinding (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRMetaHost.RequestRuntimeLoadedNotification
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRMetaHost::QueryLegacyV2RuntimeBinding
helpviewer_keywords:
- QueryLegacyV2RuntimeBinding method [.NET Framework hosting]
- ICLRMetaHost::QueryLegacyV2RuntimeBinding method [.NET Framework hosting]
ms.assetid: 9929817e-acc9-40b7-960c-598664e04b60
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c273a1690828e37c8f7fcf5071e42e5bb2c58228
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="iclrmetahostquerylegacyv2runtimebinding-method"></a><span data-ttu-id="5c9f3-102">ICLRMetaHost::QueryLegacyV2RuntimeBinding (Método)</span><span class="sxs-lookup"><span data-stu-id="5c9f3-102">ICLRMetaHost::QueryLegacyV2RuntimeBinding Method</span></span>
<span data-ttu-id="5c9f3-103">Devuelve una interfaz que representa un tiempo de ejecución a la que Directiva de activación heredada se ha enlazado, por ejemplo, mediante el uso de la `useLegacyV2RuntimeActivationPolicy` del atributo en el [ \<Inicio > elemento](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) entrada del archivo de configuración mediante el uso directo de la API de activación heredadas o llamando a la [ICLRRuntimeInfo:: Bindaslegacyv2runtime](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-bindaslegacyv2runtime-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="5c9f3-103">Returns an interface that represents a runtime to which legacy activation policy has been bound, for example, by using the `useLegacyV2RuntimeActivationPolicy` attribute on the [\<startup> element](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) configuration file entry, by direct use of the legacy activation APIs, or by calling the [ICLRRuntimeInfo::BindAsLegacyV2Runtime](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-bindaslegacyv2runtime-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c9f3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5c9f3-104">Syntax</span></span>  
  
```  
HRESULT QueryLegacyV2RuntimeBinding (  
    [in] REFIID riid,  
    [out, iid_is(riid), retval] LPVOID *ppUnk);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5c9f3-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5c9f3-105">Parameters</span></span>  
 `riid`  
 <span data-ttu-id="5c9f3-106">[in] El único valor válido para este parámetro es de Required.Currently `IID_ICLRRuntimeInfo`.</span><span class="sxs-lookup"><span data-stu-id="5c9f3-106">[in] Required.Currently the only valid value for this parameter is `IID_ICLRRuntimeInfo`.</span></span>  
  
 `ppUnk`  
 <span data-ttu-id="5c9f3-107">[out] Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="5c9f3-107">[out] Required.</span></span> <span data-ttu-id="5c9f3-108">Cuando este método vuelve, contiene un puntero a la [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interfaz que representa un tiempo de ejecución que se ha enlazado a la directiva de activación heredada.</span><span class="sxs-lookup"><span data-stu-id="5c9f3-108">When this method returns, contains a pointer to the [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface that represents a runtime that has been bound to legacy activation policy.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5c9f3-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="5c9f3-109">Return Value</span></span>  
 <span data-ttu-id="5c9f3-110">Este método devuelve los siguientes HRESULT específicos así como los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="5c9f3-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="5c9f3-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5c9f3-111">HRESULT</span></span>|<span data-ttu-id="5c9f3-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="5c9f3-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5c9f3-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="5c9f3-113">S_OK</span></span>|<span data-ttu-id="5c9f3-114">El método se completó correctamente y devolvió un tiempo de ejecución que se enlazó a la directiva de activación heredada.</span><span class="sxs-lookup"><span data-stu-id="5c9f3-114">The method completed successfully and returned a runtime that was bound to legacy activation policy.</span></span>|  
|<span data-ttu-id="5c9f3-115">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="5c9f3-115">S_FALSE</span></span>|<span data-ttu-id="5c9f3-116">El método se completó correctamente, pero un tiempo de ejecución heredado no se enlazó.</span><span class="sxs-lookup"><span data-stu-id="5c9f3-116">The method completed successfully, but a legacy runtime has not yet been bound.</span></span>|  
|<span data-ttu-id="5c9f3-117">E_NOINTERFACE</span><span class="sxs-lookup"><span data-stu-id="5c9f3-117">E_NOINTERFACE</span></span>|<span data-ttu-id="5c9f3-118">El método encontró un tiempo de ejecución que se enlazó a la directiva de activación heredada, pero ese tiempo de ejecución no admite `riid`.</span><span class="sxs-lookup"><span data-stu-id="5c9f3-118">The method found a runtime that was bound to legacy activation policy, but `riid` is not supported by that runtime.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5c9f3-119">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5c9f3-119">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5c9f3-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5c9f3-120">Requirements</span></span>  
 <span data-ttu-id="5c9f3-121">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5c9f3-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5c9f3-122">**Encabezado:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="5c9f3-122">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="5c9f3-123">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5c9f3-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5c9f3-124">**Versiones de .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5c9f3-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c9f3-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="5c9f3-125">See Also</span></span>  
 [<span data-ttu-id="5c9f3-126">ICLRMetaHost (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5c9f3-126">ICLRMetaHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)  
 [<span data-ttu-id="5c9f3-127">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="5c9f3-127">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)