---
title: Interface IGCHost2
ms.date: 03/30/2017
api_name:
- IGCHost2
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IGCHost2
helpviewer_keywords:
- IGCHost2 interface [.NET Framework hosting]
ms.assetid: e5323fa4-18ac-424d-859d-a65a550d08d9
topic_type:
- apiref
ms.openlocfilehash: 7529ecd215d74eb0eedbec8b90eba367ed20d56f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95687737"
---
# <a name="igchost2-interface"></a>Interface IGCHost2

Fornece métodos para obter informações sobre o sistema de coleta de lixo e para controlar alguns aspectos da coleta de lixo.  
  
> [!NOTE]
> Para um novo desenvolvimento, recomendamos que você use a interface [ICLRGCManager2](iclrgcmanager2-interface.md) em vez disso.  
  
## <a name="methods"></a>Métodos  
  
|Método|DESCRIÇÃO|  
|------------|-----------------|  
|[Método SetGCStartupLimitsEx](igchost2-setgcstartuplimitsex-method.md)|Define o tamanho do segmento e o tamanho máximo para a geração 0. Habilita a geração 0 e os tamanhos de segmento maiores que `DWORD` .|  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** GCHost. idl, GCHost. h  
  
 **Biblioteca:** Incluído como um recurso no MSCorEE.dll  
  
 **.NET Framework versões:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Confira também

- [Interfaces de hospedagem](hosting-interfaces.md)
- [Interfaces de hospedagem CLR](clr-hosting-interfaces.md)
- [Coclass CorRuntimeHost](corruntimehost-coclass.md)
