---
title: Controlando a auto inicialização do host de serviço do WCF
ms.date: 03/30/2017
f1_keywords:
- WcfOptions
ms.assetid: 6abe5d34-519b-4cef-8f02-3c0a7f125585
ms.openlocfilehash: 2033e693003d0b50bcdada428e4a5f451b3ad67e
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96255072"
---
# <a name="controlling-auto-launching-of-wcf-service-host"></a>Controlando a auto inicialização do host de serviço do WCF

Você pode controlar o recurso de inicialização automática do WcfSvcHost.exe host de serviço do Windows Communication Foundation (WCF) para um projeto de biblioteca de serviço WCF, quando você depura outro projeto na mesma solução do Visual Studio que contém vários projetos.  
  
 Para fazer isso, clique com o botão direito do mouse no projeto de serviço WCF no **Gerenciador de soluções**, escolha **Propriedades** e clique na guia **Opções do WCF** . A caixa de seleção **Iniciar host de serviço WCF ao depurar outro projeto na mesma solução** está habilitada por padrão. Você pode desmarcar a caixa para que o host de serviço do WCF para esse projeto específico não seja iniciado quando outro projeto for depurado na mesma solução.  
  
 Esse comportamento não afeta a depuração F5 ou Adicionar Referência de Serviço funcionalidades para este projeto.  
  
 Essa opção está disponível para os seguintes projetos:  
  
- Projeto de biblioteca de serviço WCF.  
  
- Projeto de biblioteca de serviço de fluxo de trabalho Sequencial.  
  
- Projeto de biblioteca do serviço de fluxo de trabalho de máquina de estado.  
  
- Projeto de biblioteca de serviço de distribuição.  
  
## <a name="see-also"></a>Veja também

- [Host de serviço do WCF (WcfSvcHost.exe)](wcf-service-host-wcfsvchost-exe.md)
