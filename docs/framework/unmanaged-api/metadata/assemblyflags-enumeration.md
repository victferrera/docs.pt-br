---
title: Enumeração AssemblyFlags
ms.date: 03/30/2017
api_name:
- AssemblyFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- AssemblyFlags
helpviewer_keywords:
- AssemblyFlags enumeration [.NET Framework metadata]
ms.assetid: 40f9bd9e-16ec-447e-81b0-168c875e9866
topic_type:
- apiref
ms.openlocfilehash: 561b4d68a574a2859286fb5f2e2d950518a9d29d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732769"
---
# <a name="assemblyflags-enumeration"></a>Enumeração AssemblyFlags

Contém valores que descrevem os recursos de tempo de execução de um assembly.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
typedef enum {  
    afImplicitExportedTypes = 0x0001,  
    afImplicitResources = 0x0002,  
    afNonSideBySideAppDomain = 0x0010,  
    afNonSideBySideProcess = 0x0020,  
    afNonSideBySideMachine = 0x0030  
} AssemblyFlags;  
```  
  
## <a name="members"></a>Membros  
  
|Membro|DESCRIÇÃO|  
|------------|-----------------|  
|`afImplicitExportedTypes`|Especifica que as definições de tipo exportadas são implícitas dentro dos arquivos que compõem o assembly. No .NET Framework versões 1,0 e 1,1, esse valor é sempre considerado definido.|  
|`afImplicitResources`|Especifica que as definições de recursos são implícitas dentro dos arquivos que compõem o assembly. No .NET Framework 1,0 e 1,1, esse valor é sempre considerado definido.|  
|`afNonSideBySideAppDomain`|Especifica que o assembly não pode ser executado com outras versões se estiverem em execução no mesmo domínio de aplicativo.|  
|`afNonSideBySideProcess`|Especifica que o assembly não pode ser executado com outras versões se estiverem em execução no mesmo processo.|  
|`afNonSideBySideMachine`|Especifica que o assembly não pode ser executado com outras versões se estiverem em execução no mesmo computador.|  
  
## <a name="remarks"></a>Comentários  

 Os valores entre 0x0010 e 0x0070, inclusive, são usados para descrever os recursos de compatibilidade lado a lado do assembly referenciado. Se nenhum desses valores for definido, o assembly será considerado compatível lado a lado.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** MsCorEE. h  
  
 **Biblioteca:** Incluído como um recurso no MsCorEE.dll  
  
 **.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Confira também

- [Enumerações de metadados](metadata-enumerations.md)
- [Interface IMetaDataAssemblyEmit](imetadataassemblyemit-interface.md)
