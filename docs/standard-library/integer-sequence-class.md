---
title: integer_sequence sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- type_traits/std::index_sequence
- type_traits/std::make_index_sequence
- type_traits/std::integer_sequence
- type_traits/std::make_integer_sequence
- type_traits/std::index_sequence_for
dev_langs:
- C++
helpviewer_keywords:
- std::index_sequence
- std::make_index_sequence
- std::integer_sequence
- std::make_integer_sequence
- std::index_sequence_for
ms.assetid: 2cfdddee-819d-478e-bb78-c8a9c2696803
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3bac468f8cafc56f7fba5e13a8b210f9a6a8fd3b
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="integersequence-class"></a>integer_sequence Sınıfı

Bir tamsayı dizisini temsil eder. Türetme ve variadic türleri std::tuple gibi parametre paketlerinde genişletmek için kullanılan\<T... >, geçirilir bağımsız değişken olarak bir işlev.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class T, T... Vals>
struct integer_sequence
```

### <a name="parameters"></a>Parametreler

T değerlerin türü; bir tamsayı türünde olmalıdır: bool, char, char16_t, char32_t, wchar_t imzalı veya imzasız tamsayı türleri.

Tam sayı türü T. değerleri dizisini temsil eden elenen A olmayan tür parametresi paketi

## <a name="members"></a>Üyeler

|||
|-|-|
|`static size_t size() noexcept`|Dizideki öğelerin sayısı.|
|TypeDef T value_type|Dizideki her öğe türü. Bir tamsayı türünde olmalıdır.|

## <a name="remarks"></a>Açıklamalar

Doğrudan bir işlevine geçirilen parametre paketi tüm özel kitaplığı Yardımcıları paketten olabilir. Ne zaman bir parametre paketi bir işlevine geçirilen bir türü bir parçasıdır ve dizinlerini öğeleri erişmek için gereksinim duyduğunuz ardından paketinden çıkarın yapmanın en kolay yolu kullanmaktır `integer_sequence` ve onun ilişkili türün diğer adları `make_integer_sequence`, `index_sequence`, `make_index_sequence`ve `index_sequence_for`.

## <a name="example"></a>Örnek

Aşağıdaki örnek özgün teklifine dayalı [N3658](http://open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3658.html). Nasıl kullanılacağını gösterir bir `integer_sequence` oluşturmak için bir `std::tuple` gelen bir `std::array<T,N>`ve nasıl kullanılacağını bir `integer_sequence` tanımlama grubu üyeleri alınamıyor.

İçinde `a2t` işlevi, bir `index_sequence` bir diğer adı `integer_sequence` göre `size_t` tamsayı türü. `make_index_sequence` oluşturan derleme zamanında bir sıfır tabanlı bir diğer adı `index_sequence` çağıran tarafından geçirilen dizi aynı sayıda öğe ile. `a2t` geçirir `index_sequence` değerine göre `a2t_` , burada ifade `a[I]...` ayıklar `I`, ve ardından öğeleri için verildiğinde `make_tuple` hangi tüketir bunları olarak tek tek bağımsız değişken. Sıra üç öğeler içeriyorsa, örneğin, `make_tuple` make_tuple adlandırılır ([0], [1], a[2]). Dizi öğeleri Elbette herhangi bir türü olabilir.

Uygula işlevi kabul eden bir [std::tuple](../standard-library/tuple-class.md)ve bir integer_sequence kullanarak üretir `tuple_size` yardımcı sınıfı. Unutmayın [std::decay_t](../standard-library/decay-class.md)_is gerekli olduğundan [tuple_size](../standard-library/tuple-size-class-tuple.md) başvuru türleri ile çalışmaz. `apply_` İşlevi tanımlama grubu üyeleri ayıklar ve bunları bir işlev çağrısı için olarak ayrı bağımsız değişkenlerini iletir. Bu örnekte değerlerin yazdıran basit lambda ifadesi bir işlevdir.

```

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

Yapmak için bir `index_sequence` kullanmak için bir parametre paketi, `index_sequence_for` \<T... > için diğer ad olduğu `make_index_sequence` \<sizeof... (T) >

## <a name="requirements"></a>Gereksinimler

Başlık: < type_traits >

Namepace: std

## <a name="see-also"></a>Ayrıca bkz.

[Üç Nokta ve Variadic Şablonları](../cpp/ellipses-and-variadic-templates.md)<br/>
