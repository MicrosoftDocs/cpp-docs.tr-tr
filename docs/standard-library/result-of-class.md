---
title: result_of Sınıfı
ms.date: 02/21/2019
f1_keywords:
- type_traits/std::result_of
- type_traits/std::result_of_t
- type_traits/std::result_of::type
helpviewer_keywords:
- std::result_of
- std::result_of_t
- std::result_of::type
ms.assetid: 5374a096-4b4a-4712-aa97-6852c5cdd6be
ms.openlocfilehash: 54806f965cc46058e3c82b4863bb45782abe079e
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87202317"
---
# <a name="result_of-class"></a>result_of Sınıfı

Belirtilen bağımsız değişken türlerini alan çağrılabilir türün dönüş türünü belirler. C++ 14 ' te eklenmiştir ve C++ 17 ' de kullanımdan kaldırılmıştır.

## <a name="syntax"></a>Söz dizimi

```cpp
template<class>
struct result_of; // Causes a static assert

template <class Fn, class... ArgTypes>
struct result_of<Fn(ArgTypes...)>;

// Helper type
template<class T>
   using result_of_t = typename result_of<T>::type;
```

### <a name="parameters"></a>Parametreler

*FN*\
Sorgulanacak çağrılabilir tür.

*ArgTypes*\
Sorgu yapılacak çağrılabilir türe bağımsız değişken listesinin türleri.

## <a name="remarks"></a>Açıklamalar

Bu şablonu, derleme zamanında `Fn` ( `ArgTypes` ), *FN* 'nin çağrılabilir tür, işlev başvurusu veya çağrılabilir türe başvuru olarak, *ArgTypes*içindeki türlerin bir bağımsız değişken listesi kullanılarak çağrılan (), bu şablonu kullanın. `type`Sınıf şablonunun üyesi, `decltype(std::invoke(declval<Fn>(), declval<ArgTypes>()...))` değerlendirilmediği ifade doğru biçimlendirilmişse sonuç türünü adlandırır `std::invoke(declval<Fn>(), declval<ArgTypes>()...)` . Aksi halde, Sınıf şablonunda üye yoktur `type` . Tür *FN* ve parametre paketi *ArgTypes* içindeki tüm türler, tamamlanmış **`void`** bir veya daha fazla türdeki diziler olmalıdır. C++ 17 ' de [invoke_result](invoke-result-class.md) kullanım dışı bırakıldı.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<type_traits>

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)\
[invoke_result sınıfı](invoke-result-class.md)
