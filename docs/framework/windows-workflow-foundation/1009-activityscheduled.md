---
title: 1009 - ActivityScheduled
ms.date: 03/30/2017
ms.assetid: 307e38b6-d47e-47a4-9708-e74d8314b1a1
ms.openlocfilehash: 812531d4206dfee20f183b9461330e71263b0bf8
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96239764"
---
# <a name="1009---activityscheduled"></a>1009 - ActivityScheduled

## <a name="properties"></a>Propriedades  
  
|||  
|-|-|  
|ID|1009|  
|Palavras-chave|WFRuntime|  
|Nível|Informações do|  
|Canal|Os aplicativos de servidor de Microsoft-Windows- aplicativo/depuração|  
  
## <a name="description"></a>Descrição  

 Indica que uma atividade está sendo agendada para a execução.  
  
## <a name="message"></a>Mensagem  

 Atividade pai “%1", DisplayName: “%2", InstanceId: “%3" agendaram a atividade filho “%4", DisplayName: “%5", InstanceId: “%6".  
  
## <a name="details"></a>Detalhes  
  
|Nome do item de dados|Tipo de item de dados|Descrição|  
|--------------------|--------------------|-----------------|  
|ParentActivity|xs:string|O nome do tipo de atividade pai.|  
|ParentDisplayName|xs:string|O nome para exibição de atividade pai.|  
|ParentInstanceId|xs:string|A identificação de instância de atividade pai.|  
|ChildActivity|xs:string|O nome do tipo de atividade filho agendada.|  
|ChildDisplayName|xs:string|O nome para exibição de atividade filho agendada.|  
|ChildInstanceId|xs:string|A identificação de instância de atividade filho agendada.|  
|AppDomain|xs:string|A cadeia de caracteres retornada por AppDomain.CurrentDomain.FriendlyName.|
