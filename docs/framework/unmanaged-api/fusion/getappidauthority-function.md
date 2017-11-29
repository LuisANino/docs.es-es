---
title: "GetAppIdAuthority (Función)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: GetAppIdAuthority
api_location:
- fusion.dll
- clr.dll
api_type: COM
f1_keywords: GetAppIdAuthority
helpviewer_keywords: GetAppIdAuthority function [.NET Framework fusion]
ms.assetid: 9f968dad-0d09-47fb-bebc-94c39a0d16ad
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 8a403b4e77a847321d0fe884c5a5d274f0538a64
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="getappidauthority-function"></a><span data-ttu-id="b8ed4-102">GetAppIdAuthority (Función)</span><span class="sxs-lookup"><span data-stu-id="b8ed4-102">GetAppIdAuthority Function</span></span>
<span data-ttu-id="b8ed4-103">Obtiene un puntero a un [IAppIdAuthority](../../../../docs/framework/unmanaged-api/fusion/iappidauthority-interface.md) instancia que administra las claves para las identidades de la aplicación y referencias.</span><span class="sxs-lookup"><span data-stu-id="b8ed4-103">Gets a pointer to an [IAppIdAuthority](../../../../docs/framework/unmanaged-api/fusion/iappidauthority-interface.md) instance that manages keys for application identities and references.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8ed4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b8ed4-104">Syntax</span></span>  
  
```  
HRESULT GetAppIdAuthority (  
    [out] IAppIdAuthority **ppIAppIdAuthority  
 );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b8ed4-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b8ed4-105">Parameters</span></span>  
 `ppIAppIdAuthority`  
 <span data-ttu-id="b8ed4-106">[out] El valor devuelto `IAppIdAuthority` puntero.</span><span class="sxs-lookup"><span data-stu-id="b8ed4-106">[out] The returned `IAppIdAuthority` pointer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b8ed4-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b8ed4-107">Requirements</span></span>  
 <span data-ttu-id="b8ed4-108">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b8ed4-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b8ed4-109">**Encabezado:** Isolation.h</span><span class="sxs-lookup"><span data-stu-id="b8ed4-109">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="b8ed4-110">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b8ed4-110">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8ed4-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="b8ed4-111">See Also</span></span>  
 [<span data-ttu-id="b8ed4-112">IAppIdAuthority (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b8ed4-112">IAppIdAuthority Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iappidauthority-interface.md)  
 [<span data-ttu-id="b8ed4-113">Funciones estáticas globales de fusión</span><span class="sxs-lookup"><span data-stu-id="b8ed4-113">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)