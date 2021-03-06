---
title: Análise de código no .NET
titleSuffix: ''
description: Saiba mais sobre a análise de código-fonte no SDK do .NET.
ms.date: 12/04/2020
ms.topic: overview
ms.custom: updateeachrelease
helpviewer_keywords:
- code analysis
- code analyzers
ms.openlocfilehash: 2f59b97de6f92e5a9bf927e1318286e400017dad
ms.sourcegitcommit: 81f1bba2c97a67b5ca76bcc57b37333ffca60c7b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "97009840"
---
# <a name="overview-of-net-source-code-analysis"></a>Visão geral da análise de código-fonte do .NET

Os analisadores do .NET Compiler Platform (Roslyn) inspecionam código em C# ou no Visual Basic em busca de problemas de estilo e de qualidade. A partir do .NET 5,0, esses analisadores estão incluídos no SDK do .NET e você não precisa instalá-los separadamente. Se o projeto for destinado ao .NET 5 ou posterior, a análise de código será habilitada por padrão. Se o projeto tiver como alvo uma implementação diferente do .NET, por exemplo, .NET Core, .NET Standard ou .NET Framework, você deverá habilitar manualmente a análise de código definindo a propriedade [EnableNETAnalyzers](../../core/project-sdk/msbuild-props.md#enablenetanalyzers) como `true` .

Se você não quiser migrar para o SDK do .NET 5 + ou se preferir um modelo baseado em pacote NuGet, os analisadores também estarão disponíveis no [pacote NuGet Microsoft. CodeAnalysis. Netanalyzers](https://www.nuget.org/packages/Microsoft.CodeAnalysis.NetAnalyzers). Você pode preferir um modelo baseado em pacote para atualizações de versão sob demanda.

> [!NOTE]
> Os analisadores .NET são independentes de estrutura de destino. Ou seja, seu projeto não precisa ter como destino uma implementação específica do .NET. Os analisadores funcionam para projetos direcionados `net5.0` , bem como para versões anteriores do .net, como `netcoreapp3.1` e `net472` .

Se violações de regra forem encontradas por um analisador, elas serão relatadas como uma sugestão, aviso ou erro, dependendo de como cada regra é [configurada](configuration-options.md). Violações de análise de código aparecem com o prefixo "CA" ou "IDE" para diferenciá-las dos erros do compilador.

## <a name="code-quality-analysis"></a>Análise de qualidade de código

As regras de *análise de qualidade de código* ("CAxxxx") inspecionam seu código em C# ou Visual Basic para fins de segurança, desempenho, design e outros problemas. A análise é habilitada, por padrão, para projetos direcionados ao .NET 5,0 ou posterior. Você pode habilitar a análise de código em projetos direcionados a versões anteriores do .NET definindo a propriedade [EnableNETAnalyzers](../../core/project-sdk/msbuild-props.md#enablenetanalyzers) como `true` . Você também pode desabilitar a análise de código para seu projeto definindo `EnableNETAnalyzers` como `false` .

> [!TIP]
> Se você estiver usando o Visual Studio:
>
> - Muitas regras do analisador têm *correções de código* associadas que você pode aplicar para corrigir o problema. As correções de código são mostradas no menu de ícones de lâmpada.
> - Você pode habilitar ou desabilitar a análise de código clicando com o botão direito do mouse em um projeto no Gerenciador de soluções e selecionando **Propriedades**  >  guia **análise de código** > **habilitar analisadores .net**.

### <a name="enabled-rules"></a>Regras habilitadas

As regras a seguir estão habilitadas, por padrão, no .NET 5,0.

| ID do diagnóstico | Categoria | Severidade | Descrição |
| - | - | - | - |
| [CA1416](/visualstudio/code-quality/ca1416) | Interoperabilidade | Aviso | Analisador de compatibilidade de plataforma |
| [CA1417](/visualstudio/code-quality/ca1417) | Interoperabilidade | Aviso | Não usar `OutAttribute` em parâmetros de cadeia de caracteres para P/Invokes |
| [CA1831](/visualstudio/code-quality/ca1831) | Desempenho | Aviso | Use `AsSpan` em vez de indexadores baseados em intervalo para cadeia de caracteres quando apropriado |
| [CA2013](/visualstudio/code-quality/ca2013) | Confiabilidade | Aviso | Não usar `ReferenceEquals` com tipos de valor |
| [CA2014](/visualstudio/code-quality/ca2014) | Confiabilidade | Aviso | Não usar `stackalloc` em loops |
| [CA2015](/visualstudio/code-quality/ca2015) | Confiabilidade | Aviso | Não defina finalizadores para tipos derivados de <xref:System.Buffers.MemoryManager%601> |
| [CA2200](/visualstudio/code-quality/ca2200) | Uso | Aviso | Relançar para preservar detalhes da pilha
| [CA2247](/visualstudio/code-quality/ca2247) | Uso | Aviso | O argumento passado para o Construtor TaskCompletionSource deve ser <xref:System.Threading.Tasks.TaskCreationOptions> enum em vez de <xref:System.Threading.Tasks.TaskContinuationOptions> |

Você pode alterar a severidade dessas regras para desabilitá-las ou promovê-las para erros. Você também pode [habilitar mais regras](#enable-additional-rules).

- Para obter uma lista de regras incluídas em cada versão do SDK do .NET, consulte [versões do analisador](https://github.com/dotnet/roslyn-analyzers/blob/master/src/NetAnalyzers/Core/AnalyzerReleases.Shipped.md).
- Para obter uma lista de todas as regras de qualidade de código, consulte [regras de qualidade de código](quality-rules/index.md).

### <a name="enable-additional-rules"></a>Habilitar regras adicionais

O *modo de análise* refere-se a uma configuração de análise de código predefinida, em que nenhuma, algumas ou todas as regras estão habilitadas. No modo de análise padrão, apenas um pequeno número de regras é [habilitado como avisos de compilação](#enabled-rules). Você pode alterar o modo de análise para seu projeto definindo a propriedade [analysismode](../../core/project-sdk/msbuild-props.md#analysismode) no arquivo de projeto. Os valores permitidos são:

| Valor | Descrição |
| - | - |
| `AllDisabledByDefault` | Esse é o modo mais conservador. Todas as regras são desabilitadas por padrão. Você pode [optar](configuration-options.md) seletivamente por regras individuais para habilitá-las.<br /><br />`<AnalysisMode>AllDisabledByDefault</AnalysisMode>` |
| `AllEnabledByDefault` | Esse é o modo mais agressivo. Todas as regras são habilitadas como avisos de compilação. Você pode [recusar](configuration-options.md) seletivamente as regras individuais para desabilitá-las.<br /><br />`<AnalysisMode>AllEnabledByDefault</AnalysisMode>` |
| `Default` | O modo padrão, em que algumas regras são habilitadas como avisos, outras são habilitadas apenas como sugestões de IDE do Visual Studio com correções de código correspondentes e o restante é completamente desabilitado. Você pode [aceitar ou recusar](configuration-options.md) seletivamente as regras individuais para desabilitá-las.<br /><br />`<AnalysisMode>Default</AnalysisMode>` |

Para localizar a severidade padrão de cada regra disponível e se a regra está habilitada ou não no modo de análise padrão, consulte a [lista completa de regras](https://github.com/dotnet/roslyn-analyzers/blob/master/src/NetAnalyzers/Core/AnalyzerReleases.Shipped.md).

### <a name="treat-warnings-as-errors"></a>Tratar avisos como erros

Se você usar o `-warnaserror` sinalizador ao compilar seus projetos, todos os avisos de análise de código também serão tratados como erros. Se você não quiser que os avisos de qualidade de código (CAxxxx) sejam tratados como erros em presença de `-warnaserror` , você poderá definir a `CodeAnalysisTreatWarningsAsErrors` Propriedade do MSBuild como `false` no arquivo do projeto.

```xml
<PropertyGroup>
  <CodeAnalysisTreatWarningsAsErrors>false</CodeAnalysisTreatWarningsAsErrors>
</PropertyGroup>
```

Você ainda verá quaisquer avisos de análise de código, mas eles não interromperão sua compilação.

### <a name="latest-updates"></a>Atualizações mais recentes

Por padrão, você obterá as regras de análise de código mais recentes e as severidades de regra padrão ao atualizar para versões mais recentes do SDK do .NET. Se você não quiser esse comportamento, por exemplo, se quiser garantir que nenhuma regra nova seja habilitada ou desabilitada, você poderá substituí-la de uma das seguintes maneiras:

- Defina a `AnalysisLevel` Propriedade MSBuild com um valor específico para bloquear os avisos para esse conjunto. Ao atualizar para um SDK mais recente, você ainda obterá correções de bug para esses avisos, mas nenhum aviso novo será habilitado e nenhum aviso existente será desabilitado. Por exemplo, para bloquear o conjunto de regras para as que acompanham a versão 5,0 do SDK do .NET, adicione a seguinte entrada ao arquivo de projeto.

  ```xml
  <PropertyGroup>
    <AnalysisLevel>5.0</AnalysisLevel>
  </PropertyGroup>
  ```

  > [!TIP]
  > O valor padrão da `AnalysisLevel` propriedade é `latest` , o que significa que você sempre Obtém as últimas regras de análise de código à medida que passa para versões mais recentes do SDK do .net.

  Para obter mais informações e ver uma lista de possíveis valores, consulte [AnalysisLevel](../../core/project-sdk/msbuild-props.md#analysislevel).

- Instale o [pacote NuGet Microsoft. CodeAnalysis. Netanalyzers](https://github.com/dotnet/roslyn-analyzers#microsoftcodeanalysisnetanalyzers) para desassociar atualizações de regra das atualizações do SDK do .net. A instalação do pacote desativa os analisadores internos do SDK e gera um aviso de compilação se o SDK contiver uma versão de assembly do analisador mais recente do que a do pacote NuGet.

## <a name="code-style-analysis"></a>Análise de estilo de código

As regras de *análise de estilo de código* ("IDExxxx") permitem que você defina e mantenha o estilo de código consistente na codebase. As configurações de habilitação padrão são:

- Compilação de linha de comando: a análise de estilo de código está desabilitada, por padrão, para todos os projetos .NET em compilações de linha de comando.
- Visual Studio: a análise de estilo de código está habilitada, por padrão, para todos os projetos .NET dentro do Visual Studio como [ações rápidas de refatoração de código](/visualstudio/ide/code-generation-in-visual-studio).

A partir do .NET 5,0, você pode habilitar a análise de estilo de código no Build, tanto na linha de comando quanto dentro do Visual Studio. Violações de estilo de código aparecem como avisos ou erros com um prefixo "IDE". Isso permite que você imponha estilos de código consistentes no momento da compilação.

Para obter uma lista completa de regras de análise de estilo de código, consulte [regras de estilo de código](style-rules/index.md).

### <a name="enable-on-build"></a>Habilitar no Build

Siga estas etapas para habilitar a análise de estilo de código na compilação:

1. Defina a propriedade [EnforceCodeStyleInBuild](../../core/project-sdk/msbuild-props.md#enforcecodestyleinbuild) do MSBuild como `true` .

1. Em um arquivo *. editorconfig* , [Configure](configuration-options.md) cada regra de estilo de código "IDE" que você deseja executar na compilação como um aviso ou um erro. Por exemplo:

   ```ini
   [*.{cs,vb}]
   # IDE0040: Accessibility modifiers required (escalated to a build warning)
   dotnet_diagnostic.IDE0040.severity = warning
   ```

   Como alternativa, você pode configurar a categoria "estilo" inteira para ser um aviso ou erro, por padrão, e, em seguida, desativar seletivamente as regras que você não deseja executar na compilação. Por exemplo:

   ```ini
   [*.{cs,vb}]

   # Default severity for analyzer diagnostics with category 'Style' (escalated to build warnings)
   dotnet_analyzer_diagnostic.category-Style.severity = warning

   # IDE0040: Accessibility modifiers required (disabled on build)
   dotnet_diagnostic.IDE0040.severity = silent
   ```

> [!NOTE]
> O recurso de análise de estilo de código é experimental e pode mudar entre as versões do .NET 5 e do .NET 6.

## <a name="suppress-a-warning"></a>Suprimir um aviso

Para suprimir uma violação de regra, defina a opção de severidade para essa ID de regra como `none` em um arquivo EditorConfig. Por exemplo:

```ini
dotnet_diagnostic.CA1822.severity = none
```

O Visual Studio fornece maneiras adicionais de suprimir avisos das regras de análise de código. Para obter mais informações, consulte [suprimir violações](/visualstudio/code-quality/use-roslyn-analyzers#suppress-violations).

Para obter mais informações sobre severidades de regra, consulte [Configurar a severidade da regra](configuration-options.md#severity-level).

## <a name="third-party-analyzers"></a>Analisadores de terceiros

Além dos analisadores .NET oficiais, você também pode instalar analisadores de terceiros, como [StyleCop](https://www.nuget.org/packages/StyleCop.Analyzers/), [Roslynator](https://www.nuget.org/packages/Roslynator.Analyzers/), [analisadores de xUnit](https://www.nuget.org/packages/xunit.analyzers/)e o [analisador de sonar](https://www.nuget.org/packages/SonarAnalyzer.CSharp/).

## <a name="see-also"></a>Confira também

- [Referência da regra de análise de qualidade de código](quality-rules/index.md)
- [Referência da regra de análise de estilo de código](style-rules/index.md)
- [Análise de código no Visual Studio](/visualstudio/code-quality/roslyn-analyzers-overview)
- [SDK da Plataforma do Compilador .NET](../../csharp/roslyn-sdk/index.md)
- [Tutorial: escrever seu primeiro analisador e correção de código](../../csharp/roslyn-sdk/tutorials/how-to-write-csharp-analyzer-code-fix.md)
