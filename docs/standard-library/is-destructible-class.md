---
description: 'Hakkında daha fazla bilgi edinin: is_destructible sınıfı'
title: is_destructible sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_destructible
helpviewer_keywords:
- is_destructible
ms.assetid: 3bb9b718-1ad5-49ae-93cc-92b93b546b4d
ms.openlocfilehash: fcd41c292c0054553b165529a85e7b23312d3c2e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97231166"
---
# <a name="is_destructible-class"></a>is_destructible sınıfı

Türün geri çevrilebilir olup olmadığını test eder.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class T>
struct is_destructible;
```

### <a name="parameters"></a>Parametreler

*Şı*\
Sorgulanacak tür.

## <a name="remarks"></a>Açıklamalar

Tür *T* türü, yeniden çevrilebilir bir tür ise true, aksi durumda false değerini taşır. Geri çevrilebilir türler, başvuru türleri, nesne türleri ve `U` değerlendirilmeyecek işlenene eşit bir tür için `remove_all_extents_t<T>` doğru biçimlendirilmiş türlerdir `std::declval<U&>.~U()` . Eksik türler, ve işlev türleri dahil diğer türler, geri **`void`** çevrilebilir türler değildir.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<type_traits>

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)
