---
title: 'Alteração significativa: middleware: o middleware do manipulador de exceção lançará a exceção original se o manipulador não for encontrado'
description: 'Saiba mais sobre a alteração significativa no ASP.NET Core 5,0 intitulado middleware: o middleware do manipulador de exceção lança uma exceção original se o manipulador não for encontrado'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: 8801d3e6950d66fd9f24e051fd8729c50eb0b282
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760514"
---
# <a name="middleware-exception-handler-middleware-throws-original-exception-if-handler-not-found"></a>Middleware: o middleware do manipulador de exceção lança a exceção original se o manipulador não for encontrado

Antes de ASP.NET Core 5,0, o [middleware do manipulador de exceção](xref:Microsoft.AspNetCore.Builder.ExceptionHandlerExtensions.UseExceptionHandler%2A) executa o manipulador de exceção configurado quando uma exceção ocorreu. Se o manipulador de exceção, configurado via <xref:Microsoft.AspNetCore.Builder.ExceptionHandlerOptions.ExceptionHandlingPath> , não puder ser encontrado, uma resposta HTTP 404 será produzida. A resposta é enganosa, pois:

* Parece ser um erro de usuário.
* Obscurece o fato de que uma exceção ocorreu no servidor.

Para resolver o erro enganoso no ASP.NET Core 5,0, o `ExceptionHandlerMiddleware` lançará a exceção original se o manipulador de exceção não puder ser encontrado. Como resultado, uma resposta HTTP 500 é produzida pelo servidor. A resposta será mais fácil de examinar nos logs do servidor ao depurar o erro ocorrido.

Para obter uma discussão, consulte o problema do GitHub [dotnet/aspnetcore # 25288](https://github.com/dotnet/aspnetcore/issues/25288).

## <a name="version-introduced"></a>Versão introduzida

5,0 RC 1

## <a name="old-behavior"></a>Comportamento antigo

O middleware do manipulador de exceção produz uma resposta HTTP 404 se o manipulador de exceção configurado não puder ser encontrado.

## <a name="new-behavior"></a>Novo comportamento

O middleware do manipulador de exceção lançará a exceção original se o manipulador de exceção configurado não puder ser encontrado.

## <a name="reason-for-change"></a>Motivo da alteração

O erro HTTP 404 não torna óbvio que ocorreu uma exceção no servidor. Essa alteração produz um erro HTTP 500 para deixá-lo óbvio que:

* O problema não é causado por um erro do usuário.
* Exceção encontrada no servidor.

## <a name="recommended-action"></a>Ação recomendada

Não há nenhuma alteração de API. Todos os aplicativos existentes continuarão a ser compilados e executados. A exceção gerada é tratada pelo servidor. Por exemplo, a exceção é convertida em uma resposta de erro HTTP 500 por [Kestrel](/aspnet/core/fundamentals/servers/kestrel) ou [HTTP.sys](/aspnet/core/fundamentals/servers/httpsys).

## <a name="affected-apis"></a>APIs afetadas

Nenhum

<!--

### Category

ASP.NET Core

### Affected APIs

Not detectable via API analysis

-->
