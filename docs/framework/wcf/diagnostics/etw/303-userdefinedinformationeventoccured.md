---
title: 303 - UserDefinedInformationEventOccured
ms.date: 03/30/2017
ms.assetid: 5ed5acaf-3755-4417-92c4-4ebc8e854ca1
ms.openlocfilehash: 8597d84184caea9fc5dc7778cfc6d05e7dc592db
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96243424"
---
# <a name="303---userdefinedinformationeventoccured"></a>303 - UserDefinedInformationEventOccured

## <a name="properties"></a>Propriedades  
  
|||  
|-|-|  
|ID|303|  
|Palavras-chave|Solução de problemas, HealthMonitoring, UserEvents, ServiceModel, EndToEndMonitoring|  
|Nível|Informações do|  
|Canal|Os aplicativos de servidor de Microsoft-Windows- aplicativo/analítico|  
  
## <a name="description"></a>Descrição  

 Esse evento é emitido a partir do código do usuário. Os desenvolvedores podem emitir esse evento quando um evento informativo definido por personalizado ocorrer em seu serviço. Isso pode ser feito usando as <xref:System.Diagnostics.Eventing> APIs. Além disso, há um exemplo do WCF que encapsula essa API e demonstra como emitir esse evento corretamente.  
  
## <a name="message"></a>Mensagem  

 Nome: ' %1 ', referência: ' %2 ', carga: %3  
  
## <a name="details"></a>Detalhes  
  
|Nome do item de dados|Tipo de item de dados|Descrição|  
|--------------------|--------------------|-----------------|  
|Nome|`xs:string`|O nome definido pelo usuário do evento|  
|HostReference|`xs:string`|Os serviços hospedados da Web, este campo identificam exclusivamente o serviço na hierarquia da Web. Seu formato é definido como ' nome do site aplicativo caminho virtual&#124;serviço caminho virtual&#124;ServiceName '. Exemplo: ' Default Web site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService '.|  
|Carga útil|`xs:string`|A carga definida pelo usuário do evento.|
