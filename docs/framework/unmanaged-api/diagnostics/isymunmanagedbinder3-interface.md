---
title: Interface ISymUnmanagedBinder3
ms.date: 03/30/2017
api_name:
- ISymUnmanagedBinder3
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedBinder3 Interface
helpviewer_keywords:
- ISymUnmanagedBinder3 interface [.NET Framework debugging]
ms.assetid: 37527a84-4b03-4f08-8135-94d898599089
topic_type:
- apiref
ms.openlocfilehash: 0cb0b91f2dca8203c37599400b3b61f84eb7d282
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727309"
---
# <a name="isymunmanagedbinder3-interface"></a>Interface ISymUnmanagedBinder3

Estende a interface do fichário de símbolos. Obtenha essa interface chamando `QueryInterface` um objeto que implementa a `ISymUnmanagedBinder` interface.  
  
> [!IMPORTANT]
> É um risco de segurança abrir um arquivo de banco de dados do programa (PDB) de uma fonte não confiável.  
  
## <a name="methods"></a>Métodos  
  
|Método|DESCRIÇÃO|  
|------------|-----------------|  
|[Método GetReaderFromCallback](isymunmanagedbinder3-getreaderfromcallback-method.md)|Permite que o usuário implemente ou forneça por meio de um retorno de chamada `IID_IDiaReadExeAtRVACallback` ou `IID_IDiaReadExeAtOffsetCallback` para obter as informações do diretório de depuração da memória|  
  
## <a name="requirements"></a>Requisitos  

 **Cabeçalho:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Confira também

- [Interfaces de armazenamento de símbolo de diagnóstico](diagnostics-symbol-store-interfaces.md)
- [Interface ISymUnmanagedBinder](isymunmanagedbinder-interface.md)
- [Interface ISymUnmanagedBinder2](isymunmanagedbinder2-interface.md)
