---
title: WeakRef::As yöntemi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::WeakRef::As
dev_langs:
- C++
helpviewer_keywords:
- As method
ms.assetid: 7173da62-b3fe-44d6-aea4-1aa97e69b221
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7dd0dca806c1568d88c20eec6a7ac63e5fb242fb
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40020362"
---
# <a name="weakrefas-method"></a>WeakRef::As Yöntemi
Belirtilen ayarlar `ComPtr` belirtilen arabirim temsil etmek için işaretçi parametresi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
template<typename U>  
HRESULT As(  
   _Out_ ComPtr<U>* ptr  
);  
  
template<typename U>  
HRESULT As(  
   _Out_ Details::ComPtrRef<ComPtr<U>> ptr  
);  
```  
  
### <a name="parameters"></a>Parametreler  
 *U*  
 Bir arabirim kimliği.  
  
 *ptr*  
 Bu işlem tamamlandığında, parametre temsil eden bir nesne *U*.  
  
## <a name="return-value"></a>Dönüş Değeri  
  
-   Bu işlem başarılı olursa S_OK; Aksi takdirde, nedenini belirten bir HRESULT, işlem başarısız oldu, ve *ptr* ayarlanır **nullptr**.  
  
-   Geçerli bu işlem başarılı olursa S_OK **WeakRef** nesne zaten yayımlandı. Parametre *ptr* ayarlanır **nullptr**.  
  
-   Geçerli bu işlem başarılı olursa S_OK **WeakRef** nesne parametresinden türetilmemiş *U*. Parametre *ptr* ayarlanır **nullptr**.  
  
## <a name="remarks"></a>Açıklamalar  
 Bir hata varsa yayıldığını parametresi *U* olduğu `IWeakReference`, veya türünden türetilmediğinden `IInspectable`.  
  
 İlk şablon kodunuzda kullanması gereken biçimidir. İkinci şablonu olduğu gibi C++ dil özellikleri destekleyen bir iç, Yardımcısı özelleştirmesi [otomatik](../cpp/auto-cpp.md) kesinti anahtar sözcüğü yazın.  
  
 Windows 10 SDK'SINDAN başlayarak, bu yöntem ayarlı değil **WeakRef** için örnek **nullptr** zayıf başvuru elde edilemedi, bu nedenle, kaçının için WeakRef denetler ve hata denetimi kod **nullptr**. Bunun yerine, kontrol *ptr* için **nullptr**.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** client.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [WeakRef Sınıfı](../windows/weakref-class.md)