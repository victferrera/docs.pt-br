---
title: Método ICorProfilerCallback4::ReJITError
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback4.ReJITError
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback4::ReJITError
helpviewer_keywords:
- ReJITError method, ICorProfilerCallback4 interface [.NET Framework profiling]
- ICorProfilerCallback4::ReJITError method [.NET Framework profiling]
ms.assetid: d7888aa9-dfaa-420f-9f99-e06ab35ca482
topic_type:
- apiref
ms.openlocfilehash: 46312aaf530e69f0e6a90e35515f1373d01b4340
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730234"
---
# <a name="icorprofilercallback4rejiterror-method"></a>Método ICorProfilerCallback4::ReJITError

Notifica o criador de perfil de que o compilador JIT (just-in-time) encontrou um erro no processo de recompilação.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
HRESULT ReJITError(  
    [in] ModuleID    moduleId,  
    [in] mdMethodDef methodId,  
    [in] FunctionID  functionId,  
    [in] HRESULT     hrStatus);  
```  
  
## <a name="parameters"></a>Parâmetros  

 `moduleID`  
 no O `ModuleID` em que foi feita a tentativa de recompilação com falha.  
  
 `methodId`  
 no O `MethodDef` do método em que a tentativa de recompilação com falha foi feita.  
  
 `functionId`  
 no A instância de função que está sendo recompilada ou marcada para recompilação. Esse valor pode ser `NULL` se a falha ocorrer em uma base por método, em vez de uma base por instanciação (por exemplo, se o criador de perfil especificou um token de metadados inválido para o método a ser recompilado).  
  
 `hrStatus`  
 no Um HRESULT que indica a natureza da falha. Consulte a seção status HRESULTs para obter uma lista de valores.  
  
## <a name="return-value"></a>Valor Retornado  

 Os valores retornados desse retorno de chamada são ignorados.  
  
## <a name="status-hresults"></a>Status HRESULTs  
  
|Matriz de status HRESULT|DESCRIÇÃO|  
|--------------------------|-----------------|  
|E_INVALIDARG|O `moduleID` `methodDef` token ou é `NULL` .|  
|CORPROF_E_DATAINCOMPLETE|O módulo ainda não está totalmente carregado ou está em processo de descarregamento.|  
|CORPROF_E_MODULE_IS_DYNAMIC|O módulo especificado foi gerado dinamicamente (por exemplo, por `Reflection.Emit` ) e, portanto, não é suportado por esse método.|  
|CORPROF_E_FUNCTION_IS_COLLECTIBLE|O método é instanciado em um assembly de coleção e, portanto, não pode ser recompilado. Observe que os tipos e funções definidos em um contexto não-reflexão (por exemplo, `List<MyCollectibleStruct>` ) podem ser instanciados em um assembly de coleção.|  
|E_OUTOFMEMORY|O CLR ficou sem memória ao tentar marcar o método especificado para recompilação JIT.|  
|Outros|O sistema operacional retornou uma falha fora do controle do CLR. Por exemplo, se uma chamada do sistema para alterar a proteção de acesso de uma página de memória falhar, o erro do sistema operacional será exibido.|  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** CorProf. idl, CorProf. h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versões:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Confira também

- [Interface ICorProfilerCallback](icorprofilercallback-interface.md)
- [Interface ICorProfilerCallback4](icorprofilercallback4-interface.md)
