---
title: Estrutura BucketParameters
ms.date: 03/30/2017
api_name:
- BucketParameters
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- BucketParameters
helpviewer_keywords:
- BucketParameters structure [.NET Framework hosting]
ms.assetid: 9432487e-f276-45d6-9a13-9a68024dbd46
topic_type:
- apiref
ms.openlocfilehash: 8b54cb30ec96ad0fb7851af6f2d465fe771886ac
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95677842"
---
# <a name="bucketparameters-structure"></a>Estrutura BucketParameters

Armazena o nome de tipo de um evento e os parâmetros para a exceção atual associada ao evento.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
typedef struct _BucketParameters {  
    BOOL  fInited;
    WCHAR pszEventTypeName[255];
    WCHAR pszParams[10][255];
} BucketParameters;  
```  
  
## <a name="members"></a>Membros  
  
|Membro|DESCRIÇÃO|  
|------------|-----------------|  
|`fInited`|`true`, se o restante desta estrutura for válido; caso contrário, `false` .|  
|`pszEventTypeName`|Nome do tipo de evento.|  
|`pszParams`|Uma matriz de cadeias de caracteres, cada uma delas especifica um parâmetro para a exceção atual associada ao evento.|  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** MSCorEE. idl  
  
 **.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Confira também

- [Estruturas de hospedagem](hosting-structures.md)
