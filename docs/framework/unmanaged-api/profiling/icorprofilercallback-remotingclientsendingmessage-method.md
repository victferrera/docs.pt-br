---
title: Método ICorProfilerCallback::RemotingClientSendingMessage
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RemotingClientSendingMessage
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RemotingClientSendingMessage
helpviewer_keywords:
- RemotingClientSendingMessage method [.NET Framework profiling]
- ICorProfilerCallback::RemotingClientSendingMessage method [.NET Framework profiling]
ms.assetid: 54d9a5a5-3877-49c1-a503-ce7c7943bc2a
topic_type:
- apiref
ms.openlocfilehash: 2ef8f066831df1437bd0b6a6f155dd459cae1eb2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95676836"
---
# <a name="icorprofilercallbackremotingclientsendingmessage-method"></a>Método ICorProfilerCallback::RemotingClientSendingMessage

Notifica o criador de perfil de que o cliente está enviando uma solicitação para o servidor.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
HRESULT RemotingClientSendingMessage(  
    [in] GUID *pCookie,  
    [in] BOOL fIsAsync);  
```  
  
## <a name="parameters"></a>Parâmetros  

 `pCookie`  
 no Um valor que corresponde ao valor fornecido em [ICorProfilerCallback:: RemotingServerReceivingMessage](icorprofilercallback-remotingserverreceivingmessage-method.md) sob estas condições:  
  
- Os cookies de GUID de comunicação remota estão ativos.  
  
- O canal tem sucesso ao transmitir a mensagem.  
  
- Os cookies de GUID estão ativos no processo do lado do servidor.  
  
 Isso permite um emparelhamento fácil de chamadas remotas e a criação de uma pilha de chamadas lógica.  
  
 `fIsAsync`  
 no Um valor que é `true` se a chamada for assíncrona; caso contrário, `false` .  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** CorProf. idl, CorProf. h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Confira também

- [Interface ICorProfilerCallback](icorprofilercallback-interface.md)
