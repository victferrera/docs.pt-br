---
title: 'Como: Transformar um fragmento de nó'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 73a6c582-b9d7-4fa7-9a05-6d931e1f3de8
ms.openlocfilehash: f5eb8e7826dd132fd46f6f476335416e7dd03269
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722681"
---
# <a name="how-to-transform-a-node-fragment"></a>Como: Transformar um fragmento de nó

Quando você transforma os dados contidos em um objeto de <xref:System.Xml.XmlDocument> ou de <xref:System.Xml.XPath.XPathDocument> as transformações XSLT se aplicam a um documento no dataset. Ou seja se você passar em um nó que não seja o nó de diretório base, isso não impede que o processo de transformação acessar todos os nós do documento carregado. Para transformar um fragmento de nó, você deve criar um objeto separado que contém apenas o fragmento de nó, e passa esse objeto para o método de <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A> .  
  
## <a name="procedures"></a>Procedimentos  
  
#### <a name="to-transform-a-node-fragment"></a>Para transformar um fragmento do nó  
  
1. Crie um objeto que contém o documento de origem.  
  
2. Localize o nó de fragmento que você deseja que a transformação.  
  
3. Crie o objeto separado com apenas o fragmento de nó.  
  
4. Passe o fragmento do nó para o método de <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A> .  
  
## <a name="example"></a>Exemplo  

 O exemplo transforma um fragmento e saída do nó os resultados no console.  
  
 [!code-csharp[XSLT_NodeFrag#1](../../../../samples/snippets/csharp/VS_Snippets_Data/XSLT_NodeFrag/CS/xslt_frag.cs#1)]
 [!code-vb[XSLT_NodeFrag#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XSLT_NodeFrag/VB/xslt_frag.vb#1)]  
  
### <a name="input"></a>Entrada  
  
##### <a name="booksxml"></a>books.xml  

 [!code-xml[XML_Core_Files#1](../../../../samples/snippets/xml/VS_Snippets_Data/XML_Core_Files/XML/books.xml#1)]  
  
##### <a name="singlexsl"></a>single.xsl  

 [!code-xml[XSLT_NodeFrag#2](../../../../samples/snippets/xml/VS_Snippets_Data/XSLT_NodeFrag/XML/single.xsl#2)]  
  
### <a name="output"></a>Saída  

 O título de livro é o homem de confiança.  
  
## <a name="see-also"></a>Confira também

- [Usando a classe XslCompiledTransform](using-the-xslcompiledtransform-class.md)
