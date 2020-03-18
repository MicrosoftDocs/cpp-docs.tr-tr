---
title: '&lt;string_view&gt; işleçleri'
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
ms.openlocfilehash: 871b7dc93f5d548897cf77e55dbacf5a104cbee9
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79446759"
---
# <a name="ltstring_viewgt-operators"></a>&lt;string_view&gt; işleçleri

Örtük bir dönüştürmenin sağlandığı iki string_view nesnesini veya bir string_view ve diğer bir dize nesnesini (örneğin, [std:: String](basic-string-class.md)veya **char\*** ) karşılaştırmak için bu işleçleri kullanın. 

||||
|-|-|-|
|[operator!=](#op_neq)|[işleç&gt;](#op_gt)|[işleç&gt;=](#op_gt_eq)|
|[işleç&lt;](#op_lt)|[işleç&lt;&lt;](#op_lt_lt)|[işleç&lt;=](#op_lt_eq)|
|[işleç = =](#op_eq_eq)|["" SV işleci](#op_sv)|

## <a name="op_neq"></a>işleç! =

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

*sol*\
Herhangi bir dönüştürülebilir dize türü veya Karşılaştırılacak `basic_string_view` türü bir nesne.

*sağ*\
Herhangi bir dönüştürülebilir dize türü veya Karşılaştırılacak `basic_string_view` türü bir nesne.

### <a name="return-value"></a>Dönüş Değeri

işlecin sol tarafındaki nesne sağ taraftaki nesneye sözcüıgrafik eşit değilse **true** ; Aksi halde **yanlış**.

### <a name="remarks"></a>Açıklamalar

Kapalı bir dönüştürme *convertible_string_type* diğer taraftaki string_view arasında bulunmalıdır. 

Karşılaştırma, karakter sıralarının ikili bir lexıgraf karşılaştırmasını temel alır. Aynı sayıda öğe varsa ve öğelerin tümü eşitse, iki nesne eşittir. Aksi takdirde, bunlar eşit değildir.

## <a name="op_eq_eq"></a>işleç = =

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

*sol*\
Herhangi bir dönüştürülebilir dize türü veya Karşılaştırılacak `basic_string_view` türü bir nesne.

*sağ*\
Herhangi bir dönüştürülebilir dize türü veya Karşılaştırılacak `basic_string_view` türü bir nesne.

### <a name="return-value"></a>Dönüş Değeri

işlecin sol tarafındaki nesne sağ taraftaki nesneye sözcüıgrafik eşitse **true** ; Aksi halde **yanlış**.

### <a name="remarks"></a>Açıklamalar

Kapalı bir dönüştürme *convertible_string_type* diğer taraftaki string_view arasında bulunmalıdır. 

Karşılaştırma, karakter sıralarının ikili bir lexıgraf karşılaştırmasını temel alır. Aynı sayıda öğe varsa ve öğelerin tümü eşitse, iki nesne eşittir.


## <a name="op_lt"></a>işleç&lt;

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

*sol*\
Herhangi bir dönüştürülebilir dize türü veya Karşılaştırılacak `basic_string_view` türü bir nesne.

*sağ*\
Herhangi bir dönüştürülebilir dize türü veya Karşılaştırılacak `basic_string_view` türü bir nesne.

### <a name="return-value"></a>Dönüş Değeri

işlecin sol tarafındaki nesne sağ taraftaki nesnenin lexıgrafik değerinden küçükse **true** ; Aksi halde **yanlış**.

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

## <a name="op_lt_eq"></a>işleç&lt;=

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

*sol*\
Herhangi bir dönüştürülebilir dize türü veya Karşılaştırılacak `basic_string_view` türü bir nesne.

*sağ*\
Herhangi bir dönüştürülebilir dize türü veya Karşılaştırılacak `basic_string_view` türü bir nesne.

### <a name="return-value"></a>Dönüş Değeri

işlecin sol tarafındaki nesne sağ taraftaki nesneye sözcüıgrafik veya daha küçükse **true** ; Aksi halde **yanlış**.

### <a name="remarks"></a>Açıklamalar

Bkz. [operatör&lt;](#op_lt).

## <a name="op_lt_lt"></a>işleç&lt;&lt;

Çıkış akışına bir string_view yazar.

```cpp
template <class CharType, class Traits>
inline basic_ostream<CharType, Traits>& operator<<(
    basic_ostream<CharType, Traits>& Ostr, const basic_string_view<CharType, Traits> Str);
```

### <a name="parameters"></a>Parametreler

*OSTR*\
yazılan çıkış akışı.

*Str*\
Bir çıkış akışına girilecek string_view.

### <a name="return-value"></a>Dönüş Değeri

yazılan çıkış akışı.

### <a name="remarks"></a>Açıklamalar

Bir string_view içeriğini bir çıkış akışına eklemek için, örneğin [std:: cout](iostream.md#cout)kullanarak bu işleci kullanın.

## <a name="op_gt"></a>işleç&gt;

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

*sol*\
Herhangi bir dönüştürülebilir dize türü veya Karşılaştırılacak `basic_string_view` türü bir nesne.

*sağ*\
Herhangi bir dönüştürülebilir dize türü veya Karşılaştırılacak `basic_string_view` türü bir nesne.

### <a name="return-value"></a>Dönüş Değeri

işlecin sol tarafındaki nesne sağ taraftaki string_view nesnesinden sözcüıgrafik büyükse **true** . Aksi halde **yanlış**.

### <a name="remarks"></a>Açıklamalar

Bkz. [operatör&lt;](#op_lt).

## <a name="op_gt_eq"></a>işleç&gt;=

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

*sol*\
Herhangi bir dönüştürülebilir dize türü veya Karşılaştırılacak `basic_string_view` türü bir nesne.

*sağ*\
Herhangi bir dönüştürülebilir dize türü veya Karşılaştırılacak `basic_string_view` türü bir nesne.

### <a name="return-value"></a>Dönüş Değeri

işlecin sol tarafındaki nesne sağ taraftaki nesneye sözcüıgrafik büyükse veya buna eşitse **true** ; Aksi halde **yanlış**.

### <a name="remarks"></a>Açıklamalar

Bkz. [operatör&lt;](#op_lt).

## <a name="op_sv"></a>"" SV işleci (string_view Sabit)

Bir dize sabit değerinden string_view oluşturur. Ad alanı `std::literals::string_view_literals`gerektirir. 

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

[\<string_view >](../standard-library/string-view.md)
