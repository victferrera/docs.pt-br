---
title: 'Como: Implementar partições dinâmicas'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tasks, how to create a dynamic partitioner
ms.assetid: c875ad12-a161-43e6-ad1c-3d6927c536a7
ms.openlocfilehash: 1120d846743ac3b89d2d110b4d1abdd0083f9eab
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/18/2020
ms.locfileid: "94825735"
---
# <a name="how-to-implement-dynamic-partitions"></a>Como: Implementar partições dinâmicas

O exemplo a seguir mostra como implementar um <xref:System.Collections.Concurrent.OrderablePartitioner%601?displayProperty=nameWithType> personalizado que implementa o particionamento dinâmico e pode ser usado de determinadas sobrecargas <xref:System.Threading.Tasks.Parallel.ForEach%2A> e do PLINQ.  
  
## <a name="example"></a>Exemplo

Cada vez que uma partição chama <xref:System.Collections.IEnumerator.MoveNext%2A> no enumerador, o enumerador fornece a partição com um elemento de lista. No caso do PLINQ e do <xref:System.Threading.Tasks.Parallel.ForEach%2A>, a partição é uma instância de <xref:System.Threading.Tasks.Task>. Como as solicitações ocorrem simultaneamente em vários threads, o acesso ao índice atual é sincronizado.  

[!code-csharp[TPL_Partitioners#04](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_partitioners/cs/partitioner02.cs#OrderableListPartitioner)]
[!code-vb[TPL_Partitioners#04](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_partitioners/vb/dynamicpartitioner.vb#04)]  

Este é um exemplo de particionamento, com cada parte consistindo em um elemento. Ao fornecer mais elementos de uma vez, você pode reduzir a contenção no bloqueio e, teoricamente, alcançar um desempenho mais rápido. No entanto, em algum momento, partes maiores podem exigir lógica de balanceamento de carga adicional para manter todos os threads ocupados até que todo o trabalho seja concluído.  
  
## <a name="see-also"></a>Confira também

* [Particionadores personalizados para PLINQ e TPL](custom-partitioners-for-plinq-and-tpl.md)
* [Como: implementar um particionador para particionamento estático](how-to-implement-a-partitioner-for-static-partitioning.md)
