---
title: Segurança em LINQ to SQL
ms.date: 03/30/2017
ms.assetid: d49787f7-414e-4c71-aa33-80a5895536b1
ms.openlocfilehash: 6260f0c565a25764c8fabd2770d4f06a987aa9bb
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91173387"
---
# <a name="security-in-linq-to-sql"></a>Segurança em LINQ to SQL

Os riscos de segurança são sempre presentes em que você se conecta a um base de dados. Embora LINQ to SQL pode incluir algumas novas maneiras de trabalhar com dados no SQL Server, não fornece os mecanismos de segurança adicionais.  
  
## <a name="access-control-and-authentication"></a>Controle de acesso e autenticação  

 LINQ to SQL não tem seu próprio mecanismos de modelo ou de autenticação de usuário. Use a segurança do SQL Server para controlar o acesso a base de dados, para tabelas de base de dados, modos de exibição, e procedimentos armazenados que são mapeados para o seu modelo de objeto. Conceda acesso mìnima necessário aos usuários e requer senhas de alta segurança para autenticação de usuário.  
  
## <a name="mapping-and-schema-information"></a>Mapeamento e informações de esquema  

 O mapeamento de tipo de SQL-CLR e informações do esquema de base de dados no seu modelo de objeto ou arquivos de mapeamento externo estão disponíveis para todos com acesso 2 esses arquivos no sistema de arquivos. Suponha que as informações de esquema estarão disponíveis para todos que possam acessar o modelo de objeto ou o arquivo de mapeamento externo. Para evitar o acesso mais difundido às informações de esquema, use mecanismos de segurança de arquivo para proteger arquivos de origem e arquivos de mapeamento.  
  
## <a name="connection-strings"></a>Cadeias de Conexão  

 Usar senhas em cadeias de conexão deve ser impedida sempre que possível. Não é apenas uma cadeia de conexão um risco para a segurança em próprio, mas a cadeia de conexão também pode ser adicionada em texto não criptografado para o modelo de objeto ou arquivo de mapeamento externo ao usar a ferramenta de linha de comando Object Relational Designer ou de SQLMetal. Qualquer pessoa com acesso ao modelo de objeto ou arquivo de mapeamento externo através do sistema de arquivos pode ver a senha de conexão (se é incluído na cadeia de conexão).  
  
 Para minimizar esses riscos, use a segurança integrada para fazer uma conexão confiável com SQL Server. Usando essa abordagem, você não tiver que armazenar uma senha na cadeia de conexão. Para obter mais informações, consulte [SQL Server Security](../sql-server-security.md).  
  
 Na ausência de segurança integrado, uma senha de texto não será necessária na cadeia de conexão. A melhor maneira para ajudar a proteger a cadeia de conexão, na ordem crescente de risco, é a seguinte:  
  
- Use segurança integrada.  
  
- Proteger cadeias de conexão com senhas e minimizar passar ao redor de cadeias de conexão.  
  
- Use uma classe de <xref:System.Data.SqlClient.SqlConnection?displayProperty=nameWithType> em vez de uma cadeia de conexão já que limita a duração de exibição. A classe LINQ to SQL <xref:System.Data.Linq.DataContext?displayProperty=nameWithType> pode ser instanciada usando <xref:System.Data.SqlClient.SqlConnection>.  
  
- Minimize o tempo de vida e toque em pontos para todas as cadeias de conexão.  
  
## <a name="see-also"></a>Veja também

- [Informações gerais](background-information.md)
- [Perguntas frequentes](frequently-asked-questions.md)
