---
title: Move İşlevi
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- internal/Microsoft::WRL::Details::Move
helpviewer_keywords:
- Move function
ms.assetid: c9525426-97e8-4d8c-9877-b689d8a0dc67
ms.openlocfilehash: 65fe85e95453165430c7ef3cfd4c4bb2babd9868
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80213713"
---
# <a name="move-function"></a>Move İşlevi

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

## <a name="syntax"></a>Sözdizimi

```cpp
template<class T>
inline typename RemoveReference<T>::Type&& Move(
   _Inout_ T&& arg
);
```

### <a name="parameters"></a>Parametreler

*Şı*<br/>
Bağımsız değişkenin türü.

*değişkeni*<br/>
Taşınacak bir bağımsız değişken.

## <a name="return-value"></a>Dönüş Değeri

Başvuru veya rvalue-başvuru nitelikleri sonrasında parametre *arg* , varsa, kaldırılmıştır.

## <a name="remarks"></a>Açıklamalar

Belirtilen bağımsız değişkeni bir konumdan diğerine kaydırır.

Daha fazla bilgi için, [rvalue başvuru bildirimci: & &](../../cpp/rvalue-reference-declarator-amp-amp.md)' nin **taşıma semantiğini** bölümüne bakın.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** iç. h

**Ad alanı:** Microsoft:: WRL::D euçlar

## <a name="see-also"></a>Ayrıca bkz.

[Microsoft::WRL::Details Ad Alanı](microsoft-wrl-details-namespace.md)
