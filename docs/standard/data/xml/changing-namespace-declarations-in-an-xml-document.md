---
title: Alterando declarações namespace em um documento XML
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a2758f40-e497-4964-8d8d-1bb68af14dcd
ms.openlocfilehash: 95f9c6301f656ad4da5edcfb66521589b9195114
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725359"
---
# <a name="changing-namespace-declarations-in-an-xml-document"></a>Alterando declarações namespace em um documento XML

**XmlDocument** expõe declarações de namespace e atributos **xmlns** como parte do modelo de objeto de documento. São armazenados em **XmlDocument**, para que, quando você salvar o documento, ele possa preservar o local desses atributos. Alterar esses atributos não tem efeito nas propriedades **Name**, **NamespaceURI** e **Prefix** de outros nós já na árvore. Por exemplo, se você carregar o documento a seguir, o elemento `test` terá **NamespaceURI** `123.`  
  
```xml  
<test xmlns="123"/>  
```  
  
 Se você remover o atributo `xmlns` como indicado a seguir, o elemento `test` ainda terá o **NamespaceURI**`123`.  
  
```vb  
doc.documentElement.RemoveAttribute("xmlns")  
```  
  
```csharp  
doc.documentElement.RemoveAttribute("xmlns");  
```  
  
 Da mesma forma, se você adicionar um atributo diferente de `xmlns` ao elemento `doc` como indicado a seguir, o elemento `test` ainda terá **NamespaceURI** `123`.  
  
```vb  
doc.documentElement.SetAttribute("xmlns","456")
```  
  
```csharp  
doc.documentElement.SetAttribute("xmlns","456");  
```  
  
 Portanto, alterar atributos `xmlns` não terá nenhum efeito até que você salve e recarregue o objeto **XmlDocument**.  
  
## <a name="see-also"></a>Confira também

- [XML Document Object Model (DOM)](xml-document-object-model-dom.md)
