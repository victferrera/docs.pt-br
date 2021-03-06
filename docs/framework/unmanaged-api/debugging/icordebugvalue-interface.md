---
title: Interface ICorDebugValue
ms.date: 03/30/2017
api_name:
- ICorDebugValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue
helpviewer_keywords:
- ICorDebugValue interface [.NET Framework debugging]
ms.assetid: b2f7007f-c446-4b18-aed1-a25cff8aee31
topic_type:
- apiref
ms.openlocfilehash: 7d3c35ed6cda637e3b885afe089ddfa590d51076
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95683596"
---
# <a name="icordebugvalue-interface"></a>Interface ICorDebugValue

Representa um valor no processo que está sendo depurado. O valor pode ser um valor de leitura ou de gravação.  
  
## <a name="methods"></a>Métodos  
  
|Método|DESCRIÇÃO|  
|------------|-----------------|  
|[Método CreateBreakpoint](icordebugvalue-createbreakpoint-method.md)|Este método não está implementado no momento.|  
|[Método GetAddress](icordebugvalue-getaddress-method.md)|Obtém o endereço desse `ICorDebugValue` objeto, que está no processo de depuração.|  
|[Método GetSize](icordebugvalue-getsize-method.md)|Obtém o tamanho, em bytes, deste `ICorDebugValue` objeto.|  
|[Método GetType](icordebugvalue-gettype-method.md)|Obtém o tipo primitivo deste `ICorDebugValue` objeto.|  
  
## <a name="remarks"></a>Comentários  

 Em geral, a propriedade de um objeto de valor é passada quando é retornada. O destinatário é responsável por remover uma referência do objeto quando ele é concluído com o objeto.  
  
 Dependendo de onde o valor foi recuperado, o valor pode não permanecer válido depois que o processo for retomado. Portanto, em geral, o valor não deve ser mantido em uma chamada do método [ICorDebugController:: Continue](icordebugcontroller-continue-method.md) .  
  
> [!NOTE]
> Esta interface não dá suporte para chamada remota, seja entre computadores ou processos cruzados.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Confira também

- [Interface ICorDebugValue3](icordebugvalue3-interface.md)
- [Depurando interfaces](debugging-interfaces.md)
