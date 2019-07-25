---
title: is_destructible sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_destructible
helpviewer_keywords:
- is_destructible
ms.assetid: 3bb9b718-1ad5-49ae-93cc-92b93b546b4d
ms.openlocfilehash: 80592a6fca274533a798b2f5a2459d336ee2c301
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68452729"
---
# <a name="isdestructible-class"></a>is_destructible sınıfı

Türün geri çevrilebilir olup olmadığını test eder.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class T>
struct is_destructible;
```

### <a name="parameters"></a>Parametreler

*ŞI*\
Sorgulanacak tür.

## <a name="remarks"></a>Açıklamalar

Tür *T* türü, yeniden çevrilebilir bir tür ise true, aksi durumda false değerini taşır. Geri çevrilebilir türler, başvuru türleri, nesne türleri ve değerlendirilmeyecek işlenene `U` `remove_all_extents_t<T>` `std::declval<U&>.~U()` eşit bir tür için doğru biçimlendirilmiş türlerdir. Tamamlanmamış türler, **void**ve işlev türleri dahil diğer türler, geri çevrilebilir türler değildir.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<type_traits >

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)
