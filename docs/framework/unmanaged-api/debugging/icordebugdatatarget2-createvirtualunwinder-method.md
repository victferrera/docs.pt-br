---
title: Método ICorDebugDataTarget2::CreateVirtualUnwinder
ms.date: 03/30/2017
ms.assetid: 354c8b4c-7d23-45c6-a7d7-3be4c2a5b772
ms.openlocfilehash: 0967b1cda86eab35015279edeed9a6b9852036b6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95713919"
---
# <a name="icordebugdatatarget2createvirtualunwinder-method"></a>Método ICorDebugDataTarget2::CreateVirtualUnwinder

Cria um novo unwinder de pilha que inicia o desenrolamento de um contexto inicial (que não é necessariamente folha de um thread).  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
HRESULT CreateVirtualUnwinder(  
    [in] DWORD nativeThreadID,  
    [in] ULONG32 contextFlags,  
    [in] ULONG32 cbContext,  
    [in, size_is(cbContext)] BYTE initialContext[],  
    [out] ICorDebugVirtualUnwinder ** ppUnwinder);  
};  
```  
  
## <a name="parameters"></a>Parâmetros  

 nativeThreadID  
 [in] O ID de thread nativo do thread cuja pilha será desenrolada.  
  
 contextFlags  
 [in] Sinalizadores que especificam quais partes do contexto são definidos em `initialContext`.  
  
 cbContext  
 [in] O tamanho do `initialContext`.  
  
 initialContext  
 [in] Os dados no contexto.  
  
 ppUnwinder  
 [out] Um ponteiro para o endereço de um objeto de interface ICorDebugVirtualUnwinder.  
  
## <a name="return-value"></a>Valor Retornado  

 `S_OK` se bem-sucedido. Qualquer outro `HRESULT` indica uma falha. Qualquer falha `HRESULT` recebida pelo MSCorDbi é considerada fatal e faz com que os métodos [ICorDebug](icordebug-interface.md) sejam retornados `CORDBG_E_DATA_TARGET_ERROR` .  
  
## <a name="remarks"></a>Comentários  
  
> [!NOTE]
> Esse método está disponível somente com .NET Native.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versões:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Confira também

- [Interface ICorDebugDataTarget2](icordebugdatatarget2-interface.md)
- [Depurando interfaces](debugging-interfaces.md)
