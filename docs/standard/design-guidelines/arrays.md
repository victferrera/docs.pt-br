---
title: Matrizes
ms.date: 10/22/2008
helpviewer_keywords:
- class library design guidelines [.NET Framework], arrays
- arrays [.NET Framework], usage guidelines
- empty arrays
ms.assetid: 66a1b3d8-6f3f-4715-b235-e1ff95e32d8e
ms.openlocfilehash: 11c1d23af4cf599ba632144634947520a1647ae7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95701387"
---
# <a name="arrays"></a>Matrizes

✔️ preferir usar coleções em matrizes em APIs públicas. A seção [coleções](guidelines-for-collections.md) fornece detalhes sobre como escolher entre coleções e matrizes.

 ❌ Não use campos de matriz somente leitura. O próprio campo é somente leitura e não pode ser alterado, mas os elementos na matriz podem ser alterados.

 ✔️ Considere o uso de matrizes denteadas em vez de matrizes multidimensionais.

 Uma matriz denteada é uma matriz com elementos que também são matrizes. As matrizes que compõem os elementos podem ser de tamanhos diferentes, levando a menos espaço desperdiçado para alguns conjuntos de dados (por exemplo, matriz esparsa) em comparação com matrizes multidimensionais. Além disso, o CLR otimiza as operações de índice em matrizes denteadas, para que possam apresentar um melhor desempenho de tempo de execução em alguns cenários.

 *Partes © 2005, 2009 Microsoft Corporation. Todos os direitos reservados.*

 *Reimpresso com permissão da Pearson Education, Inc. das [Diretrizes de Design do Framework: convenções, linguagens e padrões para bibliotecas do .NET reutilizável, 2ª edição](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) por Krzysztof Cwalina e Brad Abrams, publicado em 22 de outubro de 2008 por Addison-Wesley Professional como parte da série de desenvolvimento do Microsoft Windows.*

## <a name="see-also"></a>Confira também

- <xref:System.Array>
- [Diretrizes de design de estrutura](index.md)
- [Diretrizes de uso](usage-guidelines.md)
