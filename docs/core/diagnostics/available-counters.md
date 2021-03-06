---
title: EventCounters bem conhecido no .NET
description: Examine o EventCounters publicado pelo tempo de execução e pelas bibliotecas do .NET.
ms.topic: reference
ms.date: 12/17/2020
ms.openlocfilehash: 724e49ba616a7f656d629a0443ec5e322a51d6f5
ms.sourcegitcommit: 4b79862c5b41fbd86cf38f926f6a49516059f6f2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/18/2020
ms.locfileid: "97681956"
---
# <a name="well-known-eventcounters-in-net"></a>EventCounters bem conhecido no .NET

O tempo de execução e as bibliotecas do .NET implementam e publicam várias [`EventCounter`](./event-counters.md) que podem ser usadas para identificar e diagnosticar vários problemas de desempenho. Este documento é uma referência nos provedores que podem ser usados para monitorá-los `EventCounters` e suas descrições.

## <a name="systemruntime-counters"></a>Contadores System. Runtime

Os contadores a seguir são publicados como parte do tempo de execução do .NET (CoreCLR) e são mantidos no [`RuntimeEventSource.cs`](https://github.com/dotnet/coreclr/blob/master/src/System.Private.CoreLib/src/System/Diagnostics/Eventing/RuntimeEventSource.cs) .

| Contador | Descrição |
|--|--|
| :::no-loc text="% Time in GC since last GC"::: (`time-in-gc`) | A porcentagem de tempo no GC desde o último GC |
| :::no-loc text="Allocation Rate"::: (`alloc-rate`) | O número de bytes alocados por intervalo de atualização |
| :::no-loc text="CPU Usage"::: (`cpu-usage`) | A porcentagem de uso da CPU do processo |
| :::no-loc text="Exception Count"::: (`exception-count`) | O número de exceções que ocorreram |
| :::no-loc text="GC Heap Size"::: (`gc-heap-size`) | O número de bytes considerados alocados com base em <xref:System.GC.GetTotalMemory(System.Boolean)?displayProperty=nameWithType> |
| :::no-loc text="Gen 0 GC Count"::: (`gen-0-gc-count`) | O número de vezes que GC ocorreu para Gen 0 por intervalo de atualização |
| :::no-loc text="Gen 0 Size"::: (`gen-0-size`) | O número de bytes para Gen 0 GC |
| :::no-loc text="Gen 1 GC Count"::: (`gen-1-gc-count`) | O número de vezes que GC ocorreu para Gen 1 por intervalo de atualização |
| :::no-loc text="Gen 1 Size"::: (`gen-1-size`) | O número de bytes para Gen 1 GC |
| :::no-loc text="Gen 2 GC Count"::: (`gen-2-gc-count`) | O número de vezes que GC ocorreu para Gen 2 por intervalo de atualização |
| :::no-loc text="Gen 2 Size"::: (`gen-2-size`) | O número de bytes para Gen 2 GC |
| :::no-loc text="LOH Size"::: (`loh-size`) | O número de bytes para o heap de objeto grande |
| :::no-loc text="POH Size"::: (`poh-size`) | O número de bytes para o heap de objeto fixado (disponível no .NET 5 e versões posteriores) |
| :::no-loc text="GC Fragmentation"::: (`gc-fragmentation`) | A fragmentação do heap de GC (disponível no .NET 5 e versões posteriores) |
| :::no-loc text="Monitor Lock Contention Count"::: (`monitor-lock-contention-count`) | O número de vezes que houve contenção ao tentar usar o bloqueio do monitor, com base em <xref:System.Threading.Monitor.LockContentionCount?displayProperty=nameWithType> |
| :::no-loc text="Number of Active Timers"::: (`active-timer-count`) | O número de <xref:System.Threading.Timer> instâncias atualmente ativas, com base em <xref:System.Threading.Timer.ActiveCount?displayProperty=nameWithType> |
| :::no-loc text="Number of Assemblies Loaded"::: (`assembly-count`) | O número de <xref:System.Reflection.Assembly> instâncias carregadas em um processo em um ponto no tempo |
| :::no-loc text="ThreadPool Completed Work Item Count"::: (`threadpool-completed-items-count`) | O número de itens de trabalho que foram processados até o momento no <xref:System.Threading.ThreadPool> |
| :::no-loc text="ThreadPool Queue Length"::: (`threadpool-queue-length`) | O número de itens de trabalho que estão enfileirados no momento para serem processados no <xref:System.Threading.ThreadPool> |
| :::no-loc text="ThreadPool Thread Count"::: (`threadpool-thread-count`) | O número de threads do pool de threads que existem atualmente no <xref:System.Threading.ThreadPool> , com base em <xref:System.Threading.ThreadPool.ThreadCount?displayProperty=nameWithType> |
| :::no-loc text="Working Set"::: (`working-set`) | A quantidade de memória física mapeada para o contexto do processo em uma base pontual em <xref:System.Environment.WorkingSet?displayProperty=nameWithType> |
| :::no-loc text="IL Bytes Jitted"::: (`il-bytes-jitted`) | O tamanho total do ILs que são compilados em JIT, em bytes (disponíveis no .NET 5 e em versões posteriores) |
| :::no-loc text="Method Jitted Count"::: (`method-jitted-count`) | O número de métodos compilados por JIT (disponíveis no .NET 5 e versões posteriores) |

## <a name="microsoftaspnetcorehosting-counters"></a>Contadores "Microsoft. AspNetCore. Hosting"

Os contadores a seguir são publicados como parte do [ASP.NET Core](/aspnet/core) e são mantidos no [`HostingEventSource.cs`](https://github.com/dotnet/aspnetcore/blob/master/src/Hosting/Hosting/src/Internal/HostingEventSource.cs) .

| Contador | Descrição |
|--|--|
| :::no-loc text="Current Requests"::: (`current-requests`) | O número total de solicitações que foram iniciadas, mas ainda não foram interrompidas |
| :::no-loc text="Failed Requests"::: (`failed-requests`) | O número total de solicitações com falha ocorridas durante a vida útil do aplicativo |
| :::no-loc text="Request Rate"::: (`requests-per-second`) | O número de solicitações que ocorrem por intervalo de atualização |
| :::no-loc text="Total Requests"::: (`total-requests`) | O número total de solicitações que ocorreram durante a vida útil do aplicativo |

## <a name="microsoftaspnetcorehttpconnections-counters"></a>Contadores "Microsoft. AspNetCore. http. Connections"

Os contadores a seguir são publicados como parte do [ASP.NET Core signalr](/aspnet/core/signalr/introduction) e são mantidos no [`HttpConnectionsEventSource.cs`](https://github.com/dotnet/aspnetcore/blob/master/src/SignalR/common/Http.Connections/src/Internal/HttpConnectionsEventSource.cs) .

| Contador | Descrição |
|--|--|
| :::no-loc text="Average Connection Duration"::: (`connections-duration`) | A duração média de uma conexão em milissegundos |
| :::no-loc text="Current Connections"::: (`current-connections`) | O número de conexões ativas que foram iniciadas, mas ainda não foram interrompidas |
| :::no-loc text="Total Connections Started"::: (`connections-started`) | O número total de conexões que foram iniciadas |
| :::no-loc text="Total Connections Stopped"::: (`connections-stopped`) | O número total de conexões que foram interrompidas |
| :::no-loc text="Total Connections Timed Out"::: (`connections-timed-out`) | O número total de conexões que atingiram o tempo limite |

## <a name="microsoft-aspnetcore-server-kestrel-counters"></a>Contadores "Microsoft-AspNetCore-Server-Kestrel"

Os contadores a seguir são publicados como parte do [servidor web ASP.NET Core Kestrel](/aspnet/core/fundamentals/servers/kestrel) e são mantidos no [`KestrelEventSource.cs`](https://github.com/dotnet/aspnetcore/blob/master/src/Servers/Kestrel/Core/src/Internal/Infrastructure/KestrelEventSource.cs) .

| Contador | Descrição |
|--|--|
| :::no-loc text="Connection Queue Length"::: (`connection-queue-length`) | O comprimento atual da fila de conexão |
| :::no-loc text="Connection Rate"::: (`connections-per-second`) | O número de conexões por intervalo de atualização para o servidor Web |
| :::no-loc text="Current Connections"::: (`current-connections`) | O número atual de conexões ativas com o servidor Web |
| :::no-loc text="Current TLS Handshakes"::: (`current-tls-handshakes`) | O número atual de Handshakes TLS |
| :::no-loc text="Current Upgraded Requests (WebSockets)"::: (`current-upgraded-requests`) | O número atual de solicitações atualizadas (WebSockets) |
| :::no-loc text="Failed TLS Handshakes"::: (`failed-tls-handshakes`) | O número total de Handshakes de TLS com falha |
| :::no-loc text="Request Queue Length"::: (`request-queue-length`) | O comprimento atual da fila de solicitações |
| :::no-loc text="TLS Handshake Rate"::: (`tls-handshakes-per-second`) | O número de Handshakes TLS por intervalo de atualização |
| :::no-loc text="Total Connections"::: (`total-connections`) | O número total de conexões com o servidor Web |
| :::no-loc text="Total TLS Handshakes"::: (`total-tls-handshakes`) | O número total de Handshakes TLS com o servidor Web |
