---
description: 'Daha fazla bilgi edinin: Swap Işlevi (WRL)'
title: Swap Işlevi (WRL)
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- internal/Microsoft::WRL::Details::Swap
ms.assetid: ed134a08-ceb7-4279-aa02-a183c3a426ea
ms.openlocfilehash: e81c9e332c6c6a69f475f53132689dc99fffdfee
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97186200"
---
# <a name="swap-function-wrl"></a>Swap Işlevi (WRL)

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

## <a name="syntax"></a>Sözdizimi

```cpp
WRL_NOTHROW inline void Swap(
   _Inout_ T& left,
   _Inout_ T& right
);
```

### <a name="parameters"></a>Parametreler

*tarafta*<br/>
İlk bağımsız değişken.

*Right*<br/>
İkinci bağımsız değişken.

## <a name="return-value"></a>Dönüş Değeri

## <a name="remarks"></a>Açıklamalar

Belirtilen iki bağımsız değişkenin değerlerini değiş tokuş eder.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** iç. h

**Ad alanı:** Microsoft:: WRL::D euçlar

## <a name="see-also"></a>Ayrıca bkz.

[Microsoft:: WRL::D euçlar ad alanı](microsoft-wrl-details-namespace.md)
