---
title: Removendo conteúdo do nó em DOM
ms.date: 03/30/2017
ms.assetid: 615d81a7-f44f-416c-a9ab-bfe03f85e6e4
ms.openlocfilehash: d624e3eff3d61c2b8d312f370a4a11e3aede37e5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721485"
---
# <a name="removing-node-content-in-the-dom"></a>Removendo conteúdo do nó em DOM

Para os tipos de nós que herdam de <xref:System.Xml.XmlCharacterData>, que são <xref:System.Xml.XmlComment>, <xref:System.Xml.XmlText>, <xref:System.Xml.XmlCDataSection>, <xref:System.Xml.XmlWhitespace>, e os tipos de nós de <xref:System.Xml.XmlSignificantWhitespace> , você pode remover os caracteres usando o método de <xref:System.Xml.XmlCharacterData.DeleteData%2A> , que remove um intervalo de caracteres de nó. Se você deseja remover completamente o conteúdo, você remover o nó que contém o conteúdo. Se você desejar manter o nó, mas o conteúdo está incorreto, então modificar o conteúdo. Para saber mais sobre como alterar o conteúdo de um nó, confira [Modificando nós, conteúdo e valores em um documento XML](modifying-nodes-content-and-values-in-an-xml-document.md).  
  
## <a name="see-also"></a>Confira também

- [XML Document Object Model (DOM)](xml-document-object-model-dom.md)
