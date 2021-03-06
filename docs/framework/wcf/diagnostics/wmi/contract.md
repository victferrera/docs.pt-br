---
title: Contrato
ms.date: 03/30/2017
ms.assetid: aa00f6b3-7e1f-4213-841a-206463fca20b
ms.openlocfilehash: 0df39bbd0b273f1e898ccbe585be288cc245b7f5
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96274134"
---
# <a name="contract"></a>Contrato

Contrato  
  
## <a name="syntax"></a>Sintaxe  
  
```csharp
class Contract  
{  
  sint32 AppDomainId;  
  Behavior Behaviors[];  
  string Name;  
  string Namespace;  
  Operation Operations[];  
  sint32 ProcessId;  
  Contract ref;  
  string SessionMode;  
  string Type;  
};  
```  
  
## <a name="methods"></a>Métodos  

 A classe Contract não define nenhum método.  
  
## <a name="properties"></a>Propriedades  

 A classe Contract tem as seguintes propriedades:  
  
### <a name="appdomainid"></a>AppDomainid  

 Tipo de dados: sint32  
  
 Tipo de acesso: Somente leitura  
  
 A ID de AppDomain do AppDomain que hospeda o contrato.  
  
### <a name="behaviors"></a>Comportamentos  

 Tipo de dados: matriz de comportamento  
  
 Tipo de acesso: Somente leitura  
  
 Os comportamentos associados a este contrato.  
  
### <a name="name"></a>Nome  

 Tipo de dados: cadeia de caracteres  
  
 Tipo de acesso: Somente leitura  
  
 O nome do contrato em WSDL.  
  
### <a name="namespace"></a>Namespace  

 Tipo de dados: cadeia de caracteres  
  
 Tipo de acesso: Somente leitura  
  
 O namespace do `portType` elemento no WSDL.  
  
### <a name="operations"></a>Operações  

 Tipo de dados: matriz de operação  
  
 Tipo de acesso: Somente leitura  
  
 As operações deste contrato.  
  
### <a name="processid"></a>ProcessId  

 Tipo de dados: sint32  
  
 Tipo de acesso: Somente leitura  
  
 A ID do processo que hospeda o contrato.  
  
### <a name="ref"></a>ref  

 Tipo de dados: contrato  
  
 Tipo de acesso: Somente leitura  
  
 O tipo de retorno de chamada quando o contrato é um contrato duplex.  
  
### <a name="sessionmode"></a>SessionMode  

 Tipo de dados: cadeia de caracteres  
  
 Tipo de acesso: Somente leitura  
  
 Indica se o contrato requer que a associação associada a este contrato use sessões de canal.  
  
### <a name="type"></a>Tipo  

 Tipo de dados: cadeia de caracteres  
  
 Tipo de acesso: Somente leitura  
  
 O tipo do contrato.  
  
## <a name="requirements"></a>Requisitos  
  
|MOF|Declarado em ServiceModel. mof.|  
|---------|-----------------------------------|  
|Namespace|Definido em root\ServiceModel|  
  
## <a name="see-also"></a>Confira também

- <xref:System.ServiceModel.Description.ContractDescription>
