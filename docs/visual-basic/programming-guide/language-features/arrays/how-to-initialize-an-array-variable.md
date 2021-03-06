---
title: Como inicializar uma variável de matriz
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], initializing
- arrays [Visual Basic], variables
- arrays [Visual Basic], initializing
- arrays [Visual Basic], declaring
ms.assetid: aadd7a60-7ca4-4608-b986-091f19e7fc10
ms.openlocfilehash: 1add054a6cb6468f4581f92ca3a258c5b0cdc77d
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/23/2020
ms.locfileid: "91058853"
---
# <a name="how-to-initialize-an-array-variable-in-visual-basic"></a>Como inicializar uma variável de matriz no Visual Basic

Você Inicializa uma variável de matriz, incluindo um literal de matriz em uma `New` cláusula e especificando os valores iniciais da matriz. Você pode especificar o tipo ou permitir que ele seja inferido com base nos valores no literal de matriz. Para obter mais informações sobre como o tipo é inferido, consulte "populando uma matriz com valores iniciais" em [matrizes](index.md).  
  
### <a name="to-initialize-an-array-variable-by-using-an-array-literal"></a>Para inicializar uma variável de matriz usando um literal de matriz  
  
- Na `New` cláusula ou quando você atribui o valor de matriz, forneça os valores de elemento entre chaves ( `{}` ). O exemplo a seguir mostra várias maneiras de declarar, criar e inicializar uma variável para conter uma matriz que tem elementos do tipo `Char` .  
  
     [!code-vb[VbVbalrArrays#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrArrays/VB/Class1.vb#16)]  
  
     Depois que cada instrução é executada, a matriz que é criada tem um comprimento de 3, com elementos no índice 0 até o índice 2 que contém os valores iniciais. Se você fornecer o limite superior e os valores, deverá incluir um valor para cada elemento do índice 0 por meio do limite superior.  
  
     Observe que você não precisa especificar o limite superior do índice se fornecer valores de elemento em um literal de matriz. Se nenhum limite superior for especificado, o tamanho da matriz será inferido com base no número de valores no literal de matriz.  
  
### <a name="to-initialize-a-multidimensional-array-variable-by-using-array-literals"></a>Para inicializar uma variável de matriz multidimensional usando literais de matriz  
  
- Aninhe valores entre chaves ( `{}` ) entre chaves. Verifique se os literais de matriz aninhada inferem como matrizes do mesmo tipo e comprimento. O exemplo de código a seguir mostra vários exemplos de inicialização de matriz multidimensional.  
  
     [!code-vb[VbVbalrArrays#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrArrays/VB/Class1.vb#17)]  
  
- Você pode especificar explicitamente os limites da matriz ou deixá-los fora e fazer com que o compilador inferir os limites da matriz com base nos valores no literal da matriz. Se você fornecer os limites superiores e os valores, deverá incluir um valor para cada elemento do índice 0 por meio do limite superior em cada dimensão. O exemplo a seguir mostra várias maneiras de declarar, criar e inicializar uma variável para conter uma matriz bidimensional que tem elementos do tipo `Short`  
  
     [!code-vb[VbVbalrArrays#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrArrays/VB/Class1.vb#18)]  
  
     Depois que cada instrução é executada, a matriz criada contém seis elementos inicializados que têm índices `(0,0)` ,,,, `(0,1)` `(0,2)` `(1,0)` `(1,1)` e `(1,2)` . Cada local da matriz contém o valor `10` .  
  
- O exemplo a seguir itera por meio de uma matriz multidimensional. Em um aplicativo de console do Windows que é gravado em Visual Basic, Cole o código dentro do `Sub Main()` método. Os últimos comentários mostram a saída.  
  
     [!code-vb[VbVbalrArrays#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrArrays/VB/Class1.vb#31)]  
  
### <a name="to-initialize-a-jagged-array-variable-by-using-array-literals"></a>Para inicializar uma variável de matriz denteada usando literais de matriz  
  
- Aninhe os valores de objeto entre chaves ( `{}` ). Embora você também possa aninhar literais de matriz que especificam matrizes de comprimentos diferentes, no caso de uma matriz denteada, certifique-se de que os literais de matriz aninhada sejam colocados entre parênteses ( `()` ). Os parênteses forçam a avaliação dos literais de matriz aninhada e as matrizes resultantes são usadas como os valores iniciais da matriz denteada. O exemplo de código a seguir mostra dois exemplos de inicialização de matriz denteada.  
  
     [!code-vb[VbVbalrArrays#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrArrays/VB/Class1.vb#19)]  
  
- O exemplo a seguir itera por meio de uma matriz denteada. Em um aplicativo de console do Windows que é gravado em Visual Basic, Cole o código dentro do `Sub Main()` método.  Os últimos comentários no código mostram a saída.  
  
     [!code-vb[VbVbalrArrays#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrArrays/VB/Class1.vb#32)]  
  
## <a name="see-also"></a>Confira também

- [matrizes](index.md)
- [Solução de problemas de matrizes](troubleshooting-arrays.md)
