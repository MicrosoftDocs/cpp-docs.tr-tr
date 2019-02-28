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
ms.openlocfilehash: bb5e75a897029ded2e00e491d93d2df41a3e115b
ms.sourcegitcommit: 4299caac2dc9e806c74ac833d856a3838b0f52a1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/28/2019
ms.locfileid: "57006847"
---
# <a name="isinvocable-isinvocabler-isnothrowinvocable-isnothrowinvocabler-classes"></a>is_invocable, is_invocable_r, is_nothrow_invocable, is_nothrow_invocable_r sınıfları

Bu şablonlar, belirtilen bağımsız değişken türleriyle çağrılabilen bir tür belirler. `is_invocable_r` ve `is_nothrow_invocable_r` ayrıca çağrısının sonucunu belirli bir türe dönüştürülebilir olup olmadığını belirler. `is_nothrow_invocable` ve `is_nothrow_invocable_r` çağırma, özel durum oluşturması beklenmiyor biliniyorsa da belirler. C ++ 17'de eklendi.

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

*Çağrılabilir*<br/>
Sorgu için çağrılabilir türü.

*Args*<br/>
Sorgulamak için bağımsız değişken türleri.

*Dönüştürülebilir*<br/>
Sonuç türü, *Callable* dönüştürülebilir olmalıdır.

## <a name="remarks"></a>Açıklamalar

`is_invocable` Tür koşulu barındırıyorsa doğru çağrılabilir türü *Callable* bağımsız değişkenler kullanılarak çağrılabilir *Args* değerlendirilmemiş bir bağlamda.

`is_invocable_r` Tür koşulu barındırıyorsa doğru çağrılabilir türü *Callable* bağımsız değişkenler kullanılarak çağrılabilir *Args* sonucu olarak dönüştürülebilir türde üretmek için değerlendirilmemiş bir bağlamda  *Dönüştürülebilir*.

`is_nothrow_invocable` Tür koşulu barındırıyorsa doğru çağrılabilir türü *Callable* bağımsız değişkenler kullanılarak çağrılabilir *Args* değerlendirilmemiş bir bağlamda ve aynı çağrı gibi bir özel durum oluşturması beklenmiyor bilinir.

`is_nothrow_invocable_r` Tür koşulu barındırıyorsa doğru çağrılabilir türü *Callable* bağımsız değişkenler kullanılarak çağrılabilir *Args* sonucu olarak dönüştürülebilir türde üretmek için değerlendirilmemiş bir bağlamda  *Dönüştürülebilir*, ve bu tür bir çağrı, bir özel durum oluşturması beklenmiyor bilinmektedir.

Her tür *dönüştürülebilir*, *Callable*, parametre paketi içindeki türler *Args* tam bir tür, bilinmeyen bağlı bir dizi veya bir olasılıkla cv nitelenmiş olmalıdır**void**. Aksi halde, koşul davranışı tanımsızdır.

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

**Başlık:** \<type_traits >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)<br/>
[çağırma](functional-functions.md#invoke)<br/>
