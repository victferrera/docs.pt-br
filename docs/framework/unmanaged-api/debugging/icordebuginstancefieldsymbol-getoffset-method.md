---
title: 'Método ICorDebugInstanceFieldSymbol:: GetOffset'
ms.date: 03/30/2017
ms.assetid: 7e470150-2b92-4425-989c-315f48964fd2
ms.openlocfilehash: 2d73de46bbb1023f20dd9023076630611c74be5d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724917"
---
# <a name="icordebuginstancefieldsymbolgetoffset-method"></a>Método ICorDebugInstanceFieldSymbol:: GetOffset

Obtém o deslocamento em bytes deste campo de instância em sua classe pai.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
HRESULT GetOffset(  
   [out] ULONG32 *pcbOffset  
);  
```  
  
## <a name="parameters"></a>Parâmetros  

 `pcbOffset`  
 Um ponteiro para o número de bytes que esse campo de instância é deslocado em sua classe pai.  
  
## <a name="remarks"></a>Comentários  
  
> [!NOTE]
> Esse método está disponível somente com .NET Native.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versões:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Confira também

- [Interface ICorDebugInstanceFieldSymbol](icordebuginstancefieldsymbol-interface.md)
- [Depurando interfaces](debugging-interfaces.md)
