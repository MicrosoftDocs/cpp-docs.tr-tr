---
title: result_of sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
f1_keywords:
- type_traits/std::result_of
- type_traits/std::result_of_t
- type_traits/std::result_of::type
dev_langs:
- C++
helpviewer_keywords:
- std::result_of
- std::result_of_t
- std::result_of::type
ms.assetid: 5374a096-4b4a-4712-aa97-6852c5cdd6be
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b385d822c2f58d26938b3300207a790dc1193060
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38953055"
---
# <a name="resultof-class"></a>result_of Sınıfı

Belirtilen bağımsız değişken türleri alan çağrılabilir türü dönüş türünü belirler.

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

*Fn* çağrılabilir türü için sorgu.

*ArgTypes* bağımsız değişken listesi sorguya çağrılabilir türüne türlerini.

## <a name="remarks"></a>Açıklamalar

Sonuç türü derleme zamanında belirlemek için bu şablonu kullanın `Fn`(`ArgTypes`), burada *Fn* çağrılabilir türü, işlev başvurusu veya içinde türlerininbirbağımsızdeğişkenlistesikullanılarakçağrılançağrılabilirtürünebaşvuru *ArgTypes*. `type` Şablon sınıfının üye adları sonuç türü `decltype(std::invoke(declval<Fn>(), declval<ArgTypes>()...))` varsa değerlendirilmemiş ifade `std::invoke(declval<Fn>(), declval<ArgTypes>()...)` doğru oluşturulmamış. Aksi takdirde, Şablon sınıfı üyesi yok `type`. Türü *Fn* ve tüm türleri parametre paketi *ArgTypes* tam türler olmalıdır **void**, veya bilinmeyen bağlı bir dizi.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<type_traits >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)<br/>
