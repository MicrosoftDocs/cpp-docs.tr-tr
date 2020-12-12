---
description: 'Daha fazla bilgi edinin: Move Işlevi'
title: Move İşlevi
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- internal/Microsoft::WRL::Details::Move
helpviewer_keywords:
- Move function
ms.assetid: c9525426-97e8-4d8c-9877-b689d8a0dc67
ms.openlocfilehash: eada3cac16abc445a9c48d01240f4ccf46d78372
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97209314"
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

*T*<br/>
Bağımsız değişkenin türü.

*değişkeni*<br/>
Taşınacak bir bağımsız değişken.

## <a name="return-value"></a>Dönüş Değeri

Başvuru veya rvalue-başvuru nitelikleri sonrasında parametre *arg* , varsa, kaldırılmıştır.

## <a name="remarks"></a>Açıklamalar

Belirtilen bağımsız değişkeni bir konumdan diğerine kaydırır.

Daha fazla bilgi için, [rvalue başvuru bildirimci:  &&](../../cpp/rvalue-reference-declarator-amp-amp.md)' nin **taşıma semantiğini** bölümüne bakın.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** iç. h

**Ad alanı:** Microsoft:: WRL::D euçlar

## <a name="see-also"></a>Ayrıca bkz.

[Microsoft:: WRL::D euçlar ad alanı](microsoft-wrl-details-namespace.md)
