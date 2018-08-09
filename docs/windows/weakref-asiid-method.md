---
title: Weakref::asııd yöntemi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::WeakRef::AsIID
dev_langs:
- C++
helpviewer_keywords:
- AsIID method
ms.assetid: 94e87309-32da-4dbb-8233-e77313a1f448
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 60d2900876d7a9fbee7a193d0575bf3afdf4335b
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40012186"
---
# <a name="weakrefasiid-method"></a>WeakRef::AsIID Yöntemi
Belirtilen ayarlar `ComPtr` belirtilen arabirim kimliği. temsil etmek için işaretçi parametresi  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT AsIID(  
   REFIID riid,  
   _Out_ ComPtr<IInspectable>* ptr  
);  
```  
  
### <a name="parameters"></a>Parametreler  
 *riid*  
 Bir arabirim kimliği.  
  
 *ptr*  
 Bu işlem tamamlandığında, parametre temsil eden bir nesne *riid*.  
  
## <a name="return-value"></a>Dönüş Değeri  
  
-   Bu işlem başarılı olursa S_OK; Aksi takdirde, nedenini belirten bir HRESULT, işlem başarısız oldu, ve *ptr* ayarlanır **nullptr**.  
  
-   Geçerli bu işlem başarılı olursa S_OK **WeakRef** nesne zaten yayımlandı. Parametre *ptr* ayarlanır **nullptr**.  
  
-   Geçerli bu işlem başarılı olursa S_OK **WeakRef** nesne parametresinden türetilmemiş *riid*. Parametre *ptr* ayarlanır **nullptr**. (Daha fazla bilgi için açıklamalara bakın.)  
  
## <a name="remarks"></a>Açıklamalar  
 Bir hata varsa yayıldığını parametresi *riid* türünden türetilmediğinden `IInspectable`. Bu hata, dönüş değeri yerine geçer.  
  
 İlk şablon kodunuzda kullanması gereken biçimidir. (Burada gösterilen olmasa üst bilgi dosyasında bildirilen) ikinci gibi C++ dil özellikleri destekleyen bir iç, Yardımcısı özelleştirmesi şablonudur [otomatik](../cpp/auto-cpp.md) kesinti anahtar sözcüğü yazın.  
  
 Windows 10 SDK'SINDAN başlayarak, bu yöntem ayarlı değil **WeakRef** için örnek **nullptr** zayıf başvuru elde edilemedi, bu nedenle, kaçının denetlervehatadenetimikod**WeakRef** için **nullptr**. Bunun yerine, kontrol *ptr* için **nullptr**.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** client.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [WeakRef Sınıfı](../windows/weakref-class.md)