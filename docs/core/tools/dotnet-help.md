---
title: 'Comando dotnet help: CLI de .NET Core'
description: "El comando dotnet help muestra documentación en línea más detallada para el comando especificado."
author: mairaw
ms.author: mairaw
ms.date: 08/17/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.workload: dotnetcore
ms.openlocfilehash: 47b7b53b9f13935bbd2cf508c7c57d00584822d0
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="dotnet-help-reference"></a>Referencia de dotnet help

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-2plus.md)]

## <a name="name"></a>nombre

`dotnet help`: muestra documentación más detallada en línea para el comando especificado.

## <a name="synopsis"></a>Sinopsis

`dotnet help <COMMAND_NAME> [-h|--help]`

## <a name="description"></a>Description

El comando `dotnet help` abre la página de referencia para obtener información más detallada sobre el comando especificado en docs.microsoft.com.

## <a name="arguments"></a>Argumentos

`COMMAND_NAME`

Nombre del comando de la CLI de .NET Core. Para obtener una lista de los comandos de la CLI válidos, vea [Comandos de la CLI](index.md#cli-commands).

## <a name="options"></a>Opciones

`-h|--help`

Imprime una corta ayuda para el comando.

## <a name="examples"></a>Ejemplos

Se abre la página de documentación del comando [dotnet new](dotnet-new.md):

`dotnet help new`
