---
title: 'Como: executar um procedimento armazenado parametrizado usando EntityCommand'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 4f5639bf-bb7f-4982-bb1d-c7caa4348888
ms.openlocfilehash: ec1ff7cdbdc83bc409b191f0aefe2b50cbad9225
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91192159"
---
# <a name="how-to-execute-a-parameterized-stored-procedure-using-entitycommand"></a>Como: executar um procedimento armazenado parametrizado usando EntityCommand

Este tópico mostra como executar um procedimento armazenado parametrizado usando a classe de <xref:System.Data.EntityClient.EntityCommand> .  
  
### <a name="to-run-the-code-in-this-example"></a>Para executar o código nesse exemplo  
  
1. Adicione o [modelo escolar](/previous-versions/dotnet/netframework-4.0/bb896300(v=vs.100)) ao seu projeto e configure seu projeto para usar o Entity Framework. Para obter mais informações, consulte [como: usar o assistente de modelo de dados de entidade](/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).  
  
2. Na página de código do seu aplicativo, adicione as seguintes instruções `using` (`Imports` no Visual Basic):  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
3. Importar o procedimento armazenado `GetStudentGrades` e especificar entidades de `CourseGrade` como um tipo de retorno. Para obter informações sobre como importar um procedimento armazenado, consulte [como importar um procedimento armazenado](/previous-versions/dotnet/netframework-4.0/bb896231(v=vs.100)).  
  
## <a name="example"></a>Exemplo  

 O código a seguir executa o procedimento armazenado `GetStudentGrades` onde `StudentId` é um parâmetro necessário. Os resultados são lidos em seguida <xref:System.Data.EntityClient.EntityDataReader>.  
  
 [!code-csharp[DP EntityServices Concepts#StoredProcWithEntityCommand](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#storedprocwithentitycommand)]
 [!code-vb[DP EntityServices Concepts#StoredProcWithEntityCommand](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#storedprocwithentitycommand)]  
  
## <a name="see-also"></a>Veja também

- [Provedor EntityClient para Entity Framework](entityclient-provider-for-the-entity-framework.md)
