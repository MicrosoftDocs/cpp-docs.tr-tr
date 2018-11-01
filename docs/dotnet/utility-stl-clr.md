---
title: yardımcı program (STL/CLR)
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- <cliext/utility>
- cliext::pair
- cliext::pair::pair
- cliext::pair::first
- cliext::pair::first_type
- cliext::pair::second
- cliext::pair::second_type
- cliext::pair::swap
- cliext::make_pair
- cliext::pair::operator=
- cliext::pair::operator==
- cliext::pair::operator>=
- cliext::pair::operator>
- cliext::pair::operator!=
- cliext::pair::operator<=
- cliext::pair::operator<
helpviewer_keywords:
- <utility> header [STL/CLR]
- utility header [STL/CLR]
- <cliext/utility> header [STL/CLR]
- first member [STL/CLR]
- first_type member [STL/CLR]
- second member [STL/CLR]
- second_type member [STL/CLR]
- swap member [STL/CLR]
- make_pair function [STL/CLR]
- pair class [STL/CLR]
- pair member [STL/CLR]
- operator== member [STL/CLR]
- operator= member [STL/CLR]
- operator>= member [STL/CLR]
- operator> member [STL/CLR]
- operator!= member [STL/CLR]
- operator<= member [STL/CLR]
- operator< member [STL/CLR]
ms.assetid: fb48cb75-d5ef-47ce-b526-bf60dc86c552
ms.openlocfilehash: 817e4224e926ea305312aaebc6d94bc19e51e82f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50633580"
---
# <a name="utility-stlclr"></a>yardımcı program (STL/CLR)

STL/CLR üstbilgisini `<cliext/utility>` şablon sınıfını tanımlamak için `pair` ve çeşitli destekleyici şablon işlevleri.

## <a name="syntax"></a>Sözdizimi

```cpp
#include <utility>
```

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<cliext/yardımcı programı >

**Namespace:** cliext

## <a name="declarations"></a>Bildirimler

|örneği|Açıklama|
|-----------|-----------------|
|[pair (STL/CLR)](#pair)|Bir öğe çiftinin kaydır.|

|İşleç|Açıklama|
|--------------|-----------------|
|[operator== (pair) (STL/CLR)](#op_eq)|Karşılaştırma çifti eşit.|
|[operator!= (pair) (STL/CLR)](#op_neq)|Eşit değildir karşılaştırma eşleştirin.|
|[operator< (pair) (STL/CLR)](#op_lt)|Çifti karşılaştırma küçüktür.|
|[İşleç\<(eşleştirmesi) (STL/CLR)](#op_lteq)|Küçüktür veya eşittir pair karşılaştırma.|
|[operator> (pair) (STL/CLR)](#op_gt)|Çifti karşılaştırma büyük.|
|[operator>= (pair) (STL/CLR)](#op_gteq)|Çifti büyüktür veya eşittir karşılaştırma.|

|İşlev|Açıklama|
|--------------|-----------------|
|[make_pair (STL/CLR)](#make_pair)|Bir çift değer çiftinden olun.|

## <a name="members"></a>Üyeler

##<a name="pair"></a> çift (STL/CLR)
Şablon sınıfı, değer çiftinin sarmalayan bir nesne tanımlar.

### <a name="syntax"></a>Sözdizimi

```cpp
template<typename Value1,
    typename Value2>
    ref class pair;
```

#### <a name="parameters"></a>Parametreler

*Değer1*<br/>
İlk sarılan değer türü.

*Value2*<br/>
İkinci sarılan değer türü.

## <a name="members"></a>Üyeler

|Tür Tanımlaması|Açıklama|
|---------------------|-----------------|
|[pair::first_type (STL/CLR)](#first_type)|İlk sarılan değer türü.|
|[pair::second_type (STL/CLR)](#second_type)|İkinci sarılan değer türü.|

|Üye nesnesi|Açıklama|
|-------------------|-----------------|
|[pair::first (STL/CLR)](#first)|İlk değeri depolanır.|
|[pair::second (STL/CLR)](#second)|İkinci depolanan değeri.|

|Üye İşlevi|Açıklama|
|---------------------|-----------------|
|[pair::pair (STL/CLR)](#pair_pair)|Çifti nesnesi oluşturur.|
|[pair::swap (STL/CLR)](#swap)|İki çiftleri içeriğini değiştirir.|

|İşleç|Açıklama|
|--------------|-----------------|
|[pair::operator= (STL/CLR)](#op_as)|Depolanan değer çiftini değiştirir.|

## <a name="remarks"></a>Açıklamalar

Bir değer çifti nesnesini depolar. Bu şablon sınıfının iki değerleri tek bir nesnede birleştirmek için kullanın. Ayrıca, nesne `cliext::pair` (aşağıda açıklanmıştır) yalnızca yönetilen türleri; türleri kullanın bir çift yönetilmeyen depolama `std::pair`bildirilen `<utility>`.

## <a name="first"></a> pair::First (STL/CLR)

İlk sarılan değer.

### <a name="syntax"></a>Sözdizimi

```cpp
Value1 first;
```

### <a name="remarks"></a>Açıklamalar

Nesne ilk sarılan değer depolar.

### <a name="example"></a>Örnek

```cpp
// cliext_pair_first.cpp
// compile with: /clr
#include <cliext/utility>

int main()
    {
    cliext::pair<wchar_t, int> c1(L'x', 3);
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);

    cliext::pair<wchar_t, int>::first_type first_val = c1.first;
    cliext::pair<wchar_t, int>::second_type second_val = c1.second;
    System::Console::WriteLine("[{0}, {1}]", first_val, second_val);
    return (0);
    }
```

```Output
[x, 3]
```

## <a name="first_type"></a> pair::first_type (STL/CLR)

İlk sarılan değer türü.

### <a name="syntax"></a>Sözdizimi

```cpp
typedef Value1 first_type;
```

### <a name="remarks"></a>Açıklamalar

Şablon parametresi için bir eşanlamlı türüdür *Value1*.

### <a name="example"></a>Örnek

```cpp
// cliext_pair_first_type.cpp
// compile with: /clr
#include <cliext/utility>

int main()
    {
    cliext::pair<wchar_t, int> c1(L'x', 3);
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);

    cliext::pair<wchar_t, int>::first_type first_val = c1.first;
    cliext::pair<wchar_t, int>::second_type second_val = c1.second;
    System::Console::WriteLine("[{0}, {1}]", first_val, second_val);
    return (0);
    }
```

```Output
[x, 3]
```

## <a name="op_as"></a> pair::operator (STL/CLR) =

Depolanan değer çiftini değiştirir.

### <a name="syntax"></a>Sözdizimi

```cpp
pair<Value1, Value2>% operator=(pair<Value1, Value2>% right);
```

#### <a name="parameters"></a>Parametreler

*sağ*<br/>
Kopyalanacak çifti.

### <a name="remarks"></a>Açıklamalar

Üye işleci kopyaları *doğru* ardından nesneye döndürür `*this`. Saklı değerler çiftinin bir kopyasını depolanan değer çiftinin değiştirmek için kullandığınız *doğru*.

### <a name="example"></a>Örnek

```cpp
// cliext_pair_operator_as.cpp
// compile with: /clr
#include <cliext/utility>

int main()
    {
    cliext::pair<wchar_t, int> c1(L'x', 3);
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);

// assign to a new pair
    cliext::pair<wchar_t, int> c2;
    c2 = c1;
    System::Console::WriteLine("[{0}, {1}]", c2.first, c2.second);
    return (0);
    }
```

```Output
[x, 3]
[x, 3]
```

## <a name="pair_pair"></a> pair::pair (STL/CLR)

Çifti nesnesi oluşturur.

### <a name="syntax"></a>Sözdizimi

```cpp
pair();
pair(pair<Coll>% right);
pair(pair<Coll>^ right);
pair(Value1 val1, Value2 val2);
```

#### <a name="parameters"></a>Parametreler

*sağ*<br/>
Depolamak için çifti.

*val1*<br/>
Depolamak için ilk değer.

*Val2*<br/>
Depolamak için ikinci değer.

### <a name="remarks"></a>Açıklamalar

Oluşturucu:

`pair();`

saklı çifti oluşturulmuş varsayılan değerlerle başlatır.

Oluşturucu:

`pair(pair<Value1, Value2>% right);`

saklı çifti ile başlatır `right.` [pair::first (STL/CLR)](../dotnet/pair-first-stl-clr.md) ve `right.` [pair::second (STL/CLR)](../dotnet/pair-second-stl-clr.md).

`pair(pair<Value1, Value2>^ right);`

saklı çifti ile başlatır `right->` [pair::first (STL/CLR)](../dotnet/pair-first-stl-clr.md) ve `right>` [pair::second (STL/CLR)](../dotnet/pair-second-stl-clr.md).

Oluşturucu:

`pair(Value1 val1, Value2 val2);`

saklı çifti ile başlatır *val1* ve *val2*.

### <a name="example"></a>Örnek

```cpp
// cliext_pair_construct.cpp
// compile with: /clr
#include <cliext/utility>

int main()
    {
// construct an empty container
    cliext::pair<wchar_t, int> c1;
    System::Console::WriteLine("[{0}, {1}]",
        c1.first == L'\0' ? "\\0" : "??", c1.second);

// construct with a pair of values
    cliext::pair<wchar_t, int> c2(L'x', 3);
    System::Console::WriteLine("[{0}, {1}]", c2.first, c2.second);

// construct by copying another pair
    cliext::pair<wchar_t, int> c3(c2);
    System::Console::WriteLine("[{0}, {1}]", c3.first, c3.second);

// construct by copying a pair handle
    cliext::pair<wchar_t, int> c4(%c3);
    System::Console::WriteLine("[{0}, {1}]", c4.first, c4.second);

    return (0);
    }
```

```Output
[\0, 0]
[x, 3]
[x, 3]
[x, 3]
```

## <a name="second"></a> pair::Second (STL/CLR)

İkinci değer kaydırılır.

### <a name="syntax"></a>Sözdizimi

```cpp
Value2 second;
```

### <a name="remarks"></a>Açıklamalar

Nesneyi ikinci sarılan değer depolar.

### <a name="example"></a>Örnek

```cpp
// cliext_pair_second.cpp
// compile with: /clr
#include <cliext/utility>

int main()
    {
    cliext::pair<wchar_t, int> c1(L'x', 3);
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);

    cliext::pair<wchar_t, int>::first_type first_val = c1.first;
    cliext::pair<wchar_t, int>::second_type second_val = c1.second;
    System::Console::WriteLine("[{0}, {1}]", first_val, second_val);
    return (0);
    }
```

```Output
[x, 3]
```

## <a name="second_type"></a> pair::second_type (STL/CLR)

İkinci sarılan değer türü.

### <a name="syntax"></a>Sözdizimi

```cpp
typedef Value2 second_type;
```

### <a name="remarks"></a>Açıklamalar

Şablon parametresi için bir eşanlamlı türüdür *Value2*.

### <a name="example"></a>Örnek

```cpp
// cliext_pair_second_type.cpp
// compile with: /clr
#include <cliext/utility>

int main()
    {
    cliext::pair<wchar_t, int> c1(L'x', 3);
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);

    cliext::pair<wchar_t, int>::first_type first_val = c1.first;
    cliext::pair<wchar_t, int>::second_type second_val = c1.second;
    System::Console::WriteLine("[{0}, {1}]", first_val, second_val);
    return (0);
    }
```

```Output
[x, 3]
```

## <a name="swap"></a> pair::Swap (STL/CLR)

İki çiftleri içeriğini değiştirir.

### <a name="syntax"></a>Sözdizimi

```cpp
void swap(pair<Value1, Value2>% right);
```

#### <a name="parameters"></a>Parametreler

*sağ*<br/>
İçeriklerini takas çifti.

### <a name="remarks"></a>Açıklamalar

Üye işlevi değiştirir saklanan değer çifti arasında `*this` ve *doğru*.

### <a name="example"></a>Örnek

```cpp
// cliext_pair_swap.cpp
// compile with: /clr
#include <cliext/adapter>
#include <cliext/deque>

typedef cliext::collection_adapter<
    System::Collections::ICollection> Mycoll;
int main()
    {
    cliext::deque<wchar_t> d1;
    d1.push_back(L'a');
    d1.push_back(L'b');
    d1.push_back(L'c');
    Mycoll c1(%d1);

// display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// construct another container with repetition of values
    cliext::deque<wchar_t> d2(5, L'x');
    Mycoll c2(%d2);
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// swap and redisplay
    c1.swap(c2);
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
x x x x x
x x x x x
a b c
```

## <a name="make_pair"></a> make_pair (STL/CLR)

Olun bir `pair` gelen bir değer çifti.

### <a name="syntax"></a>Sözdizimi

```cpp
template<typename Value1,
    typename Value2>
    pair<Value1, Value2> make_pair(Value1 first, Value2 second);
```

#### <a name="parameters"></a>Parametreler

*Değer1*<br/>
İlk sarılan değer türü.

*Value2*<br/>
İkinci sarılan değer türü.

*ilk*<br/>
Kaydırmak için ilk değer.

*Saniye*<br/>
Kaydırmak için ikinci değer.

### <a name="remarks"></a>Açıklamalar

Şablon işlevinin döndürdüğü `pair<Value1, Value2>(first, second)`. Oluşturmak için kullandığınız bir `pair<Value1, Value2>` nesneden bir değer çifti.

### <a name="example"></a>Örnek

```cpp
// cliext_make_pair.cpp
// compile with: /clr
#include <cliext/utility>

int main()
    {
    cliext::pair<wchar_t, int> c1(L'x', 3);
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);

    c1 = cliext::make_pair(L'y', 4);
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);
    return (0);
    }
```

```Output
[x, 3]
[y, 4]
```

## <a name="op_neq"></a> işleç! = (çifti) (STL/CLR)

Eşit değildir karşılaştırma eşleştirin.

### <a name="syntax"></a>Sözdizimi

```cpp
template<typename Value1,
    typename Value2>
    bool operator!=(pair<Value1, Value2>% left,
        pair<Value1, Value2>% right);
```

#### <a name="parameters"></a>Parametreler

*Sol*<br/>
Karşılaştırılacak sol çifti.

*sağ*<br/>
Karşılaştırılacak doğru çifti.

### <a name="remarks"></a>Açıklamalar

İşleç işlevini döndürür `!(left == right)`. Test etmek için kullandığınız olmadığını *sol* aynı sıralı değil *doğru* iki çiftleri karşılaştırılan öğe öğe olduğunda.

### <a name="example"></a>Örnek

```cpp
// cliext_pair_operator_ne.cpp
// compile with: /clr
#include <cliext/utility>

int main()
    {
    cliext::pair<wchar_t, int> c1(L'x', 3);
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);
    cliext::pair<wchar_t, int> c2(L'x', 4);
    System::Console::WriteLine("[{0}, {1}]", c2.first, c2.second);

    System::Console::WriteLine("[x 3] != [x 3] is {0}",
        c1 != c1);
    System::Console::WriteLine("[x 3] != [x 4] is {0}",
        c1 != c2);
    return (0);
    }
```

```Output
[x, 3]
[x, 4]
[x 3] != [x 3] is False
[x 3] != [x 4] is True
```

## <a name="op_lt"></a> İşleç&lt; (çifti) (STL/CLR)

Çifti karşılaştırma küçüktür.

### <a name="syntax"></a>Sözdizimi

```cpp
template<typename Value1,
    typename Value2>
    bool operator<(pair<Value1, Value2>% left,
        pair<Value1, Value2>% right);
```

#### <a name="parameters"></a>Parametreler

*Sol*<br/>
Karşılaştırılacak sol çifti.

*sağ*<br/>
Karşılaştırılacak doğru çifti.

### <a name="remarks"></a>Açıklamalar

İşleç işlevini döndürür `left.first <` `right.first || !(right.first <` `left.first &&` `left.second <` `right.second`. Test etmek için kullandığınız olmadığını *sol* sıralanır önce *doğru* iki çiftleri karşılaştırılan öğe öğe olduğunda.

### <a name="example"></a>Örnek

```cpp
// cliext_pair_operator_lt.cpp
// compile with: /clr
#include <cliext/utility>

int main()
    {
    cliext::pair<wchar_t, int> c1(L'x', 3);
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);
    cliext::pair<wchar_t, int> c2(L'x', 4);
    System::Console::WriteLine("[{0}, {1}]", c2.first, c2.second);

    System::Console::WriteLine("[x 3] < [x 3] is {0}",
        c1 < c1);
    System::Console::WriteLine("[x 3] < [x 4] is {0}",
        c1 < c2);
    return (0);
    }
```

```Output
[x, 3]
[x, 4]
[x 3] < [x 3] is False
[x 3] < [x 4] is True
```

## <a name="op_lteq"></a> İşleç&lt;(eşleştirmesi) (STL/CLR)

Küçüktür veya eşittir pair karşılaştırma.

### <a name="syntax"></a>Sözdizimi

```cpp
template<typename Value1,
    typename Value2>
    bool operator<=(pair<Value1, Value2>% left,
        pair<Value1, Value2>% right);
```

#### <a name="parameters"></a>Parametreler

*Sol*<br/>
Karşılaştırılacak sol çifti.

*sağ*<br/>
Karşılaştırılacak doğru çifti.

### <a name="remarks"></a>Açıklamalar

İşleç işlevini döndürür `!(right < left)`. Test etmek için kullandığınız olmadığını *sol* sonra sıralı değil *doğru* iki çiftleri karşılaştırılan öğe öğe olduğunda.

### <a name="example"></a>Örnek

```cpp
// cliext_pair_operator_le.cpp
// compile with: /clr
#include <cliext/utility>

int main()
    {
    cliext::pair<wchar_t, int> c1(L'x', 3);
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);
    cliext::pair<wchar_t, int> c2(L'x', 4);
    System::Console::WriteLine("[{0}, {1}]", c2.first, c2.second);

    System::Console::WriteLine("[x 3] <= [x 3] is {0}",
        c1 <= c1);
    System::Console::WriteLine("[x 4] <= [x 3] is {0}",
        c2 <= c1);
    return (0);
    }
```

```Output
[x, 3]
[x, 4]
[x 3] <= [x 3] is True
[x 4] <= [x 3] is False
```

## <a name="op_eq"></a> işleç == (çifti) (STL/CLR)

Karşılaştırma çifti eşit.

### <a name="syntax"></a>Sözdizimi

```cpp
template<typename Value1,
    typename Value2>
    bool operator==(pair<Value1, Value2>% left,
        pair<Value1, Value2>% right);
```

#### <a name="parameters"></a>Parametreler

*Sol*<br/>
Karşılaştırılacak sol çifti.

*sağ*<br/>
Karşılaştırılacak doğru çifti.

### <a name="remarks"></a>Açıklamalar

İşleç işlevini döndürür `left.first ==` `right.first &&` `left.second ==` `right.second`. Test etmek için kullandığınız olmadığını *sol* aynı sıralı *doğru* iki çiftleri karşılaştırılan öğe öğe olduğunda.

### <a name="example"></a>Örnek

```cpp
// cliext_pair_operator_eq.cpp
// compile with: /clr
#include <cliext/utility>

int main()
    {
    cliext::pair<wchar_t, int> c1(L'x', 3);
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);
    cliext::pair<wchar_t, int> c2(L'x', 4);
    System::Console::WriteLine("[{0}, {1}]", c2.first, c2.second);

    System::Console::WriteLine("[x 3] == [x 3] is {0}",
        c1 == c1);
    System::Console::WriteLine("[x 3] == [x 4] is {0}",
        c1 == c2);
    return (0);
    }
```

```Output
[x, 3]
[x, 4]
[x 3] == [x 3] is True
[x 3] == [x 4] is False
```

## <a name="op_gt"></a> İşleç&gt; (çifti) (STL/CLR)

Çifti karşılaştırma büyük.

### <a name="syntax"></a>Sözdizimi

```cpp
template<typename Value1,
    typename Value2>
    bool operator>(pair<Value1, Value2>% left,
        pair<Value1, Value2>% right);
```

#### <a name="parameters"></a>Parametreler

*Sol*<br/>
Karşılaştırılacak sol çifti.

*sağ*<br/>
Karşılaştırılacak doğru çifti.

### <a name="remarks"></a>Açıklamalar

İşleç işlevini döndürür `right` `<` `left`. Test etmek için kullandığınız olmadığını *sol* sonra sıralı *doğru* iki çiftleri karşılaştırılan öğe öğe olduğunda.

### <a name="example"></a>Örnek

```cpp
// cliext_pair_operator_gt.cpp
// compile with: /clr
#include <cliext/utility>

int main()
    {
    cliext::pair<wchar_t, int> c1(L'x', 3);
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);
    cliext::pair<wchar_t, int> c2(L'x', 4);
    System::Console::WriteLine("[{0}, {1}]", c2.first, c2.second);

    System::Console::WriteLine("[x 3] > [x 3] is {0}",
        c1 > c1);
    System::Console::WriteLine("[x 4] > [x 3] is {0}",
        c2 > c1);
    return (0);
    }
```

```Output
[x, 3]
[x, 4]
[x 3] > [x 3] is False
[x 4] > [x 3] is True
```

## <a name="op_gteq"></a> İşleç&gt;(eşleştirmesi) (STL/CLR)

Çifti büyüktür veya eşittir karşılaştırma.

### <a name="syntax"></a>Sözdizimi

```cpp
template<typename Value1,
    typename Value2>
    bool operator>=(pair<Value1, Value2>% left,
        pair<Value1, Value2>% right);
```

#### <a name="parameters"></a>Parametreler

*Sol*<br/>
Karşılaştırılacak sol çifti.

*sağ*<br/>
Karşılaştırılacak doğru çifti.

### <a name="remarks"></a>Açıklamalar

İşleç işlevini döndürür `!(left < right)`. Test etmek için kullandığınız olmadığını *sol* önce sıralı değil *doğru* iki çiftleri karşılaştırılan öğe öğe olduğunda.

### <a name="example"></a>Örnek

```cpp
// cliext_pair_operator_ge.cpp
// compile with: /clr
#include <cliext/utility>

int main()
    {
    cliext::pair<wchar_t, int> c1(L'x', 3);
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);
    cliext::pair<wchar_t, int> c2(L'x', 4);
    System::Console::WriteLine("[{0}, {1}]", c2.first, c2.second);

    System::Console::WriteLine("[x 3] >= [x 3] is {0}",
        c1 >= c1);
    System::Console::WriteLine("[x 3] >= [x 4] is {0}",
        c1 >= c2);
    return (0);
    }
```

```Output
[x, 3]
[x, 4]
[x 3] >= [x 3] is True
[x 3] >= [x 4] is False
```