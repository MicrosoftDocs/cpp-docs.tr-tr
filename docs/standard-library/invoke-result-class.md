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
ms.openlocfilehash: 8cd72e62fcb65209482fd9677afcc2ec83356feb
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2019
ms.locfileid: "72689513"
---
# <a name="invoke_result-class"></a>invoke_result sınıfı

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

*Çağrılabilir* \
Sorgulanacak çağrılabilir tür.

*Bağımsız değişkenler* \
Sorgu yapılacak çağrılabilir türe bağımsız değişken listesinin türleri.

## <a name="remarks"></a>Açıklamalar

Bu şablonu, derleme *zamanında çağrılabilir ' in (* *args*...), *çağrılabilir* ve *bağımsız değişkenler* içindeki tüm türlerin herhangi bir tam tür, bilinmeyen bir dizi ya da olası CV nitelikli `void` olduğunu anlamak için kullanın. Sınıf şablonunun `type` üyesi, arguments bağımsız değişkenleri kullanılarak çağrıldığında *çağrılabilir* dönüş türünü adlandırır *...* . @No__t_3 üyesi yalnızca *çağrılabilir* bağımsız değişkenler kullanılarak çağrıldığında çağrılabilir *çağrılabilir..* . değerlendirilmemiştir. Aksi takdirde, Sınıf şablonunda, derleme zamanında belirli bir bağımsız değişken türü kümesinde SFıNAE testlerine izin veren üye `type` yoktur.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<type_traits >

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[< type_traits >](../standard-library/type-traits.md) \
[Resync](functional-functions.md#invoke)
