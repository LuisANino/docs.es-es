---
title: "Parámetros REF CURSOR de Oracle"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c6b25b8b-0bdd-41b2-9c7c-661f070c2247
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: f01ace7bc7dfe1191dac8990210032b60e16f255
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="oracle-ref-cursors"></a>Parámetros REF CURSOR de Oracle
El proveedor de datos de .NET Framework para Oracle admite Oracle **REF CURSOR** tipo de datos. Cuando utilice el proveedor de datos para trabajar con cursores REF CURSOR de Oracle, debe tener en cuenta los siguientes comportamientos.  
  
> [!NOTE]
>  Algunos de ellos difieren de los del proveedor Microsoft OLE DB para Oracle (MSDAORA).  
  
-   Por motivos de rendimiento, el proveedor de datos para Oracle no enlaza automáticamente **REF CURSOR** tipos de datos, como hace MSDAORA, a menos que especifique explícitamente.  
  
-   El proveedor de datos no admite ninguna secuencia de escape ODBC, lo que incluye el escape {resultset} usado para especificar parámetros REF CURSOR.  
  
-   Para ejecutar un procedimiento almacenado que devuelve los cursores REF CURSOR, debe definir los parámetros en la <xref:System.Data.OracleClient.OracleParameterCollection> con una <xref:System.Data.OracleClient.OracleType> de **Cursor** y un <xref:System.Data.OracleClient.OracleParameter.Direction%2A> de **salida**. El proveedor de datos admite el enlace de cursores REF CURSOR sólo como parámetros de salida; no los admite como parámetros de entrada.  
  
-   No se permite la obtención de un <xref:System.Data.OracleClient.OracleDataReader> del valor del parámetro. Los valores son del tipo <xref:System.DBNull> después de la ejecución del comando.  
  
-   El único **CommandBehavior** valor de enumeración que funciona con los cursores REF cursor (por ejemplo, al llamar a <xref:System.Data.OracleClient.OracleCommand.ExecuteReader%2A>) es **CloseConnection**; todos los demás se omiten.  
  
-   El orden de los cursores REF cursor en el **OracleDataReader** depende del orden de los parámetros en la **OracleParameterCollection**. Se omite la propiedad <xref:System.Data.OracleClient.OracleParameter.ParameterName%2A>.  
  
-   PL/SQL **tabla** no se admite el tipo de datos. No obstante, los cursores REF CURSOR resultan más eficientes. Si tiene que utilizar un **tabla** tipo de datos, utilice el proveedor de datos OLE DB .NET con MSDAORA.  
  
## <a name="in-this-section"></a>En esta sección  
 [Ejemplos de REF CURSOR](../../../../docs/framework/data/adonet/ref-cursor-examples.md)  
 Contiene tres ejemplos en los que se muestra el uso de cursores REF CURSOR.  
  
 [Parámetros REF CURSOR en un objeto OracleDataReader](../../../../docs/framework/data/adonet/ref-cursor-parameters-in-an-oracledatareader.md)  
 Muestra cómo ejecutar un procedimiento almacenado PL/SQL que devuelve un parámetro REF CURSOR y lee el valor como un **OracleDataReader**.  
  
 [Recuperación de datos desde varios parámetros REF CURSOR utilizando un objeto OracleDataReader](../../../../docs/framework/data/adonet/retrieving-data-from-multiple-ref-cursors.md)  
 Muestra cómo ejecutar un procedimiento almacenado PL/SQL que devuelve dos parámetros REF CURSOR y lee los valores mediante un **OracleDataReader**.  
  
 [Relleno de un conjunto de datos utilizando uno o varios parámetros REF CURSOR](../../../../docs/framework/data/adonet/filling-a-dataset-using-one-or-more-ref-cursors.md)  
 Muestra cómo ejecutar un procedimiento almacenado PL/SQL que devuelve dos parámetros REF CURSOR y llena un <xref:System.Data.DataSet> con las filas que se devuelven.  
  
## <a name="see-also"></a>Vea también  
 [Oracle y ADO.NET](../../../../docs/framework/data/adonet/oracle-and-adonet.md)  
 [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](http://go.microsoft.com/fwlink/?LinkId=217917)
