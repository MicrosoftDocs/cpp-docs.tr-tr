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
ms.openlocfilehash: 53394a10464e2688953cd1b5703530e2719b7593
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80076452"
---
# <a name="is_invocable-is_invocable_r-is_nothrow_invocable-is_nothrow_invocable_r-classes"></a>is_invocable, is_invocable_r, is_nothrow_invocable, is_nothrow_invocable_r sınıfları

Bu şablonlar, bir türün belirtilen bağımsız değişken türleriyle çağrılabileceğini tespit edebilir. `is_invocable_r` ve `is_nothrow_invocable_r` Ayrıca, çağrının sonucunun belirli bir türe dönüştürülebilir olup olmadığını da saptayabilir. `is_nothrow_invocable` ve `is_nothrow_invocable_r`, çağrının özel durumlar throw olarak bilinmediğine da sahiptir. C++ 17 ' ye eklenmiştir.

## <a name="syntax"></a>Sözdizimi

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

*Bağımsız değişkenler*\
Sorgulanacak bağımsız değişken türleri.

*Dönüştürülebilir*\
*Çağrılabilir* sonucu türü, öğesine dönüştürülebilir olmalıdır.

## <a name="remarks"></a>Açıklamalar

Çağrılabilir tür *çağrılabilir* , değerlendirilmiş olmayan bir *bağlamda arguments bağımsız değişkenleri kullanılarak* çağrıbiliyorsa, `is_invocable` türü koşulu true olarak tutulur.

Çağrılabilir tür *çağrılabilir* , *dönüştürülebilir*bir bağlamda bağımsız değişkenler kullanılarak çağrılabilir olarak çağrılabilir bir sonuç türü oluşturmak için, çağrılabilir *türü olarak çağrılabilir* . `is_invocable_r`

Çağrılabilir tür *çağrılabilir* , değerlendirilmiş bir *bağlamda arguments bağımsız değişkenleri kullanılarak* çağrılırsa ve böyle bir çağrının özel durum oluşturmayacak şekilde çağrılabildiği durumlarda `is_nothrow_invocable` türü koşulu true olarak tutulur.

Çağrılabilir türde *çağrılabilir* bir sonuç türü oluşturmak için değerlendirilmeyen bağlamdaki *arguments bağımsız değişkenleri kullanılarak* çağrılabiliyorsa ve böyle bir çağrının özel durum oluşturmadığı biliniyorsa, `is_nothrow_invocable_r` türü koşulu *true olarak tutulur*.

*Dönüştürülebilir*, *çağrılabilir*ve Parameter Pack *args* türlerindeki türlerin her biri, tam bir tür, bilinmeyen bir dizi veya büyük olasılıkla MF nitelenmiş **void**olmalıdır. Aksi takdirde, koşulun davranışı tanımsız olur.

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

**Üst bilgi:** \<type_traits >

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[< type_traits >](../standard-library/type-traits.md)\
[Resync](functional-functions.md#invoke)
