---
title: Método ICorDebugType::GetBase
ms.date: 03/30/2017
api_name:
- ICorDebugType.GetBase
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::GetBase
helpviewer_keywords:
- ICorDebugType::GetBase method [.NET Framework debugging]
- GetBase method [.NET Framework debugging]
ms.assetid: f24e1af9-c220-4f79-ae62-4153ec17ea81
topic_type:
- apiref
ms.openlocfilehash: 967f8f25e240f484ae86852c740be12cd3a6409e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95681815"
---
# <a name="icordebugtypegetbase-method"></a>Método ICorDebugType::GetBase

Obtém um ponteiro de interface para um ICorDebugType que representa o tipo base, se houver um, do tipo representado por este `ICorDebugType` .  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
HRESULT GetBase (  
    [out] ICorDebugType   **pBase  
);  
```  
  
## <a name="parameters"></a>Parâmetros  

 `pBase`  
 fora Um ponteiro para o endereço de um `ICorDebugType` objeto que representa o tipo base.  
  
## <a name="remarks"></a>Comentários  

 Pesquisar o tipo base de um tipo é útil para implementar a funcionalidade comum do depurador, como imprimir todos os campos de um objeto ou suas classes pai.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
