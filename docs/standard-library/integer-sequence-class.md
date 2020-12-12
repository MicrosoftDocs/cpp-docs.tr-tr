---
description: 'Hakkında daha fazla bilgi edinin: integer_sequence sınıfı'
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
ms.openlocfilehash: 321e41c2c3bfaa1f89c05f799dedc4f4250f0a2d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97323981"
---
# <a name="integer_sequence-class"></a>integer_sequence Sınıfı

Bir tamsayı dizisini temsil eder. , \<T...> Bir işleve bağımsız değişken olarak geçirilen std:: Tuple gibi değişken olmayan türlerde parametre paketlerini bırakmak ve genişletmek için kullanılabilir.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class T, T... Vals>
struct integer_sequence
```

### <a name="parameters"></a>Parametreler

*Şı*\
Değerlerin türü; tamsayı türü olmalıdır: bool, Char, char16_t, char32_t, wchar_t veya imzalı ya da işaretsiz tamsayı türleri.

*Varış*\
T türünde bir değer dizisini temsil eden tür olmayan bir parametre paketi.

## <a name="members"></a>Üyeler

|Ad|Açıklama|
|-|-|
|`static size_t size() noexcept`|Dizideki öğelerin sayısı.|
|`typedef T value_type`|Dizideki her öğenin türü. Bir integral türü olmalıdır.|

## <a name="remarks"></a>Açıklamalar

Bir işleve doğrudan geçirilen bir parametre paketi özel bir kitaplık yardımcıları olmadan yüklenebilir. Bir parametre paketi, işleve geçirilen bir türün parçası olduğunda ve öğelere erişmek için dizinlerle ihtiyacınız olduğunda, onu paketten çıkarmanın en kolay yolu `integer_sequence` ve ilgili tür diğer adları,, ve ' ı kullanılır `make_integer_sequence` `index_sequence` `make_index_sequence` `index_sequence_for` .

## <a name="example"></a>Örnek

Aşağıdaki örnek, [N3658](https://wg21.link/n3658)orijinal teklifini temel alır. Bir `integer_sequence` ' dan ' a oluşturmak için ' nin nasıl kullanılacağını `std::tuple` `std::array<T,N>` ve `integer_sequence` demet üyelerine ulaşmak için nasıl kullanılacağını gösterir.

`a2t`İşlevinde, `index_sequence` `integer_sequence` tamsayı türüne göre bir diğer addır `size_t` . `make_index_sequence` , derleme süresi `index_sequence` içinde, çağıran tarafından geçirilen dizi ile aynı sayıda öğe ile sıfır tabanlı bir ad oluşturur. `a2t``index_sequence`değerine göre değerini öğesine geçirir `a2t_` , burada ifade `a[I]...` paketleri `I` ve sonra öğeler, bağımsız `make_tuple` bağımsız değişkenler olarak tüketir. Örneğin, dizi üç öğe içeriyorsa, `make_tuple` make_tuple (a [0], [1], bir [2]) olarak çağırılır. Dizi öğelerinin kendileri herhangi bir tür olabilir.

Apply işlevi bir [std:: Tuple](../standard-library/tuple-class.md)kabul eder ve `integer_sequence` yardımcı sınıfını kullanarak bir üretir `tuple_size` . [Tuple_size](../standard-library/tuple-size-class-tuple.md) başvuru türleriyle çalışmadığından [std::d ecay_t](../standard-library/decay-class.md) gerekli olduğunu unutmayın. `apply_`İşlevi demet üyelerinin paketini kaldırır ve bunları bir işlev çağrısına ayrı bağımsız değişkenler olarak iletir. Bu örnekte, işlevi değerleri yazdıran basit bir lambda ifadesidir.

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

Bir `index_sequence` parametre paketi için bir `index_sequence_for` \<T...> diğer ad olan öğesini kullanın`make_index_sequence`\<sizeof...(T)>

## <a name="requirements"></a>Gereksinimler

Üst bilgi \<type_traits\>

Ad hızadı: std

## <a name="see-also"></a>Ayrıca bkz.

[Üç nokta ve değişken bağımsız değişken Şablonlar](../cpp/ellipses-and-variadic-templates.md)
