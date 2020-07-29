---
title: is_invocable, is_invocable_r, is_nothrow_invocable, is_nothrow_invocable_r sınıfları
ms.date: 02/21/2019
f1_keywords:
- type_traits/std::is_invocable
- type_traits/std::is_invocable_r
- type_traits/std::is_nothrow_invocable
- type_traits/std::is_nothrow_invocable_r
helpviewer_keywords:
- is_invocable class
- is_invocable
- is_invocable_r class
- is_invocable_r
- is_nothrow_invocable class
- is_nothrow_invocable
- is_nothrow_invocable_r class
- is_nothrow_invocable_r
ms.openlocfilehash: 47801eff0ea0c41c7b69dfb7a1aa5190a43f1b75
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87233112"
---
# <a name="is_invocable-is_invocable_r-is_nothrow_invocable-is_nothrow_invocable_r-classes"></a>is_invocable, is_invocable_r, is_nothrow_invocable, is_nothrow_invocable_r sınıfları

Bu şablonlar, bir türün belirtilen bağımsız değişken türleriyle çağrılabileceğini tespit edebilir. `is_invocable_r``is_nothrow_invocable_r`Ayrıca, çağrının sonucunun belirli bir türe dönüştürülebilir olup olmadığını da belirleyebilirsiniz. `is_nothrow_invocable``is_nothrow_invocable_r`Ayrıca, çağrının özel durumlar throw olarak bilinmesinin bilinmediğini de belirleyebilirsiniz. C++ 17 ' ye eklenmiştir.

## <a name="syntax"></a>Söz dizimi

```cpp
template <class Callable, class... Args>
struct is_invocable;

template <class Convertible, class Callable, class... Args>
struct is_invocable_r;

template <class Callable, class... Args>
struct is_nothrow_invocable;

template <class Convertible, class Callable, class... Args>
struct is_nothrow_invocable_r;

// Helper templates
template <class Callable, class... Args>
inline constexpr bool is_invocable_v =
    std::is_invocable<Callable, Args...>::value;

template <class Convertible, class Callable, class... Args>
inline constexpr bool is_invocable_r_v =
    std::is_invocable_r<Convertible, Callable, Args...>::value;

template <class Callable, class... Args>
inline constexpr bool is_nothrow_invocable_v =
    std::is_nothrow_invocable<Callable, Args...>::value;

template <class Convertible, class Callable, class... Args>
inline constexpr bool is_nothrow_invocable_r_v =
    std::is_nothrow_invocable_r<Convertible, Callable, Args...>::value;
```

### <a name="parameters"></a>Parametreler

*Çağrılabilir*\
Sorgulanacak çağrılabilir tür.

*Args*\
Sorgulanacak bağımsız değişken türleri.

*Üstü*\
*Çağrılabilir* sonucu türü, öğesine dönüştürülebilir olmalıdır.

## <a name="remarks"></a>Açıklamalar

`is_invocable`Çağrılabilir tür *çağrılabilir* , değerlendirilmiş olmayan bir bağlamda arguments bağımsız değişkenleri kullanılarak çağrıbiliyorsa tür *Args* koşulu true olarak tutulur.

`is_invocable_r`Çağrılabilir tür çağrılabilir, *dönüştürülebilir*bir bağlamda bağımsız değişkenler kullanılarak çağrılabilir olarak çağrılabilir bir sonuç türü *Args* oluşturmak için, çağrılabilir türü *çağrılabilir* .

`is_nothrow_invocable`Çağrılabilir tür *çağrılabilir* değeri, değerlendirilmiş bir bağlamda arguments bağımsız değişkenleri kullanılarak çağrılabiliyorsa ve bu *Args* tür bir çağrının özel durum oluşturmayacak bilinen bir tür koşulu true olur.

`is_nothrow_invocable_r`Çağrılabilir tür *çağrılabilir* değeri, *dönüştürülebilir*bir bağlam türü oluşturmak için değerlendirilmeyen bağlamdaki arguments *bağımsız* değişkenleri kullanılarak çağrılabiliyorsa ve bu tür bir çağrının özel durum oluşturmadığı biliniyorsa, tür koşulu true olarak tutulur.

*Dönüştürülebilir*, *çağrılabilir*ve parametre paketi *bağımsız değişkenlerinin* türlerindeki türlerin her biri, tam bir tür, bilinmeyen bir dizi veya bir MF nitelenmiş olmalıdır **`void`** . Aksi takdirde, koşulun davranışı tanımsız olur.

## <a name="example"></a>Örnek

```cpp
// std__type_traits__is_invocable.cpp
// compile using: cl /EHsc /std:c++17 std__type_traits__is_invocable.cpp
#include <type_traits>

auto test1(int) noexcept -> int (*)()
{
    return nullptr;
}

auto test2(int) -> int (*)()
{
    return nullptr;
}

int main()
{
    static_assert( std::is_invocable<decltype(test1), short>::value );

    static_assert( std::is_invocable_r<int(*)(), decltype(test1), int>::value );
    static_assert( std::is_invocable_r<long(*)(), decltype(test1), int>::value ); // fails

    static_assert( std::is_nothrow_invocable<decltype(test1), int>::value );
    static_assert( std::is_nothrow_invocable<decltype(test2), int>::value ); // fails

    static_assert( std::is_nothrow_invocable_r<int(*)(), decltype(test1), int>::value );
    static_assert( std::is_nothrow_invocable_r<int(*)(), decltype(test2), int>::value ); // fails
}
```

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<type_traits>

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)\
[Resync](functional-functions.md#invoke)
