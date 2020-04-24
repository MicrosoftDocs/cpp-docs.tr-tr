---
title: integer_sequence Sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::index_sequence
- type_traits/std::make_index_sequence
- type_traits/std::integer_sequence
- type_traits/std::make_integer_sequence
- type_traits/std::index_sequence_for
helpviewer_keywords:
- std::index_sequence
- std::make_index_sequence
- std::integer_sequence
- std::make_integer_sequence
- std::index_sequence_for
ms.assetid: 2cfdddee-819d-478e-bb78-c8a9c2696803
ms.openlocfilehash: 3de64f7855b5158f1565580d305e2a6eeaf3e76f
ms.sourcegitcommit: 89d9e1cb08fa872483d1cde98bc2a7c870e505e9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "82031478"
---
# <a name="integer_sequence-class"></a>integer_sequence Sınıfı

Bir karşıcı sırayı temsil eder. Bir işleve bağımsız değişken olarak geçirilen std::tuple\<T...> gibi variadik türlerdeki parametre paketlerini bulmak ve genişletmek için kullanılabilir.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class T, T... Vals>
struct integer_sequence
```

### <a name="parameters"></a>Parametreler

*T*\
Değerlerin türü; ayrılmaz bir tür olmalıdır: bool, char, char16_t, char32_t, wchar_t veya imzalı veya imzasız tamsayı türleri.

*Vals*\
İntegral türü T değerleri dizisini temsil eden tür olmayan bir parametre paketi.

## <a name="members"></a>Üyeler

|||
|-|-|
|`static size_t size() noexcept`|Dizideki öğe sayısı.|
|`typedef T value_type`|Dizideki her öğenin türü. Ayrılmaz bir tür olmalı.|

## <a name="remarks"></a>Açıklamalar

Doğrudan bir işleve geçirilen parametre paketi, özel kitaplık yardımcıları olmadan açılabilir. Bir parametre paketi bir işleve geçirilen bir türün parçasıysa ve öğelere erişmek için indekslere ihtiyacınız olduğunda, `integer_sequence` onu açmanın en `make_integer_sequence` `index_sequence`kolay `make_index_sequence`yolu `index_sequence_for`kullanmak ve ilgili tür adlarını kullanmaktır, , , ve .

## <a name="example"></a>Örnek

Aşağıdaki örnek, [n3658'in](https://wg21.link/n3658)özgün teklifine dayanmaktadır. Bir'den `std::array<T,N>`bir `std::tuple` `integer_sequence` in nasıl kullanılacağını ve bir'in `integer_sequence` tuple üyelerine ulaşmak için nasıl kullanılacağını gösterir.

İşlevde, `a2t` `index_sequence` integral türüne `integer_sequence` `size_t` dayalı bir diğer addır. `make_index_sequence`derleme zamanda, arayan tarafından geçirilen diziyle aynı `index_sequence` sayıda öğeiçeren sıfır tabanlı bir diğer addır. `a2t``index_sequence` değeri `a2t_` , ifadenin `a[I]...` paketaçtığı `I`yere geçirir ve sonra öğeler bunları `make_tuple` tek tek bağımsız değişkenolarak tüketen öğelerle beslenir. Örneğin, sıra üç öğe içeriyorsa, make_tuple(a[0], `make_tuple` a[1], a[2]) olarak adlandırılır. Dizi öğeleri kendilerini tabii ki herhangi bir tür olabilir.

Apply işlevi bir [std kabul eder::tuple](../standard-library/tuple-class.md), `tuple_size` ve yardımcı sınıf kullanarak bir `integer_sequence` üretir. tuple_size başvuru türleri ile [çalışmadığından](../standard-library/tuple-size-class-tuple.md) [std::decay_t](../standard-library/decay-class.md) gerekli olduğunu unutmayın. İşlev, `apply_` tuple üyelerini boşaltır ve bunları ayrı bağımsız değişkenler olarak işlev çağrısına ileder. Bu örnekte işlev, değerleri yazdıran basit bir lambda ifadesidir.

```cpp
#include <stddef.h>
#include <iostream>
#include <tuple>
#include <utility>
#include <array>
#include <string>

using namespace std;

// Create a tuple from the array and the index_sequence
template<typename Array, size_t... I>
auto a2t_(const Array& a, index_sequence<I...>)
{
    return make_tuple(a[I]...);
}

// Create an index sequence for the array, and pass it to the
// implementation function a2t_
template<typename T, size_t N>
auto a2t(const array<T, N>& a)
{
    return a2t_(a, make_index_sequence<N>());
}

// Call function F with the tuple members as separate arguments.
template<typename F, typename Tuple = tuple<T...>, size_t... I>
decltype(auto) apply_(F&& f, Tuple&& args, index_sequence<I...>)
{
    return forward<F>(f)(get<I>(forward<Tuple>(args))...);
}

// Create an index_sequence for the tuple, and pass it with the
// function object and the tuple to the implementation function apply_
template<typename F, typename Tuple = tuple<T...>>
decltype(auto) apply(F&& f, Tuple&& args)
{
    using Indices = make_index_sequence<tuple_size<decay_t<Tuple>>::value >;
    return apply_(forward<F>(f), forward<Tuple>(args), Indices());
}

int main()
{
    const array<string, 3> arr { "Hello", "from", "C++14" };

    //Create a tuple given a array
    auto tup = a2t(arr);

    // Extract the tuple elements
    apply([](const string& a, const string& b, const string& c) {cout << a << " " << b << " " << c << endl; }, tup);

    char c;
    cin >> c;
}
```

Bir `index_sequence` parametre paketi için bir `index_sequence_for` \<yapmak için, t...> `make_index_sequence` \<kullanın boyutlar için bir takma ad ... (T)>

## <a name="requirements"></a>Gereksinimler

Üstbilgi: \<type_traits\>

Namepace: std

## <a name="see-also"></a>Ayrıca bkz.

[Elipsler ve Variadik Şablonlar](../cpp/ellipses-and-variadic-templates.md)
