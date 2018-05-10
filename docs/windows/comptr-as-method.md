---
title: ComPtr::As yöntemi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::ComPtr::As
dev_langs:
- C++
helpviewer_keywords:
- As method
ms.assetid: 2ad6c262-9bdb-4c59-a330-1af8bcd445cc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: fb9fd0ff09f6775a95ff881d9f8cbaa3edc61065
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
---
# <a name="comptras-method"></a>ComPtr::As Yöntemi
Belirtilen şablon parametresi tarafından tanımlanan arabirimi temsil eden bir ComPtr nesnesi döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
template<typename U>  
HRESULT As(  
   _Out_ ComPtr<U>* p  
) const;  
  
template<typename U>  
HRESULT As(  
   _Out_ Details::ComPtrRef<ComPtr<U>> p  
) const;  
  
```  
  
#### <a name="parameters"></a>Parametreler  
 `U`  
 Parametresi tarafından gösterilemeyecek kadar arabirimi `p`.  
  
 `p`  
 Parametresi tarafından belirtilen arabirimi temsil eden bir ComPtr nesnesi `U`. Parametre `p` geçerli ComPtr nesnesine başvurmadığından gerekir.  
  
## <a name="remarks"></a>Açıklamalar  
 İlk şablon kodunuzda kullanması gereken biçimidir. C++ dil özellikleri gibi destekleyen bir iç, yardımcı uzmanlık ikinci şablonudur [otomatik](../cpp/auto-cpp.md) kesintisi anahtar sözcüğü yazın.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa S_OK; Aksi takdirde, HRESULT hata gösterir.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** client.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ComPtr Sınıfı](../windows/comptr-class.md)