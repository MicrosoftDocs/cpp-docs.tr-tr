---
title: "WeakRef::As yöntemi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: client/Microsoft::WRL::WeakRef::As
dev_langs: C++
helpviewer_keywords: As method
ms.assetid: 7173da62-b3fe-44d6-aea4-1aa97e69b221
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 5160cb93d6660eaf990856a58d5b9379e911125e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="weakrefas-method"></a>WeakRef::As Yöntemi
Belirtilen ComPtr işaretçi parametresini belirtilen arabirimi temsil edecek şekilde ayarlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
template<  
   typename U  
>  
HRESULT As(  
   _Out_ ComPtr<U>* ptr  
);  
  
template<  
   typename U  
>  
HRESULT As(  
   _Out_ Details::ComPtrRef<ComPtr<U>> ptr  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `U`  
 Bir arabirim kimliği  
  
 `ptr`  
 Bu işlem tamamlandığında, parametre temsil eden bir nesne `U`.  
  
## <a name="return-value"></a>Dönüş Değeri  
  
-   Bu işlem başarılı olursa S_OK; Aksi takdirde, nedenini belirten bir HRESULT işlemi başarısız oldu, ve `ptr` ayarlanır `nullptr`.  
  
-   Bu işlem başarılı olur, ancak geçerli WeakRef nesne zaten yayımlandı S_OK. Parametre `ptr` ayarlanır `nullptr`.  
  
-   Bu işlem başarılı olur, ancak geçerli WeakRef nesne parametresinden türetilmemiş S_OK `U`. Parametre `ptr` ayarlanır `nullptr`.  
  
## <a name="remarks"></a>Açıklamalar  
 Bir hata durumunda yayılan parametresi `U` IWeakReference ya da Iınspectable türetilmemiş.  
  
 İlk şablon kodunuzda kullanması gereken biçimidir. C++ dil özellikleri gibi destekleyen bir iç, yardımcı uzmanlık ikinci şablonudur [otomatik](../cpp/auto-cpp.md) kesintisi anahtar sözcüğü yazın.  
  
 Windows 10 SDK'sı başlayarak, bu yöntem WeakRef örneği ayarlanmamışsa `nullptr` zayıf başvuru edinilemedi, bu nedenle, kaçının için WeakRef denetler ve hata denetimi kodu `nullptr`. Bunun yerine, denetleme `ptr` için `nullptr`.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** client.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [WeakRef sınıfı](../windows/weakref-class.md)