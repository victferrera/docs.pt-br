---
title: Imagens oficiais do .NET Docker
description: Arquitetura de microsserviços do .NET para aplicativos .NET em contêineres | Imagens oficiais do .NET Docker
ms.date: 01/30/2020
ms.openlocfilehash: 9339c21897749db854262e280321658ce1f541cb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95675510"
---
# <a name="official-net-docker-images"></a>Imagens oficiais do .NET Docker

As imagens oficiais do .NET Docker são imagens do Docker criadas e otimizadas pela Microsoft. Eles estão disponíveis publicamente nos repositórios da Microsoft no [Hub do Docker](https://hub.docker.com/u/microsoft/). Cada repositório pode conter várias imagens, dependendo de versões do .NET e, dependendo do sistema operacional e das versões (Linux Debian, Linux Alpine, Windows Nano Server, Windows Server Core, etc.).

Desde o .NET Core 2,1, todas as imagens do .NET Core, incluindo para ASP.NET Core, estão disponíveis no Hub do Docker no repositório de imagens do .NET Core: <https://hub.docker.com/_/microsoft-dotnet/> .

Desde maio de 2018, as imagens da Microsoft estão sendo [agregadas no registro de contêiner da Microsoft](https://azure.microsoft.com/blog/microsoft-syndicates-container-catalog/). O catálogo oficial ainda está disponível no Hub do Docker e você encontrará o endereço atualizado para efetuar pull da imagem.

A maioria dos repositórios de imagens fornece marcação extensiva para ajudá-lo a selecionar não apenas uma versão específica do Framework, mas também para escolher um sistema operacional (versão do Windows ou distribuição do Linux).

## <a name="net-core-and-docker-image-optimizations-for-development-versus-production"></a>Otimizações de imagem do .NET Core e do Docker para desenvolvimento versus produção

Ao criar imagens do Docker para desenvolvedores, a Microsoft se concentrava nos seguintes cenários principais:

- Imagens usadas para *desenvolver* e criar aplicativos .NET Core.

- Imagens usadas para *executar* aplicativos .NET Core.

Por que várias imagens? Ao desenvolver, criar e executar aplicativos em contêineres, você geralmente tem prioridades diferentes. Fornecendo diferentes imagens para essas tarefas separadas, a Microsoft ajuda a otimizar os processos separados de desenvolver, criar e implantar aplicativos.

### <a name="during-development-and-build"></a>Durante o desenvolvimento e o build

Durante o desenvolvimento, o que é importante é a velocidade em que é possível iterar alterações e a capacidade de depurá-las. O tamanho da imagem não é tão importante quanto a capacidade de fazer alterações no código e ver as alterações rapidamente. Algumas ferramentas e "contêineres de agente de compilação" usam a imagem do .NET Core (*MCR.Microsoft.com/dotnet/SDK:3.1*) de desenvolvimento durante o processo de desenvolvimento e compilação. Ao criar dentro de um contêiner do Docker, os aspectos importantes são os elementos necessários para compilar seu aplicativo. Isso inclui o compilador e quaisquer outras dependências do .NET.

Por que este tipo de imagem de build é importante? Você não implanta essa imagem para produção. Em vez disso, é uma imagem que você usa para criar o conteúdo que você coloca em uma imagem de produção. Essa imagem seria usada no ambiente de integração contínua (CI) ou no ambiente de compilação ao usar compilações de vários estágios do Docker.

### <a name="in-production"></a>Em produção

O que é importante na produção é a rapidez com que é possível implantar e iniciar seus contêineres com base em uma imagem do .NET Core de produção. Portanto, a imagem somente de tempo de execução com base em *MCR.Microsoft.com/dotnet/ASPNET:3.1* é pequena para que possa viajar rapidamente pela rede de seu registro do Docker para os hosts do Docker. O conteúdo está pronto para ser executado, habilitando o tempo mais rápido possível da inicialização do contêiner ao processamento de resultados. No modelo do Docker, não há necessidade de compilação de código C\#, como há quando você executa dotnet build ou dotnet publish ao usar o contêiner de build.

Nessa imagem otimizada, você coloca apenas os binários e outros conteúdos necessários para executar o aplicativo. Por exemplo, o conteúdo criado pelo `dotnet publish` contém apenas os arquivos binários .net compilados, imagens,. js e. css. Ao longo do tempo, você verá imagens que contêm pacotes pré-compilados (compilação de IL para nativa que ocorre em runtime).

Embora haja várias versões das imagens do .NET Core e do ASP.NET Core, todas elas compartilham uma ou mais camadas, incluindo a camada base. Portanto, a quantidade de espaço em disco necessário para armazenar uma imagem é pequena; ela é composta apenas pelo delta entre sua imagem personalizada e sua imagem de base. O resultado é que é rápido extrair a imagem do Registro.

Quando você explorar os repositórios de imagem do .NET no Hub do Docker, encontrará várias versões de imagem confidenciais ou marcadas. Essas marcas ajudam a decidir qual usar, dependendo da versão de que você precisa, como as que estão na tabela a seguir:

| Imagem | Comentários |
|-------|----------|
| mcr.microsoft.com/dotnet/aspnet:**3,1** | ASP.NET Core, somente com runtime e otimizações de ASP.NET Core, no Linux e no Windows (várias arquiteturas) |
| mcr.microsoft.com/dotnet/sdk:**3,1** | .NET Core, com SDKs incluídos, no Linux e no Windows (várias arquiteturas) |

> [!div class="step-by-step"]
> [Anterior](net-container-os-targets.md) 
>  [Avançar](../architect-microservice-container-applications/index.md)
