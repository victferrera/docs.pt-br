---
title: MDA failedQI
description: Examine o MDA (Assistente de depuração gerenciada) do failedQI no .NET, que pode ser ativado quando uma conversão ativa ou uma chamada COM de um RCW (Runtime Callable Wrapper) falhar.
ms.date: 03/30/2017
helpviewer_keywords:
- failed QueryInterface
- FailedQI MDA
- QueryInterface call failures
- MDAs (managed debugging assistants), failed QueryInterface
- managed debugging assistants (MDAs), failed QueryInterface
ms.assetid: 902dc863-34b3-477c-b433-b8a6bb6133c6
ms.openlocfilehash: bbd8d5644f8620444d80845b9920b925b6891176
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96244321"
---
# <a name="failedqi-mda"></a>MDA failedQI

O MDA (assistente para depuração gerenciada) `failedQI` é ativado quando o tempo de execução chama `QueryInterface` em um ponteiro de interface COM em nome de um RCW (Runtime Callable Wrapper) e a chamada `QueryInterface` falha.  
  
## <a name="symptoms"></a>Sintomas  

 Uma conversão em um RCW falha ou uma chamada ao COM em um RCW falha inesperadamente.  
  
## <a name="cause"></a>Causa  
  
- A chamada é feita do contexto incorreto.  
  
- O proxy registrado está falhando a chamada `QueryInterface` porque houve uma tentativa de realizar a chamada no contexto incorreto.  
  
- Um proxy de propriedade do OLE retornou uma falha HRESULT.  
  
## <a name="resolution"></a>Resolução  

 Consulte a documentação do MSDN sobre as regras do COM.  
  
## <a name="effect-on-the-runtime"></a>Efeito sobre o runtime  

 Se uma chamada `QueryInterface` falhar, o contexto será alternado e haverá uma tentativa de realizar a chamada `QueryInterface` novamente para ver se um contexto incorreto estava com uma falha.  
  
## <a name="output"></a>Saída  

 O nome gerenciado da interface, o GUID da interface e o HRESULT da falha.  
  
## <a name="configuration"></a>Configuração  
  
```xml  
<mdaConfig>  
  <assistants>  
    <failedQI/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a>Veja também

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [Diagnosticando erros com assistentes de depuração gerenciados](diagnosing-errors-with-managed-debugging-assistants.md)
- [Realizando marshaling de interoperabilidade](../interop/interop-marshaling.md)
