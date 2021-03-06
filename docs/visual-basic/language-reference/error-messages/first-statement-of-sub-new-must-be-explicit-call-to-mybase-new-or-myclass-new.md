---
title: "A primeira instrução deste 'Sub New' deve ser uma chamada explícita para MyBase.New' ou 'MyClass.New' porque '<constructorname>' na classe base '<baseclassname>' de '<derivedclassname>' está marcado como obsoleto: '<errormessage>'"
ms.date: 07/20/2015
f1_keywords:
- vbc30920
- bc30920
helpviewer_keywords:
- BC30920
ms.assetid: e47dc755-4294-4368-b813-2177b7677957
ms.openlocfilehash: 4b927e3eed8f9d7f46255b907342465f48263724
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "92163032"
---
# <a name="bc30920-first-statement-of-this-sub-new-must-be-an-explicit-call-to-mybasenew-or-myclassnew-because-the-constructorname-in-the-base-class-baseclassname-of-derivedclassname-is-marked-obsolete-errormessage"></a>BC30920: a primeira instrução deste ' Sub New ' deve ser uma chamada explícita para ' MyBase. New ' ou ' MyClass. New ' porque o ' \<constructorname> ' na classe base ' \<baseclassname> ' de ' \<derivedclassname> ' está marcado como obsoleto: ' \<errormessage> '

Um construtor de classe não chama explicitamente um construtor de classe base e o construtor da classe base implícita é marcado com o <xref:System.ObsoleteAttribute> atributo e a diretiva para tratá-lo como um erro.

 Quando um construtor de classe derivada não chama um construtor de classe base, Visual Basic tenta gerar uma chamada implícita para um construtor de classe base sem parâmetros. Se não houver nenhum construtor acessível na classe base que possa ser chamado sem argumentos, Visual Basic não poderá gerar uma chamada implícita. Nesse caso, o Construtor necessário é marcado com o <xref:System.ObsoleteAttribute> atributo, portanto Visual Basic não pode chamá-lo.

 Você pode marcar qualquer elemento de programação como não sendo mais usado aplicando <xref:System.ObsoleteAttribute> -se a ele. Se você fizer isso, poderá definir a propriedade do atributo <xref:System.ObsoleteAttribute.IsError%2A> como `True` ou `False` . Se você defini-lo como `True` , o compilador tratará uma tentativa de usar o elemento como um erro. Se você defini-lo como `False` , ou deixá-lo como padrão `False` , o compilador emitirá um aviso se houver uma tentativa de usar o elemento.

 **ID do erro:** BC30920

## <a name="to-correct-this-error"></a>Para corrigir este erro

1. Examine a mensagem de erro entre aspas e execute a ação apropriada.

2. Inclua uma chamada para `MyBase.New()` ou `MyClass.New()` como a primeira instrução do `Sub New` na classe derivada.

## <a name="see-also"></a>Veja também

- [Visão geral de atributos](../../programming-guide/concepts/attributes/index.md)
