---
title: "CorDeclSecurity (Enumeración)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorDeclSecurity
api_location: mscoree.dll
api_type: COM
f1_keywords: CorDeclSecurity
helpviewer_keywords: CorDeclSecurity enumeration [.NET Framework metadata]
ms.assetid: 864f1267-d267-4696-8df7-1f83f8444d6f
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: e5ba8de0a8db315e5c06586ad2248cfea241653b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="cordeclsecurity-enumeration"></a><span data-ttu-id="8297b-102">CorDeclSecurity (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="8297b-102">CorDeclSecurity Enumeration</span></span>
<span data-ttu-id="8297b-103">Especifica las acciones de seguridad que se pueden realizar mediante la seguridad declarativa.</span><span class="sxs-lookup"><span data-stu-id="8297b-103">Specifies the security actions that can be performed using declarative security.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8297b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8297b-104">Syntax</span></span>  
  
```  
typedef enum CorDeclSecurity {  
  
    dclActionMask               =   0x001f,  
    dclActionNil                =   0x0000,  
    dclRequest                  =   0x0001,  
    dclDemand                   =   0x0002,  
    dclAssert                   =   0x0003,  
    dclDeny                     =   0x0004,  
    dclPermitOnly               =   0x0005,  
    dclLinktimeCheck            =   0x0006,  
    dclInheritanceCheck         =   0x0007,  
    dclRequestMinimum           =   0x0008,  
    dclRequestOptional          =   0x0009,  
    dclRequestRefuse            =   0x000a,  
    dclPrejitGrant              =   0x000b,  
    dclPrejitDenied             =   0x000c,  
    dclNonCasDemand             =   0x000d,  
    dclNonCasLinkDemand         =   0x000e,  
    dclNonCasInheritance        =   0x000f,  
    dclLinkDemandChoice         =   0x0010,  
    dclInheritanceDemandChoice  =   0x0011,  
    dclDemandChoice             =   0x0012,  
    dclMaximumValue             =   0x0012  
  
} CorDeclSecurity;  
```  
  
## <a name="members"></a><span data-ttu-id="8297b-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="8297b-105">Members</span></span>  
  
|<span data-ttu-id="8297b-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="8297b-106">Member</span></span>|<span data-ttu-id="8297b-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="8297b-107">Description</span></span>|  
|------------|-----------------|  
|`dclActionMask`|<span data-ttu-id="8297b-108">Reservado.</span><span class="sxs-lookup"><span data-stu-id="8297b-108">Reserved.</span></span>|  
|`dclActionNil`|<span data-ttu-id="8297b-109">Reservado.</span><span class="sxs-lookup"><span data-stu-id="8297b-109">Reserved.</span></span>|  
|`dclRequest`|<span data-ttu-id="8297b-110">Reservado.</span><span class="sxs-lookup"><span data-stu-id="8297b-110">Reserved.</span></span>|  
|`dclDemand`|<span data-ttu-id="8297b-111">Todos los autores de llamada de la pila necesitan que se les conceda el permiso especificado por el objeto de permiso actual.</span><span class="sxs-lookup"><span data-stu-id="8297b-111">All callers higher in the call stack are required to have been granted the permission specified by the current permission object.</span></span>|  
|`dclAssert`|<span data-ttu-id="8297b-112">El código de llamada puede tener acceso al recurso identificado por el objeto de permiso actual, incluso si los llamadores situados en la pila no tienen permiso para tener acceso al recurso</span><span class="sxs-lookup"><span data-stu-id="8297b-112">The calling code can access the resource identified by the current permission object, even if callers higher in the stack have not been granted permission to access the resource</span></span>|  
|`dclDeny`|<span data-ttu-id="8297b-113">La capacidad de tener acceso al recurso especificado por el objeto de permiso actual se deniega a los llamadores, incluso si se les ha concedido permiso para tener acceso a él.</span><span class="sxs-lookup"><span data-stu-id="8297b-113">The ability to access the resource specified by the current permission object is denied to callers, even if they have been granted permission to access it.</span></span>|  
|`dclPermitOnly`|<span data-ttu-id="8297b-114">Solo se puede acceder a los recursos especificados por este objeto de permiso, aunque al código se le haya concedido permiso de acceso a otros recursos.</span><span class="sxs-lookup"><span data-stu-id="8297b-114">Only the resources specified by this permission object can be accessed, even if the code has been granted permission to access other resources.</span></span>|  
|`dclLinktimeCheck`|<span data-ttu-id="8297b-115">El llamador inmediato es necesario que se les conceda el permiso especificado para un determinado período de tiempo.</span><span class="sxs-lookup"><span data-stu-id="8297b-115">The immediate caller is required to have been granted the specified permission for a given period of time.</span></span>|  
|`dclInheritanceCheck`|<span data-ttu-id="8297b-116">La clase derivada hereda de otra clase o invalida un método es necesaria que se les conceda el permiso especificado.</span><span class="sxs-lookup"><span data-stu-id="8297b-116">The derived class inheriting another class or overriding a method is required to have been granted the specified permission.</span></span>|  
|`dclRequestMinimum`|<span data-ttu-id="8297b-117">El llamador puede solicitar los permisos mínimos necesarios ejecutar código.</span><span class="sxs-lookup"><span data-stu-id="8297b-117">The caller can request for the minimum permissions required for code to run.</span></span> <span data-ttu-id="8297b-118">Esta acción solo se puede usar en el ámbito del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="8297b-118">This action can only be used within the scope of the assembly.</span></span>|  
|`dclRequestOptional`|<span data-ttu-id="8297b-119">El llamador puede solicitar permisos adicionales que son opcionales (no necesarias para ejecutar).</span><span class="sxs-lookup"><span data-stu-id="8297b-119">The caller can request for additional permissions that are optional (not required to run).</span></span> <span data-ttu-id="8297b-120">Esta solicitud rechaza implícitamente todos los demás permisos no solicitados específicamente.</span><span class="sxs-lookup"><span data-stu-id="8297b-120">This request implicitly refuses all other permissions not specifically requested.</span></span> <span data-ttu-id="8297b-121">Esta acción solo se puede usar en el ámbito del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="8297b-121">This action can only be used within the scope of the assembly.</span></span>|  
|`dclRequestRefuse`|<span data-ttu-id="8297b-122">No se le concederá la solicitud del llamador para los permisos que puedan usar indebidamente.</span><span class="sxs-lookup"><span data-stu-id="8297b-122">The caller's request for permissions that might be misused will not be granted.</span></span> <span data-ttu-id="8297b-123">Esta acción solo se puede usar en el ámbito del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="8297b-123">This action can only be used within the scope of the assembly.</span></span>|  
|`dclPrejitGrant`|<span data-ttu-id="8297b-124">Reservado.</span><span class="sxs-lookup"><span data-stu-id="8297b-124">Reserved.</span></span>|  
|`dclPrejitDenied`|<span data-ttu-id="8297b-125">Reservado.</span><span class="sxs-lookup"><span data-stu-id="8297b-125">Reserved.</span></span>|  
|`dclNonCasDemand`|<span data-ttu-id="8297b-126">Reservado.</span><span class="sxs-lookup"><span data-stu-id="8297b-126">Reserved.</span></span>|  
|`dclNonCasLinkDemand`|<span data-ttu-id="8297b-127">Es necesario que el llamador inmediato haya recibido el permiso especificado.</span><span class="sxs-lookup"><span data-stu-id="8297b-127">The immediate caller is required to have been granted the specified permission.</span></span>|  
|`dclNonCasInheritance`|<span data-ttu-id="8297b-128">Reservado.</span><span class="sxs-lookup"><span data-stu-id="8297b-128">Reserved.</span></span>|  
|`dclLinkDemandChoice`|<span data-ttu-id="8297b-129">Reservado.</span><span class="sxs-lookup"><span data-stu-id="8297b-129">Reserved.</span></span>|  
|`dclInheritanceDemandChoice`|<span data-ttu-id="8297b-130">Reservado.</span><span class="sxs-lookup"><span data-stu-id="8297b-130">Reserved.</span></span>|  
|`dclDemandChoice`|<span data-ttu-id="8297b-131">Reservado.</span><span class="sxs-lookup"><span data-stu-id="8297b-131">Reserved.</span></span>|  
|`dclMaximumValue`|<span data-ttu-id="8297b-132">Reservado.</span><span class="sxs-lookup"><span data-stu-id="8297b-132">Reserved.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8297b-133">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8297b-133">Requirements</span></span>  
 <span data-ttu-id="8297b-134">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8297b-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8297b-135">**Encabezado:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="8297b-135">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="8297b-136">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8297b-136">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8297b-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="8297b-137">See Also</span></span>  
 [<span data-ttu-id="8297b-138">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="8297b-138">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)