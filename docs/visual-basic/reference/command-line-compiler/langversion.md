---
title: -langversion
ms.date: 03/10/2018
helpviewer_keywords:
- /langversion compiler option [Visual Basic]
- langversion compiler option [Visual Basic]
- -langversion compiler option [Visual Basic]
ms.custom: updateeachrelease
ms.assetid: 59b7b0c8-2dde-4e9b-94e7-0237f7e0bafb
ms.openlocfilehash: 9921df0b8bb1a4808528b58a5a38d75e5e3fbdd2
ms.sourcegitcommit: ae2e8a61a93c5cf3f0035c59e6b064fa2f812d14
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/02/2020
ms.locfileid: "89359253"
---
# <a name="-langversion-visual-basic"></a>-langversion (Visual Basic)

Faz com que o compilador aceite apenas a sintaxe que está incluída na versão especificada do idioma de Visual Basic.  
  
## <a name="syntax"></a>Sintaxe  
  
```console  
-langversion:version  
```  
  
## <a name="arguments"></a>Argumentos

 `version`\
 Obrigatórios. A versão de idioma a ser usada durante a compilação. Os valores aceitos são,,,,,,,, `9` `10` `11` `12` `14` `15` `15.3` `15.5` `16` `default` e `latest` .

 Qualquer um dos números inteiros também pode ser especificado usando `.0` como a versão secundária, por exemplo, `11.0` .

 Você pode ver a lista de todos os valores possíveis especificando `-langversion:?` na linha de comando.

## <a name="remarks"></a>Comentários

A `-langversion` opção especifica qual sintaxe o compilador aceita. Por exemplo, se você especificar que a versão do idioma é 9,0, o compilador gerará erros de sintaxe válida somente na versão 10,0 e posterior.

Você pode usar essa opção ao desenvolver aplicativos direcionados a diferentes versões do .NET Framework. Por exemplo, se você estiver direcionando .NET Framework 3,5, poderá usar essa opção para garantir que não use a sintaxe da versão de linguagem 10,0.

Você pode definir `-langversion` diretamente apenas usando a linha de comando. Para obter mais informações, consulte [Definindo uma Versão Específica do .NET Framework como Destino](/visualstudio/ide/visual-studio-multi-targeting-overview).

## <a name="example"></a>Exemplo

O código a seguir é compilado `sample.vb` para o Visual Basic 9,0.

```console
vbc -langversion:9.0 sample.vb
```

## <a name="see-also"></a>Confira também

- [Compilador de linha de comando do Visual Basic](index.md)
- [Linhas de Comando de Compilação de Exemplo](sample-compilation-command-lines.md)
