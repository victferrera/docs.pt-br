---
title: Método ISymUnmanagedMethod::GetScopeFromOffset
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetScopeFromOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetScopeFromOffset
helpviewer_keywords:
- GetScopeFromOffset method [.NET Framework debugging]
- ISymUnmanagedMethod::GetScopeFromOffset method [.NET Framework debugging]
ms.assetid: d14cf210-81f8-46e1-8b19-6ddec0ba8b11
topic_type:
- apiref
ms.openlocfilehash: cf2784ce0ac6e614e75a341660808b9fe03ada0e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95699437"
---
# <a name="isymunmanagedmethodgetscopefromoffset-method"></a>Método ISymUnmanagedMethod::GetScopeFromOffset

Obtém o escopo léxico mais delimitador dentro desse método que envolve o deslocamento fornecido. Isso pode ser usado para iniciar pesquisas de variáveis locais.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
HRESULT GetScopeFromOffset(  
    [in]  ULONG32 offset,  
    [out, retval] ISymUnmanagedScope**  pRetVal);  
```  
  
## <a name="parameters"></a>Parâmetros  

 `offset`  
 no Um `ULONG` que contém o deslocamento.  
  
 `pRetVal`  
 fora Um ponteiro que é definido para a interface [ISymUnmanagedScope](isymunmanagedscope-interface.md) retornada.  
  
## <a name="return-value"></a>Valor Retornado  

 S_OK se o método tiver sucesso; caso contrário, E_FAIL ou algum outro código de erro.  
  
## <a name="requirements"></a>Requisitos  

 **Cabeçalho:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Confira também

- [Interface ISymUnmanagedMethod](isymunmanagedmethod-interface.md)
