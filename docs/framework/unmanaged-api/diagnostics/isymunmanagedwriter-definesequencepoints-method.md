---
title: Método ISymUnmanagedWriter::DefineSequencePoints
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.DefineSequencePoints
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::DefineSequencePoints
helpviewer_keywords:
- DefineSequencePoints method [.NET Framework debugging]
- ISymUnmanagedWriter::DefineSequencePoints method [.NET Framework debugging]
ms.assetid: 64202baf-be6b-40ba-8162-8cc6c0c9b8e1
topic_type:
- apiref
ms.openlocfilehash: af8beb1ec627b93faeb7329a03579319ca3880ed
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95678318"
---
# <a name="isymunmanagedwriterdefinesequencepoints-method"></a>Método ISymUnmanagedWriter::DefineSequencePoints

Define um grupo de pontos de sequência dentro do método atual. Cada linha inicial e coluna inicial definem o início de uma instrução dentro de um método. Cada linha final e coluna final definem o final de uma instrução dentro de um método. As matrizes devem ser classificadas em ordem crescente de deslocamentos. O deslocamento é sempre medido a partir do início do método, em bytes.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
HRESULT DefineSequencePoints(  
    [in] ISymUnmanagedDocumentWriter*  document,  
    [in] ULONG32 spCount,  
    [in, size_is(spCount)] ULONG32     offsets[],  
    [in, size_is(spCount)] ULONG32     lines[],  
    [in, size_is(spCount)] ULONG32     columns[],  
    [in, size_is(spCount)] ULONG32     endLines[],  
    [in, size_is(spCount)] ULONG32     endColumns[]);  
```  
  
## <a name="parameters"></a>Parâmetros  

 `document`  
 no O objeto de documento para o qual os pontos de sequência estão sendo definidos.  
  
 `spCount`  
 no Um `ULONG32` que indica o tamanho de cada um dos `offsets` buffers,,, `lines` `columns` `endLines` e `endColumns` .  
  
 `offsets`  
 no O deslocamento dos pontos de sequência medidos a partir do início do método.  
  
 `lines`  
 no Os números de linha inicial dos pontos de sequência.  
  
 `columns`  
 no Os números de coluna inicial dos pontos de sequência.  
  
 `endLines`  
 no Os números de linha final dos pontos de sequência. Esse parâmetro é opcional.  
  
 `endColumns`  
 no Os números de coluna final dos pontos de sequência. Esse parâmetro é opcional.  
  
## <a name="return-value"></a>Valor Retornado  

 S_OK se o método tiver sucesso; caso contrário, E_FAIL ou algum outro código de erro.  
  
## <a name="requirements"></a>Requisitos  

 **Cabeçalho:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Confira também

- [Interface ISymUnmanagedWriter](isymunmanagedwriter-interface.md)
