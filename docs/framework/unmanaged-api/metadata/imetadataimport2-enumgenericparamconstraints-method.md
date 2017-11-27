---
title: "IMetaDataImport2::EnumGenericParamConstraints (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport2.EnumGenericParamConstraints
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport2::EnumGenericParamConstraints
helpviewer_keywords:
- EnumGenericParamConstraints method [.NET Framework metadata]
- IMetaDataImport2::EnumGenericParamConstraints method [.NET Framework metadata]
ms.assetid: 8a7d4e40-28fe-4e14-b801-4049880130e7
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 9afbcae016ce111456588ddbbc9f664dd7e76196
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimport2enumgenericparamconstraints-method"></a><span data-ttu-id="93a47-102">IMetaDataImport2::EnumGenericParamConstraints (Método)</span><span class="sxs-lookup"><span data-stu-id="93a47-102">IMetaDataImport2::EnumGenericParamConstraints Method</span></span>
<span data-ttu-id="93a47-103">Obtiene un enumerador para una matriz de restricciones de parámetros genéricos asociada al parámetro genérico representado por el token especificado.</span><span class="sxs-lookup"><span data-stu-id="93a47-103">Gets an enumerator for an array of generic parameter constraints associated with the generic parameter represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="93a47-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="93a47-104">Syntax</span></span>  
  
```  
HRESULT EnumGenericParamConstraints (  
    [in, out] HCORENUM                *phEnum,  
    [in]  mdGenericParam              tk,  
    [out] mdGenericParamConstraint    rGenericParamConstraints[],  
    [in]  ULONG                       cMax,  
    [out] ULONG                       *pcGenericParamConstraints  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="93a47-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="93a47-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="93a47-106">[entrada, salida] Un puntero para el enumerador.</span><span class="sxs-lookup"><span data-stu-id="93a47-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `tk`  
 <span data-ttu-id="93a47-107">[in]   Un token que representa el parámetro genérico cuyas restricciones son que hay que enumerar.</span><span class="sxs-lookup"><span data-stu-id="93a47-107">[in]   A token that represents the generic parameter whose constraints are to be enumerated.</span></span>  
  
 `rGenericParamConstraints`  
 <span data-ttu-id="93a47-108">[out] La matriz de restricciones de parámetro genérico para enumerar.</span><span class="sxs-lookup"><span data-stu-id="93a47-108">[out] The array of generic parameter constraints to enumerate.</span></span>  
  
 `cMax`  
 <span data-ttu-id="93a47-109">[in]   El número máximo solicitado de símbolos (tokens) para colocar en `rGenericParamConstraints`.</span><span class="sxs-lookup"><span data-stu-id="93a47-109">[in]   The requested maximum number of tokens to place in `rGenericParamConstraints`.</span></span>  
  
 `pcGenericParamConstraints`  
 <span data-ttu-id="93a47-110">[out] Un puntero al número de símbolos (tokens) se coloca en `rGenericParamConstraints`.</span><span class="sxs-lookup"><span data-stu-id="93a47-110">[out] A pointer to the number of tokens placed in `rGenericParamConstraints`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="93a47-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="93a47-111">Return Value</span></span>  
  
|<span data-ttu-id="93a47-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="93a47-112">HRESULT</span></span>|<span data-ttu-id="93a47-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="93a47-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="93a47-114">`EnumGenericParameterConstraints`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="93a47-114">`EnumGenericParameterConstraints` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="93a47-115">`phEnum`no tiene ningún elemento de miembro.</span><span class="sxs-lookup"><span data-stu-id="93a47-115">`phEnum` has no member elements.</span></span> <span data-ttu-id="93a47-116">En este caso, `pcGenericParameterConstraints` se establece en 0 (cero).</span><span class="sxs-lookup"><span data-stu-id="93a47-116">In this case, `pcGenericParameterConstraints` is set to 0 (zero).</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="93a47-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="93a47-117">Requirements</span></span>  
 <span data-ttu-id="93a47-118">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="93a47-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="93a47-119">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="93a47-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="93a47-120">**Biblioteca:** usada como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="93a47-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="93a47-121">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="93a47-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93a47-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="93a47-122">See Also</span></span>  
 [<span data-ttu-id="93a47-123">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="93a47-123">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)  
 [<span data-ttu-id="93a47-124">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="93a47-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)