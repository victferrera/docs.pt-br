---
title: 'Alteração significativa: Azure: pacotes de integração do Azure prefixados da Microsoft removidos'
description: 'Saiba mais sobre a alteração significativa no ASP.NET Core 5,0 intitulado Azure: pacotes de integração do Azure prefixados da Microsoft removidos'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: b9f685b8c9fdcd73044f78840f2732809a0de710
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760518"
---
# <a name="azure-microsoft-prefixed-azure-integration-packages-removed"></a><span data-ttu-id="821b3-103">Azure: pacotes de integração do Azure prefixados da Microsoft removidos</span><span class="sxs-lookup"><span data-stu-id="821b3-103">Azure: Microsoft-prefixed Azure integration packages removed</span></span>

<span data-ttu-id="821b3-104">Os pacotes a seguir `Microsoft.*` que fornecem integração entre ASP.NET Core e SDKs do Azure não estão incluídos no ASP.NET Core 5,0:</span><span class="sxs-lookup"><span data-stu-id="821b3-104">The following `Microsoft.*` packages that provide integration between ASP.NET Core and Azure SDKs aren't included in ASP.NET Core 5.0:</span></span>

* <span data-ttu-id="821b3-105">[Microsoft.Extensions.Configuração. AzureKeyVault](https://www.nuget.org/packages/Microsoft.Extensions.Configuration.AzureKeyVault/), que integra [Azure Key Vault](/azure/key-vault/) ao sistema de [configuração](/aspnet/core/fundamentals/configuration/).</span><span class="sxs-lookup"><span data-stu-id="821b3-105">[Microsoft.Extensions.Configuration.AzureKeyVault](https://www.nuget.org/packages/Microsoft.Extensions.Configuration.AzureKeyVault/), which integrates [Azure Key Vault](/azure/key-vault/) into the [Configuration system](/aspnet/core/fundamentals/configuration/).</span></span>
* <span data-ttu-id="821b3-106">[Microsoft. AspNetCore. dataprotection. AzureKeyVault](https://www.nuget.org/packages/Microsoft.AspNetCore.DataProtection.AzureKeyVault/), que integra Azure Key Vault ao [sistema de proteção de dados ASP.NET Core](/aspnet/core/security/data-protection/introduction).</span><span class="sxs-lookup"><span data-stu-id="821b3-106">[Microsoft.AspNetCore.DataProtection.AzureKeyVault](https://www.nuget.org/packages/Microsoft.AspNetCore.DataProtection.AzureKeyVault/), which integrates Azure Key Vault into the [ASP.NET Core Data Protection system](/aspnet/core/security/data-protection/introduction).</span></span>
* <span data-ttu-id="821b3-107">[Microsoft. AspNetCore. dataprotection. AzureStorage](https://www.nuget.org/packages/Microsoft.AspNetCore.DataProtection.AzureStorage/), que integra o [armazenamento de BLOBs do Azure](/azure/storage/blobs/) ao sistema de proteção de dados ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="821b3-107">[Microsoft.AspNetCore.DataProtection.AzureStorage](https://www.nuget.org/packages/Microsoft.AspNetCore.DataProtection.AzureStorage/), which integrates [Azure Blob Storage](/azure/storage/blobs/) into the ASP.NET Core Data Protection system.</span></span>

<span data-ttu-id="821b3-108">Para obter uma discussão sobre esse problema, consulte [dotnet/aspnetcore # 19570](https://github.com/dotnet/aspnetcore/issues/19570).</span><span class="sxs-lookup"><span data-stu-id="821b3-108">For discussion on this issue, see [dotnet/aspnetcore#19570](https://github.com/dotnet/aspnetcore/issues/19570).</span></span>

## <a name="version-introduced"></a><span data-ttu-id="821b3-109">Versão introduzida</span><span class="sxs-lookup"><span data-stu-id="821b3-109">Version introduced</span></span>

<span data-ttu-id="821b3-110">5,0 visualização 1</span><span class="sxs-lookup"><span data-stu-id="821b3-110">5.0 Preview 1</span></span>

## <a name="old-behavior"></a><span data-ttu-id="821b3-111">Comportamento antigo</span><span class="sxs-lookup"><span data-stu-id="821b3-111">Old behavior</span></span>

<span data-ttu-id="821b3-112">Os `Microsoft.*` pacotes integraram os serviços do Azure com as APIs de proteção de dados e configuração.</span><span class="sxs-lookup"><span data-stu-id="821b3-112">The `Microsoft.*` packages integrated Azure services with the Configuration and Data Protection APIs.</span></span>

## <a name="new-behavior"></a><span data-ttu-id="821b3-113">Novo comportamento</span><span class="sxs-lookup"><span data-stu-id="821b3-113">New behavior</span></span>

<span data-ttu-id="821b3-114">Novos `Azure.*` pacotes integram os serviços do Azure com as APIs de configuração e proteção de dados.</span><span class="sxs-lookup"><span data-stu-id="821b3-114">New `Azure.*` packages integrate Azure services with the Configuration and Data Protection APIs.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="821b3-115">Motivo da alteração</span><span class="sxs-lookup"><span data-stu-id="821b3-115">Reason for change</span></span>

<span data-ttu-id="821b3-116">A alteração foi feita porque os `Microsoft.*` pacotes foram:</span><span class="sxs-lookup"><span data-stu-id="821b3-116">The change was made because the `Microsoft.*` packages were:</span></span>

* <span data-ttu-id="821b3-117">Usando versões desatualizadas do SDK do Azure.</span><span class="sxs-lookup"><span data-stu-id="821b3-117">Using outdated versions of the Azure SDK.</span></span> <span data-ttu-id="821b3-118">Atualizações simples não eram possíveis porque as novas versões do SDK do Azure incluíram alterações significativas.</span><span class="sxs-lookup"><span data-stu-id="821b3-118">Simple updates weren't possible because the new versions of the Azure SDK included breaking changes.</span></span>
* <span data-ttu-id="821b3-119">Vinculado à agenda de lançamento do .NET Core.</span><span class="sxs-lookup"><span data-stu-id="821b3-119">Tied to the .NET Core release schedule.</span></span> <span data-ttu-id="821b3-120">A transferência da propriedade dos pacotes para a equipe do SDK do Azure habilita atualizações de pacote à medida que o SDK do Azure é atualizado.</span><span class="sxs-lookup"><span data-stu-id="821b3-120">Transferring ownership of the packages to the Azure SDK team enables package updates as the Azure SDK is updated.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="821b3-121">Ação recomendada</span><span class="sxs-lookup"><span data-stu-id="821b3-121">Recommended action</span></span>

<span data-ttu-id="821b3-122">Nos projetos ASP.NET Core 2,1 ou posteriores, substitua o antigo `Microsoft.*` pelos novos `Azure.*` pacotes.</span><span class="sxs-lookup"><span data-stu-id="821b3-122">In ASP.NET Core 2.1 or later projects, replace the old `Microsoft.*` with the new `Azure.*` packages.</span></span>

| <span data-ttu-id="821b3-123">Antigo</span><span class="sxs-lookup"><span data-stu-id="821b3-123">Old</span></span> | <span data-ttu-id="821b3-124">Novo</span><span class="sxs-lookup"><span data-stu-id="821b3-124">New</span></span> |
|--|--|
| `Microsoft.AspNetCore.DataProtection.AzureKeyVault` | [<span data-ttu-id="821b3-125">Azure. Extensions. AspNetCore. dataprotection. Keys</span><span class="sxs-lookup"><span data-stu-id="821b3-125">Azure.Extensions.AspNetCore.DataProtection.Keys</span></span>](https://www.nuget.org/packages/Azure.Extensions.AspNetCore.DataProtection.Keys) |
| `Microsoft.AspNetCore.DataProtection.AzureStorage` | [<span data-ttu-id="821b3-126">Azure. Extensions. AspNetCore. dataprotection. BLOBs</span><span class="sxs-lookup"><span data-stu-id="821b3-126">Azure.Extensions.AspNetCore.DataProtection.Blobs</span></span>](https://www.nuget.org/packages/Azure.Extensions.AspNetCore.DataProtection.Blobs) |
| `Microsoft.Extensions.Configuration.AzureKeyVault` | [<span data-ttu-id="821b3-127">Azure.Extensions.AspNetCore.Configuração. Confidenciais</span><span class="sxs-lookup"><span data-stu-id="821b3-127">Azure.Extensions.AspNetCore.Configuration.Secrets</span></span>](https://www.nuget.org/packages/Azure.Extensions.AspNetCore.Configuration.Secrets) |

<span data-ttu-id="821b3-128">Os novos pacotes usam uma nova versão do SDK do Azure que inclui alterações significativas.</span><span class="sxs-lookup"><span data-stu-id="821b3-128">The new packages use a new version of the Azure SDK that includes breaking changes.</span></span> <span data-ttu-id="821b3-129">Os padrões de uso geral não são alterados.</span><span class="sxs-lookup"><span data-stu-id="821b3-129">The general usage patterns are unchanged.</span></span> <span data-ttu-id="821b3-130">Algumas sobrecargas e opções podem diferir para se adaptar às alterações nas APIs do SDK do Azure subjacentes.</span><span class="sxs-lookup"><span data-stu-id="821b3-130">Some overloads and options may differ to adapt to changes in the underlying Azure SDK APIs.</span></span>

<span data-ttu-id="821b3-131">Os pacotes antigos vão:</span><span class="sxs-lookup"><span data-stu-id="821b3-131">The old packages will:</span></span>

* <span data-ttu-id="821b3-132">Ter suporte da equipe de ASP.NET Core pelo tempo de vida do .NET Core 2,1 e 3,1.</span><span class="sxs-lookup"><span data-stu-id="821b3-132">Be supported by the ASP.NET Core team for the lifetime of .NET Core 2.1 and 3.1.</span></span>
* <span data-ttu-id="821b3-133">Não ser incluído no .NET 5.</span><span class="sxs-lookup"><span data-stu-id="821b3-133">Not be included in .NET 5.</span></span>

<span data-ttu-id="821b3-134">Ao atualizar seu projeto para o .NET 5, migre para os `Azure.*` pacotes para manter o suporte.</span><span class="sxs-lookup"><span data-stu-id="821b3-134">When upgrading your project to .NET 5, transition to the `Azure.*` packages to maintain support.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="821b3-135">APIs afetadas</span><span class="sxs-lookup"><span data-stu-id="821b3-135">Affected APIs</span></span>

- <xref:Microsoft.Extensions.Configuration.AzureKeyVaultConfigurationExtensions.AddAzureKeyVault%2A?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.DataProtection.AzureDataProtectionBuilderExtensions.ProtectKeysWithAzureKeyVault%2A?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.DataProtection.AzureDataProtectionBuilderExtensions.PersistKeysToAzureBlobStorage%2A?displayProperty=nameWithType>

<!--

### Category

ASP.NET Core

### Affected APIs

- `Overload:Microsoft.Extensions.Configuration.AzureKeyVaultConfigurationExtensions.AddAzureKeyVault`
- `Overload:Microsoft.AspNetCore.DataProtection.AzureDataProtectionBuilderExtensions.ProtectKeysWithAzureKeyVault`
- `Overload:Microsoft.AspNetCore.DataProtection.AzureDataProtectionBuilderExtensions.PersistKeysToAzureBlobStorage`

-->