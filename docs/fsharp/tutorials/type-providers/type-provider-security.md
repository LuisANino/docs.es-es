---
title: Seguridad del proveedor de tipos
description: "Obtenga información acerca de la seguridad del proveedor de tipo de F #, incluida la forma de cambiar la configuración de confianza de un proveedor de tipos."
keywords: "visual f#, f#, programación funcional"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 9c5a8a1f-5a31-490d-83c0-8beabda75c78
ms.openlocfilehash: c8f03ee90d4dce1d3484a9dfe8951d500d509a2b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="type-provider-security"></a>Seguridad del proveedor de tipos

Proveedores de tipo son ensamblados (archivos DLL) al que hace referencia el proyecto de F # o el script que contienen código para conectarse a orígenes de datos externos y esta información de tipo de superficie para el entorno de tipo de F #. Por lo general, solo se ejecuta código en los ensamblados que se hace referencia, al compilar y, a continuación, ejecute el código (o en el caso de una secuencia de comandos, envíe el código de F # Interactive). Sin embargo, un ensamblado de proveedor de tipo se ejecutará dentro de Visual Studio cuando simplemente se explora el código en el editor. Esto sucede porque los proveedores de tipo que deba ejecutar para agregar información adicional para el editor, por ejemplo, información rápida sobre herramientas, finalización de IntelliSense y así sucesivamente. Como resultado, hay consideraciones de seguridad adicionales para el tipo de proveedor ensamblados, ya que se ejecutan automáticamente en el proceso de Visual Studio.


## <a name="security-warning-dialog"></a>Cuadro de diálogo de advertencia de seguridad
Cuando se usa un ensamblado de proveedor de tipo concreto por primera vez, Visual Studio muestra un cuadro de diálogo de seguridad que le advierte que el proveedor de tipo está a punto de ejecutarse. Antes de Visual Studio carga el proveedor de tipos, ofrece la oportunidad de decidir si confiar en este proveedor determinado. Si confía en el origen del proveedor de tipo, a continuación, seleccione "confiar en este proveedor de tipo". Si no confía en el origen del proveedor de tipo, a continuación, seleccione "no confiar en este proveedor de tipo." Confiar en el proveedor permite que se ejecuta dentro de Visual Studio y proporcionar IntelliSense y compilar características. Pero si el propio proveedor de tipo es malintencionado, al ejecutar su código pueda poner en peligro el equipo.

Si el proyecto contiene código que hace referencia a proveedores de tipos que eligió en el cuadro de diálogo no confía, a continuación, en tiempo de compilación, el compilador notificará un error que indica que el proveedor de tipos no es de confianza. Los tipos que son depende del proveedor de tipo no es de confianza se indican mediante un subrayado ondulado rojo. Es seguro examinar el código en el editor.

Si decide cambiar la configuración de confianza directamente en Visual Studio, realice los pasos siguientes.


#### <a name="to-change-the-trust-settings-for-type-providers"></a>Para cambiar la configuración de confianza para los proveedores de tipo

1. En el `Tools` menú, seleccione `Options`y expanda el `F# Tools` nodo.
<br />

2. Seleccione `Type Providers`, en la lista de proveedores de tipo, seleccione la casilla de verificación para los proveedores de tipo confía y desactive la casilla de verificación para los que no confías.
<br />


## <a name="see-also"></a>Vea también
[Proveedores de tipos](index.md)
