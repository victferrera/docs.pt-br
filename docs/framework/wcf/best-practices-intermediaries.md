---
title: 'Melhores práticas: intermediários'
ms.date: 03/30/2017
ms.assetid: 2d41b337-8132-4ac2-bea2-6e9ae2f00f8d
ms.openlocfilehash: 57be78681147dfc5bc37701a76c1347040f5da1f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96277888"
---
# <a name="best-practices-intermediaries"></a>Melhores práticas: intermediários

Deve-se ter cuidado para lidar corretamente com falhas ao chamar intermediários para garantir que os canais do lado do serviço no intermediário sejam fechados corretamente.  
  
 Considere este cenário. Um cliente faz uma chamada para um intermediário que chama um serviço de back-end.  O serviço de back-end não define nenhum contrato de falha, portanto, qualquer falha gerada desse serviço será tratada como uma falha não tipada.  O serviço de back-end gera um <xref:System.ApplicationException> e o WCF anula corretamente o canal do lado do serviço. <xref:System.ApplicationException>Em seguida, as superfícies como uma <xref:System.ServiceModel.FaultException> que são geradas para o intermediário. O intermediário relança o <xref:System.ApplicationException> . O WCF interpreta isso como uma falha não tipada do intermediário e a encaminha para o cliente. Após o recebimento da falha, tanto o intermediário quanto o cliente falham em seus canais do lado do cliente. No entanto, o canal do lado do serviço do intermediário permanece aberto porque o WCF não sabe que a falha é fatal.  
  
 A prática recomendada neste cenário é detectar se a falha proveniente do serviço é fatal e, nesse caso, o intermediário deve falhar em seu canal do lado do serviço, conforme mostrado no trecho de código a seguir.  
  
```csharp  
catch (Exception e)  
{  
    bool faulted = service.State == CommunicationState.Faulted;  
    service.Abort();  
    if (faulted)  
    {  
        throw new ApplicationException(e.Message);  
    }  
    else  
    {  
        throw;  
    }  
}  
```  
  
## <a name="see-also"></a>Veja também

- [Tratamento de erros do WCF](wcf-error-handling.md)
- [Especificando e lidando com falhas em contratos e serviços](specifying-and-handling-faults-in-contracts-and-services.md)
