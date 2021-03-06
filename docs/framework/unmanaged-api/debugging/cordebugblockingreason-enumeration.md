---
title: Enumeração CorDebugBlockingReason
ms.date: 03/30/2017
api_name:
- CorDebugBlockingReason
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugBlockingReason
helpviewer_keywords:
- CorDebugBlockingReason enumeration [.NET Framework debugging]
ms.assetid: a6ac2531-ddfe-46fd-88fe-8b1eabe0b255
topic_type:
- apiref
ms.openlocfilehash: ddd03d70656ad52fd9d577beedc60b51c7b305d5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95672845"
---
# <a name="cordebugblockingreason-enumeration"></a>Enumeração CorDebugBlockingReason

Especifica os motivos pelos quais um thread pode ficar bloqueado em um determinado objeto.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
Typedef enum CorDebugBlockingReason  
{  
   BLOCKING_NONE = 0  
   BLOCKING_MONITOR_CRITICAL_SECTION = 1  
   BLOCKING_MONITOR_EVENT = 2  
}  CorDebugBlockingReason;  
```  
  
## <a name="members"></a>Membros  
  
|Membro|DESCRIÇÃO|  
|------------|-----------------|  
|`BLOCKING_NONE`|Somente para uso interno.|  
|`BLOCKING_MONITOR_CRITICAL_SECTION`|Um thread está tentando adquirir a seção crítica associada ao bloqueio de monitor em um objeto. Normalmente, isso ocorre quando você chama um dos <xref:System.Threading.Monitor.Enter%2A?displayProperty=nameWithType> métodos ou <xref:System.Threading.Monitor.TryEnter%2A?displayProperty=nameWithType> .|  
|`BLOCKING_MONITOR_EVENT`|Um thread está aguardando o evento que está associado a um bloqueio de monitor para um objeto. Normalmente, isso ocorre quando você chama um dos <xref:System.Threading.Monitor?displayProperty=nameWithType> `Wait` métodos.|  
  
## <a name="remarks"></a>Comentários  

 Quando o `BLOCKING_MONITOR_CRITICAL_SECTION` `BLOCKING_MONITOR_EVENT` membro ou é usado em uma estrutura [CorDebugBlockingObject](cordebugblockingobject-structure.md) , o `pBlockingObject` membro da estrutura aponta para uma interface "ICorDebugValue" que representa o objeto que está sendo inserido. Também é garantido implementar a interface [ICorDebugHeapValue3](icordebugheapvalue3-interface.md) .  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versões:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Confira também

- [Declarando enumerações](debugging-enumerations.md)
- [Depuração](index.md)
