---
title: Interface IGCHost
ms.date: 03/30/2017
api_name:
- IGCHost
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IGCHost
helpviewer_keywords:
- IGCHost interface [.NET Framework hosting]
ms.assetid: 9ad70ffd-6963-4ab2-8c84-3d86c3fb8deb
topic_type:
- apiref
ms.openlocfilehash: 8965797321e68443c01d05f97d147f2320a76739
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724286"
---
# <a name="igchost-interface"></a>Interface IGCHost

Fornece métodos para obter informações sobre o sistema de coleta de lixo e para controlar alguns aspectos da coleta de lixo.  
  
> [!NOTE]
> Começando com o .NET Framework 4,5, você pode usar o método [IGCHost2:: SetGCStartupLimitsEx](igchost2-setgcstartuplimitsex-method.md) para definir o tamanho de um segmento de coleta de lixo e o tamanho máximo da geração 0 do sistema de coleta de lixo para valores maiores que o `DWORD` limite imposto pelo método [SetGCStartupLimits](igchost-setgcstartuplimits-method.md) .  
  
> [!NOTE]
> Essa interface é apenas para uso de especialistas. Ele pode afetar o desempenho de um aplicativo se for usado de forma inadequada.  
  
## <a name="methods"></a>Métodos  
  
|Método|DESCRIÇÃO|  
|------------|-----------------|  
|[Método Collect](igchost-collect-method.md)|Força a ocorrência de uma coleção para a geração determinada, independentemente do estado da coleta de lixo atual.|  
|[Método GetStats](igchost-getstats-method.md)|Obtém as estatísticas do estado atual do sistema de coleta de lixo.|  
|[Método GetThreadStats](igchost-getthreadstats-method.md)|Obtém as estatísticas por thread para a coleta de lixo.|  
|[Método SetGCStartupLimits](igchost-setgcstartuplimits-method.md)|Define o tamanho do segmento e o tamanho máximo para a geração 0.|  
|[Método SetVirtualMemLimit](igchost-setvirtualmemlimit-method.md)|Define o tamanho máximo da memória virtual do tempo de execução.|  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** GCHost. idl, GCHost. h  
  
 **Biblioteca:** Incluído como um recurso no MSCorEE.dll  
  
 **.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Confira também

- [Interfaces de hospedagem](hosting-interfaces.md)
- [Coclass CorRuntimeHost](corruntimehost-coclass.md)
