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
ms.openlocfilehash: 5a3265cfe4b2629bf02925ea6e3eeb0c4acb1e0e
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68451209"
---
# <a name="resultof-class"></a>result_of Sınıfı

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

*FN*\
Sorgulanacak çağrılabilir tür.

*ArgTypes*\
Sorgu yapılacak çağrılabilir türe bağımsız değişken listesinin türleri.

## <a name="remarks"></a>Açıklamalar

Bu şablonu, derleme zamanında `Fn`(), *FN* 'nin çağrılabilir tür, işlev başvurusu veya çağrılabilir türe başvuru olarak, *ArgTypes*içindeki türlerin bir bağımsız değişken listesi kullanılarak çağrılan (`ArgTypes`), bu şablonu kullanın. Şablon sınıfının `decltype(std::invoke(declval<Fn>(), declval<ArgTypes>()...))` `std::invoke(declval<Fn>(), declval<ArgTypes>()...)`üyesi, değerlendirilmemiştir ifadesi doğru biçimlendirilmişse sonuç türünü adlandırır. `type` Aksi halde, şablon sınıfının üyesi `type`yoktur. Tür *FN* ve parametre paketi *ArgTypes* içindeki tüm türler, bilinmeyen sınırlı sayıda tür, **void**veya diziler olmalıdır. C++ 17 ' de [invoke_result](invoke-result-class.md) kullanımı kullanım dışı.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<type_traits >

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[< type_traits >](../standard-library/type-traits.md)\
[invoke_result sınıfı](invoke-result-class.md)
