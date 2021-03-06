---
title: Método ICorDebugILFrame::EnumerateArguments
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame.EnumerateArguments
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame::EnumerateArguments
helpviewer_keywords:
- ICorDebugILFrame::EnumerateArguments method [.NET Framework debugging]
- EnumerateArguments method [.NET Framework debugging]
ms.assetid: 00ac81e2-a774-422a-bd88-54a4b3c99f73
topic_type:
- apiref
ms.openlocfilehash: 9b0bc59b67b5d4b2184733f22616433bf33be616
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95703220"
---
# <a name="icordebugilframeenumeratearguments-method"></a>Método ICorDebugILFrame::EnumerateArguments

Obtém um enumerador para os argumentos neste quadro.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
HRESULT EnumerateArguments (  
    [out] ICorDebugValueEnum    **ppValueEnum  
);  
```  
  
## <a name="parameters"></a>Parâmetros  

 `ppValueEnum`  
 fora Um ponteiro para o endereço de um objeto ICorDebugValueEnum que é o enumerador para os argumentos neste quadro.  
  
## <a name="remarks"></a>Comentários  

 `EnumerateArguments` Obtém um enumerador que pode listar os argumentos disponíveis no quadro de chamada que é representado por esse objeto ICorDebugILFrame. A lista incluirá argumentos que são [vararg](/cpp/windows/vararg) (ou seja, um número variável de argumentos), bem como argumentos que não são `vararg` .  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
