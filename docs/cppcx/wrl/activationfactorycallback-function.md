---
title: ActivationFactoryCallback İşlevi
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Details::ActivationFactoryCallback
helpviewer_keywords:
- ActivationFactoryCallback function
ms.assetid: dd40c79b-1273-4f2a-8c24-ae9926fb4fd9
ms.openlocfilehash: 4743e7724c5aba4171cb017654267afaac676f24
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62303883"
---
# <a name="activationfactorycallback-function"></a>ActivationFactoryCallback İşlevi

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

## <a name="syntax"></a>Sözdizimi

```cpp
inline HRESULT STDAPICALLTYPE ActivationFactoryCallback(
   HSTRING activationId,
   IActivationFactory **ppFactory
);
```

### <a name="parameters"></a>Parametreler

*Activationıd*<br/>
Bir çalışma zamanı sınıfı adının belirten bir dize için işler.

*ppFactory*<br/>
Bu işlem tamamlandığında, parametresine karşılık geldiği bir etkinleştirme fabrikası *Activationıd*.

## <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK; Aksi takdirde, hatayı açıklayan bir HRESULT. Büyük olasılıkla başarısız HRESULTs, CLASS_E_CLASSNOTAVAILABLE ve E_INVALIDARG verilmiştir.

## <a name="remarks"></a>Açıklamalar

Belirtilen etkinleştirme kimliği için kullanılan etkinleştirme üreteci alır

Windows çalışma zamanı ve çalışma zamanı sınıf adıyla belirtilen bir nesne istemek için bu geri çağırma işlevini çağırır.

## <a name="requirements"></a>Gereksinimler

**Başlık:** module.h

**Namespace:** Microsoft::wrl:: details

## <a name="see-also"></a>Ayrıca bkz.

[Microsoft::WRL::Details Ad Alanı](microsoft-wrl-details-namespace.md)