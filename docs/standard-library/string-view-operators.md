---
title: '&lt;string_view &gt; işleçleri'
description: '`string_view`İki `string_view` nesneyi veya bir `string_view` diğer dize nesnesini karşılaştırmak için kullanılan operatörler için API başvurusu'
ms.date: 01/15/2021
f1_keywords:
- xstring/basic_string_view::operator!=
- xstring/basic_string_view::operator&gt;
- xstring/basic_string_view::operator&gt;=
- xstring/basic_string_view::operator&lt;
- xstring/basic_string_view::operator&lt;&lt;
- xstring/basic_string_view::operator&lt;=
- xstring/basic_string_view::operator+
- xstring/basic_string_view::operator==
- xstring/std::literals::string_view_literals::operator "sv
- std::literals::string_view_literals::operator sv
- std::literals::string_view_literals
- string_view_literals
helpviewer_keywords:
- std::basic_string_view::operator!=
- std::basic_string_view::operator&gt;
- std::basic_string_view::operator&gt;=
- std::basic_string_view::operator&lt;
- std::basic_string_view::operator&lt;&lt;
- std::basic_string_view::operator&lt;=, std::basic_string_view::operator==
ms.openlocfilehash: a14d82dc0b29f88cb25f5b24f0836f033d2b828e
ms.sourcegitcommit: 3d9cfde85df33002e3b3d7f3509ff6a8dc4c0a21
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/21/2021
ms.locfileid: "98666907"
---
# <a name="string_view-operators"></a>`<string_view>` işleçleri

Bu işleçleri `string_view` , iki nesneyi veya bir `string_view` ve bir [`std::string`](basic-string-class.md) `char*` örtük dönüştürmenin sağlandığı bir diğer dize nesnesini (veya veya) karşılaştırmak için kullanın.

[`operator!=`](#op_neq)\
[`operator>`](#op_gt)\
[`operator>=`](#op_gt_eq)\
[`operator<`](#op_lt)\
[`operator<<`](#op_lt_lt)\
[`operator<=`](#op_lt_eq)\
[`operator==`](#op_eq_eq)\
[`operator""sv`](#op_sv)

## <a name="operator"></a><a name="op_neq"></a> `operator!=`

İşlecin sol tarafındaki nesnenin sağ taraftaki nesneye eşit olup olmadığını sınar.

```cpp
template <class CharType, class Traits>
bool operator!=(
    const basic_string_view<CharType, Traits>& left,
    const basic_string_view<CharType, Traits>& right);

template <class CharType, class Traits>
bool operator!=(
    const basic_string_view<CharType, Traits>& left,
    convertible_string_type right);

template <class CharType, class Traits>
bool operator!=(
    convertible_string_type left,
    const basic_string_view<CharType, Traits>& right);
```

### <a name="parameters"></a>Parametreler

*tarafta*\
Herhangi bir dönüştürülebilir dize türü veya Karşılaştırılacak türü bir nesne `basic_string_view` .

*Right*\
Herhangi bir dönüştürülebilir dize türü veya Karşılaştırılacak türü bir nesne `basic_string_view` .

### <a name="return-value"></a>Dönüş Değeri

**`true`** işlecin sol tarafındaki nesne sağ taraftaki nesneye sözcüıgrafik olarak eşit değilse; Aksi takdirde **`false`** .

### <a name="remarks"></a>Açıklamalar

Kapalı bir dönüştürme, diğer taraftaki *convertible_string_type* arasında olmalıdır `string_view` .

Karşılaştırma, karakter sıralarının ikili bir lexıgraf karşılaştırmasını temel alır. Aynı sayıda öğe varsa ve öğelerin tümü eşitse, iki nesne eşittir. Aksi takdirde, bunlar eşit değildir.

## <a name="operator"></a><a name="op_eq_eq"></a> `operator==`

İşlecin sol tarafındaki nesnenin sağ taraftaki nesneye eşit olup olmadığını sınar.

```cpp
template <class CharType, class Traits>
bool operator==(
    const basic_string_view<CharType, Traits>& left,
    const basic_string_view<CharType, Traits>& right);

template <class CharType, class Traits>
bool operator==(
    const basic_string_view<CharType, Traits>& left,
    convertible_string_type right);

template <class CharType, class Traits>
bool operator==(
    convertible_string_type left,
    const basic_string_view<CharType, Traits>& right);
```

### <a name="parameters"></a>Parametreler

*tarafta*\
Herhangi bir dönüştürülebilir dize türü veya Karşılaştırılacak türü bir nesne `basic_string_view` .

*Right*\
Herhangi bir dönüştürülebilir dize türü veya Karşılaştırılacak türü bir nesne `basic_string_view` .

### <a name="return-value"></a>Dönüş Değeri

**`true`** işlecin sol tarafındaki nesne, sağ taraftaki nesneye sözcüıgrafik eşitse; Aksi takdirde **`false`** .

### <a name="remarks"></a>Açıklamalar

Kapalı bir dönüştürme, diğer taraftaki *convertible_string_type* arasında olmalıdır `string_view` .

Karşılaştırma, karakter sıralarının ikili bir lexıgraf karşılaştırmasını temel alır. Aynı sayıda öğe varsa ve öğelerin tümü eşitse, iki nesne eşittir.

## <a name="operator"></a><a name="op_lt"></a> `operator<`

İşlecin sol tarafındaki nesnenin sağ taraftaki nesneden daha az olup olmadığını sınar.

```cpp
template <class CharType, class Traits>
bool operator<(
    const basic_string_view<CharType, Traits>& left,
    const basic_string_view<CharType, Traits>& right);

template <class CharType, class Traits>
bool operator<(
    const basic_string_view<CharType, Traits>& left,
    convertible_string_type right);

template <class CharType, class Traits>
bool operator<(
    convertible_string_type left,
    const basic_string_view<CharType, Traits>& right);
```

### <a name="parameters"></a>Parametreler

*tarafta*\
Herhangi bir dönüştürülebilir dize türü veya Karşılaştırılacak türü bir nesne `basic_string_view` .

*Right*\
Herhangi bir dönüştürülebilir dize türü veya Karşılaştırılacak türü bir nesne `basic_string_view` .

### <a name="return-value"></a>Dönüş Değeri

**`true`** işlecin sol tarafındaki nesne sağ taraftaki nesnenin lexıgrafik değerinden küçükse; Aksi takdirde **`false`** .

### <a name="remarks"></a>Açıklamalar

Kapalı bir dönüştürme *convertible_string_type* diğer taraftaki string_view arasında bulunmalıdır.

Karşılaştırma, karakter sıralarının ikili bir lexıgraf karşılaştırmasını temel alır. İlk eşit olmayan karakter çiftinden karşılaşıldığında, bu Karşılaştırmanın sonucu döndürülür. Eşit olmayan karakter bulunamazsa, ancak bir dizi kısaysa, daha kısa bir sıra daha uzundur. Diğer bir deyişle, "Cat", "Kediler" den küçüktür.

### <a name="example"></a>Örnek

```cpp
#include <string>
#include <string_view>

using namespace std;

int main()
{
    string_view sv1 { "ABA" };
    string_view sv2{ "ABAC" };
    string_view sv3{ "ABAD" };
    string_view sv4{ "ABACE" };

    bool result = sv2 > sv1; // true
    result = sv3 > sv2; // true
    result = sv3 != sv1; // true
    result = sv4 < sv3; // true because `C` < `D`
}
```

## <a name="operator"></a><a name="op_lt_eq"></a> `operator<=`

İşlecin sol tarafındaki nesnenin sağ taraftaki nesneden küçük veya ona eşit olup olmadığını sınar.

```cpp
template <class CharType, class Traits>
bool operator<=(
    const basic_string_view<CharType, Traits>& left,
    const basic_string_view<CharType, Traits>& right);

template <class CharType, class Traits>
bool operator<=(
    const basic_string_view<CharType, Traits>& left,
    convertible_string_type right);

template <class CharType, class Traits>
bool operator<=(
    convertible_string_type left,
    const basic_string_view<CharType, Traits>& right);
```

### <a name="parameters"></a>Parametreler

*tarafta*\
Herhangi bir dönüştürülebilir dize türü veya Karşılaştırılacak türü bir nesne `basic_string_view` .

*Right*\
Herhangi bir dönüştürülebilir dize türü veya Karşılaştırılacak türü bir nesne `basic_string_view` .

### <a name="return-value"></a>Dönüş Değeri

**`true`** işlecin sol tarafındaki nesne, sağ taraftaki nesneye sözcüıgrafik veya daha küçükse, Aksi takdirde **`false`** .

### <a name="remarks"></a>Açıklamalar

Bkz [`operator<`](#op_lt) ..

## <a name="operator"></a><a name="op_lt_lt"></a> `operator<<`

Bir `string_view` çıkış akışına yazar.

```cpp
template <class CharType, class Traits>
inline basic_ostream<CharType, Traits>& operator<<(
    basic_ostream<CharType, Traits>& Ostr, const basic_string_view<CharType, Traits> Str);
```

### <a name="parameters"></a>Parametreler

*`Ostr`*\
yazılan çıkış akışı.

*`Str`*\
Bir çıkış akışına girilecek string_view.

### <a name="return-value"></a>Dönüş Değeri

yazılan çıkış akışı.

### <a name="remarks"></a>Açıklamalar

Örneğin kullanarak bir çıkış akışına içeriğini eklemek için bu işleci kullanın `string_view` [`std::cout`](iostream.md#cout) .

## <a name="operator"></a><a name="op_gt"></a> `operator>`

İşlecin sol tarafındaki nesnenin sağ taraftaki nesneden daha büyük olup olmadığını sınar.

```cpp
template <class CharType, class Traits>
bool operator>(
    const basic_string_view<CharType, Traits>& left,
    const basic_string_view<CharType, Traits>& right);

template <class CharType, class Traits>
bool operator>(
    const basic_string_view<CharType, Traits>& left,
    convertible_string_type right);

template <class CharType, class Traits>
bool operator>(
    convertible_string_type left,
    const basic_string_view<CharType, Traits>& right);
```

### <a name="parameters"></a>Parametreler

*tarafta*\
Herhangi bir dönüştürülebilir dize türü veya Karşılaştırılacak türü bir nesne `basic_string_view` .

*Right*\
Herhangi bir dönüştürülebilir dize türü veya Karşılaştırılacak türü bir nesne `basic_string_view` .

### <a name="return-value"></a>Dönüş Değeri

**`true`** işlecin sol tarafındaki nesne sağ taraftaki nesneden daha fazla lexıgrafik büyükse `string_view` ; Aksi takdirde **`false`** .

### <a name="remarks"></a>Açıklamalar

Bkz [`operator<`](#op_lt) ..

## <a name="operator"></a><a name="op_gt_eq"></a> `operator>=`

İşlecin sol tarafındaki nesnenin sağ taraftaki nesneden büyük veya ona eşit olup olmadığını sınar.

```cpp
template <class CharType, class Traits>
bool operator>=(
    const basic_string_view<CharType, Traits>& left,
    const basic_string_view<CharType, Traits>& right);

template <class CharType, class Traits>
bool operator>=(
    const basic_string_view<CharType, Traits>& left,
    convertible_string_type right);

template <class CharType, class Traits>
bool operator>=(
    convertible_string_type left,
    const basic_string_view<CharType, Traits>& right);
```

### <a name="parameters"></a>Parametreler

*`left`*\
Herhangi bir dönüştürülebilir dize türü veya Karşılaştırılacak türü bir nesne `basic_string_view` .

*`right`*\
Herhangi bir dönüştürülebilir dize türü veya Karşılaştırılacak türü bir nesne `basic_string_view` .

### <a name="return-value"></a>Dönüş Değeri

**`true`** işlecin sol tarafındaki nesne sağ taraftaki nesneye sözcüıgrafik büyük veya ona eşitse; Aksi takdirde **`false`** .

### <a name="remarks"></a>Açıklamalar

Bkz [`operator<`](#op_lt) ..

## <a name="operator-sv-string_view-literal"></a><a name="op_sv"></a>`operator"" sv`( `string_view` sabit değer)

Bir dize sabit değerinden bir oluşturur `string_view` . Ad alanı gerektirir `std::literals::string_view_literals` .

### <a name="example"></a>Örnek

```cpp

using namespace std;
using namespace literals::string_view_literals;

    string_view sv{ "Hello"sv };
    wstring_view wsv{ L"Hello"sv };
    u16string_view sv16{ u"Hello"sv };
    u32string_view sv32{ U"Hello"sv };
```

## <a name="requirements"></a>Gereksinimler

[`/std:c++17`](../build/reference/std-specify-language-standard-version.md)

## <a name="see-also"></a>Ayrıca bkz.

[`<string_view>`](../standard-library/string-view.md)
