---
title: Método INotifySink2::OnSyncCallOut
ms.date: 03/30/2017
api_name:
- INotifySink2.OnSyncCallOut
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- INotifySink2::OnSyncCallOut
helpviewer_keywords:
- INotifySink2::OnSyncCallOut method [.NET Framework debugging]
- OnSyncCallOut method [.NET Framework debugging]
ms.assetid: 97f15656-8677-4079-8553-a1d8603355d6
topic_type:
- apiref
ms.openlocfilehash: 00f6032f41caf54d7366de30a449f1ae76e8bbd0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719977"
---
# <a name="inotifysink2onsynccallout-method"></a>Método INotifySink2::OnSyncCallOut

É invocado quando uma chamada está fora.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
HRESULT OnSyncCallOut  
(  
    [in]  CALL_ID  in_CallID,  
    [out, size_is(, *out_pBufferSize)] BYTE**  out_ppBuffer,  
    [out] DWORD*   out_pBufferSize  
);  
```  
  
## <a name="parameters"></a>Parâmetros  

 `in_CallID`  
 no ID da chamada que está fora. Consulte [estrutura de CALL_ID](call-id-structure.md).  
  
 `out_ppBuffer`  
 fora Buffer de chamadas.  
  
 `out_pBufferSize`  
 fora Tamanho do buffer de chamada, em bytes.  
  
## <a name="return-value"></a>Valor Retornado  

 S_OK se o método tiver sucesso.  
  
## <a name="requirements"></a>Requisitos  

 **Cabeçalho:** ProtocolNotify2. idl  
  
## <a name="see-also"></a>Confira também

- [Interface INotifySink2](inotifysink2-interface.md)
- [Interface INotifySource2](inotifysource2-interface.md)
- [Interface INotifyConnection2](inotifyconnection2-interface.md)
