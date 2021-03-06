---
title: Método ICorDebugType::GetType
ms.date: 03/30/2017
api_name:
- ICorDebugType.GetType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::GetType
helpviewer_keywords:
- ICorDebugType::GetType method [.NET Framework debugging]
- GetType method, ICorDebugType interface [.NET Framework debugging]
ms.assetid: d6e64534-4d47-4ad0-a340-7590e07e2b4a
topic_type:
- apiref
ms.openlocfilehash: f0f45d5f0b2ea8cefa6bd36e909ae43d80c968ed
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95700880"
---
# <a name="icordebugtypegettype-method"></a>Método ICorDebugType::GetType

Obtém um valor de CorElementType que descreve o tipo nativo do Common Language Runtime (CLR) <xref:System.Type> representado por esse ICorDebugType.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
HRESULT GetType (  
    [out] CorElementType   *ty  
);  
```  
  
## <a name="parameters"></a>Parâmetros  

 `ty`  
 fora Um ponteiro para um valor da `CorElementType` enumeração que indica o CLR <xref:System.Type> que isso `ICorDebugType` representa.  
  
## <a name="remarks"></a>Comentários  

 Se o valor de `ty` for ELEMENT_TYPE_CLASS ou ELEMENT_TYPE_VALUETYPE, o método [ICorDebugType:: GetClass](icordebugtype-getclass-method.md) poderá ser chamado para obter o tipo não instanciado para um tipo genérico; caso contrário, não chame `ICorDebugType::GetClass` .  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
