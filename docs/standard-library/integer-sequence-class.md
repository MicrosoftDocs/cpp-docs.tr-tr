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
ms.openlocfilehash: ca923933ac7a401f6a3ef14f821ceb04b844797b
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68451013"
---
# <a name="integersequence-class"></a>integer_sequence Sınıfı

Bir tamsayı dizisini temsil eder. , Std:: Tuple\<T gibi bağımsız değişken türlerde parametre paketlerini bırakmak ve genişletmek için kullanılabilir... bir işleve bağımsız değişken olarak geçirilen >.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class T, T... Vals>
struct integer_sequence
```

### <a name="parameters"></a>Parametreler

*ŞI*\
Değerlerin türü; bir integral türü olmalıdır: bool, Char, char16_t, char32_t, wchar_t veya imzalı ya da işaretsiz tamsayı türleri.

*Varış*\
T türünde bir değer dizisini temsil eden tür olmayan bir parametre paketi.

## <a name="members"></a>Üyeler

|||
|-|-|
|`static size_t size() noexcept`|Dizideki öğelerin sayısı.|
|`typedef T value_type`|Dizideki her öğenin türü. Bir integral türü olmalıdır.|

## <a name="remarks"></a>Açıklamalar

Bir işleve doğrudan geçirilen bir parametre paketi özel bir kitaplık yardımcıları olmadan yüklenebilir. Bir parametre paketi, işleve geçirilen bir türün parçası olduğunda ve öğelere erişmek için dizinlerle ihtiyacınız olduğunda, onu paketten çıkarmanın en `integer_sequence` kolay yolu, ve ilgili tür diğer adları `make_integer_sequence`, `index_sequence` `make_index_sequence`, ve `index_sequence_for`'ıkullanmaktır.

## <a name="example"></a>Örnek

Aşağıdaki örnek, [N3658](http://open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3658.html)orijinal teklifini temel alır. Bir `integer_sequence` `std::tuple` ' dan `integer_sequence` ' a oluşturmak için ' nin nasıl kullanılacağını ve demet üyelerine ulaşmak için nasıl kullanılacağını gösterir. `std::array<T,N>`

İşlevinde, tamsayıtürüne`size_t` göre bir `index_sequence` `integer_sequence`diğeraddır. `a2t` `make_index_sequence`, derleme süresi içinde, çağıran tarafından geçirilen dizi ile aynı sayıda `index_sequence` öğe ile sıfır tabanlı bir ad oluşturur. `a2t``a2t_` `a[I]...` `I`değerine göre değerini öğesine geçirir, burada ifade paketleri ve sonra öğeler `make_tuple` , bağımsız bağımsız değişkenler olarak tüketir. `index_sequence` Örneğin, dizi üç öğe içeriyorsa, `make_tuple` make_tuple (a [0], [1], bir [2]) olarak çağrılır. Dizi öğelerinin kendileri herhangi bir tür olabilir.

Apply işlevi bir [std:: Tuple](../standard-library/tuple-class.md)kabul eder ve `tuple_size` yardımcı sınıfını kullanarak `integer_sequence` bir üretir. [Tuple_size](../standard-library/tuple-size-class-tuple.md) başvuru türleriyle çalışmadığından [std::d ecay_t](../standard-library/decay-class.md) gereklidir. `apply_` İşlevi demet üyelerinin paketini kaldırır ve bunları bir işlev çağrısına ayrı bağımsız değişkenler olarak iletir. Bu örnekte, işlevi değerleri yazdıran basit bir lambda ifadesidir.

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

Bir parametre paketi `index_sequence` için oluşturmak üzere T. `index_sequence_for`. öğesini kullanın \<. sizeof için `make_index_sequence` \<bir diğer ad >... (T) >

## <a name="requirements"></a>Gereksinimler

Üst bilgi \<: type_traits\>

Ad hızadı: std

## <a name="see-also"></a>Ayrıca bkz.

[Üç Nokta ve Variadic Şablonları](../cpp/ellipses-and-variadic-templates.md)
