---
title: comando de restauração da ferramenta dotnet
description: O comando dotnet ferramenta de restauração instala em seu computador as ferramentas locais do .NET que estão no escopo para o diretório atual.
ms.date: 02/14/2020
ms.openlocfilehash: 3425bc6b78fd53f578c209013f83b006305dbb81
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96242923"
---
# <a name="dotnet-tool-restore"></a>dotnet tool restore

**Este artigo aplica-se a:** ✔️ SDK do .net Core 3,0 e versões posteriores

## <a name="name"></a>Nome

`dotnet tool restore` -Instala as ferramentas locais do .NET que estão no escopo do diretório atual.

## <a name="synopsis"></a>Sinopse

```dotnetcli
dotnet tool restore
    [--configfile <FILE>] [--add-source <SOURCE>]
    [tool-manifest <PATH_TO_MANIFEST_FILE>] [--disable-parallel]
    [--ignore-failed-sources] [--no-cache] [--interactive]
    [-v|--verbosity <LEVEL>]

dotnet tool restore -h|--help
```

## <a name="description"></a>Descrição

O `dotnet tool restore` comando localiza o arquivo de manifesto da ferramenta que está no escopo do diretório atual e instala as ferramentas listadas nele. Para obter informações sobre arquivos de manifesto, consulte [instalar uma ferramenta local](global-tools.md#install-a-local-tool) e [invocar uma ferramenta local](global-tools.md#invoke-a-local-tool).

## <a name="options"></a>Opções

- **`--configfile <FILE>`**

  O arquivo de configuração do NuGet (*nuget.config*) a ser usado.

- **`--add-source <SOURCE>`**

  Adiciona outra origem do pacote NuGet a ser usada durante a instalação.

- **`--tool-manifest <PATH>`**

  Caminho para o arquivo de manifesto.

- **`--disable-parallel`**

  Impedir a restauração de vários projetos em paralelo.

- **`--ignore-failed-sources`**

  Tratar falhas de origem do pacote como avisos.

- **`--no-cache`**

  Não armazene em cache pacotes e solicitações HTTP.

- **`--interactive`**

  Permite que o comando pare e aguarde a entrada ou uma ação do usuário (por exemplo, para concluir a autenticação).

- **`-h|--help`**

  Imprime uma ajuda breve para o comando.

- **`-v|--verbosity <LEVEL>`**

  Define o nível de detalhes do comando. Os valores permitidos são `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.

## <a name="example"></a>Exemplo

- **`dotnet tool restore`**

  Restaura as ferramentas locais para o diretório atual.

## <a name="see-also"></a>Veja também

- [Ferramentas .NET](global-tools.md)
- [Tutorial: instalar e usar uma ferramenta local do .NET usando a CLI do .NET](local-tools-how-to-use.md)
