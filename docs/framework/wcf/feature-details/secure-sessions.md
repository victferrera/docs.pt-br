---
title: Sessões seguras
ms.date: 03/30/2017
ms.assetid: 7b50602f-d7b5-42e9-8e92-1f0413df0d8b
ms.openlocfilehash: fd8406af0c37981b2ddc7ab8ddb0c82c63cbc0b1
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96288535"
---
# <a name="secure-sessions"></a>Sessões seguras

Um recurso do Windows Communication Foundation (WCF) é uma sessão confiável que garante que as mensagens sejam recebidas na ordem em que foram enviadas. Os tópicos nesta seção discutem as implicações de segurança a serem consideradas ao criar uma sessão confiável. Para obter mais informações sobre sessões confiáveis, consulte [usando sessões](../using-sessions.md).  
  
> [!NOTE]
> Quando a representação é necessária no Windows XP, use uma sessão segura sem um símbolo de contexto de segurança com estado (SCT). Quando SCTs com estado são usados com representação, um <xref:System.InvalidOperationException> é gerado. Para obter mais informações, consulte [cenários sem suporte](unsupported-scenarios.md).  
  
## <a name="in-this-section"></a>Nesta seção  
  
|||  
|-|-|  
|[Sessões seguras e conversas seguras](secure-conversations-and-secure-sessions.md)|Conversas seguras e sessões seguras são sinônimos. Este tópico explica como funciona uma conversa segura e quando e por que usar o padrão.|  
|[Como: criar uma sessão segura](how-to-create-a-secure-session.md)|Percorre as noções básicas da criação de uma sessão segura.|  
|[Como: criar um token de contexto de segurança para uma sessão segura](how-to-create-a-security-context-token-for-a-secure-session.md)|Percorre as etapas de criação de um Web farm que manterá o estado e as sessões com clientes.|  
|[Considerações de segurança para sessões seguras](security-considerations-for-secure-sessions.md)|Descreve considerações especiais para sessões seguras.|  
  
## <a name="reference"></a>Referência  

 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Channels>  
  
## <a name="related-sections"></a>Seções relacionadas  

 [Sessões,instanciação e simultaneidade](sessions-instancing-and-concurrency.md)  
  
 [Serviços de implantação e projeção](../designing-and-implementing-services.md)  
  
## <a name="see-also"></a>Veja também

- [Como: habilitar a detecção de reprodução de mensagem](how-to-enable-message-replay-detection.md)
- [Ataques por repetição](replay-attacks.md)
- [Como: criar um serviço que requer sessões](how-to-create-a-service-that-requires-sessions.md)
