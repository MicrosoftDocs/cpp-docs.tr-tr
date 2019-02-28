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
ms.openlocfilehash: f60a3ef6528da33fd1117fc940e961e9fe0987df
ms.sourcegitcommit: 4299caac2dc9e806c74ac833d856a3838b0f52a1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/28/2019
ms.locfileid: "57006558"
---
# <a name="resultof-class"></a>result_of Sınıfı

Belirtilen bağımsız değişken türleri alan çağrılabilir türü dönüş türünü belirler. C ++ 17'de kullanımdan C ++ 14, eklendi.

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

*fn*<br/>
Sorgu için çağrılabilir türü.

*ArgTypes*<br/>
Bağımsız değişken listesi sorguya çağrılabilir türüne türlerini.

## <a name="remarks"></a>Açıklamalar

Sonuç türü derleme zamanında belirlemek için bu şablonu kullanın `Fn`(`ArgTypes`), burada *Fn* çağrılabilir türü, işlev başvurusu veya içinde türlerininbirbağımsızdeğişkenlistesikullanılarakçağrılançağrılabilirtürünebaşvuru *ArgTypes*. `type` Şablon sınıfının üye adları sonuç türü `decltype(std::invoke(declval<Fn>(), declval<ArgTypes>()...))` varsa değerlendirilmemiş ifade `std::invoke(declval<Fn>(), declval<ArgTypes>()...)` doğru oluşturulmamış. Aksi takdirde, Şablon sınıfı üyesi yok `type`. Türü *Fn* ve tüm türleri parametre paketi *ArgTypes* tam türler olmalıdır **void**, veya bilinmeyen bağlı bir dizi. Sunulmasıyla kullanım dışı [invoke_result](invoke-result-class.md) içinde C ++ 17.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<type_traits >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)<br/>
[invoke_result sınıfı](invoke-result-class.md)<br/>
