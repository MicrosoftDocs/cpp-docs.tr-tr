---
title: '&lt;tanımlama grubu&gt; işlevleri'
ms.date: 11/04/2016
f1_keywords:
- tuple/std::get
- tuple/std::make_tuple
- tuple/std::tie
ms.assetid: bc6be38f-5258-4c14-b81b-63caa335fd44
helpviewer_keywords:
- std::get [C++]
- std::make_tuple [C++]
- std::tie [C++]
- std::get [C++]
- std::make_tuple [C++]
- std::tie [C++]
ms.openlocfilehash: 46c386ecffb8fbbf7c07d40b334afd91d261ebcf
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/06/2020
ms.locfileid: "78866204"
---
# <a name="lttuplegt-functions"></a>&lt;tanımlama grubu&gt; işlevleri

## <a name="apply"></a>uygulayabilirsiniz

```cpp
template <class F, class Tuple> constexpr decltype(auto) apply(F&& f, Tuple&& t);
```

### <a name="remarks"></a>Açıklamalar

Bir demet *t*ile *F* işlevini çağırır.

## <a name="forward"></a>forward_as_tuple

```cpp
template <class... TTypes>
    constexpr tuple<TTypes&&...> forward_as_tuple(TTypes&&...) noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

`tuple<TTypes&&...>(std::forward<TTypes>(t)...)` döndürür.

### <a name="remarks"></a>Açıklamalar

Bir işleve bağımsız değişken olarak iletmek *için uygun olan* bağımsız değişkenlere başvuru tanımlama grubu oluşturur.

## <a name="get"></a>Al

`tuple` nesnesinden bir öğeyi, dizine veya (C++ 14 ' de) türüne göre alır.

```cpp
// by index:
// get reference to Index element of tuple
template <size_t Index, class... Types>
   constexpr tuple_element_t<Index, tuple<Types...>>& get(tuple<Types...>& Tuple) noexcept;

// get const reference to Index element of tuple
template <size_t Index, class... Types>
   constexpr const tuple_element_t<Index, tuple<Types...>>& get(const tuple<Types...>& Tuple) noexcept;

// get rvalue reference to Index element of tuple
template <size_t Index, class... Types>
   constexpr tuple_element_t<Index, tuple<Types...>>&& get(tuple<Types...>&& Tuple) noexcept;

// (C++14) by type:
// get reference to T element of tuple
template <class T, class... Types>
   constexpr T& get(tuple<Types...>& Tuple) noexcept;

// get const reference to T element of tuple
template <class T, class... Types>
   constexpr const T& get(const tuple<Types...>& Tuple) noexcept;

// get rvalue reference to T element of tuple
template <class T, class... Types>
   constexpr T&& get(tuple<Types...>&& Tuple) noexcept;
```

### <a name="parameters"></a>Parametreler

*Dizin*\
Alınacak öğenin dizini.

*Türler*\
Tanımlama sırasında bildirim sırasına göre bildirildiği türlerin sırası.

*T*\
Alınacak öğenin türü.

*Tanımlama grubu*\
Herhangi bir sayıda öğe içeren `std::tuple`.

### <a name="remarks"></a>Açıklamalar

Şablon işlevleri, Dizin *dizinindeki*değere veya `tuple` nesnesinde *T* türüne bir başvuru döndürür.

Kayıt düzeni T türünde birden fazla veya daha az öğe içeriyorsa `get<T>(Tuple)` çağırmak derleyici hatası oluşturur.

### <a name="example"></a>Örnek

```cpp
#include <tuple>
#include <iostream>
#include <string>

using namespace std;

int main() {
    tuple<int, double, string> tup(0, 1.42, "Call me Tuple");

    // get elements by index
    cout << " " << get<0>(tup);
    cout << " " << get<1>(tup);
    cout << " " << get<2>(tup) << endl;

    // get elements by type
    cout << " " << get<int>(tup);
    cout << " " << get<double>(tup);
    cout << " " << get<string>(tup) << endl;
}
```

```Output
0 1.42 Call me Tuple
0 1.42 Call me Tuple
```

## <a name="make_from_tuple"></a>make_from_tuple

```cpp
template <class T, class Tuple> constexpr T make_from_tuple(Tuple&& t);
```

### <a name="remarks"></a>Açıklamalar

`return make_from_tuple_impl<T>(forward<Tuple>(t), make_index_sequence<tuple_size_v<decay_t<Tuple>>>{})`ile aynı.

## <a name="make_tuple"></a>make_tuple

Öğe değerlerinden bir `tuple` oluşturur.

```cpp
template <class T1, class T2, ..., class TN>
   tuple<V1, V2, ..., VN> make_tuple(const T1& t1, const T2& t2, ..., const TN& tN);
```

### <a name="parameters"></a>Parametreler

*TN*\
Nth Function parametresinin türü.

*tN*\
Nth işlev parametresinin değeri.

### <a name="remarks"></a>Açıklamalar

Şablon işlevi, karşılık gelen tür `Ti` `cv` `reference_wrapper<X>`olduğunda her tür `Vi` `X&` `tuple<V1, V2, ..., VN>(t1, t2, ..., tN)`döndürür. Aksi takdirde, `Ti`.

`make_tuple` avantajlarından biri, depolanan nesne türlerinin derleyici tarafından otomatik olarak belirlenmesi ve açıkça belirtilmesi gerekmez. `make_tuple` kullandığınızda `make_tuple<int, int>(1, 2)` gibi açık şablon bağımsız değişkenlerini kullanmayın, çünkü gereksiz bir şekilde ayrıntılıdır ve derleme hatasına neden olabilecek karmaşık rvalue başvuru sorunları ekler.

### <a name="example"></a>Örnek

```cpp
// std__tuple__make_tuple.cpp
// compile by using: /EHsc
#include <tuple>
#include <iostream>

typedef std::tuple<int, double, int, double> Mytuple;
int main() {
    Mytuple c0(0, 1, 2, 3);

// display contents " 0 1 2 3"
    std::cout << std::get<0>(c0) << " ";
    std::cout << std::get<1>(c0) << " ";
    std::cout << std::get<2>(c0) << " ";
    std::cout << std::get<3>(c0) << std::endl;

    c0 = std::make_tuple(4, 5, 6, 7);

// display contents " 4 5 6 7"
    std::cout << std::get<0>(c0) << " ";
    std::cout << std::get<1>(c0) << " ";
    std::cout << std::get<2>(c0) << " ";
    std::cout << std::get<3>(c0) << std::endl;

    return (0);
}
```

```Output
0 1 2 3
4 5 6 7
```

## <a name="swap"></a>Kur

```cpp
template <class... Types>
    void swap(tuple<Types...>& x, tuple<Types...>& y) noexcept(see below );
```

## <a name="tie"></a>formlarınızı

Öğe başvurularından bir `tuple` oluşturur.

```cpp
template <class T1, class T2, ..., class TN>
tuple<T1&, T2&, ..., TN&> tie(T1& t1, T2& t2, ..., TN& tN);
```

### <a name="parameters"></a>Parametreler

*TN*\
N demet öğesinin temel türü.

### <a name="remarks"></a>Açıklamalar

Şablon işlevi `tuple<T1&, T2&, ..., TN&>(t1, t2, ..., tN)`döndürür.

### <a name="example"></a>Örnek

```cpp
// std__tuple__tie.cpp
// compile with: /EHsc
#include <tuple>
#include <iostream>

typedef std::tuple<int, double, int, double> Mytuple;
int main() {
    Mytuple c0(0, 1, 2, 3);

// display contents " 0 1 2 3"
    std::cout << " " << std::get<0>(c0);
    std::cout << " " << std::get<1>(c0);
    std::cout << " " << std::get<2>(c0);
    std::cout << " " << std::get<3>(c0);
    std::cout << std::endl;

    int v4 = 4;
    double v5 = 5;
    int v6 = 6;
    double v7 = 7;
    std::tie(v4, v5, v6, v7) = c0;

// display contents " 0 1 2 3"
    std::cout << " " << v4;
    std::cout << " " << v5;
    std::cout << " " << v6;
    std::cout << " " << v7;
    std::cout << std::endl;

    return (0);
}
```

```Output
0 1 2 3
0 1 2 3
```

## <a name="tuple_cat"></a>tuple_cat

```cpp
template <class... Tuples> constexpr tuple<CTypes...> tuple_cat(Tuples&&...);
```

### <a name="return-value"></a>Dönüş Değeri

Her tür öğesi başlatılarak oluşturulan bir demet nesnesi.

## <a name="tuple_element_t"></a>tuple_element_t

```cpp
template <size_t I, class T>
    using tuple_element_t = typename tuple_element<I, T>::type;
```

## <a name="tuple_size_v"></a>tuple_size_v

```cpp
template <class T>
    inline constexpr size_t tuple_size_v = tuple_size<T>::value;
```
