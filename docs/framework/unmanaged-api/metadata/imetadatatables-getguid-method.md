---
title: "IMetaDataTables::GetGuid (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataTables.GetGuid
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataTables::GetGuid
helpviewer_keywords:
- GetGuid method [.NET Framework metadata]
- IMetaDataTables::GetGuid method [.NET Framework metadata]
ms.assetid: a3546316-e24d-417f-9909-e45d42c9d471
topic_type: apiref
caps.latest.revision: "15"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 52b96fbe582a5c8e1818462a5e28970dbaf50605
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="imetadatatablesgetguid-method"></a><span data-ttu-id="51eea-102">IMetaDataTables::GetGuid (Método)</span><span class="sxs-lookup"><span data-stu-id="51eea-102">IMetaDataTables::GetGuid Method</span></span>
<span data-ttu-id="51eea-103">Obtiene un identificador GUID de la fila en el índice especificado.</span><span class="sxs-lookup"><span data-stu-id="51eea-103">Gets a GUID from the row at the specified index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="51eea-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="51eea-104">Syntax</span></span>  
  
```  
HRESULT GetGuid (   
    [in]  ULONG       ixGuid,  
    [out] const GUID  **ppGUID  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="51eea-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="51eea-105">Parameters</span></span>  
 `ixGuid`  
 <span data-ttu-id="51eea-106">[in] El índice de la fila de la que se va a obtener el GUID.</span><span class="sxs-lookup"><span data-stu-id="51eea-106">[in] The index of the row from which to get the GUID.</span></span>  
  
 `ppGuid`  
 <span data-ttu-id="51eea-107">[out] Un puntero a un puntero al GUID del servicio.</span><span class="sxs-lookup"><span data-stu-id="51eea-107">[out] A pointer to a pointer to the GUID.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="51eea-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="51eea-108">Remarks</span></span>  
 <span data-ttu-id="51eea-109">No se recomienda el uso de este método, porque no devuelve resultados coherentes.</span><span class="sxs-lookup"><span data-stu-id="51eea-109">We do not recommend the use of this method, because it does not return consistent results.</span></span> <span data-ttu-id="51eea-110">Para obtener información acerca de la tabla GUID, consulte la documentación de Common Language Infrastructure (CLI), especialmente "partición II: definición y semántica de los metadatos".</span><span class="sxs-lookup"><span data-stu-id="51eea-110">For information about the GUID table, see the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics".</span></span> <span data-ttu-id="51eea-111">La documentación está disponible en línea; vea [ECMA C# and Common Language Infrastructure Standards](http://go.microsoft.com/fwlink/?LinkID=99212) (Estándares de ECMA C# y Common Language Infrastructure) en MSDN y [Standard ECMA-335 - Common Language Infrastructure (CLI)](http://go.microsoft.com/fwlink/?LinkID=65552) (Estándar ECMA-335: Common Language Infrastructure [CLI]) en el sitio web de Ecma International.</span><span class="sxs-lookup"><span data-stu-id="51eea-111">The documentation is available online; see [ECMA C# and Common Language Infrastructure Standards](http://go.microsoft.com/fwlink/?LinkID=99212) on MSDN and [Standard ECMA-335 - Common Language Infrastructure (CLI)](http://go.microsoft.com/fwlink/?LinkID=65552) on the Ecma International Web site.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="51eea-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="51eea-112">Requirements</span></span>  
 <span data-ttu-id="51eea-113">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="51eea-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="51eea-114">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="51eea-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="51eea-115">**Biblioteca:** usada como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="51eea-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="51eea-116">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="51eea-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51eea-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="51eea-117">See Also</span></span>  
 [<span data-ttu-id="51eea-118">IMetaDataTables (interfaz)</span><span class="sxs-lookup"><span data-stu-id="51eea-118">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)  
 [<span data-ttu-id="51eea-119">IMetaDataTables2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="51eea-119">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)