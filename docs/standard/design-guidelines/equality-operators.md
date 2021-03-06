---
title: Operadores de igualdade
ms.date: 10/22/2008
helpviewer_keywords:
- class library design guidelines [.NET Framework], Equals method
- class library design guidelines [.NET Framework], equality operator
- equality operator (==) [.NET Framework]
- Equals method
- == operator (equality) [.NET Framework]
ms.assetid: bc496a91-fefb-4ce0-ab4c-61f09964119a
ms.openlocfilehash: 2331a852adb4dd254af85060a5077f454bcfe0eb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95734420"
---
# <a name="equality-operators"></a>Operadores de igualdade

Esta seção discute como sobrecarregar operadores de igualdade e se refere `operator==` e `operator!=` como operadores de igualdade.

 ❌ Não sobrecarregar um dos operadores de igualdade e não o outro.

 ✔️ garantir que <xref:System.Object.Equals%2A?displayProperty=nameWithType> e os operadores de igualdade tenham exatamente a mesma semântica e características de desempenho semelhantes.

 Isso geralmente significa que `Object.Equals` o precisa ser substituído quando os operadores de igualdade estão sobrecarregados.

 ❌ Evite lançar exceções de operadores de igualdade.

 Por exemplo, retorne FALSE se um dos argumentos for nulo em vez de lançá-lo `NullReferenceException` .

## <a name="equality-operators-on-value-types"></a>Operadores de igualdade em tipos de valor

 ✔️ sobrecarregar os operadores de igualdade em tipos de valor, se a igualdade for significativa.

 Na maioria das linguagens de programação, não há nenhuma implementação padrão de `operator==` para tipos de valor.

## <a name="equality-operators-on-reference-types"></a>Operadores de igualdade em tipos de referência

 ❌ EVITE sobrecarregar operadores de igualdade em tipos de referência mutáveis.

 Muitas linguagens têm operadores de igualdade internos para tipos de referência. Os operadores internos geralmente implementam a igualdade de referência e muitos desenvolvedores ficam surpresos quando o comportamento padrão é alterado para a igualdade do valor.

 Esse problema é mitigado para tipos de referência imutáveis porque a imutabilidade torna muito mais difícil observar a diferença entre igualdade de referência e igualdade de valor.

 ❌ EVITE sobrecarregar operadores de igualdade em tipos de referência se a implementação for significativamente mais lenta do que a de igualdade de referência.

 *Partes © 2005, 2009 Microsoft Corporation. Todos os direitos reservados.*

 *Reimpresso com permissão da Pearson Education, Inc. das [Diretrizes de Design do Framework: convenções, linguagens e padrões para bibliotecas do .NET reutilizável, 2ª edição](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) por Krzysztof Cwalina e Brad Abrams, publicado em 22 de outubro de 2008 por Addison-Wesley Professional como parte da série de desenvolvimento do Microsoft Windows.*

## <a name="see-also"></a>Confira também

- [Diretrizes de design de estrutura](index.md)
- [Diretrizes de uso](usage-guidelines.md)
