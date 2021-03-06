---
title: Cortar aplicativos independentes
description: Saiba como cortar aplicativos independentes para reduzir seu tamanho. O .NET Core agrupa o tempo de execução com um aplicativo que é publicado de forma independente e, em geral, inclui mais do tempo de execução e, em seguida, é necessário.
author: jamshedd
ms.author: jamshedd
ms.date: 04/03/2020
ms.openlocfilehash: bf38ffe4d47986ae78c6cf2b2e5ecb292411ba6c
ms.sourcegitcommit: 6d09ae36acba0b0e2ba47999f8f1a725795462a2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/29/2020
ms.locfileid: "92925279"
---
# <a name="trim-self-contained-deployments-and-executables"></a>Cortar implantações e executáveis autossuficientes

O [modelo de implantação dependente de estrutura](index.md#publish-framework-dependent) foi o modelo de implantação mais bem-sucedido desde o início do .net. Nesse cenário, o desenvolvedor de aplicativos agrupa apenas o aplicativo e os assemblies de terceiros, com a expectativa de que as bibliotecas de tempo de execução .NET e estrutura estarão disponíveis no computador cliente. Esse modelo de implantação continua sendo o dominante no .NET Core, mas há alguns cenários em que o modelo dependente de estrutura não é o ideal. A alternativa é publicar um [aplicativo](index.md#publish-self-contained)independente, em que o tempo de execução e a estrutura do .NET Core são agrupados com o aplicativo e com assemblies de terceiros.

O modelo de implantação de preparo – autocontido é uma versão especializada do modelo de implantação independente que é otimizado para reduzir o tamanho da implantação. Minimizar o tamanho da implantação é um requisito crítico para alguns cenários do lado do cliente, como aplicativos mais Incrivelmenteos. Dependendo da complexidade do aplicativo, apenas um subconjunto dos assemblies da estrutura são referenciados e um subconjunto do código dentro de cada assembly é necessário para executar o aplicativo. As partes não utilizadas das bibliotecas são desnecessárias e podem ser cortadas do aplicativo empacotado.

No entanto, há um risco de que a análise de tempo de compilação do aplicativo possa causar falhas em tempo de execução, devido ao fato de não poder analisar de maneira confiável vários padrões de código problemáticos (amplamente centrados no uso de reflexão). Como a confiabilidade não pode ser garantida, esse modelo de implantação é oferecido como um recurso de visualização.

O mecanismo de análise de tempo de compilação fornece avisos ao desenvolvedor de padrões de código que são problemáticos para detectar qual outro código é necessário. O código pode ser anotado com atributos para informar ao corte o que mais incluir. Muitos padrões de reflexão podem ser substituídos com geração de código em tempo de compilação usando [geradores de origem](https://github.com/dotnet/roslyn/blob/master/docs/features/source-generators.md).

O modo de corte para os aplicativos é configurado com a `TrimMode` configuração. O valor padrão é `copyused` e agrupa os assemblies referenciados com o aplicativo. O `link` valor é usado com aplicativos Webassembly mais podestas e corta código não utilizado em assemblies. Avisos de análise de corte fornecem informações sobre padrões de código em que uma análise de dependência completa não era possível. Esses avisos são suprimidos por padrão e podem ser ativados definindo o sinalizador `SuppressTrimAnalysisWarnings` como `false` . Para obter mais informações sobre as opções de corte disponíveis, consulte [Opções de corte](trimming-options.md).

> [!NOTE]
> O corte é um recurso experimental no .NET Core 3,1 e no .NET 5,0. O corte _só_ está disponível para aplicativos que são publicados internamente.

## <a name="prevent-assemblies-from-being-trimmed"></a>Impedir que os assemblies sejam cortados

Há cenários em que a funcionalidade de corte falhará ao detectar referências. Por exemplo, quando a reflexão é usada em um assembly de tempo de execução, seja pelo aplicativo ou por uma biblioteca que é referenciada pelo seu aplicativo, o assembly não é referenciado diretamente. O corte não reconhece essas referências indiretas e excluiria a biblioteca da pasta publicada.

Quando o código está indiretamente referenciando um assembly por meio de reflexão, você pode impedir que o assembly seja cortado com a `<TrimmerRootAssembly>` configuração. O exemplo a seguir mostra como impedir que um assembly chamado `System.Security` assembly seja cortado:

```xml
<ItemGroup>
    <TrimmerRootAssembly Include="System.Security" />
</ItemGroup>
```

### <a name="support-for-ssl-certificates"></a>Suporte para certificados SSL

Se seu aplicativo carregar certificados SSL, como em um aplicativo de ASP.NET Core, você desejará garantir que, ao cortar, você impeça o corte de assemblies que ajudarão no carregamento de certificados SSL.

Podemos atualizar nosso arquivo de projeto para incluir o seguinte para ASP.NET Core 3,1:

```xml
<Project Sdk="Microsoft.NET.Sdk.Web">
  <PropertyGroup>...</PropertyGroup>
  <!--Include the following for .aspnetcore 3.1-->
  <ItemGroup>
    <TrimmerRootAssembly Include="System.Net" />
    <TrimmerRootAssembly Include="System.Net.Security" />
    <TrimmerRootAssembly Include="System.Security" />
  </ItemGroup>
  ...
</Project>
```

Se estivermos usando o .NET 5,0, podemos atualizar nosso arquivo de projeto para incluir o seguinte:

```xml
<Project Sdk="Microsoft.NET.Sdk.Web">
 <PropertyGroup>...</PropertyGroup>
 <!--Include the following for .net 5.0-->
 <ItemGroup>
    <TrimmerRootAssembly Include="System.Net.Security" />
    <TrimmerRootAssembly Include="System.Security" />
  </ItemGroup>
  ...
</Project>
```

## <a name="trim-your-app---cli"></a>Cortar sua app-CLI

Corte seu aplicativo usando o comando [dotnet Publish](../tools/dotnet-publish.md) . Ao publicar seu aplicativo, defina as seguintes propriedades:

- Publicar como um aplicativo independente para um tempo de execução específico: `-r win-x64`
- Habilitar corte: `/p:PublishTrimmed=true`

O exemplo a seguir publica um aplicativo para o Windows como independente e corta a saída.

```xml
<PropertyGroup>
    <RuntimeIdentifier>win-x64</RuntimeIdentifier>
    <PublishTrimmed>true</PublishTrimmed>
</PropertyGroup>
```

O exemplo a seguir publica um aplicativo no modo de corte agressivo em que o código não utilizado nos assemblies será cortado e os avisos de corte serão habilitados.

```xml
<PropertyGroup>
    <RuntimeIdentifier>win-x64</RuntimeIdentifier>
    <PublishTrimmed>true</PublishTrimmed>
    <TrimMode>link</TrimMode>
    <SuppressTrimAnalysisWarnings>false</SuppressTrimAnalysisWarnings>
</PropertyGroup>
```

Para obter mais informações, consulte [publicar aplicativos .NET Core com CLI do .NET Core](deploy-with-cli.md).

## <a name="trim-your-app---visual-studio"></a>Cortar seu aplicativo-Visual Studio

O Visual Studio cria perfis de publicação reutilizáveis que controlam como seu aplicativo é publicado.

01. No painel **Gerenciador de soluções** , clique com o botão direito do mouse no projeto que você deseja publicar. Selecione **publicar...** .

    :::image type="content" source="media/trim-self-contained/visual-studio-solution-explorer.png" alt-text="Gerenciador de Soluções com um menu de clique com o botão direito do mouse, realçando a opção publicar.":::

    Se você ainda não tiver um perfil de publicação, siga as instruções para criar um e escolha o tipo de destino da **pasta** .

01. Escolha **Editar** .

    :::image type="content" source="media/trim-self-contained/visual-studio-publish-edit-settings.png" alt-text="Gerenciador de Soluções com um menu de clique com o botão direito do mouse, realçando a opção publicar.":::

01. Na caixa de diálogo **configurações de perfil** , defina as seguintes opções:

    - Defina o **modo de implantação** **como autônomo** .
    - Defina o **tempo de execução de destino** para a plataforma na qual você deseja publicar.
    - Selecione **aparar assemblies não utilizados (em visualização)** .

    Escolha **salvar** para salvar as configurações e retornar para a caixa de diálogo de **publicação** .

    :::image type="content" source="media/trim-self-contained/visual-studio-publish-properties.png" alt-text="Gerenciador de Soluções com um menu de clique com o botão direito do mouse, realçando a opção publicar.":::

01. Escolha **publicar** para publicar seu aplicativo cortado.

Para obter mais informações, consulte [publicar aplicativos .NET Core com o Visual Studio](deploy-with-vs.md).

## <a name="trim-your-app---visual-studio-for-mac"></a>Corte do seu aplicativo-Visual Studio para Mac

Visual Studio para Mac não fornece opções para cortar seu aplicativo durante a publicação. Você precisará publicar manualmente seguindo as instruções da seção [cortar sua app-CLI](#trim-your-app---cli) . Para obter mais informações, consulte [publicar aplicativos .NET Core com CLI do .NET Core](deploy-with-cli.md).

## <a name="see-also"></a>Veja também

- [Implantação de aplicativo .NET Core](index.md).
- [Publicar aplicativos .NET Core com CLI do .NET Core](deploy-with-cli.md).
- [Publicar aplicativos .NET Core com o Visual Studio](deploy-with-vs.md).
- [dotnet Publish comando](../tools/dotnet-publish.md).
