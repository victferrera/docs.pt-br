---
title: Método ICorDebugProcess::GetHelperThreadID
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.GetHelperThreadID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::GetHelperThreadID
helpviewer_keywords:
- GetHelperThreadID method [.NET Framework debugging]
- ICorDebugProcess::GetHelperThreadID method [.NET Framework debugging]
ms.assetid: 84e1e605-37c1-49a5-8e12-35db85654622
topic_type:
- apiref
ms.openlocfilehash: 77cc658e28c7a69d8c4aeeed2f3e7ea40f0d2af6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724566"
---
# <a name="icordebugprocessgethelperthreadid-method"></a>Método ICorDebugProcess::GetHelperThreadID

Obtém a ID do thread do sistema operacional (SO) do thread auxiliar interno do depurador.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
HRESULT GetHelperThreadID (  
    [out] DWORD *pThreadID  
);  
```  
  
## <a name="parameters"></a>Parâmetros  

 `pThreadID`  
 fora Um ponteiro para a ID de thread do sistema operacional do thread auxiliar interno do depurador.  
  
## <a name="remarks"></a>Comentários  

 Durante a depuração gerenciada e não gerenciada, é responsabilidade do depurador garantir que o thread com a ID especificada permaneça em execução se atingir um ponto de interrupção colocado pelo depurador. Um depurador também pode desejar ocultar esse thread do usuário. Se nenhum thread auxiliar existir no processo ainda, o `GetHelperThreadID` método retornará zero em * `pThreadID` .  
  
 Não é possível armazenar em cache a ID do thread auxiliar, pois ela pode mudar ao longo do tempo. Você deve consultar novamente a ID do thread em cada evento de parada.  
  
 A ID de thread do thread auxiliar do depurador estará correta em cada evento [ICorDebugManagedCallback:: CreateThread](icordebugmanagedcallback-createthread-method.md) não gerenciado, permitindo que um depurador determine a ID do thread do seu thread auxiliar e o oculte do usuário. Um thread que é identificado como um thread auxiliar durante um evento não gerenciado `ICorDebugManagedCallback::CreateThread` nunca executará código de usuário gerenciado.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** CorDebug. idl. CorDebug. h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
