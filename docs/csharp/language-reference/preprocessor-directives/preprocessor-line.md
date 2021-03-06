---
title: '#<a name="line-c-reference"></a>line (Referencia de C#)'
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: '#line'
helpviewer_keywords: '#line directive [C#]'
ms.assetid: 6439e525-5dd5-4acb-b8ea-efabb32ff95b
caps.latest.revision: "13"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 3d2f42915d214349eebff40949482d7f603c0c2c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="line-c-reference"></a>#line (Referencia de C#)
`#line` le permite modificar el número de línea del compilador y (opcionalmente) la salida del nombre de archivo de errores y advertencias. En este ejemplo, se muestra cómo notificar dos advertencias asociadas con números de línea. La directiva `#line 200` fuerza el número de línea para que sea 200 (aunque el valor predeterminado es 7) y hasta la siguiente directiva #line, el nombre de archivo se notificará como "Especial". La directiva #line predeterminada devuelve la numeración de líneas a su numeración predeterminada, que cuenta las líneas a las que la directiva anterior ha cambiado el número.  
  
```csharp
class MainClass  
{  
    static void Main()  
    {  
#line 200 "Special"  
        int i;    // CS0168 on line 200  
        int j;    // CS0168 on line 201  
#line default  
        char c;   // CS0168 on line 9  
        float f;  // CS0168 on line 10  
#line hidden // numbering not affected  
        string s;   
        double d; // CS0168 on line 13  
    }  
}  
```  
  
## <a name="remarks"></a>Comentarios  
 La directiva `#line` podría usarse en un paso intermedio automatizado en el proceso de compilación. Por ejemplo, si se han eliminado las líneas del archivo de código fuente original, pero aún quiere que el compilador genere unos resultados en función de la numeración de líneas original en el archivo, puede quitar las líneas y, después, simular la numeración de líneas original con `#line`.  
  
 La directiva `#line hidden` oculta las líneas sucesivas del depurador, de forma que, cuando el desarrollador ejecuta paso a paso el código, cualquier línea entre `#line hidden` y la siguiente directiva `#line` (suponiendo que no sea otra directiva `#line hidden`) se depurará paso a paso por procedimientos. Esta opción también se puede usar para permitir que ASP.NET diferencie entre el código generado por el equipo y el definido por el usuario. Aunque ASP.NET es el consumidor principal de esta característica, es probable que la usen más generadores de código fuente.  
  
 Una directiva `#line hidden` no afecta a los nombres de archivo o números de línea en el informe de errores. Es decir, si se produce un error en un bloque oculto, el compilador notificará el nombre de archivo y número de línea reales del error.  
  
 La directiva `#line filename` especifica el nombre de archivo que quiere que aparezca en la salida del compilador. De forma predeterminada, se usa el nombre real del archivo de código fuente. El nombre de archivo debe estar entre comillas dobles ("") y debe ir precedido de un número de línea.  
  
 Un archivo de código fuente puede tener cualquier número de directivas `#line`.  
  
## <a name="example-1"></a>Ejemplo 1  
 En el ejemplo siguiente, se muestra cómo el depurador omite las líneas ocultas en el código. Al ejecutar el ejemplo, mostrará tres líneas de texto. En cambio, al establecer un punto de interrupción, como se muestra en el ejemplo, y presionar F10 para recorrer el código, observará que el depurador omite la línea oculta. Tenga también en cuenta que, incluso si configura un punto de interrupción en la línea oculta, el depurador lo omitirá.  
  
```csharp
// preprocessor_linehidden.cs  
using System;  
class MainClass   
{  
    static void Main()   
    {  
        Console.WriteLine("Normal line #1."); // Set break point here.  
#line hidden  
        Console.WriteLine("Hidden line.");  
#line default  
        Console.WriteLine("Normal line #2.");  
    }  
}  
```  
  
## <a name="see-also"></a>Vea también  
 [Referencia de C#](../../../csharp/language-reference/index.md)  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
 [Directivas de preprocesador de C#](../../../csharp/language-reference/preprocessor-directives/index.md)
