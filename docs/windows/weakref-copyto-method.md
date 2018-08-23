---
title: WeakRef::CopyTo yöntemi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::WeakRef::CopyTo
dev_langs:
- C++
helpviewer_keywords:
- CopyTo method
ms.assetid: f83de6da-b3d4-41a6-9845-cd725ecf3b75
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 791e9040d9e35c7dfb657cca38e26c01e86c86c4
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42594427"
---
# <a name="weakrefcopyto-method"></a>WeakRef::CopyTo Yöntemi

Bir işaretçi bir arabirim için kullanılabiliyorsa, belirtilen bir işaretçi değişkenine atar.

## <a name="syntax"></a>Sözdizimi

```cpp
HRESULT CopyTo(
   REFIID riid,
   _Deref_out_ IInspectable** ptr
);

template<typename U>
HRESULT CopyTo(
   _Deref_out_ U** ptr
);

HRESULT CopyTo(
   _Deref_out_ IWeakReference** ptr
);
```

### <a name="parameters"></a>Parametreler

*U*  
İşaretçi bir `IInspectable` arabirimi. Bir hata varsa yayıldığını *U* türünden türetilmediğinden `IInspectable`.

*riid*  
Bir arabirim kimliği. Bir hata varsa yayıldığını *riid* türünden türetilmediğinden `IWeakReference`.

*ptr*  
Karakteriyle dolaylı bir işaretçiye `IInspectable` veya `IWeakReference`.

## <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK; Aksi takdirde, hatayı açıklayan bir HRESULT. Daha fazla bilgi için **açıklamalar**.

## <a name="remarks"></a>Açıklamalar

S_OK dönüş değeri, bu işlem başarılı oldu, ancak güçlü bir başvuru zayıf başvuru çözümlendiği olup olmadığını göstermez anlamına gelir. S_OK döndürülürse, bu parametrenin test *p* güçlü bir başvuru; diğer bir deyişle, parametre *p* değerine eşit değildir **nullptr**.

Windows 10 SDK'SINDAN başlayarak, bu yöntem ayarlı değil **WeakRef** için örnek **nullptr** zayıf başvuru elde edilemedi, bu nedenle, kaçının için WeakRef denetleyen kod denetlenirken hata oluştu **nullptr**. Bunun yerine, kontrol *ptr* için **nullptr**.

## <a name="requirements"></a>Gereksinimler

**Başlık:** client.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Ayrıca Bkz.

[WeakRef Sınıfı](../windows/weakref-class.md)