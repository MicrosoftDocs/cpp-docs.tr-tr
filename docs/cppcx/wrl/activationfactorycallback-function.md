---
description: 'Daha fazla bilgi edinin: ActivationFactoryCallback Işlevi'
title: ActivationFactoryCallback İşlevi
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Details::ActivationFactoryCallback
helpviewer_keywords:
- ActivationFactoryCallback function
ms.assetid: dd40c79b-1273-4f2a-8c24-ae9926fb4fd9
ms.openlocfilehash: 9398b3f681e32c7a73b46de549ce7c41a3af6196
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97204621"
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

*activationId*<br/>
Çalışma zamanı sınıf adını belirten bir dizeye işleyin.

*ppFactory*<br/>
Bu işlem tamamlandığında, *activationId* parametresine karşılık gelen bir etkinleştirme fabrikası.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa S_OK; Aksi takdirde, hatayı açıklayan bir HRESULT. Olası Hata HRESULTs CLASS_E_CLASSNOTAVAILABLE ve E_INVALIDARG.

## <a name="remarks"></a>Açıklamalar

Belirtilen etkinleştirme KIMLIĞI için etkinleştirme fabrikasını alır.

Windows Çalışma Zamanı, bu geri çağırma işlevini, çalışma zamanı sınıf adı tarafından belirtilen bir nesne isteyecek şekilde çağırır.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Module. h

**Ad alanı:** Microsoft:: WRL::D euçlar

## <a name="see-also"></a>Ayrıca bkz.

[Microsoft:: WRL::D euçlar ad alanı](microsoft-wrl-details-namespace.md)
