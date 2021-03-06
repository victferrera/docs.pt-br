---
title: Método ICLRDataTarget::GetThreadContext
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.GetThreadContext
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::GetThreadContext
helpviewer_keywords:
- ICLRDataTarget::GetThreadContext method [.NET Framework debugging]
- GetThreadContext method, ICLRDataTarget interface [.NET Framework debugging]
ms.assetid: b9d8c3b5-3a2e-4225-95d4-dd052c4532c3
topic_type:
- apiref
ms.openlocfilehash: 35b7bff5d4d778a429ddc1dcd0206e6e8970ee4f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95703493"
---
# <a name="iclrdatatargetgetthreadcontext-method"></a>Método ICLRDataTarget::GetThreadContext

Obtém o contexto de execução atual para o thread determinado no processo de destino. Esse método é chamado pelo Common Language Runtime Data Access Services.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
HRESULT GetThreadContext (  
    [in] ULONG32            threadID,  
    [in] ULONG32            contextFlags,  
    [in] ULONG32            contextSize,  
    [out, size_is(contextSize)]
        BYTE                *context  
);  
```  
  
## <a name="parameters"></a>Parâmetros  

 `threadID`  
 no O identificador do sistema operacional de um thread no processo de destino.  
  
 `contextFlags`  
 no Sinalizadores que especificam quais partes do contexto retornar. A implementação retornará pelo menos essas partes do contexto.  
  
 `contextSize`  
 no O tamanho do contexto.  
  
 `context`  
 fora Ponteiro para um buffer no qual o contexto será colocado.  
  
 Os dados no `context` buffer devem estar no formato da estrutura do Win32 `CONTEXT` . O contexto especifica dados de registro específicos do processador, de modo que a definição da estrutura do Win32 `CONTEXT` depende da arquitetura do processador. Consulte o arquivo de cabeçalho WinNT. h para obter a definição da estrutura do Win32 `CONTEXT` .  
  
## <a name="remarks"></a>Comentários  

 Este método é implementado pelo autor do aplicativo de depuração.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** ClrData. idl, ClrData. h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Confira também

- [Interface ICLRDataTarget](iclrdatatarget-interface.md)
