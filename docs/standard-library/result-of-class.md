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
ms.openlocfilehash: ab575ac31936e7003f19fc2ceb3c5b1727d0728c
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2019
ms.locfileid: "72688994"
---
# <a name="result_of-class"></a>result_of Sınıfı

Belirtilen bağımsız değişken türlerini alan çağrılabilir türün dönüş türünü belirler. C++ 14 ' te eklenmiştir ve C++ 17 ' de kullanımdan kaldırılmıştır.

## <a name="syntax"></a>Sözdizimi

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

*Fn* \
Sorgulanacak çağrılabilir tür.

*ArgTypes* \
Sorgu yapılacak çağrılabilir türe bağımsız değişken listesinin türleri.

## <a name="remarks"></a>Açıklamalar

Bu şablonu, derleme zamanında (`ArgTypes`) `Fn` (), *FN* 'nin çağrılabilir bir tür, işlev başvurusu veya çağrılabilir türe başvuru olarak, *ArgTypes*içindeki türlerin bir bağımsız değişken listesi kullanılarak çağrılır. Sınıf şablonunun `type` üyesi, değerlendirilmeden `std::invoke(declval<Fn>(), declval<ArgTypes>()...)` ifadesi doğru biçimlendirilmişse `decltype(std::invoke(declval<Fn>(), declval<ArgTypes>()...))` sonuç türünü adlandırır. Aksi halde, Sınıf şablonunda `type` üye yok. Tür *FN* ve parametre paketi *ArgTypes* içindeki tüm türler, bilinmeyen sınırlı sayıda tür, **void**veya diziler olmalıdır. C++ 17 ' de [invoke_result](invoke-result-class.md) kullanımı kullanım dışı.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<type_traits >

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[< type_traits >](../standard-library/type-traits.md) \
[invoke_result sınıfı](invoke-result-class.md)
