---
title: Construtor de tipo nomeado (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 549dea04-d93d-4c87-a292-f81b1598dbfd
ms.openlocfilehash: c673b58ee5811e3d3b74b3744d3f5291888e2253
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91197775"
---
# <a name="named-type-constructor-entity-sql"></a>Construtor de tipo nomeado (Entity SQL)

Usado para criar instâncias de tipos nominais de modelo conceitual como a entidade ou tipos complexos.  
  
## <a name="syntax"></a>Sintaxe  
  
```sql  
[{identifier. }] identifier( [expression [{, expression }]] )  
```  
  
## <a name="arguments"></a>Argumentos  

 `identifier`  
 Valor que é um identificador simples ou citado. Para obter mais informações, consulte [identificadores](identifiers-entity-sql.md)  
  
 `expression`  
 Atributos de tipo que são considerados para estar na mesma ordem que aparecem na declaração de tipo.  
  
## <a name="return-value"></a>Valor Retornado  

 Instâncias de tipos complexos nomeados e tipos de entidade.  
  
## <a name="remarks"></a>Comentários  

 Os exemplos a seguir mostram como construir o substantivo e os tipos complexos:  
  
 A expressão a seguir cria uma instância de um tipo de `Person` :  
  
 `Person("abc", 12)`  
  
 A expressão a seguir cria uma instância de um tipo complexo:  
  
 `MyModel.ZipCode(‘98118’, ‘4567’)`  
  
 A expressão a seguir cria uma instância de um tipo complexo aninhado:  
  
 `MyModel.AddressInfo('My street address', 'Seattle', 'WA', MyModel.ZipCode('98118', '4567'))`  
  
 A expressão a seguir cria uma instância de um objeto com um tipo complexo aninhado:  
  
 `MyModel.Person("Bill", MyModel.AddressInfo('My street address', 'Seattle', 'WA', MyModel.ZipCode('98118', '4567')))`  
  
 O exemplo a seguir mostra como inicializar uma propriedade de um tipo complexo para nulo:`MyModel.ZipCode(‘98118’, null)`  
  
## <a name="example"></a>Exemplo  

 A seguinte consulta SQL Entity usa o construtor chamado de tipo para criar uma instância de um tipo de modelo conceitual. A consulta é baseada no modelo de vendas AdventureWorks. Para compilar e executar essa consulta, siga estas etapas:  
  
1. Siga o procedimento em [como executar uma consulta que retorna resultados de estruturaistype](../how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2. Passe a consulta a seguir como um argumento para o método `ExecuteStructuralTypeQuery`:  
  
 [!code-sql[DP EntityServices Concepts#NAMED_TYPE_CONSTRUCTOR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#named_type_constructor)]  
  
## <a name="see-also"></a>Veja também

- [Construir tipos](constructing-types-entity-sql.md)
- [Referência de Entity SQL](entity-sql-reference.md)
