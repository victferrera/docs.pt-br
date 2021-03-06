---
title: ServiceThrottlingBehavior
ms.date: 03/30/2017
ms.assetid: 37b9e517-1f1f-4ec4-9fcb-2b8016794f5b
ms.openlocfilehash: 3bcf205964a22cdb418d0158e5ee6439169538ee
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96273978"
---
# <a name="servicethrottlingbehavior"></a>ServiceThrottlingBehavior

ServiceThrottlingBehavior  
  
## <a name="syntax"></a>Sintaxe  
  
```csharp  
class ServiceThrottlingBehavior : Behavior  
{  
  sint32 MaxConcurrentCalls;  
  sint32 MaxConcurrentInstances;  
  sint32 MaxConcurrentSessions;  
};  
```  
  
## <a name="methods"></a>Métodos  

 A classe ServiceThrottlingBehavior não define nenhum método.  
  
## <a name="properties"></a>Propriedades  

 A classe ServiceThrottlingBehavior tem as seguintes propriedades:  
  
### <a name="maxconcurrentcalls"></a>MaxConcurrentCalls  

 Tipo de dados: sint32  
  
 Tipo de acesso: Somente leitura  
  
 O número máximo de mensagens processando ativamente em todos os objetos do Dispatcher em um ServiceHost.  
  
### <a name="maxconcurrentinstances"></a>MaxConcurrentInstances  

 Tipo de dados: sint32  
  
 Tipo de acesso: Somente leitura  
  
 O número máximo de objetos de serviço que podem ser executados ao mesmo tempo.  
  
### <a name="maxconcurrentsessions"></a>MaxConcurrentSessions  

 Tipo de dados: sint32  
  
 Tipo de acesso: Somente leitura  
  
 O número máximo de sessões que um host pode aceitar ao mesmo tempo.  
  
## <a name="requirements"></a>Requisitos  
  
|MOF|Declarado em ServiceModel. mof.|  
|---------|-----------------------------------|  
|Namespace|Definido em root\ServiceModel|  
  
## <a name="see-also"></a>Confira também

- <xref:System.ServiceModel.Description.ServiceThrottlingBehavior>
