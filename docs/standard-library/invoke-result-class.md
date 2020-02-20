---
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
ms.openlocfilehash: a5f67935bde103cf10c1bd9948ac1388f5221322
ms.sourcegitcommit: f38f770bfda1c174d2b81fabda7c893b15bd83a1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/20/2020
ms.locfileid: "77473891"
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

*Bağımsız değişkenler*\
Sorgu yapılacak çağrılabilir türe bağımsız değişken listesinin türleri.

## <a name="remarks"></a>Açıklamalar

Bu şablonu, derleme *zamanında çağrılabilir ' in (* *args*...), *çağrılabilir* ve *bağımsız değişkenler* içindeki tüm türlerin herhangi bir tam tür, bilinmeyen bir dizi ya da olası CV nitelikli `void`olduğunu anlamak için kullanın. Sınıf şablonunun `type` üyesi, arguments bağımsız değişkenleri kullanılarak çağrıldığında *çağrılabilir* dönüş türünü adlandırır *...* . `type` üyesi yalnızca *çağrılabilir* bağımsız değişkenler kullanılarak çağrıldığında çağrılabilir *çağrılabilir..* . değerlendirilmemiştir. Aksi takdirde, Sınıf şablonunda, derleme zamanında belirli bir bağımsız değişken türü kümesinde SFıNAE testlerine izin veren üye `type`yoktur.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<type_traits >

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[< type_traits >](../standard-library/type-traits.md)\
[Resync](functional-functions.md#invoke)
