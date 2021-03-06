---
title: AppDomainInfo
ms.date: 03/30/2017
ms.assetid: 6610b7d8-81eb-4bec-a543-9b72ad7b6f73
ms.openlocfilehash: c5c44f4d8f6d93443802d5e1950c4d850976c5b6
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96291122"
---
# <a name="appdomaininfo"></a>AppDomainInfo

Informações de domínio do aplicativo  
  
## <a name="syntax"></a>Sintaxe  
  
```csharp
class AppDomainInfo  
{  
  sint32 AppDomainId;  
  boolean IsDefault;  
  boolean LogMalformedMessages;  
  boolean LogMessagesAtServiceLevel;  
  boolean LogMessagesAtTransportLevel;  
  TraceListener MessageLoggingTraceListeners[];  
  string Name;  
  string PerformanceCounters;  
  sint32 ProcessId;  
  string ServiceConfigPath;  
  string TraceLevel;  
  TraceListener wmiTraceListeners[];  
};  
```  
  
## <a name="methods"></a>Métodos  

 A classe AppDomainInfo não define nenhum método.  
  
## <a name="properties"></a>Propriedades  

 A classe AppDomainInfo tem as seguintes propriedades:  
  
### <a name="appdomainid"></a>AppDomainid  

 Tipo de dados: sint32  
  
 Tipo de acesso: Somente leitura  
  
 A ID do AppDomain.  
  
### <a name="isdefault"></a>IsDefault  

 Tipo de dados: booliano  
  
 Tipo de acesso: Somente leitura  
  
 Indica se AppDomain é o AppDomain padrão.  
  
### <a name="logmalformedmessages"></a>LogMalformedMessages  

 Tipo de dados: booliano  
  
 Tipo de acesso: Leitura/Gravação  
  
 Um valor que especifica se as mensagens malformadas são registradas.  
  
### <a name="logmessagesatservicelevel"></a>LogMessagesAtServiceLevel  

 Tipo de dados: booliano  
  
 Tipo de acesso: Leitura/Gravação  
  
 Um valor que especifica se as mensagens são rastreadas no nível de serviço (antes das transformações relacionadas à criptografia e ao transporte).  
  
### <a name="logmessagesattransportlevel"></a>LogMessagesAtTransportLevel  

 Tipo de dados: booliano  
  
 Tipo de acesso: Leitura/Gravação  
  
 Um valor que especifica se as mensagens são rastreadas no nível de transporte.  
  
### <a name="messageloggingtracelisteners"></a>MessageLoggingTraceListeners  

 Tipo de dados: matriz TraceListener  
  
 Tipo de acesso: Somente leitura  
  
 Os ouvintes de rastreamento de coleção que ouvem a origem de rastreamento System. WMI. MessageLogging.  
  
### <a name="name"></a>Nome  

 Tipo de dados: cadeia de caracteres  
  
 Tipo de acesso: Somente leitura  
  
 O nome do AppDomain.  
  
### <a name="performancecounters"></a>PerformanceCounters  

 Tipo de dados: cadeia de caracteres  
  
 Tipo de acesso: Somente leitura  
  
 O escopo dos contadores de desempenho ativos no AppDomain.  
  
### <a name="processid"></a>ProcessId  

 Tipo de dados: sint32  
  
 Tipo de acesso: Somente leitura  
  
 A ID do processo.  
  
### <a name="serviceconfigpath"></a>ServiceConfigPath  

 Tipo de dados: cadeia de caracteres  
  
 Tipo de acesso: Somente leitura  
  
 O caminho para a configuração do serviço.  
  
### <a name="tracelevel"></a>TraceLevel  

 Tipo de dados: cadeia de caracteres  
  
 Tipo de acesso: Leitura/Gravação  
  
 O nível de rastreamento da origem do rastreamento System. WMI.  
  
### <a name="servicemodeltracelisteners"></a>ServiceModelTraceListeners  

 Tipo de dados: matriz TraceListener  
  
 Tipo de acesso: Somente leitura  
  
 Uma coleção de ouvintes da origem de rastreamento System. ServiceModel.  
  
## <a name="requirements"></a>Requisitos  
  
|MOF|Declarado em ServiceModel. mof.|  
|---------|-----------------------------------|  
|Namespace|Definido em root\ServiceModel|
