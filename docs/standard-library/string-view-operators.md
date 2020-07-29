---
title: '&lt;string_view &gt; işleçleri'
ms.date: 04/19/2019
f1_keywords:
- xstring/basic_string_view::operator!=
- xstring/basic_string_view::operator&gt;
- xstring/basic_string_view::operator&gt;=
- xstring/basic_string_view::operator&lt;
- xstring/basic_string_view::operator&lt;&lt;
- xstring/basic_string_view::operator&lt;=
- xstring/basic_string_view::operator+
- xstring/basic_string_view::operator==
helpviewer_keywords:
- std::basic_string_view::operator!=
- std::basic_string_view::operator&gt;
- std::basic_string_view::operator&gt;=
- std::basic_string_view::operator&lt;
- std::basic_string_view::operator&lt;&lt;
- std::basic_string_view::operator&lt;=, std::basic_string_view::operator==
ms.openlocfilehash: 39727177ff0fe88e2fcc105a6cee49711b36de6e
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87222244"
---
# <a name="ltstring_viewgt-operators"></a>&lt;string_view &gt; işleçleri

İki string_view nesnesini veya bir string_view ve başka bir dize nesnesini (örneğin, [std:: String](basic-string-class.md)veya **char \* **), örtük bir dönüştürmenin sağlandığı bir şekilde karşılaştırmak için bu işleçleri kullanın.

||||
|-|-|-|
|[işleç! =](#op_neq)|[işleç&gt;](#op_gt)|[işleç&gt;=](#op_gt_eq)|
|[işleç&lt;](#op_lt)|[işleç&lt;&lt;](#op_lt_lt)|[işleç&lt;=](#op_lt_eq)|
|[işleç = =](#op_eq_eq)|["" SV işleci](#op_sv)|

## <a name="operator"></a><a name="op_neq"></a>işleç! =

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

Kapalı bir dönüştürme *convertible_string_type* diğer taraftaki string_view arasında bulunmalıdır.

Karşılaştırma, karakter sıralarının ikili bir lexıgraf karşılaştırmasını temel alır. Aynı sayıda öğe varsa ve öğelerin tümü eşitse, iki nesne eşittir. Aksi takdirde, bunlar eşit değildir.

## <a name="operator"></a><a name="op_eq_eq"></a>işleç = =

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

Kapalı bir dönüştürme *convertible_string_type* diğer taraftaki string_view arasında bulunmalıdır.

Karşılaştırma, karakter sıralarının ikili bir lexıgraf karşılaştırmasını temel alır. Aynı sayıda öğe varsa ve öğelerin tümü eşitse, iki nesne eşittir.

## <a name="operatorlt"></a><a name="op_lt"></a>işlecinde&lt;

İşlecin sol tarafındaki nesnenin sağdaki nesneden daha az olup olmadığını sınar sidestring_view

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

## <a name="operatorlt"></a><a name="op_lt_eq"></a>işlecinde&lt;=

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

Bkz [. &lt; işleci](#op_lt).

## <a name="operatorltlt"></a><a name="op_lt_lt"></a>işlecinde&lt;&lt;

Çıkış akışına bir string_view yazar.

```cpp
template <class CharType, class Traits>
inline basic_ostream<CharType, Traits>& operator<<(
    basic_ostream<CharType, Traits>& Ostr, const basic_string_view<CharType, Traits> Str);
```

### <a name="parameters"></a>Parametreler

*OSTR*\
yazılan çıkış akışı.

*Üstbilgisine*\
Bir çıkış akışına girilecek string_view.

### <a name="return-value"></a>Dönüş Değeri

yazılan çıkış akışı.

### <a name="remarks"></a>Açıklamalar

Bir string_view içeriğini bir çıkış akışına eklemek için, örneğin [std:: cout](iostream.md#cout)kullanarak bu işleci kullanın.

## <a name="operatorgt"></a><a name="op_gt"></a>işlecinde&gt;

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

**`true`** işlecin sol tarafındaki nesne sağ taraftaki string_view nesnesinden sözcüıgrafik büyükse; Aksi takdirde **`false`** .

### <a name="remarks"></a>Açıklamalar

Bkz [. &lt; işleci](#op_lt).

## <a name="operatorgt"></a><a name="op_gt_eq"></a>işlecinde&gt;=

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

*tarafta*\
Herhangi bir dönüştürülebilir dize türü veya Karşılaştırılacak türü bir nesne `basic_string_view` .

*Right*\
Herhangi bir dönüştürülebilir dize türü veya Karşılaştırılacak türü bir nesne `basic_string_view` .

### <a name="return-value"></a>Dönüş Değeri

**`true`** işlecin sol tarafındaki nesne sağ taraftaki nesneye sözcüıgrafik büyük veya ona eşitse; Aksi takdirde **`false`** .

### <a name="remarks"></a>Açıklamalar

Bkz [. &lt; işleci](#op_lt).

## <a name="operator-sv-string_view-literal"></a><a name="op_sv"></a>"" SV işleci (string_view Sabit)

Bir dize sabit değerinden string_view oluşturur. Ad alanı gerektirir `std::literals::string_view_literals` .

### <a name="example"></a>Örnek

```cpp

using namespace std;
using namespace literals::string_view_literals;

    string_view sv{ "Hello"sv };
    wstring_view wsv{ L"Hello"sv };
    u16string_view sv16{ u"Hello"sv };
    u32string_view sv32{ U"Hello"sv };
```

## <a name="see-also"></a>Ayrıca bkz.

[\<string_view>](../standard-library/string-view.md)
