---
title: "-moduleassemblyname (Opción del compilador de C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: /moduleassemblyname
helpviewer_keywords:
- moduleassemblyname compiler option [C#]
- /moduleassemblyname compiler option [C#]
- .moduleassemblyname compiler option [C#]
ms.assetid: d464d9b9-f18d-423b-95e9-66c7878fd53a
caps.latest.revision: "10"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: c8ebd6f7498adead4586c9e90ec58ca8efe81aaa
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="moduleassemblyname-c-compiler-option"></a>/moduleassemblyname (Opción del compilador de C#)
Especifica un ensamblado con tipos no públicos a los que puede acceder un archivo .netmodule.  
  
## <a name="syntax"></a>Sintaxis  
  
```console  
/moduleassemblyname:assembly_name  
```  
  
## <a name="arguments"></a>Argumentos  
 `assembly_name`  
 El nombre del ensamblado a cuyos tipos no públicos .netmodule puede tener acceso.  
  
## <a name="remarks"></a>Comentarios  
 Se debería usar **/moduleassemblyname** al compilar un .netmodule cuando se den las condiciones siguientes:  
  
-   .netmodule necesita tener acceso a los tipos no públicos de un ensamblado existente.  
  
-   Sabe el nombre del ensamblado en el que se compilará .netmodule.  
  
-   El ensamblado existente ha concedido acceso de ensamblado de confianza al ensamblado en el que se compilará .netmodule.  
  
 Para obtener más información sobre cómo compilar .netmodule, vea [/target:module (Opciones del compilador de C#)](../../../csharp/language-reference/compiler-options/target-module-compiler-option.md).  
  
 Para obtener más información sobre los ensamblados de confianza, vea [Ensamblados de confianza](../../programming-guide/concepts/assemblies-gac/friend-assemblies.md).  
  
 Esta opción no está disponible en el entorno de desarrollo; solo está disponible cuando se compila desde la línea de comandos.  
  
 Esta opción del compilador no está disponible en Visual Studio y no se puede cambiar mediante programación.  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo compila un ensamblado con un tipo privado que concede acceso de ensamblado de confianza a un ensamblado llamado csman_an_assembly.  
  
```csharp  
// moduleassemblyname_1.cs  
// compile with: /target:library  
using System;  
using System.Runtime.CompilerServices;  
  
[assembly:InternalsVisibleTo ("csman_an_assembly")]  
  
class An_Internal_Class   
{  
    public void Test()   
    {   
        Console.WriteLine("An_Internal_Class.Test called");   
    }  
}  
```  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo compila un .netmodule que tiene acceso a un tipo no público del ensamblado moduleassemblyname_1.dll. Sabiendo que este .netmodule se integrará en un ensamblado denominado csman_an_assembly, se puede especificar **/moduleassemblyname**, lo que permite que .netmodule tenga acceso a los tipos no públicos de un ensamblado que ha concedido acceso de ensamblado de confianza a csman_an_assembly.  
  
```csharp  
// moduleassemblyname_2.cs  
// compile with: /moduleassemblyname:csman_an_assembly /target:module /reference:moduleassemblyname_1.dll  
class B {  
    public void Test() {  
        An_Internal_Class x = new An_Internal_Class();  
        x.Test();  
    }  
}  
```  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo de código compila el ensamblado csman_an_assembly, haciendo referencia al ensamblado compilado previamente y a .netmodule.  
  
```csharp  
// csman_an_assembly.cs  
// compile with: /addmodule:moduleassemblyname_2.netmodule /reference:moduleassemblyname_1.dll  
class A {  
    public static void Main() {  
        B bb = new B();  
        bb.Test();  
    }  
}  
```  
  
 **Se ha llamado a An_Internal_Class.Test**  
## <a name="see-also"></a>Vea también  
 [Opciones del compilador de C#](../../../csharp/language-reference/compiler-options/index.md)  
 [Administrar propiedades de soluciones y proyectos](/visualstudio/ide/managing-project-and-solution-properties)
