---
title: -highentropyva (Opciones del compilador de C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: /highentropyva
helpviewer_keywords:
- /highentropyva compiler option [C#]
- -highentropyva compiler option [C#]
- highentropyva compiler option [C#]
ms.assetid: eaf409b3-384e-49dd-9417-62453658f421
caps.latest.revision: "8"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 5746caed8c1bf61038c97a49987c4c168eef9f3f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="highentropyva-c-compiler-options"></a>/highentropyva (Opciones del compilador de C#)
La opción del compilador **/highentropyva** indica al kernel de Windows si un archivo ejecutable determinado admite la selección aleatoria del diseño del espacio de direcciones (ASLR) de alta entropía.  
  
## <a name="syntax"></a>Sintaxis  
  
```console  
/highentropyva[+ | -]  
```  
  
## <a name="arguments"></a>Argumentos  
 `+` &#124; `-`  
 Esta opción especifica que un archivo ejecutable de 64 bits o un archivo ejecutable que está marcado con la opción del compilador [/platform:anycpu](../../../csharp/language-reference/compiler-options/platform-compiler-option.md) admite un espacio de direcciones virtuales de alta entropía. La opción está deshabilitada de forma predeterminada. Para habilitarla, use **/highentropyva+** o **/highentropyva**.  
  
## <a name="remarks"></a>Comentarios  
 La opción **/highentropyva** habilita las versiones compatibles del kernel de Windows para usar niveles superiores de entropía al aleatorizar el diseño del espacio de direcciones de un proceso como parte de ASLR. El uso de niveles superiores de entropía significa que un mayor número de direcciones se puede asignar a las regiones de memoria como pilas y montones. Como resultado, la ubicación de un área de memoria específica es más difícil de adivinar.  
  
 Cuando se especifica la opción del compilador **/highentropyva**, el archivo ejecutable de destino y todos los módulos de los que depende deben ser capaces de controlar los valores de puntero que son superiores a 4 gigabytes (GB), cuando se ejecutan como un proceso de 64 bits.
