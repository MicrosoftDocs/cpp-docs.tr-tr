---
description: 'Hakkında daha fazla bilgi edinin: invoke_result sınıfı'
title: invoke_result sınıfı
ms.date: 02/21/2019
f1_keywords:
- type_traits/std::invoke_result
- type_traits/std::invoke_result_t
- type_traits/std::invoke_result::type
helpviewer_keywords:
- std::invoke_result
- std::invoke_result_t
- std::invoke_result::type
ms.openlocfilehash: 4204ff1b0b8d38eab4b7d8c0de4709b90e12f5d3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97231504"
---
# <a name="invoke_result-class"></a>invoke_result sınıfı

Derleme zamanında belirtilen bağımsız değişken türlerini alan çağrılabilir türün dönüş türünü belirler. C++ 17 ' ye eklenmiştir.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Callable, class... Args>
   struct invoke_result<Callable(Args...)>;

// Helper type
template<class Callable, class... Args>
   using invoke_result_t = typename invoke_result<Callable, Args...>::type;
```

### <a name="parameters"></a>Parametreler

*Çağrılabilir*\
Sorgulanacak çağrılabilir tür.

*Args*\
Sorgu yapılacak çağrılabilir türe bağımsız değişken listesinin türleri.

## <a name="remarks"></a>Açıklamalar

Bu şablonu, derleme zamanında çağrılabilir (*args*...) sonuç türünü *, çağrılabilir ve* *bağımsız değişkenler* içindeki tüm  türlerin herhangi bir tam tür, bilinmeyen bir dizi veya büyük olasılıkla MF nitelikli olduğunu tespit etmek için kullanın **`void`** . `type`Sınıf şablonunun üyesi, arguments bağımsız değişkenleri kullanılarak çağrıldığında *çağrılabilir* dönüş türünü adlandırır....  `type`Üye yalnızca adlandırılmış bağımsız değişkenler kullanılarak çağrıldığında *çağrılabilir* ...  değerlendirilmemiştir. Aksi halde, Sınıf şablonunda hiçbir üye yoktur `type` ve derleme zamanında belirli bir bağımsız değişken türü kümesinde SFINAE testlerine izin verir.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<type_traits>

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)\
[Resync](functional-functions.md#invoke)
