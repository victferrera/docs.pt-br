---
title: Elemento <legacyImpersonationPolicy>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#legacyImpersonationPolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/legacyImpersonationPolicy
helpviewer_keywords:
- <legacyImpersonationPolicy> element
- legacyImpersonationPolicy element
ms.assetid: 6e00af10-42f3-4235-8415-1bb2db78394e
ms.openlocfilehash: ca10c809ddf319817aaa074ba5fc3415abf6387d
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91192510"
---
# <a name="legacyimpersonationpolicy-element"></a>Elemento \<legacyImpersonationPolicy>

Especifica que a identidade do Windows não flua entre pontos assíncronos, independentemente das configurações de fluxo para o contexto de execução no thread atual.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<legacyImpersonationPolicy>**  
  
## <a name="syntax"></a>Sintaxe  
  
```xml  
<legacyImpersonationPolicy
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Atributos e elementos  

 As seções a seguir descrevem atributos, elementos filho e elementos pai.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descrição|  
|---------------|-----------------|  
|`enabled`|Atributo obrigatório.<br /><br /> Especifica que o não <xref:System.Security.Principal.WindowsIdentity> flui em pontos assíncronos, independentemente das <xref:System.Threading.ExecutionContext> configurações de fluxo no thread atual.|  
  
## <a name="enabled-attribute"></a>Atributo habilitado  
  
|Valor|Descrição|  
|-----------|-----------------|  
|`false`|<xref:System.Security.Principal.WindowsIdentity> flui entre pontos assíncronos, dependendo das <xref:System.Threading.ExecutionContext> configurações de fluxo do thread atual. Esse é o padrão.|  
|`true`|<xref:System.Security.Principal.WindowsIdentity> não flui em pontos assíncronos, independentemente das <xref:System.Threading.ExecutionContext> configurações de fluxo no thread atual.|  
  
### <a name="child-elements"></a>Elementos filho  

 Nenhum.  
  
### <a name="parent-elements"></a>Elementos pai  
  
|Elemento|Descrição|  
|-------------|-----------------|  
|`configuration`|O elemento raiz em cada arquivo de configuração usado pelos aplicativos do Common Language Runtime e .NET Framework.|  
|`runtime`|Contém informações sobre associação do assembly e coleta de lixo.|  
  
## <a name="remarks"></a>Comentários  

 No .NET Framework versões 1,0 e 1,1, o não <xref:System.Security.Principal.WindowsIdentity> flui em nenhum ponto assíncrono definido pelo usuário. A partir do .NET Framework versão 2,0, há um <xref:System.Threading.ExecutionContext> objeto que contém informações sobre o thread em execução no momento e ele flui entre pontos assíncronos dentro de um domínio de aplicativo. O <xref:System.Security.Principal.WindowsIdentity> é incluído nesse contexto de execução e, portanto, também flui pelos pontos assíncronos, o que significa que, se existir um contexto de representação, ele fluirá também.  
  
 Começando com o .NET Framework 2,0, você pode usar o `<legacyImpersonationPolicy>` elemento para especificar que não  <xref:System.Security.Principal.WindowsIdentity> flui em pontos assíncronos.  
  
> [!NOTE]
> O Common Language Runtime (CLR) reconhece as operações de representação executadas usando apenas código gerenciado, não a representação executada fora do código gerenciado, como por meio de invocação de plataforma para código não gerenciado ou por meio de chamadas diretas para funções do Win32. Somente <xref:System.Security.Principal.WindowsIdentity> os objetos gerenciados podem fluir entre pontos assíncronos, a menos que o `alwaysFlowImpersonationPolicy` elemento tenha sido definido como true ( `<alwaysFlowImpersonationPolicy enabled="true"/>` ). Definir o `alwaysFlowImpersonationPolicy` elemento como true Especifica que a identidade do Windows sempre fluirá entre pontos assíncronos, independentemente de como a representação foi executada. Para obter mais informações sobre como fluir a representação não gerenciada em pontos assíncronos, consulte [ \<alwaysFlowImpersonationPolicy> elemento](alwaysflowimpersonationpolicy-element.md).  
  
 Você pode alterar esse comportamento padrão de duas maneiras:  
  
1. Em código gerenciado por thread.  
  
     Você pode suprimir o fluxo por thread modificando as <xref:System.Threading.ExecutionContext> <xref:System.Security.SecurityContext> configurações e usando o <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType> <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType> método, ou <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType> .  
  
2. Na chamada à interface de hospedagem não gerenciada para carregar o Common Language Runtime (CLR).  
  
     Se uma interface de hospedagem não gerenciada (em vez de um executável gerenciado simples) for usada para carregar o CLR, você poderá especificar um sinalizador especial na chamada para a função de [função CorBindToRuntimeEx](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) . Para habilitar o modo de compatibilidade para todo o processo, defina o `flags` parâmetro para a [função CorBindToRuntimeEx](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) como STARTUP_LEGACY_IMPERSONATION.  
  
 Para obter mais informações, consulte o [ \<alwaysFlowImpersonationPolicy> elemento](alwaysflowimpersonationpolicy-element.md).  
  
## <a name="configuration-file"></a>Arquivo de configuração  

 Em um aplicativo .NET Framework, esse elemento pode ser usado somente no arquivo de configuração do aplicativo.  
  
 Para um aplicativo ASP.NET, o fluxo de representação pode ser configurado no arquivo de aspnet.config encontrado no \<Windows Folder> diretório \Microsoft.NET\Framework\vx.x.xxxx.  
  
 O ASP.NET, por padrão, desabilita o fluxo de representação no arquivo de aspnet.config usando as seguintes definições de configuração:  
  
``` xml
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
      <alwaysFlowImpersonationPolicy enabled="false"/>  
   </runtime>  
</configuration>  
```  
  
 Em ASP.NET, se você quiser permitir o fluxo de representação em vez disso, deverá usar explicitamente as seguintes definições de configuração:  
  
```xml  
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="false"/>  
      <alwaysFlowImpersonationPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="example"></a>Exemplo  

 O exemplo a seguir mostra como especificar o comportamento herdado que não flui a identidade do Windows entre pontos assíncronos.  
  
```xml  
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Veja também

- [Esquema de configurações do runtime](index.md)
- [Esquema do arquivo de configuração](../index.md)
- [\<alwaysFlowImpersonationPolicy> Elementos](alwaysflowimpersonationpolicy-element.md)
