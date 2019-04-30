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
ms.openlocfilehash: 1fbb7faf7d6fc92a053c0f4d47575c5c53c7968e
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64346631"
---
# <a name="ltstringviewgt-operators"></a>&lt;string_view&gt; işleçleri

İki string_view nesnesi veya bir string_view ve başka bir dize nesnesinin karşılaştırmak için bu işleçler kullanın (örneğin [std::string](basic-string-class.md), veya **char\***) için sağlanan bir örtük dönüştürme. 

||||
|-|-|-|
|[operator!=](#op_neq)|[İşleci&gt;](#op_gt)|[İşleci&gt;=](#op_gt_eq)|
|[İşleci&lt;](#op_lt)|[İşleci&lt;&lt;](#op_lt_lt)|[İşleci&lt;=](#op_lt_eq)|
|[operator==](#op_eq_eq)|[işleç""sv](#op_sv)|

## <a name="op_neq"></a> işleç! =

İşlecin sol tarafındaki nesne işlecin sağ tarafındaki nesneye eşit olup olmadığını sınar.

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

*Sol*<br/>
Herhangi bir dönüştürülebilir dize türü veya bir nesne türü `basic_string_view` karşılaştırılmalıdır.

*sağ*<br/>
Herhangi bir dönüştürülebilir dize türü veya bir nesne türü `basic_string_view` karşılaştırılmalıdır.

### <a name="return-value"></a>Dönüş Değeri

**doğru** işlecinin sol tarafındaki nesnesi değilse, lexicographically işlecin sağ tarafındaki nesneye eşitse; Aksi takdirde **false**.

### <a name="remarks"></a>Açıklamalar

Örtük bir dönüştürme var olmalıdır *convertible_string_type* diğer tarafında string_view için. 

Karşılaştırma ikili üzerinde temel karakter sıralarının lexicographical karşılaştırma. Bunlar aynı sayıda öğe varsa ve öğeleri tüm eşitse, iki nesne eşit olur. Aksi takdirde, eşit oldukları.

## <a name="op_eq_eq"></a> işleç ==

İşlecin sol tarafındaki nesnesinin işlecin sağ tarafındaki nesneye eşit olup olmadığını sınar.

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

*Sol*<br/>
Herhangi bir dönüştürülebilir dize türü veya bir nesne türü `basic_string_view` karşılaştırılmalıdır.

*sağ*<br/>
Herhangi bir dönüştürülebilir dize türü veya bir nesne türü `basic_string_view` karşılaştırılmalıdır.

### <a name="return-value"></a>Dönüş Değeri

**doğru** nesnesinin işlecin sol tarafındaki olup olmadığını lexicographically işlecin sağ tarafındaki nesneye eşitse; Aksi takdirde **false**.

### <a name="remarks"></a>Açıklamalar

Örtük bir dönüştürme var olmalıdır *convertible_string_type* diğer tarafında string_view için. 

Karşılaştırma ikili üzerinde temel karakter sıralarının lexicographical karşılaştırma. Bunlar aynı sayıda öğe varsa ve öğeleri tüm eşitse, iki nesne eşit olur.


## <a name="op_lt"></a> İşleci&lt;

İşlecin sol tarafındaki nesne üzerinde doğru sidestring_view nesneden küçük olup olmadığını sınar
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

*Sol*<br/>
Herhangi bir dönüştürülebilir dize türü veya bir nesne türü `basic_string_view` karşılaştırılmalıdır.

*sağ*<br/>
Herhangi bir dönüştürülebilir dize türü veya bir nesne türü `basic_string_view` karşılaştırılmalıdır.

### <a name="return-value"></a>Dönüş Değeri

**doğru** işlecin sol tarafındaki nesnesinin işlecin sağ tarafındaki; nesne lexicographically değerinden olup olmadığını aksi **false**.

### <a name="remarks"></a>Açıklamalar

Örtük bir dönüştürme var olmalıdır *convertible_string_type* diğer tarafında string_view için. 

Karşılaştırma ikili üzerinde temel karakter sıralarının lexicographical karşılaştırma. İlk eşit çift karakterlerin karşılaşıldığında, bu karşılaştırma sonucu döndürülür. Hiçbir eşit olmayan karakterler bulundu, ancak daha kısa bir sıralı, küçük kısa sırası daha uzun. Diğer bir deyişle, "cat" "cats" küçüktür.

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

## <a name="op_lt_eq"></a> İşleci&lt;=

Nesnesinin işlecin sol tarafındaki küçüktür veya eşittir nesnesinin işlecin sağ tarafındaki olup olmadığını sınar.

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

*Sol*<br/>
Herhangi bir dönüştürülebilir dize türü veya bir nesne türü `basic_string_view` karşılaştırılmalıdır.

*sağ*<br/>
Herhangi bir dönüştürülebilir dize türü veya bir nesne türü `basic_string_view` karşılaştırılmalıdır.

### <a name="return-value"></a>Dönüş Değeri

**doğru** işlecinin sol tarafındaki nesne lexicographically daha az daha veya işlecin sağ tarafındaki nesneye eşitse; Aksi halde ise **false**.

### <a name="remarks"></a>Açıklamalar

Bkz: [işleci&lt;](#op_lt).

## <a name="op_lt_lt"></a> İşleci&lt;&lt;

Bir string_view bir çıkış akışına yazar.

```cpp
template <class CharType, class Traits>
inline basic_ostream<CharType, Traits>& operator<<(
    basic_ostream<CharType, Traits>& Ostr, const basic_string_view<CharType, Traits> Str);
```

### <a name="parameters"></a>Parametreler

*Ostr*<br/>
yazılmakta olan bir çıkış akışı.

*str*<br/>
Elem girilmesi string_view.

### <a name="return-value"></a>Dönüş Değeri

yazılmakta olan bir çıkış akışı.

### <a name="remarks"></a>Açıklamalar

Örneğin, bir çıkış akışına bir string_view içeriğini eklemek için bu işleci kullanın [std::cout](iostream.md#cout).

## <a name="op_gt"></a> İşleci&gt;

İşlecin sol tarafındaki nesnesinin işlecin sağ tarafındaki nesneden büyük olup olmadığını sınar.

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

*Sol*<br/>
Herhangi bir dönüştürülebilir dize türü veya bir nesne türü `basic_string_view` karşılaştırılmalıdır.

*sağ*<br/>
Herhangi bir dönüştürülebilir dize türü veya bir nesne türü `basic_string_view` karşılaştırılmalıdır.

### <a name="return-value"></a>Dönüş Değeri

**doğru** nesnesinin işlecin sol tarafındaki olup olmadığını lexicographically string_view nesnesinin işlecin sağ tarafındaki büyük; Aksi takdirde **false**.

### <a name="remarks"></a>Açıklamalar

Bkz: [işleci&lt;](#op_lt).

## <a name="op_gt_eq"></a> İşleci&gt;=

İşlecin sol tarafındaki nesnesinin değerinden büyük veya işlecin sağ tarafındaki nesneye eşit olup olmadığını sınar.

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

*Sol*<br/>
Herhangi bir dönüştürülebilir dize türü veya bir nesne türü `basic_string_view` karşılaştırılmalıdır.

*sağ*<br/>
Herhangi bir dönüştürülebilir dize türü veya bir nesne türü `basic_string_view` karşılaştırılmalıdır.

### <a name="return-value"></a>Dönüş Değeri

**doğru** nesnesinin işlecin sol tarafındaki olup olmadığını lexicographically büyüktür veya işlecin sağ tarafındaki nesneye eşitse; Aksi takdirde **false**.

### <a name="remarks"></a>Açıklamalar

Bkz: [işleci&lt;](#op_lt).

## <a name="op_sv"></a> "işleci" sv (string_view değişmez değer)

Bir dize sabit değerinden bir string_view oluşturur. Ad alanı gerektiriyor `std::literals::string_view_literals`. 

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

[\<string_view>](../standard-library/string-view.md)<br/>
