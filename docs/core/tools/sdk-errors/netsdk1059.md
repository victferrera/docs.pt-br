---
title: 'NETSDK1059: o projeto contém uma ferramenta CLI do .NET obsoleta'
description: Como resolver o problema de um projeto que contém uma ferramenta CLI do .NET obsoleta.
author: sfoslund
ms.topic: error-reference
ms.date: 10/09/2020
f1_keywords:
- NETSDK1059
ms.openlocfilehash: b80f42495e1aff8d37008946f10f68c195d5a9ec
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95713113"
---
# <a name="netsdk1059-project-contains-obsolete-net-cli-tool"></a>NETSDK1059: o projeto contém uma ferramenta CLI do .NET obsoleta

**Este artigo aplica-se a:** ✔️ SDK 2.1.100 do .NET Core e versões posteriores

Quando o SDK do .NET emite aviso NETSDK1059, seu projeto contém uma ferramenta CLI do .NET obsoleta. A partir do .NET Core 2,1, essas ferramentas estão incluídas no SDK do .NET e não precisam ser referenciadas explicitamente pelo projeto. Mais informações para a migração para o .NET Core 2,1 podem ser encontradas [aqui](https://aka.ms/dotnetclitools-in-box).
