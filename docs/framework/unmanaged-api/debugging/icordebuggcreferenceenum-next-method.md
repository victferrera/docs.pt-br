---
title: Método ICorDebugGCReferenceEnum::Next
ms.date: 03/30/2017
api_name:
- ICorDebugGCReferenceEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGCReferenceEnum::Next
helpviewer_keywords:
- Next method, ICorDebugGCReferenceEnum interface [.NET Framework debugging]
- ICorDebugGCReferenceEnum::Next method [.NET Framework debugging]
ms.assetid: 91b1345c-a94f-4ef8-9696-3823d06c6d05
topic_type:
- apiref
ms.openlocfilehash: e55c53b9610dcadee92ba9871bf52e3dacb5796b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726230"
---
# <a name="icordebuggcreferenceenumnext-method"></a>Método ICorDebugGCReferenceEnum::Next

Obtém o número especificado de instâncias de [COR_GC_REFERENCE](cor-gc-reference-structure.md) que contêm informações sobre objetos que serão coletados como lixo.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
HRESULT Next(  
    [in] ULONG celt,    [out, size_is(celt), length_is(*pceltFetched)] COR_GC_REFERENCE roots[],
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a>Parâmetros  

 celt  
 no O número de raízes a serem recuperadas.  
  
 raiz  
 fora Uma matriz de ponteiros, cada um dos quais aponta para um objeto [COR_GC_REFERENCE](cor-gc-reference-structure.md) que representa a raiz de um objeto a ser coletado pelo lixo.  
  
 pceltFetched  
 fora Um ponteiro para o número de objetos [COR_GC_REFERENCE](cor-gc-reference-structure.md) realmente retornados em `roots` . Esse valor pode ser `null` se `celt` for 1.  
  
## <a name="remarks"></a>Comentários  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versões:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Confira também

- [Interface ICorDebugGCReferenceEnum](icordebuggcreferenceenum-interface.md)
- [Depurando interfaces](debugging-interfaces.md)
