---
title: Método IHostMemoryManager::RegisterMemoryNotificationCallback
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.RegisterMemoryNotificationCallback
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::RegisterMemoryNotificationCallback
helpviewer_keywords:
- IHostMemoryManager::RegisterMemoryNotificationCallback method [.NET Framework hosting]
- RegisterMemoryNotificationCallback method [.NET Framework hosting]
ms.assetid: 65d301f6-4dbb-4b5f-8eff-82540e2b6465
topic_type:
- apiref
ms.openlocfilehash: edb29378412583d7cdec804b08f8f622d642b02f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731300"
---
# <a name="ihostmemorymanagerregistermemorynotificationcallback-method"></a>Método IHostMemoryManager::RegisterMemoryNotificationCallback

Registra um ponteiro para uma função de retorno de chamada que o host chama para notificar o Common Language Runtime (CLR) da carga de memória atual no computador.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
HRESULT RegisterMemoryNotificationCallback (  
    [in] ICLRMemoryNotificationCallback* pCallback  
);  
```  
  
## <a name="parameters"></a>Parâmetros  

 `pCallback`  
 no Um ponteiro de interface para uma instância de [ICLRMemoryNotificationCallback](iclrmemorynotificationcallback-interface.md) que é implementada pelo CLR.  
  
## <a name="return-value"></a>Valor Retornado  
  
|HRESULT|Descrição|  
|-------------|-----------------|  
|S_OK|`RegisterMemoryNotificationCallback` retornado com êxito.|  
|HOST_E_CLRNOTAVAILABLE|O CLR não foi carregado em um processo ou o CLR está em um estado no qual não pode executar código gerenciado ou processar a chamada com êxito.|  
|HOST_E_TIMEOUT|A chamada atingiu o tempo limite.|  
|HOST_E_NOT_OWNER|O chamador não possui o bloqueio.|  
|HOST_E_ABANDONED|Um evento foi cancelado enquanto um thread ou uma fibra bloqueada estava esperando.|  
|E_FAIL|Ocorreu uma falha catastrófica desconhecida. Quando um método retorna E_FAIL, o CLR não é mais utilizável no processo. As chamadas subsequentes para métodos de hospedagem retornam HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Comentários  

 Como a `ICLRMemoryNotificationCallback` interface define apenas um método ([ICLRMemoryNotificationCallback:: OnMemoryNotification](iclrmemorynotificationcallback-onmemorynotification-method.md)) e, como `pCallback` é um ponteiro para uma `ICLRMemoryNotificationCallback` instância fornecida pelo CLR, o registro é efetivamente para a própria função de retorno de chamada. O host é invocado `OnMemoryNotification` para relatar condições de pressão de memória, em vez de usar a função Win32 padrão `CreateMemoryResourceNotification` . Para obter mais informações, consulte a documentação da plataforma Windows.  
  
> [!NOTE]
> Chamadas para `OnMemoryNotification` nunca bloquear. Eles sempre retornam imediatamente.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** MSCorEE. h  
  
 **Biblioteca:** Incluído como um recurso no MSCorEE.dll  
  
 **.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Confira também

- [Interface ICLRMemoryNotificationCallback](iclrmemorynotificationcallback-interface.md)
- [Interface IHostMemoryManager](ihostmemorymanager-interface.md)
