---
title: Método ICLRStrongName::StrongNameTokenFromPublicKey
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameTokenFromPublicKey
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameTokenFromPublicKey
helpviewer_keywords:
- ICLRStrongName::StrongNameTokenFromPublicKey method [.NET Framework hosting]
- StrongNameTokenFromPublicKey method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 7962ce88-7e86-4a6f-8298-621b01ffc3c2
topic_type:
- apiref
ms.openlocfilehash: c727d4524bc40ab90eee90faf16788140a73ad9a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95677655"
---
# <a name="iclrstrongnamestrongnametokenfrompublickey-method"></a>Método ICLRStrongName::StrongNameTokenFromPublicKey

Obtém um token que representa uma chave pública. Um token de nome forte é a forma abreviada de uma chave pública.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
HRESULT StrongNameTokenFromPublicKey (
    [in]  BYTE    *pbPublicKeyBlob,  
    [in]  ULONG   cbPublicKeyBlob,  
    [out] BYTE    **ppbStrongNameToken,  
    [out] ULONG   *pcbStrongNameToken  
);  
```  
  
## <a name="parameters"></a>Parâmetros  

 `pbPublicKeyBlob`  
 no Uma estrutura do tipo [PublicKeyBlob](../strong-naming/publickeyblob-structure.md) que contém a parte pública do par de chaves usado para gerar a assinatura de nome forte.  
  
 `cbPublicKeyBlob`  
 no O tamanho, em bytes, de `pbPublicKeyBlob` .  
  
 `ppbStrongNameToken`  
 fora O token de nome forte correspondente à chave passada `pbPublicKeyBlob` . O Common Language Runtime aloca a memória na qual retornar o token. O chamador deve liberar essa memória usando o método [ICLRStrongName:: StrongNameFreeBuffer](iclrstrongname-strongnamefreebuffer-method.md) .  
  
 `pcbStrongNameToken`  
 fora O tamanho, em bytes, do token de nome forte retornado.  
  
## <a name="return-value"></a>Valor Retornado  

 `S_OK` Se o método foi concluído com êxito; caso contrário, um valor HRESULT que indica falha (consulte [valores de HRESULT comuns](/windows/win32/seccrypto/common-hresult-values) para uma lista).  
  
## <a name="remarks"></a>Comentários  

 Um token de nome forte é a forma abreviada de uma chave pública que é usada para economizar espaço ao armazenar informações de chave em metadados. Especificamente, tokens de nome forte são usados em referências de assembly para fazer referência ao assembly dependente.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** MetaHost. h  
  
 **Biblioteca:** Incluído como um recurso no mscoree.dll  
  
 **.NET Framework versões:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Confira também

- [Método StrongNameGetPublicKey](iclrstrongname-strongnamegetpublickey-method.md)
- [Estrutura PublicKeyBlob](../strong-naming/publickeyblob-structure.md)
- [Interface ICLRStrongName](iclrstrongname-interface.md)
