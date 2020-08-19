---
title: Span sınıfı (C++ Standart Kitaplığı) | Microsoft Docs
ms.date: 05/28/2020
f1_keywords:
- span/std::span
- span/std::span::const_pointer
- span/std::span::const_reference
- span/std::span::difference_type
- span/std::span::element_type
- span/std::span::iterator
- span/std::span::pointer
- span/std::span::reference
- span/std::span::reverse_iterator
- span/std::span::size_type
- span/std::span::value_type
- span/std::span::at
- span/std::span::assign
- span/std::span::back
- span/std::span::begin
- span/std::span::data
- span/std::span::empty
- span/std::span::end
- span/std::span::front
- span/std::span::rbegin
- span/std::span::rend
- span/std::span::size
- span/std::span::size_bytes
- span/std::span::operator=
- span/std::span::operator[]
helpviewer_keywords:
- std::span [C++]
- std::span [C++], const_pointer
- std::span [C++], const_reference
- std::span [C++], difference_type
- std::span [C++], element_type
- std::span [C++], iterator
- std::span [C++], pointer
- std::span [C++], reference
- std::span [C++], reverse_iterator
- std::span [C++], size_type
- std::span [C++], value_type
- std::span [C++], assign
- std::span [C++], at
- std::span [C++], back
- std::span [C++], begin
- std::span [C++], data
- std::span [C++], empty
- std::span [C++], end
- std::span [C++], front
- std::span [C++], rbegin
- std::span [C++], rend
- std::span [C++], size
- std::span [C++], size_bytes
ms.openlocfilehash: 4d5cf7f38d10814b3112a25a8da0e412f0d65093
ms.sourcegitcommit: 1839405b97036891b6e4d37c99def044d6f37eff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/18/2020
ms.locfileid: "88560458"
---
# <a name="span-class-c-standard-library"></a>Span sınıfı (C++ Standart Kitaplığı)

Bitişik nesne dizisi üzerinde basit bir görünüm sağlar. Bir yayılma, bir yerleşik dizide, veya içinde depolanan nesneler gibi bellekte geri düzenlenmiş nesneler üzerinde yinelemek ve dizinlemek için güvenli bir yol sağlar `std::array` `std::vector` .

Genellikle bir işaretçi ve bir dizin kullanarak geri dönüş nesneleri dizisine eriştiğinizde,, `span` daha güvenli, hafif bir alternatiftir.

Öğesinin boyutu, bir `span` şablon bağımsız değişkeni olarak veya belirterek çalışma zamanında belirtilerek derleme zamanında ayarlanabilir `dynamic_extent` .

## <a name="syntax"></a>Syntax

```cpp
template<class T, size_t Extent = dynamic_extent>
class span;
```

### <a name="template-parameters"></a>Şablon parametreleri

`T`\
 Yayılma alanındaki öğelerin türü.

`Extent`\
 Derleme zamanında belirtilmişse, yayılma alanındaki öğelerin sayısı. Aksi takdirde  `std::dynamic_extent` , çalışma zamanında öğe sayısı belirtilecektir.

[Kesinti Kılavuzu](#deduction_guides)

## <a name="members"></a>Üyeler

| **Tür Tanımları** | **Açıklama** |
|-|-|
| [const_pointer](#pointer) | Bir öğe işaretçisinin türü **`const`** . |
| [const_reference](#reference) | Bir öğeye başvuru türü **`const`** . |
| [difference_type](#difference_type) | İki öğe arasındaki işaretli mesafenin türü. |
| [element_type](#element_type) | Span öğesinin türü. |
| [iden](#iterator) | Bir yayılma için yineleyicinin türü. |
| [pointer](#pointer) | Bir öğe için bir işaretçi türü. |
| [başvurunun](#reference) | Bir öğe için bir başvuru türü. |
| [reverse_iterator](#reverse_iterator) | Bir yayılma için ters yineleyicinin türü. |
| [size_type](#size_type) | Yayılma alanındaki iki öğe arasındaki işaretsiz uzaklık sonucunun türü. |
| [value_type](#value_type) | Veya nitelikleri olmayan bir öğenin türü **`const`** **`volatile`** . |
| **Oluşturucular** | **Açıklama** |
|[kapsamı](#span)| Oluşturun `span` .|
| **Yineleyici desteği** | **Açıklama** |
|[başladı](#begin) | Yayılma alanındaki ilk öğeyi gösteren bir yineleyici alır.|
|[erer](#end) | Yayılma alanının sonuna işaret eden bir yineleyici alın. |
|[rbegin](#rbegin) | Yayılma alanının son öğesini işaret eden bir ters Yineleyici alın; diğer bir deyişle, ters çevrilen yayılımın başlangıcıdır.|
|[rend](#rend) | Yayılma alanının önüne işaret eden bir ters Yineleyici alın; diğer bir deyişle, ters çevrilen yayılma alanının sonu.|
| **Erişim öğeleri**| **Açıklama** |
|[Geri](#back) | Yayılma alanındaki son öğeyi alır.|
|[data](#data) | Yayılma alanındaki ilk öğenin adresini alın.|
|[yapılan](#front) | Yayılma alanındaki ilk öğeyi alır.|
|[işlecinde\[\]](#op_at) | Belirtilen konumdaki bir öğeye erişin.|
| **Gözlemciler** | **Açıklama** |
|[empty](#empty)| Yayılımın boş olup olmadığını test edin.|
|[boyutla](#size) | Yayılma alanındaki öğelerin sayısını alır.|
|[size_bytes](#size_bytes) | Yayılımın boyutunu bayt cinsinden alın.|
| **Alt görünümler** | **Açıklama**|
| [adı](#first_view) | Yayılma alanının önüne bir alt yay alın.|
| [soyadına](#last_view) | Yayılma alanının arkasında bir alt Aralık alın.|
| [alt yayılma](#sub_view) | Yayılma alanındaki her yerden bir alt yay alın.|
| **İşleçler** | **Açıklama** |
|[span:: operator =](#op_eq)| Yayılma alanını değiştirin.|
|[span:: işleci\[\]](#op_at)| Belirtilen konumdaki öğeyi alın. |

## <a name="remarks"></a>Açıklamalar

Tüm `span` üye işlevlerinde sabit zaman karmaşıklığı vardır.

Ya da aksine `array` `vector` , bir yayılımın içindeki öğeleri "sahip" olmaz. Bir yayılma, bu nesneler için depolama alanı olmadığından, içindeki öğeler için herhangi bir depolama alanı serbest vermez.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<span>

**Ad alanı:** std

**Derleyici seçeneği:** /std: c + + en son

## <a name="spanback"></a><a name="back"></a> `span::back`

Yayılma alanındaki son öğeyi alır.

```cpp
constexpr reference back() const noexcept;
```

### <a name="return-value"></a>Döndürülen değer

Yayılma alanındaki son öğeye başvuru.

### <a name="example"></a>Örnek

```cpp
#include <span>
#include <iostream>

using namespace std;

int main()
{
    int a[] = { 0,1,2 };
    span<int> mySpan(a);

    cout << mySpan.back();
}
```

```Output
2
```

## <a name="spanbegin"></a><a name="begin"></a> `span::begin`

Yayılma alanındaki ilk öğeyi gösteren bir yineleyici alır.

```cpp
constexpr iterator begin() const noexcept;
```

### <a name="return-value"></a>Döndürülen değer

Yayılma alanındaki ilk öğeyi gösteren bir yineleyici.

### <a name="example"></a>Örnek

```cpp
#include <span>
#include <iostream>

using namespace std;

int main()
{
    int a[] = { 0,1,2 };
    span<int> mySpan(a);

    auto i = mySpan.begin();
    cout << *i;
}
```

```Output
0
```

## <a name="spandata"></a><a name="data"></a> `span::data`

Yayılma verilerinin başlangıcına yönelik bir işaretçi alır.

```cpp
constexpr pointer data() const noexcept;
```

### <a name="return-value"></a>Döndürülen değer

Yayılma alanında depolanan ilk öğe için bir işaretçi.

### <a name="example"></a>Örnek

```cpp
#include <span>
#include <iostream>

using namespace std;

int main()
{
    int a[] = { 0,1,2 };
    span<int> mySpan(a);
    auto i = mySpan.data();
    cout << *i;
}
```

```Output
0
```

## <a name="spandifference_type"></a><a name="difference_type"></a> `span::difference_type`

Bir yayılma içindeki iki öğe arasındaki öğe sayısı.

```cpp
using difference_type = std::ptrdiff_t;
```

### <a name="example"></a>Örnek

```cpp
#include <span>
#include <iostream>

int main()
{
    int a[] = { 0,1,2 };
    span<int> mySpan(a);

    span<int>::difference_type distance = mySpan.end() - mySpan.begin();
    cout << distance << std::endl;
}
```

```Output
3
```

## <a name="spanelement_type"></a><a name="element_type"></a> `span::element_type`

Yayılma alanındaki öğelerin türü.

```cpp
using element_type = T;
```

### <a name="remarks"></a>Açıklamalar

Tür, bir yayılma oluşturulduğunda şablon parametresinden alınır `T` .

### <a name="example"></a>Örnek

```cpp
#include <span>
#include <iostream>

using namespace std;

int main()
{
    int a[] = { 0,1,2 };
    span<int> mySpan(a);

    span<int>::element_type et = mySpan[2];
    cout << et << endl;
}
```

```Output
2
```

## <a name="spanempty"></a><a name="empty"></a> `span::empty`

Yayılımın öğeler içerip içermediğini belirtir.

```cpp
constexpr bool empty() const noexcept;
```

### <a name="return-value"></a>Döndürülen değer

**`true`** İf ise döndürür `this->size() == 0` . Aksi takdirde **`false`** .

### <a name="example"></a>Örnek

```cpp
#include <span>
#include <iostream>

using namespace std;

int main()
{
    int a[] = { 0,1,2 };
    span<int> mySpan(a);
    bool isEmpty = mySpan.empty(); // isEmpty == false
}
```

## <a name="spanend"></a><a name="end"></a> `span::end`

Yayılımın sonuna bir yineleyici alın.

```cpp
constexpr iterator end() const noexcept;
```

### <a name="return-value"></a>Döndürülen değer

Yayılımın sonunun sonuna işaret eden bir yineleyici.

### <a name="remarks"></a>Açıklamalar

`end` , bir yineleyicinin aralığın sonunu geçtiğini test etmek için kullanılır.

Bu yineleyicinin döndürdüğü değere başvurmayın. Yineleyicinin, yayılma alanındaki son öğeden ötesine ulaşılmadığını belirlemek için kullanın.

### <a name="example"></a>Örnek

```cpp
// Iteration
for (auto it = s1.begin(); it != s1.end(); ++it)
{
    cout << *it;
}
```

## <a name="spanfirst"></a><a name="first_view"></a> `span::first`

Bu yayılma alanının önüne alınmış bir alt Aralık alın.

```cpp
constexpr auto first(size_type count) const noexcept;
template <size_t count> constexpr auto first() const noexcept;
```

### <a name="parameters"></a>Parametreler

*biriktirme*\
Bu yayılımın önünden alt yayılmaya yerleştirilecek öğe sayısı.  
Öğe sayısı, aşağıdaki gösterildiği gibi, şablona veya işleve parametre olarak belirtilir.

### <a name="return-value"></a>Döndürülen değer

`count`Bu yayılma alanının önüne öğe içeren bir yayılma.

### <a name="remarks"></a>Açıklamalar

`count`Derleme süresini doğrulamak ve sabit bir kapsamın bir yayılımını döndürdüğünden, yayılma hakkındaki bilgileri korumak mümkün olduğunda bu işlevin şablon sürümünü kullanın.

### <a name="example"></a>Örnek

```cpp
#include <span>
#include <iostream>

using namespace std;

int main()
{
    int a[] = { 0,1,2 };
    span<int> mySpan(a);

    auto first2 = mySpan.first(2);
    cout << "mySpan.first(2): ";
    for (auto& i : first2)
    {
        cout << i;
    }

    cout << "\nmySpan.first<2>: ";
    auto viewSpan = mySpan.first<2>();
    for (auto& i : viewSpan)
    {
        cout << i;
    }
}
```

```Output
mySpan.first(2): 01
mySpan.first<2>: 01
```

## <a name="spanfront"></a><a name="front"></a> `span::front`

Yayılma alanındaki ilk öğeyi alır.

```cpp
constexpr reference front() const noexcept;
```

### <a name="return-value"></a>Döndürülen değer

Yayılma alanındaki ilk öğeye başvuru.

### <a name="example"></a>Örnek

```cpp
#include <span>
#include <iostream>

using namespace std;

int main()
{
    int a[] = { 0,1,2 };
    span<int> mySpan(a);

    auto i = mySpan.front();
    cout << i;
}
```

```Output
0
```

## <a name="spaniterator"></a><a name="iterator"></a> `span::iterator`

Span öğeleri üzerinde bir yineleyici türü.

```cpp
using iterator = implementation-defined-iterator-type;
```

### <a name="remarks"></a>Açıklamalar

Bu tür, bir yayılma içindeki öğeler üzerinde bir yineleyici görevi görür.

### <a name="example"></a>Örnek

```cpp
#include <span>
#include <iostream>

using namespace std;

int main()
{
    int a[] = { 0,1,2 };
    span<int> mySpan(a);

    span<int>::iterator it = mySpan.begin();
    cout << *it++ << *it++ << *it;
}
```

```Output
012
```

## <a name="spanlast"></a><a name="last_view"></a> `span::last`

Bu yayılma alanının sonundan alınan bir alt span alın.

```cpp
constexpr span<element_type, dynamic_extent> last(const size_type count) const noexcept;
template <size_t count> constexpr span<element_type, count> last() const noexcept;
```

### <a name="parameters"></a>Parametreler

*biriktirme*\
Bu yayılma alanının sonundaki öğe sayısı alt yayılmaya konur.
Bu sayı, şablonun bir parametresi olarak veya işlev olarak aşağıda gösterildiği gibi belirtilebilir.

### <a name="return-value"></a>Döndürülen değer

`count`Bu yayılma alanındaki son öğeleri içeren bir yayılma.

### <a name="remarks"></a>Açıklamalar

`count`Derleme süresini doğrulamak ve sabit bir kapsamın bir yayılımını döndürdüğünden, yayılma hakkındaki bilgileri korumak mümkün olduğunda bu işlevin şablon sürümünü kullanın.

### <a name="example"></a>Örnek

```cpp
#include <span>
#include <iostream>

using namespace std;

int main()
{
    int a[] = { 0,1,2 };
    span<int> mySpan(a);

    auto first2 = mySpan.last(2);
    cout << "mySpan.last(2): ";
    for (auto& i : last2)
    {
        cout << i;
    }

    cout << "\nmySpan.last<2>: ";
    auto viewSpan = mySpan.last<2>();
    for (auto& i : viewSpan)
    {
        cout << i;
    }
}
```

```Output
mySpan.last(2): 12
mySpan.last<2>: 12
```

## <a name="spanoperator"></a><a name="op_at"></a> `span::operator[]`

Belirtilen konumdaki yayılma alanındaki öğeyi alır.

```cpp
constexpr reference operator[](size_type offset) const;
```

### <a name="parameters"></a>Parametreler

*konumu*\
Erişim için yayılma alanındaki sıfır tabanlı öğe.

### <a name="return-value"></a>Döndürülen değer

Konum *uzaklığında*öğeye başvuru. Konum geçersizse, davranış tanımsızdır.

### <a name="example"></a>Örnek

```cpp
#include <span>
#include <iostream>

using namespace std;

int main()
{
    int a[] = { 0,1,2 };
    span<int> mySpan(a);
    cout << mySpan[1];
}
```

```Output
1
```

## <a name="spanoperator"></a><a name="op_eq"></a> `span::operator=`

Buna başka bir span atayın.

```cpp
constexpr span& operator=(const span& other) noexcept = default;
```

### <a name="parameters"></a>Parametreler

*farklı*\
Buna atanacak olan Aralık.

### <a name="return-value"></a>Döndürülen değer

`*this`

### <a name="remarks"></a>Açıklamalar

Atama, veri işaretçisinin ve boyutunun basit bir kopyasını yapar. Bir basit kopya, `span` içerdiği öğeler için bellek ayırmadığından güvenlidir.

### <a name="example"></a>Örnek

```cpp
#include <span>
#include <iostream>

using namespace std;

int main()
{
    int a[] = { 0,1,2 };
    span<int> mySpan(a);
    span<int> mySpan2;
    mySpan2 = mySpan;
    for (auto &i : mySpan2)
    {
        cout << it;
    }
}
```

```Output
012
```

## <a name="spanpointer"></a><a name="pointer"></a> `span::pointer`

Bir işaretçiye ve işaretçiye yönelik türler **`const`** , span öğesine.

```cpp
using pointer = T*;
using const_pointer = const T*;
```

### <a name="example"></a>Örnek

```cpp
#include <span>
#include <iostream>

using namespace std;

int main()
{
    int a[] = { 0,1,2 };
    span<int> mySpan(a);

    // pointer
    span<int>::pointer ptr = &mySpan[2];
    *ptr = 9;
    cout << mySpan[2];

    // const pointer
    span<int>::const_pointer cPtr = &mySpan[0];
    // *cPtr = 9; error - const
    cout << *cPtr;
}
```

```Output
90
```

## <a name="spanrbegin"></a><a name="rbegin"></a> `span::rbegin`

Bu yayılma alanının son öğesini işaret eden bir ters Yineleyici alın.

```cpp
constexpr reverse_iterator rbegin() const noexcept;
```

### <a name="return-value"></a>Döndürülen değer

Ters çevrilen yayılımın başlangıcını gösteren bir yineleyici.

### <a name="example"></a>Örnek

```cpp
#include <span>
#include <iostream>

using namespace std;

int main()
{
    int a[] = { 0,1,2 };
    span<int> mySpan(a);

    for (auto rIt = s1.rbegin(); rIt != s1.rend(); ++rIt)
    {
        cout << *rIt;
    }
}
```

```Output
210
```

## <a name="spanreference"></a><a name="reference"></a> `span::reference`

Bir başvuru için türler ve bir başvuru, bir **`const`** span öğesine.

```cpp
using reference = T&;
using const_reference = const T&;
```

### <a name="example"></a>Örnek

```cpp
#include <span>
#include <iostream>

using namespace std;

int main()
{
    int a[] = { 0,1,2 };
    span<int> mySpan(a);

    // reference
    span<int>::reference ref = mySpan[0];
    ref = 9;
    cout << mySpan[0];
    // const reference
    span<int>::const_reference cRef = mySpan[1];
    // cRef = 9; error because const
    cout << cRef;
}
```

```Output
91
```

## <a name="spanrend"></a><a name="rend"></a> `span::rend`

Ters çevrilen yayılımın sonuna işaret eden bir rastgele erişim Yineleyici alın.

```cpp
constexpr reverse_iterator rend() const noexcept;
```

### <a name="return-value"></a>Döndürülen değer

Ters bir yineleyici, ters çevrilen yayılma alanındaki son öğeden sonraki yer tutucudur. diğer bir deyişle, geri alınamaz yayılma alanındaki ilk öğeden önceki yer tutucudur.

### <a name="remarks"></a>Açıklamalar

`rend`[span:: End](#end) bir span ile kullanıldığı için ters çevrilmiş bir yayılma ile kullanılır. Bir ters yineleyicinin, yayılma alanının sonuna ulaşmış olup olmadığını test etmek için bunu kullanın.

Tarafından döndürülen değer `rend` başvurulmamalıdır.

### <a name="example"></a>Örnek

```cpp
#include <span>
#include <iostream>

using namespace std;

int main()
{
    int a[] = { 0,1,2 };
    span<int> mySpan(a);

    for (auto rIt = s1.rbegin(); rIt != s1.rend(); ++rIt)
    {
        cout << *rIt;
    }
}
```

## <a name="spanreverse_iterator"></a><a name="reverse_iterator"></a> `span::reverse_iterator`

Bir yayılma için ters yineleyicinin türü.

```cpp
using reverse_iterator = std::reverse_iterator<iterator>;
```

### <a name="example"></a>Örnek

```cpp
#include <span>
#include <iostream>

int main()
{
    int a[] = { 0,1,2 };
    span<int> mySpan(a);

    span<int>::reverse_iterator rIt = mySpan.rbegin();
    cout << *rIt++ << *rIt++ << *rIt;
}
```

```Output
210
```

## <a name="spansize"></a><a name="size"></a> `span::size`

Yayılma alanındaki öğelerin sayısını alır.

```cpp
constexpr size_t size() const noexcept;
```

### <a name="return-value"></a>Döndürülen değer

Yayılma alanındaki öğelerin sayısı.

### <a name="example"></a>Örnek

```cpp
#include <span>
#include <iostream>

using namespace std;

int main()
{
    int a[] = { 0,1,2 };
    span<int> mySpan(a);
    cout << mySpan.size();
}
```

```Output
3
```

## <a name="spansize_bytes"></a><a name="size_bytes"></a> `span::size_bytes`

Yayılma alanındaki öğelerin boyutunu bayt cinsinden alın.

```cpp
constexpr size_type size_bytes() const noexcept;
```

### <a name="return-value"></a>Döndürülen değer

Yayılma alanındaki tüm öğelerin kaplayacağı bayt sayısı; diğer bir deyişle, `sizeof(element_type)` yayılma alanındaki öğelerin sayısıyla çarpılır.

### <a name="example"></a>Örnek

```cpp
#include <span>
#include <iostream>

using namespace std;

int main()
{
    int a[] = { 0,1,2 };
    span<int> mySpan(a);
    cout << mySpan.size_bytes(); // 3 elements * 4 (size of an int)
}
```

```Output
12
```

## <a name="spansize_type"></a><a name="size_type"></a> `span::size_type`

Bir yayılma alanındaki öğelerin sayısını depolamak için uygun işaretsiz bir tür.

```cpp
using size_type = size_t;
```

### <a name="example"></a>Örnek

```cpp
#include <span>
#include <iostream>

using namespace std;

int main()
{
    int a[] = { 0,1,2 };
    span<int> mySpan(a);

    span<int>::size_type szType = mySpan.size();
    cout << szType;
}
```

```Output
3
```

## <a name="spanspan"></a><a name="span"></a> `span::span`

`span` Kurucu.

```cpp
constexpr span() noexcept
requires (Extent == 0 || Extent == dynamic_extent) = default;

template <class It>
constexpr explicit(Extent != dynamic_extent)
span(It first, size_type count) noexcept

template <class It, class End>
constexpr explicit(Extent != dynamic_extent)
span(It first, End last) noexcept(noexcept(last - first))

template <class T, size_t N>
requires (Extent == dynamic_extent || Extent == N) && is_convertible_v<T (*)[], T (*)[]>
constexpr span(array<T, N>& arr) noexcept

template <class T, size_t N>
requires (Extent == dynamic_extent || Extent == N) && is_convertible_v<const T (*)[], T (*)[]>
constexpr span(const array<T, N>& arr) noexcept

template <size_t N>
requires (Extent == dynamic_extent || Extent == N)
constexpr span(type_identity_t<T> (&arr)[N]) noexcept

template <class R>
constexpr explicit(Extent != dynamic_extent)
span(R&& r)

// default copy ctor
constexpr span(const span& other) noexcept = default;

// converting  ctor
template <class T, size_t OtherExtent>
requires (Extent == dynamic_extent || OtherExtent == dynamic_extent ||
              Extent == OtherExtent) && is_convertible_v<T (*)[], T (*)[]>
constexpr explicit(Extent != dynamic_extent && OtherExtent == dynamic_extent)
span(const span<T, OtherExtent>& other) noexcept
```

### <a name="parameters"></a>Parametreler

*ARR*\
Diziden bir span oluşturun.

*biriktirme*\
Yayılma alanında olacak öğe sayısı.

*adı*\
Yayılma alanındaki ilk öğeye Yineleyici.

*soyadına*\
Yalnızca yayılma alanındaki son öğeyi geçen Yineleyici.

*No*\
Yayılma alanında olacak öğe sayısı.

*farklı*\
Bu yayılma alanının bir kopyasını oluşturun.

*sağ*\
Bu aralıktan bir span oluşturun.

### <a name="remarks"></a>Açıklamalar

Yayılma, içindeki nesneler üzerinde depolama alanı olmadığından, yayılma alanındaki öğeler için depolama alanı serbest vermez.

|Oluşturucu  | Açıklama  |
|---------|---------|
|`span()` | Boş bir yayılma oluşturun. Yalnızca şablon parametresi veya olduğunda aşırı yükleme çözümlemesi sırasında göz önünde bulundurululur `Extent` `0` `dynamic_extent` .|
|`span(It first, size_type count)` | `count`Yineleyiciden ilk öğeden bir span oluşturun `first` .  Yalnızca şablon parametresi olmadığında aşırı yükleme çözümlemesi sırasında kabul edilir `Extent` `dynamic_extent` . |
|`span(It first, End last)` | `first`Sona ulaşılana kadar Yineleyici içindeki öğelerden bir Aralık oluşturun `last` . Yalnızca şablon parametresi olmadığında aşırı yükleme çözümlemesi sırasında kabul edilir `Extent` `dynamic_extent` . `It` bir olmalıdır `contiguous_iterator` .  |
|`span(array<T, N>& arr) noexcept;`<br /><br />`span(const array<T, N>& arr) noexcept;`<br /><br />`span(type_identity_t<element_type> (&arr)[N]) noexcept;` |  Belirtilen dizinin öğelerinden bir yayılma alanı oluşturun `N` . Yalnızca şablon parametresi veya eşitse aşırı yükleme çözümlemesi sırasında kabul edilir `Extent` `dynamic_extent` `N` . |
|`span(R&& r)` |  Bir aralıktan yayılma oluşturun. Yalnızca şablon parametresi değilse aşırı yükleme çözümüne katılır `Extent` `dynamic_extent` .|
|`span(const span& other)` |  Derleyici tarafından oluşturulan kopya Oluşturucu. Yayılma, öğeleri tutacak belleği ayırmadığından, veri işaretçisinin basit bir kopyası güvenlidir. |
|`span(const span<OtherElementType, OtherExtent>& s) noexcept;` | Oluşturucu dönüştürülüyor: başka bir yayılma alanından yayılma oluşturun. Yalnızca şablon parametresi veya eşitse aşırı yükleme çözümüne `Extent` katılır `dynamic_extent` `N` `dynamic_extent` `Extent` .|

### <a name="example"></a>Örnek

```cpp
#include <span>

using namespace std;

int main()
{
    const int MAX=10;

    int x[MAX];
    for (int i = 0; i < MAX; i++)
    {
        x[i] = i;
    }

    span<int, MAX> span1{ x }; // fixed-size span: compiler error if size of x doesn't match template argument MAX
    span<int> span2{ x }; // size is inferred from x
    span<const int> span3 = span2; // converting constructor
    span<int> span4( span2 ); // copy constructor
}
```

## <a name="spansubspan"></a><a name="sub_view"></a> `span::subspan`

Bu yayılımın bir alt yayılımını alın.

```cpp
constexpr auto subspan(size_type offset, size_type count = dynamic_extent) const noexcept;

template <size_t offset, size_t count = dynamic_extent>
constexpr auto subspan() const noexcept
```

### <a name="parameters"></a>Parametreler

*biriktirme*\
Alt yayılmaya yerleştirilecek öğe sayısı. İse `count` `dynamic_extent` (varsayılan değer), alt span `offset` Bu yayılma alanının sonuna kadar alınır.

*konumu*\
Alt yayılma alanını başlatmak için bu yayılma alanındaki konum.

### <a name="return-value"></a>Döndürülen değer

`offset`Bu yayılmadan başlayarak bir yayılma. `count`Öğeleri içerir.

### <a name="remarks"></a>Açıklamalar

Bu işlevin bir şablon sürümü, derleme zamanında sayımı denetleyen, sabit bir kapsamın bir yayılımını döndürerek yayılma hakkındaki bilgileri koruyan kullanılabilir.

### <a name="example"></a>Örnek

```cpp
#include <span>
#include <iostream>

using namespace std;

int main()
{
    int a[] = { 0,1,2 };
    span<int> mySpan(a);

    cout << "mySpan.subspan(1,2): ";
    for (auto& i : mySpan.subspan(1,2))
    {
        cout << i;
    }
    cout << "\nmySpan.subspan<1,2>: ";
    for (auto& i : mySpan.subspan<1,2>())
    {
        cout << i;
    }
    cout << "\nmySpan.subspan<1>: ";
    for (auto& i : mySpan.subspan<1>)
    {
        cout << i;
    }
}
```

```Output
mySpan.subspan(1,2): 12
mySpan.subspan<1,2>: 12
mySpan.subspan<1>: 12
```

## <a name="spanvalue_type"></a><a name="value_type"></a> `span::value_type`

Yayılma alanındaki, veya nitelikleri olmadan öğenin türü **`const`** **`volatile`** .

```cpp
using value_type = std::remove_cv_t<T>;
```

### <a name="example"></a>Örnek

```cpp
#include <span>
#include <iostream>

using namespace std;

int main()
{
    int a[] = { 0,1,2 };
    span<int> mySpan(a);

    span<int>::value_type vType = mySpan[2];
    cout << vType;
}
```

```Output
2
```

## <a name="deduction-guides"></a><a name="deduction_guides"></a> Kesinti Kılavuzu

Yayılma için aşağıdaki kesinti yönergeleri verilmiştir.

```cpp
// Allows the extent to be deduced from std::array and C++ built-in arrays

template <class T, size_t Extent>
span(T (&)[Extent]) -> span<T, Extent>;

template <class T, size_t Size>
span(array<T, Size>&) -> span<T, Size>;

template <class T, size_t Size>
span(const array<T, Size>&) -> span<const T, Size>;

// Allows the element type to be deduced from the iterator and the end of the span.
// The iterator must be contiguous

template <contiguous_iterator It, class End>
span(It, End) -> span<remove_reference_t<iter_reference_t<It>>>;

// Allows the element type to be deduced from a range.
// The range must be contiguous

template <ranges::contiguous_range Rng>
span(Rng &&) -> span<remove_reference_t<ranges::range_reference_t<Rng>>>;
```

## <a name="see-also"></a>Ayrıca bkz.

[\<span>](../standard-library/span.md)  
[Sınıf şablonu bağımsız değişken kesintiyi kullanma](https://devblogs.microsoft.com/cppblog/how-to-use-class-template-argument-deduction/)
