---
title: 'Interfaces de C#: un paseo por el lenguaje C#'
description: Las interfaces definen contratos implementados por tipos en C#
keywords: ".NET, csharp, interfaces, herencia múltiple, polimorfismo"
author: BillWagner
ms.author: wiwagn
ms.date: 08/10/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: a9bf82f4-efd1-4216-bd34-4ef0fa48c968
ms.openlocfilehash: 673ac56f3f5732fcda02d313b6f4273708ae365f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="interfaces"></a>Interfaces

Una ***interfaz*** define un contrato que se puede implementar mediante clases y structs. Una interfaz puede contener métodos, propiedades, eventos e indexadores. Una interfaz no proporciona implementaciones de los miembros que define, simplemente especifica los miembros que se deben proporcionar mediante clases o structs que implementan la interfaz.

Las interfaces pueden usar ***herencia múltiple***. En el ejemplo siguiente, la interfaz `IComboBox` hereda de `ITextBox` y `IListBox`.

[!code-csharp[InterfacesOne](../../../samples/snippets/csharp/tour/interfaces/Program.cs#L5-L17)]

Las clases y los structs pueden implementar varias interfaces. En el ejemplo siguiente, la clase `EditBox` implementa `IControl` y `IDataBound`.

[!code-csharp[InterfacesTwo](../../../samples/snippets/csharp/tour/interfaces/Program.cs#L19-L27)]

Cuando una clase o un struct implementan una interfaz determinada, las instancias de esa clase o struct se pueden convertir implícitamente a ese tipo de interfaz. Por ejemplo

[!code-csharp[InterfacesThree](../../../samples/snippets/csharp/tour/interfaces/Program.cs#L33-L35)]

En casos donde una instancia no se conoce estáticamente para implementar una interfaz determinada, se pueden usar conversiones de tipo dinámico. Por ejemplo, las siguientes instrucciones usan conversiones de tipo dinámico para obtener las implementaciones de `IControl` y `IDataBound` de un objeto. Dado que el tipo real en tiempo de ejecución del objeto es `EditBox`, las conversiones se realizan correctamente.

[!code-csharp[InterfacesFour](../../../samples/snippets/csharp/tour/interfaces/Program.cs#L40-L42)]

En la clase `EditBox` anterior, el método `Paint` de la interfaz `IControl` y el método `Bind` de la interfaz `IDataBound` se implementan mediante miembros públicos. C# también admite ***implementaciones de miembros de interfaz*** explícitos, lo que permite que la clase o el struct eviten que los miembros se conviertan en públicos. Una implementación de miembro de interfaz explícito se escribe con el nombre de miembro de interfaz completo. Por ejemplo, la clase `EditBox` podría implementar los métodos `IControl.Paint` y `IDataBound.Bind` mediante implementaciones de miembros de interfaz explícitos del modo siguiente.

[!code-csharp[InterfacesFive](../../../samples/snippets/csharp/tour/interfaces/Program.cs#L60-L64)]

Solo se puede acceder a los miembros de interfaz explícitos mediante el tipo de interfaz. Por ejemplo, la implementación de `IControl.Paint` proporcionada por la clase EditBox anterior solo se puede invocar si se convierte primero la referencia `EditBox` al tipo de interfaz `IControl`.

[!code-csharp[InterfacesFive](../../../samples/snippets/csharp/tour/interfaces/Program.cs#L71-L74)]

>[!div class="step-by-step"]
[Anterior](arrays.md)
[Siguiente](enums.md)
