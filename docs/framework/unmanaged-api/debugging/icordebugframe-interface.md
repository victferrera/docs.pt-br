---
title: Interface ICorDebugFrame
ms.date: 03/30/2017
api_name:
- ICorDebugFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame
helpviewer_keywords:
- ICorDebugFrame interface [.NET Framework debugging]
ms.assetid: 0c48f764-3c64-4602-b2f4-4ffc60eb2c65
topic_type:
- apiref
ms.openlocfilehash: bdc17e2c6c63deae1420fe738eac51153f6b368e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726334"
---
# <a name="icordebugframe-interface"></a>Interface ICorDebugFrame

Representa um quadro na pilha atual.  
  
## <a name="methods"></a>Métodos  
  
|Método|DESCRIÇÃO|  
|------------|-----------------|  
|[Método CreateStepper](icordebugframe-createstepper-method.md)|Obtém um ICorDebugStepper para executar operações de depuração relativas a isso `ICorDebugFrame` .|  
|[Método GetCallee](icordebugframe-getcallee-method.md)|Obtém um ponteiro para o `ICorDebugFrame` na cadeia atual que este quadro chamou ou retorna NULL se esse for o quadro interno na cadeia.|  
|[Método GetCaller](icordebugframe-getcaller-method.md)|Obtém um ponteiro para o `ICorDebugFrame` na cadeia atual que chamou esse quadro ou retorna NULL se esse for o quadro mais externo na cadeia.|  
|[Método GetChain](icordebugframe-getchain-method.md)|Obtém um ponteiro para o ICorDebugChain que `ICorDebugFrame` faz parte de.|  
|[Método GetCode](icordebugframe-getcode-method.md)|Obtém um ponteiro para o ICorDebugCode associado a este quadro de pilhas.|  
|[Método GetFunction](icordebugframe-getfunction-method.md)|Obtém um ponteiro para o ICorDebugFunction que contém o código associado a esse quadro de pilhas.|  
|[Método GetFunctionToken](icordebugframe-getfunctiontoken-method.md)|Obtém o token de metadados para a função que contém o código associado a esse quadro de pilha.|  
|[Método GetStackRange](icordebugframe-getstackrange-method.md)|Obtém o intervalo de endereços absolutos do quadro de pilha representado por isso `ICorDebugFrame` .|  
  
## <a name="remarks"></a>Comentários  
  
> [!NOTE]
> Esta interface não dá suporte para chamada remota, seja entre computadores ou processos cruzados.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Confira também

- [Depurando interfaces](debugging-interfaces.md)
