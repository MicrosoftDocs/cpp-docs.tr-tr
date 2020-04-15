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
ms.openlocfilehash: 6d025230abcff42e367a231e616a13f0f8c684f0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81320284"
---
# <a name="utility-stlclr"></a>yardımcı program (STL/CLR)

Şablon sınıfını `pair` ve birkaç `<cliext/utility>` destekleyici şablon işlevlerini tanımlamak için STL/CLR üstbilgisini ekleyin.

## <a name="syntax"></a>Sözdizimi

```cpp
#include <utility>
```

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** \<cliext/utility>

**Ad alanı:** cliext

## <a name="declarations"></a>Bildirimler

|Sınıf|Açıklama|
|-----------|-----------------|
|[pair (STL/CLR)](#pair)|Bir çift öğeyi sarın.|

|İşleç|Açıklama|
|--------------|-----------------|
|[operator== (pair) (STL/CLR)](#op_eq)|Eşit karşılaştırmayı eşleştirin.|
|[işleç!= (çift) (STL/CLR)](#op_neq)|Eşit karşılaştırma değil çifti.|
|[operatör< (çift) (STL/CLR)](#op_lt)|Karşılaştırmadan daha az çifti.|
|[işleç\<= (çift) (STL/CLR)](#op_lteq)|Daha az veya eşit karşılaştırma eşleştirin.|
|[operatör> (çift) (STL/CLR)](#op_gt)|Eşleştirmeden daha büyük bir çift.|
|[işleç>= (çift) (STL/CLR)](#op_gteq)|Daha büyük veya eşit karşılaştırma çifti.|

|İşlev|Açıklama|
|--------------|-----------------|
|[make_pair (STL/CLR)](#make_pair)|Bir çift değerden bir çift yapın.|

## <a name="members"></a>Üyeler

## <a name="pair-stlclr"></a><a name="pair"></a>çifti (STL/CLR)

Şablon sınıfı, bir çift değer saran bir nesneyi açıklar.

### <a name="syntax"></a>Sözdizimi

```cpp
template<typename Value1,
    typename Value2>
    ref class pair;
```

#### <a name="parameters"></a>Parametreler

*Değer1*<br/>
İlk sarılmış değer türü.

*Değer2*<br/>
İkinci sarılmış değerin türü.

## <a name="members"></a>Üyeler

|Tür Tanımlaması|Açıklama|
|---------------------|-----------------|
|[pair::first_type (STL/CLR)](#first_type)|İlk sarılmış değerin türü.|
|[pair::second_type (STL/CLR)](#second_type)|İkinci sarılmış değerin türü.|

|Üye Nesnesi|Açıklama|
|-------------------|-----------------|
|[pair::first (STL/CLR)](#first)|İlk depolanan değer.|
|[pair::second (STL/CLR)](#second)|İkinci depolanan değer.|

|Üye İşlevi|Açıklama|
|---------------------|-----------------|
|[pair::pair (STL/CLR)](#pair_pair)|Bir çift nesne oluşturuyor.|
|[pair::swap (STL/CLR)](#swap)|İki çiftin içeriğini değiştirir.|

|İşleç|Açıklama|
|--------------|-----------------|
|[pair::operator= (STL/CLR)](#op_as)|Depolanan değer çiftinin yerine.|

## <a name="remarks"></a>Açıklamalar

Nesne bir çift değer depolar. İki değeri tek bir nesnede birleştirmek için bu şablon sınıfLarını kullanırsınız. Ayrıca, nesne `cliext::pair` (burada açıklanan) yalnızca yönetilen türleri depolar; bir çift yönetilmeyen türü `std::pair`kullanmak depolamak için , içinde `<utility>`beyan.

## <a name="pairfirst-stlclr"></a><a name="first"></a>çift::ilk (STL/CLR)

İlk sarılmış değer.

### <a name="syntax"></a>Sözdizimi

```cpp
Value1 first;
```

### <a name="remarks"></a>Açıklamalar

Nesne ilk sarılmış değeri depolar.

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

## <a name="pairfirst_type-stlclr"></a><a name="first_type"></a>çift::first_type (STL/CLR)

İlk sarılmış değerin türü.

### <a name="syntax"></a>Sözdizimi

```cpp
typedef Value1 first_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, şablon parametresi *Değer1*ile eş anlamlıdır.

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

## <a name="pairoperator-stlclr"></a><a name="op_as"></a>çifti::operator= (STL/CLR)

Depolanan değer çiftinin yerine.

### <a name="syntax"></a>Sözdizimi

```cpp
pair<Value1, Value2>% operator=(pair<Value1, Value2>% right);
```

#### <a name="parameters"></a>Parametreler

*Doğru*<br/>
Kopyalamak için eşleştirin.

### <a name="remarks"></a>Açıklamalar

Üye işleç *nesneye doğru* kopyalar, sonra döndürür. `*this` Depolanan değer çiftini, depolanan değer çiftinin bir kopyasıyla *değiştirmek*için kullanırsınız.

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

## <a name="pairpair-stlclr"></a><a name="pair_pair"></a>çift::pair (STL/CLR)

Bir çift nesne oluşturuyor.

### <a name="syntax"></a>Sözdizimi

```cpp
pair();
pair(pair<Coll>% right);
pair(pair<Coll>^ right);
pair(Value1 val1, Value2 val2);
```

#### <a name="parameters"></a>Parametreler

*Doğru*<br/>
Saklamak için çifti.

*val1*<br/>
Saksıya ilk değer.

*val2*<br/>
Saksıda ikinci değer.

### <a name="remarks"></a>Açıklamalar

Yapıcı:

`pair();`

varsayılan yapılandırılan değerlerle depolanan çifti başharfe alır.

Yapıcı:

`pair(pair<Value1, Value2>% right);`

depolanan çifti `right.`aşağıdakilerle başharfe::ilk [(STL/CLR)](../dotnet/pair-first-stl-clr.md) ve `right.` [çifti::ikinci (STL/CLR)](../dotnet/pair-second-stl-clr.md).

`pair(pair<Value1, Value2>^ right);`

depolanan çifti `right->`aşağıdakilerle başharfe::ilk [(STL/CLR)](../dotnet/pair-first-stl-clr.md) ve `right>` [çifti::ikinci (STL/CLR)](../dotnet/pair-second-stl-clr.md).

Yapıcı:

`pair(Value1 val1, Value2 val2);`

*val1* ve *val2*ile depolanan çifti başharfize eder.

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

## <a name="pairsecond-stlclr"></a><a name="second"></a>çift::ikinci (STL/CLR)

İkinci sarılmış değer.

### <a name="syntax"></a>Sözdizimi

```cpp
Value2 second;
```

### <a name="remarks"></a>Açıklamalar

Nesne ikinci sarılmış değeri depolar.

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

## <a name="pairsecond_type-stlclr"></a><a name="second_type"></a>çift::second_type (STL/CLR)

İkinci sarılmış değerin türü.

### <a name="syntax"></a>Sözdizimi

```cpp
typedef Value2 second_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, şablon parametresi *Value2*ile eş anlamlıdır.

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

## <a name="pairswap-stlclr"></a><a name="swap"></a>çifti::takas (STL/CLR)

İki çiftin içeriğini değiştirir.

### <a name="syntax"></a>Sözdizimi

```cpp
void swap(pair<Value1, Value2>% right);
```

#### <a name="parameters"></a>Parametreler

*Doğru*<br/>
İçeriği takas etmek için eşleştirin.

### <a name="remarks"></a>Açıklamalar

Üye işlev, depolanan değer çiftini `*this` *ve sağ*arasındaki değerleri değiştirir.

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

## <a name="make_pair-stlclr"></a><a name="make_pair"></a>make_pair (STL/CLR)

Bir `pair` çift değerden a yapın.

### <a name="syntax"></a>Sözdizimi

```cpp
template<typename Value1,
    typename Value2>
    pair<Value1, Value2> make_pair(Value1 first, Value2 second);
```

#### <a name="parameters"></a>Parametreler

*Değer1*<br/>
İlk sarılmış değerin türü.

*Değer2*<br/>
İkinci sarılmış değerin türü.

*Ilk*<br/>
Sarmak için ilk değer.

*Ikinci*<br/>
Sargıiçin ikinci değer.

### <a name="remarks"></a>Açıklamalar

Şablon işlevi `pair<Value1, Value2>(first, second)`döndürür. Bir `pair<Value1, Value2>` nesneyi bir çift değerden oluşturmak için kullanırsınız.

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

## <a name="operator-pair-stlclr"></a><a name="op_neq"></a>işleç!= (çift) (STL/CLR)

Eşit karşılaştırma değil çifti.

### <a name="syntax"></a>Sözdizimi

```cpp
template<typename Value1,
    typename Value2>
    bool operator!=(pair<Value1, Value2>% left,
        pair<Value1, Value2>% right);
```

#### <a name="parameters"></a>Parametreler

*Sol*<br/>
Karşılaştırmak için sol çift.

*Doğru*<br/>
Karşılaştırmak için doğru çift.

### <a name="remarks"></a>Açıklamalar

Operatör işlevi `!(left == right)`döndürür. İki çift öğeile karşılaştırıldığında *sağ* olarak aynı sıralı *olup* olmadığını test etmek için kullanabilirsiniz.

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

## <a name="operatorlt-pair-stlclr"></a><a name="op_lt"></a>işleç&lt; (çift) (STL/CLR)

Karşılaştırmadan daha az çifti.

### <a name="syntax"></a>Sözdizimi

```cpp
template<typename Value1,
    typename Value2>
    bool operator<(pair<Value1, Value2>% left,
        pair<Value1, Value2>% right);
```

#### <a name="parameters"></a>Parametreler

*Sol*<br/>
Karşılaştırmak için sol çift.

*Doğru*<br/>
Karşılaştırmak için doğru çift.

### <a name="remarks"></a>Açıklamalar

Operatör işlevi `left.first <` `right.first || !(right.first <` `left.first &&` `left.second <` `right.second`döndürür. İki çift öğeile karşılaştırıldığında sağ *önce* sıralanır *olup* olmadığını test etmek için kullanabilirsiniz.

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

## <a name="operatorlt-pair-stlclr"></a><a name="op_lteq"></a>işleç&lt;= (çift) (STL/CLR)

Daha az veya eşit karşılaştırma eşleştirin.

### <a name="syntax"></a>Sözdizimi

```cpp
template<typename Value1,
    typename Value2>
    bool operator<=(pair<Value1, Value2>% left,
        pair<Value1, Value2>% right);
```

#### <a name="parameters"></a>Parametreler

*Sol*<br/>
Karşılaştırmak için sol çift.

*Doğru*<br/>
Karşılaştırmak için doğru çift.

### <a name="remarks"></a>Açıklamalar

Operatör işlevi `!(right < left)`döndürür. İki çift öğeile karşılaştırıldığında *sağdan* sonra sol sıralanıp *sıralanmadığını* test etmek için kullanabilirsiniz.

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

## <a name="operator-pair-stlclr"></a><a name="op_eq"></a>işleç== (çift) (STL/CLR)

Eşit karşılaştırmayı eşleştirin.

### <a name="syntax"></a>Sözdizimi

```cpp
template<typename Value1,
    typename Value2>
    bool operator==(pair<Value1, Value2>% left,
        pair<Value1, Value2>% right);
```

#### <a name="parameters"></a>Parametreler

*Sol*<br/>
Karşılaştırmak için sol çift.

*Doğru*<br/>
Karşılaştırmak için doğru çift.

### <a name="remarks"></a>Açıklamalar

Operatör işlevi `left.first ==` `right.first &&` `left.second ==` `right.second`döndürür. İki çift öğeile karşılaştırıldığında *sağ* olarak aynı sıralı *olup* olmadığını test etmek için kullanabilirsiniz.

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

## <a name="operatorgt-pair-stlclr"></a><a name="op_gt"></a>işleç&gt; (çift) (STL/CLR)

Eşleştirmeden daha büyük bir çift.

### <a name="syntax"></a>Sözdizimi

```cpp
template<typename Value1,
    typename Value2>
    bool operator>(pair<Value1, Value2>% left,
        pair<Value1, Value2>% right);
```

#### <a name="parameters"></a>Parametreler

*Sol*<br/>
Karşılaştırmak için sol çift.

*Doğru*<br/>
Karşılaştırmak için doğru çift.

### <a name="remarks"></a>Açıklamalar

Operatör işlevi `right` `<` `left`döndürür. İki çift öğeile *left* karşılaştırıldığında *sağdan* sonra sol sıralanıp sıralanmadığını test etmek için kullanabilirsiniz.

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

## <a name="operatorgt-pair-stlclr"></a><a name="op_gteq"></a>işleç&gt;= (çift) (STL/CLR)

Daha büyük veya eşit karşılaştırma çifti.

### <a name="syntax"></a>Sözdizimi

```cpp
template<typename Value1,
    typename Value2>
    bool operator>=(pair<Value1, Value2>% left,
        pair<Value1, Value2>% right);
```

#### <a name="parameters"></a>Parametreler

*Sol*<br/>
Karşılaştırmak için sol çift.

*Doğru*<br/>
Karşılaştırmak için doğru çift.

### <a name="remarks"></a>Açıklamalar

Operatör işlevi `!(left < right)`döndürür. İki çift öğeile karşılaştırıldığında *sağ* önce sol sıralı *olup* olmadığını test etmek için kullanabilirsiniz.

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
