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
ms.openlocfilehash: 7c03240d3ee666fcda30562279a8dbda2ca8dc7b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62404857"
---
# <a name="invokeresult-class"></a>invoke_result sınıfı

Belirtilen bağımsız değişken türleri alan derleme zamanında çağrılabilir türü dönüş türünü belirler. C ++ 17'de eklendi.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Callable, class... Args>
   struct invoke_result<Callable(Args...)>;

// Helper type
template<lass Callable, class... Args>
   using invoke_result_t = typename invoke_result<Callable, Args...>::type;
```

### <a name="parameters"></a>Parametreler

*Çağrılabilir*<br/>
Sorgu için çağrılabilir türü.

*Args*<br/>
Bağımsız değişken listesi sorguya çağrılabilir türüne türlerini.

## <a name="remarks"></a>Açıklamalar

Sonuç türünü belirlemek için bu şablonu kullanın *Callable*(*Args*...) derleme zamanında burada *Callable* ve tüm türleri *Args* tam bir tür, bilinmeyen bağlı bir dizi veya bir olasılıkla cv nitelenmiş `void`. `type` Şablon sınıfının üye adları dönüş türünü *Callable* bağımsız değişkenler kullanılarak çağrıldığında *Args*... `type` Üye, yalnızca tanımlanan *Callable* çağrıldığında bağımsız değişkenler kullanılarak çağrılabilir *Args*... değerlendirilmemiş bir bağlamda. Aksi takdirde, Şablon sınıfı üyesi yok `type`, derleme zamanında testleri belirli bir bağımsız değişken türlerinin SFINAE sağlar.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<type_traits >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)<br/>
[çağırma](functional-functions.md#invoke)
