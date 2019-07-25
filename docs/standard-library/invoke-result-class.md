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
ms.openlocfilehash: 2b2051b0c854151cff9b439f5ec0a951c25a6387
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68447635"
---
# <a name="invokeresult-class"></a>invoke_result sınıfı

Derleme zamanında belirtilen bağımsız değişken türlerini alan çağrılabilir türün dönüş türünü belirler. C++ 17 ' ye eklenmiştir.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Callable, class... Args>
   struct invoke_result<Callable(Args...)>;

// Helper type
template<lass Callable, class... Args>
   using invoke_result_t = typename invoke_result<Callable, Args...>::type;
```

### <a name="parameters"></a>Parametreler

*Çağrılabilir*\
Sorgulanacak çağrılabilir tür.

*Args*\
Sorgu yapılacak çağrılabilir türe bağımsız değişken listesinin türleri.

## <a name="remarks"></a>Açıklamalar

Bu şablonu, derleme zamanında *çağrılabilir (* *args*...) sonuç türünü, *çağrılabilir ve* *bağımsız değişkenler* içindeki tüm türlerin herhangi bir tam tür, bilinmeyen bir dizi veya büyük olasılıkla MF nitelikli `void`olduğunu tespit etmek için kullanın. Şablon sınıfının  üyesi, bağımsız değişken bağımsız değişkenleri kullanılarak çağrıldığında çağrılabilir dönüş türünü adlandırır....  `type` Üye yalnızca adlandırılmış bağımsız değişkenler kullanılarak çağrıldığında *çağrılabilir* *...* `type` değerlendirilmemiştir. Aksi halde, şablon sınıfı, derleme zamanında `type`belirli bir bağımsız değişken türleri kümesi üzerinde SFINAE testlerine izin veren bir üyeye sahip değildir.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<type_traits >

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[< type_traits >](../standard-library/type-traits.md)\
[Resync](functional-functions.md#invoke)
