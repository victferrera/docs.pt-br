---
title: Transformações XSLT
ms.date: 03/30/2017
ms.assetid: 202f8820-224c-494f-b61e-cd127eac6e03
ms.openlocfilehash: 686b2d454eda99095bcb335c8b0edba9ecf2e304
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95685052"
---
# <a name="xslt-transformations"></a>Transformações XSLT

A linguagem XSL Transformation (XSLT) permite transformar o conteúdo de um documento XML de origem em outro documento que seja diferente no formato ou estrutura. Por exemplo, você pode usar XSLT para transformar XML em HTML para usar em um site ou para transformá-lo em um documento que contém somente os campos exigidos por um aplicativo. Esse processo de transformação é especificado pela [Recomendação da linguagem XSL Transformations (XSLT) do W3C Versão 1.0](https://www.w3.org/TR/xslt-10/).  
  
 A classe <xref:System.Xml.Xsl.XslCompiledTransform> é o processador XSLT no .NET. A classe <xref:System.Xml.Xsl.XslCompiledTransform> é compatível com a [recomendação XSLT 1.0 do W3C](https://www.w3.org/TR/xslt-10/).  
  
> [!NOTE]
> A classe <xref:System.Xml.Xsl.XslTransform> está obsoleta no .NET Framework versão 2.0. A classe <xref:System.Xml.Xsl.XslCompiledTransform> é uma nova implementação do mecanismo do XSLT. Ela inclui aprimoramentos de desempenho e novos recursos de segurança. A prática recomendada é criar aplicativos do XSLT usando a classe <xref:System.Xml.Xsl.XslCompiledTransform>.  
  
## <a name="in-this-section"></a>Nesta seção  

 [Usando a classe XslCompiledTransform](using-the-xslcompiledtransform-class.md)  
 Fornece informações sobre como usar a classe <xref:System.Xml.Xsl.XslCompiledTransform>.  
  
 [Migrar da classe XslTransform](migrating-from-the-xsltransform-class.md)  
 Aborda como migrar o código da classe <xref:System.Xml.Xsl.XslTransform>.  
  
 [Compilador de XSLT (xsltc.exe)](xslt-compiler-xsltc-exe.md)  
 Fornece informações sobre como usar o compilador do XSLT.  
  
 [Transformações XSLT com a classe XslTransform](xslt-transformations-with-the-xsltransform-class.md)  
 Fornece informações sobre como usar a classe <xref:System.Xml.Xsl.XslTransform>.  
  
## <a name="reference"></a>Referência  

 <xref:System.Xml.Xsl.XslCompiledTransform>  
 <xref:System.Xml.Xsl.XsltArgumentList>  
 <xref:System.Xml.Xsl.XsltSettings>  
  
## <a name="related-sections"></a>Seções relacionadas  

 [Documentos e dados XML](index.md)
