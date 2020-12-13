---
description: 'Daha fazla bilgi edinin: yardımcı program (STL/CLR)'
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
ms.openlocfilehash: cb55acec88ca7b687ca7ad7790c4b0073944c0c4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97177997"
---
# <a name="utility-stlclr"></a>yardımcı program (STL/CLR)

`<cliext/utility>`Şablon sınıfını `pair` ve çeşitli destekleyici şablon işlevlerini tanımlamak için STL/CLR üst bilgisini ekleyin.

## <a name="syntax"></a>Syntax

```cpp
#include <utility>
```

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<cliext/utility>

**Ad alanı:** cliext

## <a name="declarations"></a>Bildirimler

|Sınıf|Açıklama|
|-----------|-----------------|
|[pair (STL/CLR)](#pair)|Öğe çiftini sarın.|

|İşleç|Açıklama|
|--------------|-----------------|
|[operator== (pair) (STL/CLR)](#op_eq)|Eşit karşılaştırmayı eşleştirin.|
|[işleç! = (çift) (STL/CLR)](#op_neq)|Çift eşitlik karşılaştırması.|
|[işleç< (çift) (STL/CLR)](#op_lt)|Çiftin karşılaştırmasının küçüktür.|
|[operator \< = (çift) (STL/CLR)](#op_lteq)|Eşit veya daha küçük bir karşılaştırmaya eşleştirin.|
|[işleç> (çift) (STL/CLR)](#op_gt)|Eşleştirme, karşılaştırmadan daha büyük.|
|[işleç>= (çift) (STL/CLR)](#op_gteq)|Eşit veya daha büyük bir karşılaştırmayı eşleştirin.|

|İşlev|Açıklama|
|--------------|-----------------|
|[make_pair (STL/CLR)](#make_pair)|Değer çiftinden bir çift oluşturun.|

## <a name="pair-stlclr"></a><a name="pair"></a> Çift (STL/CLR)

Şablon sınıfı, bir çift değeri sarmalayan nesneyi tanımlar.

### <a name="syntax"></a>Sözdizimi

```cpp
template<typename Value1,
    typename Value2>
    ref class pair;
```

#### <a name="parameters"></a>Parametreler

*Value1*<br/>
Sarmalanan ilk değerin türü.

*Value2*<br/>
İkinci Sarmalanan değerin türü.

## <a name="members"></a>Üyeler

|Tür Tanımı|Açıklama|
|---------------------|-----------------|
|[pair::first_type (STL/CLR)](#first_type)|Sarmalanan ilk değerin türü.|
|[pair::second_type (STL/CLR)](#second_type)|Sarmalanan ikinci değerin türü.|

|Üye nesnesi|Açıklama|
|-------------------|-----------------|
|[pair::first (STL/CLR)](#first)|İlk depolanan değer.|
|[pair::second (STL/CLR)](#second)|İkinci saklı değer.|

|Üye İşlevi|Açıklama|
|---------------------|-----------------|
|[pair::pair (STL/CLR)](#pair_pair)|Bir çift nesnesi oluşturur.|
|[pair::swap (STL/CLR)](#swap)|İki çifinin içeriğini değiştirir.|

|İşleç|Açıklama|
|--------------|-----------------|
|[pair::operator= (STL/CLR)](#op_as)|Depolanan değer çiftini değiştirir.|

## <a name="remarks"></a>Açıklamalar

Nesne bir çift değer depolar. Bu şablon sınıfını, iki değeri tek bir nesne içinde birleştirmek için kullanırsınız. Ayrıca, nesnesi `cliext::pair` (burada açıklanmıştır) yalnızca yönetilen türler depolar; ' de belirtilen bir çift yönetilmeyen tür kullanımını depolamak için `std::pair` `<utility>` .

## <a name="pairfirst-stlclr"></a><a name="first"></a> Pair:: First (STL/CLR)

İlk Sarmalanan değer.

### <a name="syntax"></a>Syntax

```cpp
Value1 first;
```

### <a name="remarks"></a>Açıklamalar

Nesne, ilk Sarmalanan değeri depolar.

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

## <a name="pairfirst_type-stlclr"></a><a name="first_type"></a> Pair:: first_type (STL/CLR)

Sarmalanan ilk değerin türü.

### <a name="syntax"></a>Syntax

```cpp
typedef Value1 first_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, *değer1* şablon parametresinin eşanlamlısıdır.

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

## <a name="pairoperator-stlclr"></a><a name="op_as"></a> Pair:: operator = (STL/CLR)

Depolanan değer çiftini değiştirir.

### <a name="syntax"></a>Sözdizimi

```cpp
pair<Value1, Value2>% operator=(pair<Value1, Value2>% right);
```

#### <a name="parameters"></a>Parametreler

*Right*<br/>
Kopyalanacak eşleştirme.

### <a name="remarks"></a>Açıklamalar

Üye işleci nesnesine *sağ* kopyalar ve ardından döndürür **`*this`** . Depolanan değer çiftinin, depolanan değer çiftinin bir kopyasıyla birlikte değiştirmek için bunu *kullanırsınız.*

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

## <a name="pairpair-stlclr"></a><a name="pair_pair"></a> Çift::p hava (STL/CLR)

Bir çift nesnesi oluşturur.

### <a name="syntax"></a>Sözdizimi

```cpp
pair();
pair(pair<Coll>% right);
pair(pair<Coll>^ right);
pair(Value1 val1, Value2 val2);
```

#### <a name="parameters"></a>Parametreler

*Right*<br/>
Depolanacak eşleştirme.

*val1*<br/>
Depolanacak ilk değer.

*val2 & lt*<br/>
Depolanacak ikinci değer.

### <a name="remarks"></a>Açıklamalar

Oluşturucu:

`pair();`

depolanan çifti varsayılan oluşturulmuş değerlerle başlatır.

Oluşturucu:

`pair(pair<Value1, Value2>% right);`

saklı çifti,: `right.` [FIRST (STL/CLR)](#first) ve `right.` [çiftin:: Second (STL/CLR)](#second)ile başlatır.

`pair(pair<Value1, Value2>^ right);`

saklı çifti,: `right->` [FIRST (STL/CLR)](#first) ve `right>` [çiftin:: Second (STL/CLR)](#second)ile başlatır.

Oluşturucu:

`pair(Value1 val1, Value2 val2);`

depolanan çifti *val1* ve *val2 & lt* ile başlatır.

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

## <a name="pairsecond-stlclr"></a><a name="second"></a> Çift:: Second (STL/CLR)

Sarmalanan ikinci değer.

### <a name="syntax"></a>Syntax

```cpp
Value2 second;
```

### <a name="remarks"></a>Açıklamalar

Nesnesi, Sarmalanan ikinci değeri depolar.

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

## <a name="pairsecond_type-stlclr"></a><a name="second_type"></a> Pair:: second_type (STL/CLR)

Sarmalanan ikinci değerin türü.

### <a name="syntax"></a>Syntax

```cpp
typedef Value2 second_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, typtemplate *parametresinin* eşanlamlısıdır.

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

## <a name="pairswap-stlclr"></a><a name="swap"></a> Pair:: swap (STL/CLR)

İki çifinin içeriğini değiştirir.

### <a name="syntax"></a>Sözdizimi

```cpp
void swap(pair<Value1, Value2>% right);
```

#### <a name="parameters"></a>Parametreler

*Right*<br/>
İçeriği değiştirme eşleştirmesi.

### <a name="remarks"></a>Açıklamalar

Üye işlevi, ve sağ arasındaki depolanan değer çiftini değiştirir **`*this`** . 

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

## <a name="make_pair-stlclr"></a><a name="make_pair"></a> make_pair (STL/CLR)

`pair`Değer çiftinden bir değer yapın.

### <a name="syntax"></a>Sözdizimi

```cpp
template<typename Value1,
    typename Value2>
    pair<Value1, Value2> make_pair(Value1 first, Value2 second);
```

#### <a name="parameters"></a>Parametreler

*Value1*<br/>
Sarmalanan ilk değerin türü.

*Value2*<br/>
Sarmalanan ikinci değerin türü.

*adı*<br/>
Sarılacağı ilk değer.

*İkincisi*<br/>
Sarılacağı ikinci değer.

### <a name="remarks"></a>Açıklamalar

Şablon işlevi döndürür `pair<Value1, Value2>(first, second)` . Değer çiftinden bir nesne oluşturmak için bunu kullanırsınız `pair<Value1, Value2>` .

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

## <a name="operator-pair-stlclr"></a><a name="op_neq"></a> işleç! = (çift) (STL/CLR)

Çift eşitlik karşılaştırması.

### <a name="syntax"></a>Sözdizimi

```cpp
template<typename Value1,
    typename Value2>
    bool operator!=(pair<Value1, Value2>% left,
        pair<Value1, Value2>% right);
```

#### <a name="parameters"></a>Parametreler

*tarafta*<br/>
Karşılaştırılacak sol çift.

*Right*<br/>
Karşılaştırılacak sağa çift.

### <a name="remarks"></a>Açıklamalar

İşleç işlevi döndürülür `!(left == right)` . İki çifte öğe öğe ile karşılaştırıldığı zaman, *sol* öğenin *doğru* şekilde sıralı olup olmadığını test etmek için bunu kullanırsınız.

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

## <a name="operatorlt-pair-stlclr"></a><a name="op_lt"></a> işleç &lt; (çift) (STL/CLR)

Çiftin karşılaştırmasının küçüktür.

### <a name="syntax"></a>Sözdizimi

```cpp
template<typename Value1,
    typename Value2>
    bool operator<(pair<Value1, Value2>% left,
        pair<Value1, Value2>% right);
```

#### <a name="parameters"></a>Parametreler

*tarafta*<br/>
Karşılaştırılacak sol çift.

*Right*<br/>
Karşılaştırılacak sağa çift.

### <a name="remarks"></a>Açıklamalar

İşleç işlevi döndürülür `left.first <` `right.first || !(right.first <` `left.first &&` `left.second <` `right.second` . İki çiftler öğe öğesine göre karşılaştırıldığı zaman, *sol taraftaki sola* *doğru sıralı* olup olmadığını test etmek için bunu kullanırsınız.

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

## <a name="operatorlt-pair-stlclr"></a><a name="op_lteq"></a> operator &lt; = (çift) (STL/CLR)

Eşit veya daha küçük bir karşılaştırmaya eşleştirin.

### <a name="syntax"></a>Sözdizimi

```cpp
template<typename Value1,
    typename Value2>
    bool operator<=(pair<Value1, Value2>% left,
        pair<Value1, Value2>% right);
```

#### <a name="parameters"></a>Parametreler

*tarafta*<br/>
Karşılaştırılacak sol çift.

*Right*<br/>
Karşılaştırılacak sağa çift.

### <a name="remarks"></a>Açıklamalar

İşleç işlevi döndürülür `!(right < left)` . İki çiftler öğe öğesine göre karşılaştırıldığı zaman *farenin sağ* *tarafında* sıralı olup olmadığını test etmek için kullanırsınız.

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

## <a name="operator-pair-stlclr"></a><a name="op_eq"></a> işleç = = (çift) (STL/CLR)

Eşit karşılaştırmayı eşleştirin.

### <a name="syntax"></a>Sözdizimi

```cpp
template<typename Value1,
    typename Value2>
    bool operator==(pair<Value1, Value2>% left,
        pair<Value1, Value2>% right);
```

#### <a name="parameters"></a>Parametreler

*tarafta*<br/>
Karşılaştırılacak sol çift.

*Right*<br/>
Karşılaştırılacak sağa çift.

### <a name="remarks"></a>Açıklamalar

İşleç işlevi döndürülür `left.first ==` `right.first &&` `left.second ==` `right.second` . Bu, iki çifte öğe öğe ile karşılaştırıldığı zaman *solinin* *doğru* olup olmadığını test etmek için kullanılır.

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

## <a name="operatorgt-pair-stlclr"></a><a name="op_gt"></a> işleç &gt; (çift) (STL/CLR)

Eşleştirme, karşılaştırmadan daha büyük.

### <a name="syntax"></a>Sözdizimi

```cpp
template<typename Value1,
    typename Value2>
    bool operator>(pair<Value1, Value2>% left,
        pair<Value1, Value2>% right);
```

#### <a name="parameters"></a>Parametreler

*tarafta*<br/>
Karşılaştırılacak sol çift.

*Right*<br/>
Karşılaştırılacak sağa çift.

### <a name="remarks"></a>Açıklamalar

İşleç işlevi döndürülür `right` `<` `left` . Bu, iki çifte öğesi öğesi öğesine göre karşılaştırıldığı zaman *farenin sağ* *tarafında sıralı olup olmadığını test* etmek için kullanılır.

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

## <a name="operatorgt-pair-stlclr"></a><a name="op_gteq"></a> operator &gt; = (çift) (STL/CLR)

Eşit veya daha büyük bir karşılaştırmayı eşleştirin.

### <a name="syntax"></a>Sözdizimi

```cpp
template<typename Value1,
    typename Value2>
    bool operator>=(pair<Value1, Value2>% left,
        pair<Value1, Value2>% right);
```

#### <a name="parameters"></a>Parametreler

*tarafta*<br/>
Karşılaştırılacak sol çift.

*Right*<br/>
Karşılaştırılacak sağa çift.

### <a name="remarks"></a>Açıklamalar

İşleç işlevi döndürülür `!(left < right)` . İki çiftler öğe öğesine göre karşılaştırıldığı zaman *sağdan* *sola* doğru sıralanmadığını test etmek için bunu kullanırsınız.

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
