---
title: Método ICorRuntimeHost::GetDefaultDomain
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.GetDefaultDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::GetDefaultDomain
helpviewer_keywords:
- ICorRuntimeHost::GetDefaultDomain method [.NET Framework hosting]
- GetDefaultDomain method [.NET Framework hosting]
ms.assetid: 5e17a6fc-f335-4aae-9bb0-c3e1271a9426
topic_type:
- apiref
ms.openlocfilehash: 673c32c86c808c36db6454b8a9f0d8e68f9b1258
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720627"
---
# <a name="icorruntimehostgetdefaultdomain-method"></a>Método ICorRuntimeHost::GetDefaultDomain

Obtém um ponteiro de interface do tipo <xref:System._AppDomain?displayProperty=nameWithType> que representa o domínio padrão para o processo atual.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
HRESULT GetDefaultDomain (  
    [out] IUnknown** pAppDomain  
);  
```  
  
## <a name="parameters"></a>Parâmetros  

 `pAppDomain`  
 fora Um ponteiro de interface do tipo <xref:System._AppDomain?displayProperty=nameWithType> para a <xref:System.AppDomain> instância que representa o domínio de aplicativo padrão para o processo.  
  
 Esse ponteiro é digitado `IUnknown` , de modo que os chamadores geralmente devem chamar `QueryInterface` para obter um ponteiro de interface do tipo <xref:System._AppDomain?displayProperty=nameWithType> .  
  
## <a name="return-value"></a>Valor Retornado  
  
|HRESULT|Descrição|  
|-------------|-----------------|  
|S_OK|A operação foi bem-sucedida.|  
|S_FALSE|Falha ao concluir a operação.|  
|E_FAIL|Ocorreu uma falha catastrófica desconhecida. Se um método retornar E_FAIL, o Common Language Runtime (CLR) não poderá mais ser usado no processo. As chamadas subsequentes para qualquer API de hospedagem retornam HOST_E_CLRNOTAVAILABLE.|  
|HOST_E_CLRNOTAVAILABLE|O CLR não foi carregado em um processo ou o CLR está em um estado no qual não pode executar código gerenciado ou processar a chamada com êxito.|  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** MSCorEE. h  
  
 **Biblioteca:** Incluído como um recurso no MSCorEE.dll  
  
 **Versões do .NET Framework:** 1,0, 1,1  
  
## <a name="see-also"></a>Confira também

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- [Interface ICorRuntimeHost](icorruntimehost-interface.md)
