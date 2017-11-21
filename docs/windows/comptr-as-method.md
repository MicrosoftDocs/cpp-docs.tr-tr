---
title: "ComPtr::As yöntemi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: client/Microsoft::WRL::ComPtr::As
dev_langs: C++
helpviewer_keywords: As method
ms.assetid: 2ad6c262-9bdb-4c59-a330-1af8bcd445cc
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: e12869710694083bb0608f158c91e14df36b9ed9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="comptras-method"></a>ComPtr::As Yöntemi
Belirtilen şablon parametresi tarafından tanımlanan arabirimi temsil eden bir ComPtr nesnesi döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
template<  
   typename U  
>  
HRESULT As(  
   _Out_ ComPtr<U>* p  
) const;  
  
template<  
   typename U  
>  
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
 [ComPtr sınıfı](../windows/comptr-class.md)