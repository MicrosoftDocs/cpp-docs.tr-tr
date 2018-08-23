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
ms.openlocfilehash: 8844828028e174bd216bddb7e7c82cc9e5971a90
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42594889"
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

- Bu işlem başarılı olursa S_OK; Aksi takdirde, nedenini belirten bir HRESULT, işlem başarısız oldu, ve *ptr* ayarlanır **nullptr**.

- Geçerli bu işlem başarılı olursa S_OK **WeakRef** nesne zaten yayımlandı. Parametre *ptr* ayarlanır **nullptr**.

- Geçerli bu işlem başarılı olursa S_OK **WeakRef** nesne parametresinden türetilmemiş *riid*. Parametre *ptr* ayarlanır **nullptr**. (Daha fazla bilgi için açıklamalara bakın.)

## <a name="remarks"></a>Açıklamalar

Bir hata varsa yayıldığını parametresi *riid* türünden türetilmediğinden `IInspectable`. Bu hata, dönüş değeri yerine geçer.

İlk şablon kodunuzda kullanması gereken biçimidir. (Burada gösterilen olmasa üst bilgi dosyasında bildirilen) ikinci gibi C++ dil özellikleri destekleyen bir iç, Yardımcısı özelleştirmesi şablonudur [otomatik](../cpp/auto-cpp.md) kesinti anahtar sözcüğü yazın.

Windows 10 SDK'SINDAN başlayarak, bu yöntem ayarlı değil **WeakRef** için örnek **nullptr** zayıf başvuru elde edilemedi, bu nedenle, kaçının denetlervehatadenetimikod**WeakRef** için **nullptr**. Bunun yerine, kontrol *ptr* için **nullptr**.

## <a name="requirements"></a>Gereksinimler

**Başlık:** client.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Ayrıca Bkz.

[WeakRef Sınıfı](../windows/weakref-class.md)