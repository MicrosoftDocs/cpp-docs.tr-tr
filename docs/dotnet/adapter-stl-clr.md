---
description: 'Daha fazla bilgi edinin: bağdaştırıcı (STL/CLR)'
title: bağdaştırıcı (STL/CLR)
ms.date: 06/15/2018
ms.topic: reference
f1_keywords:
- <cliext/adapter>
- cliext::collection_adapter
- cliext::collection_adapter::base
- cliext::collection_adapter::begin
- cliext::collection_adapter::collection_adapter
- cliext::collection_adapter::difference_type
- cliext::collection_adapter::end
- cliext::collection_adapter::iterator
- cliext::collection_adapter::key_type
- cliext::collection_adapter::mapped_type
- cliext::collection_adapter::operator=
- cliext::collection_adapter::reference
- cliext::collection_adapter::size
- cliext::collection_adapter::size_type
- cliext::collection_adapter::swap
- cliext::collection_adapter::value_type
- cliext::make_collection
- cliext::range_adapter
- cliext::operator=
- cliext::range_adapter::operator=
- cliext::range_adapter::range_adapter
helpviewer_keywords:
- <adapter> header [STL/CLR]
- adapter [STL/CLR]
- <cliext/adapter> header [STL/CLR]
- collection_adapter class [STL/CLR]
- base member [STL/CLR]
- begin member [STL/CLR]
- collection_adapter member [STL/CLR]
- difference_type member [STL/CLR]
- end member [STL/CLR]
- iterator member [STL/CLR]
- key_type member [STL/CLR]
- mapped_type member [STL/CLR]
- operator= member [STL/CLR]
- reference member [STL/CLR]
- size member [STL/CLR]
- size_type member [STL/CLR]
- swap member [STL/CLR]
- value_type member [STL/CLR]
- make_collection function [STL/CLR]
- range_adapter class [STL/CLR]
- operator= member [STL/CLR]
- range_adapter member [STL/CLR]
ms.assetid: 71ce7e51-42b6-4f70-9595-303791a97677
ms.openlocfilehash: 66e6346c644bc0d176d90701722cfcd90cbb3590
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97116425"
---
# <a name="adapter-stlclr"></a>bağdaştırıcı (STL/CLR)

STL/CLR üst bilgisi `<cliext/adapter>` iki şablon sınıfı ( `collection_adapter` ve `range_adapter` ) ve şablon işlevini belirtir `make_collection` .

## <a name="syntax"></a>Syntax

```cpp
#include <cliext/adapter>
```

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<cliext/adapter>

**Ad alanı:** cliext

## <a name="declarations"></a>Bildirimler

|Sınıf|Açıklama|
|-----------|-----------------|
|[collection_adapter (STL/CLR)](#collection_adapter)|Taban sınıf kitaplığı (BCL) koleksiyonunu bir Aralık olarak kaydırır.|
|[range_adapter (STL/CLR)](#range_adapter)|Aralığı bir BCL koleksiyonu olarak kaydırır.|

|İşlev|Açıklama|
|--------------|-----------------|
|[make_collection (STL/CLR)](#make_collection)|Yineleyici çifti kullanan bir Aralık bağdaştırıcısı oluşturur.|

## <a name="members"></a>Üyeler

## <a name="collection_adapter-stlclr"></a><a name="collection_adapter"></a> collection_adapter (STL/CLR)

Bir .NET koleksiyonunu STL/CLR kapsayıcısı olarak kullanılmak üzere sarmalanmış olarak kaydırır. `collection_adapter`, Basit BIR STL/CLR kapsayıcı nesnesini tanımlayan bir şablon sınıfıdır. Bir temel sınıf kitaplığı (BCL) arabirimini sarmalanmış ve denetimli sırayı işlemek için kullandığınız bir yineleyici çifti döndürüyor.

### <a name="syntax"></a>Sözdizimi

```cpp
template<typename Coll>
    ref class collection_adapter;

template<>
    ref class collection_adapter<
        System::Collections::ICollection>;
template<>
    ref class collection_adapter<
        System::Collections::IEnumerable>;
template<>
    ref class collection_adapter<
        System::Collections::IList>;
template<>
    ref class collection_adapter<
        System::Collections::IDictionary>;
template<typename Value>
    ref class collection_adapter<
        System::Collections::Generic::ICollection<Value>>;
template<typename Value>
    ref class collection_adapter<
        System::Collections::Generic::IEnumerable<Value>>;
template<typename Value>
    ref class collection_adapter<
        System::Collections::Generic::IList<Value>>;
template<typename Key,
    typename Value>
    ref class collection_adapter<
        System::Collections::Generic::IDictionary<Key, Value>>;
```

#### <a name="parameters"></a>Parametreler

*Coll*<br/>
Sarmalanmış koleksiyonun türü.

### <a name="specializations"></a>Uzmanlıklar

|Özelleştirmesine|Açıklama|
|--------------------|-----------------|
|IEnumerable|Öğeler aracılığıyla sıralar.|
|ICollection|Bir öğe grubunu tutar.|
|IList|Sıralı bir öğe grubunu tutar.|
|IDictionary|{Key, value} çiftinin bir kümesini saklayın.|
|IEnumerable\<Value>|Yazılı öğeler aracılığıyla sıralar.|
|ICollection\<Value>|Bir tür öğe grubunu tutar.|
|IList\<Value>|Yazılı öğelerin sıralı bir grubunu tutar.|
|IDictionary\<Value>|Belirlenmiş bir {Key, value} çifti kümesi tutar.|

### <a name="members"></a>Üyeler

|Tür Tanımı|Açıklama|
|---------------------|-----------------|
|[collection_adapter::difference_type (STL/CLR)](#difference_type)|İki öğe arasındaki işaretli mesafenin türü.|
|[collection_adapter::iterator (STL/CLR)](#iterator)|Denetlenen dizi için bir yineleyici türü.|
|[collection_adapter::key_type (STL/CLR)](#key_type)|Sözlük anahtarının türü.|
|[collection_adapter::mapped_type (STL/CLR)](#mapped_type)|Sözlük değerinin türü.|
|[collection_adapter::reference (STL/CLR)](#reference)|Bir öğe için bir başvuru türü.|
|[collection_adapter::size_type (STL/CLR)](#size_type)|İki öğe arasındaki işaretli mesafenin türü.|
|[collection_adapter::value_type (STL/CLR)](#value_type)|Öğenin türü.|

|Üye İşlevi|Açıklama|
|---------------------|-----------------|
|[collection_adapter::base (STL/CLR)](#base)|Sarmalanan BCL arabirimini belirler.|
|[collection_adapter::begin (STL/CLR)](#begin)|Denetlenen dizinin başlangıcını belirtir.|
|[collection_adapter::collection_adapter (STL/CLR)](#collection_adapter_collection_adapter)|Bir bağdaştırıcı nesnesi oluşturur.|
|[collection_adapter::end (STL/CLR)](#end)|Denetlenen dizinin bitişini belirtir.|
|[collection_adapter::size (STL/CLR)](#size)|Öğe sayısını sayar.|
|[collection_adapter::swap (STL/CLR)](#swap)|İki kapsayıcının içeriğinin yerini değiştirir.|

|İşleç|Açıklama|
|--------------|-----------------|
|[collection_adapter::operator= (STL/CLR)](#op_eq)|Saklı BCL tanıtıcısının yerini alır.|

### <a name="remarks"></a>Açıklamalar

Bu şablon sınıfını, bir BCL kapsayıcısını STL/CLR kapsayıcısı olarak işlemek için kullanırsınız. , Bir `collection_adapter` BCL arabirimine bir tanıtıcı depolar, bu da bir dizi öğeyi denetler. Bir `collection_adapter` nesne `X` , giriş yineleyiciler çifti döndürür `X.begin()` ve `X.end()` öğeleri sırayla ziyaret etmek için kullanılır. Bazı uzmanlık, `X.size()` denetlenen sıranın uzunluğunu belirleyebilmek için yazmanızı de sağlar.

## <a name="collection_adapterbase-stlclr"></a><a name="base"></a> collection_adapter:: Base (STL/CLR)

Sarmalanan BCL arabirimini belirler.

### <a name="syntax"></a>Syntax

```cpp
Coll^ base();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, saklı BCL arabirimi tanıtıcısını döndürür.

### <a name="example"></a>Örnek

```cpp
// cliext_collection_adapter_base.cpp
// compile with: /clr
#include <cliext/adapter>
#include <cliext/deque>

typedef cliext::collection_adapter<
    System::Collections::ICollection> Mycoll;
int main()
    {
    cliext::deque<wchar_t> d6x(6, L'x');
    Mycoll c1(%d6x);

    // display initial contents "x x x x x x "
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    System::Console::WriteLine("base() same = {0}", c1.base() == %c1);
    return (0);
    }
```

```Output
x x x x x x
base() same = True
```

## <a name="collection_adapterbegin-stlclr"></a><a name="begin"></a> collection_adapter:: Begin (STL/CLR)

Denetlenen dizinin başlangıcını belirtir.

### <a name="syntax"></a>Syntax

```cpp
iterator begin();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, denetlenen sıranın ilk öğesini veya boş bir dizinin sonunun ötesinde bir giriş yineleyicisi döndürür.

### <a name="example"></a>Örnek

```cpp
// cliext_collection_adapter_begin.cpp
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

    // display initial contents "a b c "
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // inspect first two items
    Mycoll::iterator it = c1.begin();
    System::Console::WriteLine("*begin() = {0}", *it);
    System::Console::WriteLine("*++begin() = {0}", *++it);
    return (0);
}
```

```Output
a b c
*begin() = a
*++begin() = b
```

## <a name="collection_adaptercollection_adapter-stlclr"></a><a name="collection_adapter_collection_adapter"></a> collection_adapter:: collection_adapter (STL/CLR)

Bir bağdaştırıcı nesnesi oluşturur.

### <a name="syntax"></a>Sözdizimi

```cpp
collection_adapter();
collection_adapter(collection_adapter<Coll>% right);
collection_adapter(collection_adapter<Coll>^ right);
collection_adapter(Coll^ collection);
```

#### <a name="parameters"></a>Parametreler

*koleksiyon*<br/>
Kayılacak BCL tanıtıcısı.

*Right*<br/>
Kopyalanacak nesne.

### <a name="remarks"></a>Açıklamalar

Oluşturucu:

`collection_adapter();`

saklı tanıtıcıyı ile başlatır **`nullptr`** .

Oluşturucu:

`collection_adapter(collection_adapter<Coll>% right);`

saklı tanıtıcıyı `right.` [collection_adapter: Base (STL/CLR)](#base)ile başlatır `()` .

Oluşturucu:

`collection_adapter(collection_adapter<Coll>^ right);`

saklı tanıtıcıyı `right->` [collection_adapter: Base (STL/CLR)](#base)ile başlatır `()` .

Oluşturucu:

`collection_adapter(Coll^ collection);`

saklı tanıtıcıyı ile başlatır `collection` .

### <a name="example"></a>Örnek

```cpp
// cliext_collection_adapter_construct.cpp
// compile with: /clr
#include <cliext/adapter>
#include <cliext/deque>

typedef cliext::collection_adapter<
    System::Collections::ICollection> Mycoll;
int main()
{
    cliext::deque<wchar_t> d6x(6, L'x');

    // construct an empty container
    Mycoll c1;
    System::Console::WriteLine("base() null = {0}", c1.base() == nullptr);

    // construct with a handle
    Mycoll c2(%d6x);
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct by copying another container
    Mycoll c3(c2);
    for each (wchar_t elem in c3)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct by copying a container handle
    Mycoll c4(%c3);
    for each (wchar_t elem in c4)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    return (0);
}
```

```Output
base() null = True
x x x x x x
x x x x x x
x x x x x x
```

## <a name="collection_adapterdifference_type-stlclr"></a><a name="difference_type"></a> collection_adapter::d ifference_type (STL/CLR)

İki öğe arasındaki işaretli bir mesafe türü.

### <a name="syntax"></a>Syntax

```cpp
typedef int difference_type;
```

### <a name="remarks"></a>Açıklamalar

Türü, imzalı bir öğe sayısını tanımlar.

### <a name="example"></a>Örnek

```cpp
// cliext_collection_adapter_difference_type.cpp
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

    // display initial contents "a b c "
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // compute positive difference
    Mycoll::difference_type diff = 0;
    Mycoll::iterator it = c1.begin();
    for (; it != c1.end(); ++it)
        ++diff;
    System::Console::WriteLine("end()-begin() = {0}", diff);
    return (0);
}
```

```Output
a b c
end()-begin() = 3
```

## <a name="collection_adapterend-stlclr"></a><a name="end"></a> collection_adapter:: End (STL/CLR)

Denetlenen dizinin bitişini belirtir.

### <a name="syntax"></a>Syntax

```cpp
iterator end();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, denetimli dizinin sonunun hemen ötesinde işaret eden bir giriş yineleyicisi döndürür.

### <a name="example"></a>Örnek

```cpp
// cliext_collection_adapter_end.cpp
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

    // display initial contents "a b c "
    Mycoll::iterator it = c1.begin();
    for (; it != c1.end(); ++it)
        System::Console::Write("{0} ", *it);
    System::Console::WriteLine();
    return (0);
}
```

```Output
a b c
```

## <a name="collection_adapteriterator-stlclr"></a><a name="iterator"></a> collection_adapter:: yineleyici (STL/CLR)

Denetlenen dizi için bir yineleyici türü.

### <a name="syntax"></a>Syntax

```cpp
typedef T1 iterator;
```

### <a name="remarks"></a>Açıklamalar

Tür, `T1` Denetlenen dizi için bir giriş Yineleyici işlevi görebilecek belirtilmemiş türdeki bir nesneyi tanımlar.

### <a name="example"></a>Örnek

```cpp
// cliext_collection_adapter_iterator.cpp
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

    // display initial contents "a b c "
    Mycoll::iterator it = c1.begin();
    for (; it != c1.end(); ++it)
        System::Console::Write("{0} ", *it);
    System::Console::WriteLine();
    return (0);
}
```

```Output
a b c
```

## <a name="collection_adapterkey_type-stlclr"></a><a name="key_type"></a> collection_adapter:: key_type (STL/CLR)

Sözlük anahtarının türü.

### <a name="syntax"></a>Syntax

```cpp
typedef Key key_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, veya için bir özelleştirmede şablon parametresi için bir eş anlamlı olur `Key` `IDictionary` `IDictionary<Value>` ; Aksi takdirde tanımlı değildir.

### <a name="example"></a>Örnek

```cpp
// cliext_collection_adapter_key_type.cpp
// compile with: /clr
#include <cliext/adapter>
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
typedef cliext::collection_adapter<
    System::Collections::Generic::IDictionary<wchar_t, int>> Mycoll;
typedef System::Collections::Generic::KeyValuePair<wchar_t,int> Mypair;
int main()
{
    Mymap d1;
    d1.insert(Mymap::make_value(L'a', 1));
    d1.insert(Mymap::make_value(L'b', 2));
    d1.insert(Mymap::make_value(L'c', 3));
    Mycoll c1(%d1);

    // display contents "[a 1] [b 2] [c 3] "
    for each (Mypair elem in c1)
    {
        Mycoll::key_type key = elem.Key;
        Mycoll::mapped_type value = elem.Value;
        System::Console::Write("[{0} {1}] ", key, value);
    }
    System::Console::WriteLine();
    return (0);
}
```

```Output
[a 1] [b 2] [c 3]
```

## <a name="collection_adaptermapped_type-stlclr"></a><a name="mapped_type"></a> collection_adapter:: mapped_type (STL/CLR)

Sözlük değerinin türü.

### <a name="syntax"></a>Syntax

```cpp
typedef Value mapped_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, veya için bir özelleştirmede şablon parametresi için bir eş anlamlı olur `Value` `IDictionary` `IDictionary<Value>` ; Aksi takdirde tanımlı değildir.

### <a name="example"></a>Örnek

```cpp
// cliext_collection_adapter_mapped_type.cpp
// compile with: /clr
#include <cliext/adapter>
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
typedef cliext::collection_adapter<
    System::Collections::Generic::IDictionary<wchar_t, int>> Mycoll;
typedef System::Collections::Generic::KeyValuePair<wchar_t,int> Mypair;
int main()
{
    Mymap d1;
    d1.insert(Mymap::make_value(L'a', 1));
    d1.insert(Mymap::make_value(L'b', 2));
    d1.insert(Mymap::make_value(L'c', 3));
    Mycoll c1(%d1);

    // display contents "[a 1] [b 2] [c 3] "
    for each (Mypair elem in c1)
    {
        Mycoll::key_type key = elem.Key;
        Mycoll::mapped_type value = elem.Value;
        System::Console::Write("[{0} {1}] ", key, value);
    }
    System::Console::WriteLine();
    return (0);
}
```

```Output
[a 1] [b 2] [c 3]
```

## <a name="collection_adapteroperator-stlclr"></a><a name="op_eq"></a> collection_adapter:: operator = (STL/CLR)

Saklı BCL tanıtıcısının yerini alır.

### <a name="syntax"></a>Sözdizimi

```cpp
collection_adapter<Coll>% operator=(collection_adapter<Coll>% right);
```

#### <a name="parameters"></a>Parametreler

*Right*<br/>
Kopyalanacak bağdaştırıcı.

### <a name="remarks"></a>Açıklamalar

Üye işleci nesnesine *sağ* kopyalar ve ardından döndürür **`*this`** . Saklı BCL tanıtıcısını, depolanan BCL tanıtıcısının bir kopyasıyla değiştirmek için bu alanı *kullanabilirsiniz.*

### <a name="example"></a>Örnek

```cpp
// cliext_collection_adapter_operator_as.cpp
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

    // display initial contents "a b c "
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // assign to a new container
    Mycoll c2;
    c2 = c1;
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
}
```

```Output
a b c
a b c
```

## <a name="collection_adapterreference-stlclr"></a><a name="reference"></a> collection_adapter:: Reference (STL/CLR)

Bir öğe için bir başvuru türü.

### <a name="syntax"></a>Syntax

```cpp
typedef value_type% reference;
```

### <a name="remarks"></a>Açıklamalar

Türü bir öğesi başvurusunu tanımlar.

### <a name="example"></a>Örnek

```cpp
// cliext_collection_adapter_reference.cpp
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

    // display initial contents "a b c "
    Mycoll::iterator it = c1.begin();
    for (; it != c1.end(); ++it)
    {   // get a reference to an element
        Mycoll::reference ref = *it;
        System::Console::Write("{0} ", ref);
    }
    System::Console::WriteLine();
    return (0);
}
```

```Output
a b c
```

## <a name="collection_adaptersize-stlclr"></a><a name="size"></a> collection_adapter:: size (STL/CLR)

Öğe sayısını sayar.

### <a name="syntax"></a>Syntax

```cpp
size_type size();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi denetlenen sıranın uzunluğunu döndürür. Veya için bir özelleştirmede tanımlı değildir `IEnumerable` `IEnumerable<Value>` .

### <a name="example"></a>Örnek

```cpp
// cliext_collection_adapter_size.cpp
// compile with: /clr
#include <cliext/adapter>
#include <cliext/deque>

typedef cliext::collection_adapter<
    System::Collections::ICollection> Mycoll;
int main()
{
    cliext::deque<wchar_t> d6x(6, L'x');
    Mycoll c1(%d6x);

    // display initial contents "x x x x x x "
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    System::Console::WriteLine("size() = {0}", c1.size());
    return (0);
}
```

```Output
x x x x x x
size() = 6
```

## <a name="collection_adaptersize_type-stlclr"></a><a name="size_type"></a> collection_adapter:: size_type (STL/CLR)

İki öğe arasındaki işaretli bir mesafe türü.

### <a name="syntax"></a>Syntax

```cpp
typedef int size_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, negatif olmayan bir öğe sayısını tanımlar.

### <a name="example"></a>Örnek

```cpp
// cliext_collection_adapter_size_type.cpp
// compile with: /clr
#include <cliext/adapter>
#include <cliext/deque>

typedef cliext::collection_adapter<
    System::Collections::ICollection> Mycoll;
int main()
{
    cliext::deque<wchar_t> d6x(6, L'x');
    Mycoll c1(%d6x);

    // display initial contents "x x x x x x"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    Mycoll::size_type size = c1.size();
    System::Console::WriteLine("size() = {0}", size);
    return (0);
}
```

```Output
x x x x x x
size() = 6
```

## <a name="collection_adapterswap-stlclr"></a><a name="swap"></a> collection_adapter:: swap (STL/CLR)

İki kapsayıcının içeriğinin yerini değiştirir.

### <a name="syntax"></a>Sözdizimi

```cpp
void swap(collection_adapter<Coll>% right);
```

#### <a name="parameters"></a>Parametreler

*Right*<br/>
İçeriği takas eden kapsayıcı.

### <a name="remarks"></a>Açıklamalar

Üye işlevi, ve sağ arasındaki saklı BCL tutamaçlarını **`*this`** değiştirir .

### <a name="example"></a>Örnek

```cpp
// cliext_collection_adapter_swap.cpp
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

## <a name="collection_adaptervalue_type-stlclr"></a><a name="value_type"></a> collection_adapter:: value_type (STL/CLR)

Öğenin türü.

### <a name="syntax"></a>Syntax

```cpp
typedef Value value_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, özelleştirme içinde varsa, şablon parametre *değeri* için bir eş anlamlıdır; Aksi takdirde, için bir eş anlamlı olur `System::Object^` .

### <a name="example"></a>Örnek

```cpp
// cliext_collection_adapter_value_type.cpp
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

    // display contents "a b c" using value_type
    for (Mycoll::iterator it = c1.begin();
        it != c1.end(); ++it)
    {   // store element in value_type object
        Mycoll::value_type val = *it;

        System::Console::Write("{0} ", val);
    }
    System::Console::WriteLine();
    return (0);
}
```

```Output
a b c
```

## <a name="make_collection-stlclr"></a><a name="make_collection"></a> make_collection (STL/CLR)

Bir `range_adapter` Yineleyici çiftiyle oluşturun.

### <a name="syntax"></a>Sözdizimi

```cpp
template<typename Iter>
    range_adapter<Iter> make_collection(Iter first, Iter last);
```

#### <a name="parameters"></a>Parametreler

*Pi*<br/>
Sarmalanan yineleyiciler türü.

*adı*<br/>
Kaydıracağı ilk Yineleyici.

*soyadına*<br/>
Sarılacağı ikinci Yineleyici.

### <a name="remarks"></a>Açıklamalar

Şablon işlevi döndürür `gcnew range_adapter<Iter>(first, last)` . `range_adapter<Iter>`Yineleyicilerin çiftinden bir nesne oluşturmak için kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// cliext_make_collection.cpp
// compile with: /clr
#include <cliext/adapter>
#include <cliext/deque>

typedef cliext::deque<wchar_t> Mycont;
typedef cliext::range_adapter<Mycont::iterator> Myrange;
int main()
{
    cliext::deque<wchar_t> d1;
    d1.push_back(L'a');
    d1.push_back(L'b');
    d1.push_back(L'c');

    // display contents " a b c"
    for each (wchar_t elem in d1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    System::Collections::ICollection^ p1 =
        cliext::make_collection(d1.begin(), d1.end());
    System::Console::WriteLine("Count = {0}", p1->Count);
    System::Console::WriteLine("IsSynchronized = {0}",
        p1->IsSynchronized);
    System::Console::WriteLine("SyncRoot not nullptr = {0}",
        p1->SyncRoot != nullptr);

    // copy the sequence
    cli::array<System::Object^>^ a1 = gcnew cli::array<System::Object^>(5);

    a1[0] = L'|';
    p1->CopyTo(a1, 1);
    a1[4] = L'|';
    for each (wchar_t elem in a1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    return (0);
}
```

```Output
a b c
Count = 3
IsSynchronized = False
SyncRoot not nullptr = True
| a b c |
```

## <a name="range_adapter-stlclr"></a><a name="range_adapter"></a> range_adapter (STL/CLR)

Birkaç temel sınıf kitaplığı (BCL) arabirimini uygulamak için kullanılan yineleyiciler çiftini sarmalayan bir şablon sınıfı. Bir STL/CLR aralığını bir BCL koleksiyonu gibi işlemek için range_adapter kullanırsınız.

### <a name="syntax"></a>Sözdizimi

```cpp
template<typename Iter>
    ref class range_adapter
        :   public
        System::Collections::IEnumerable,
        System::Collections::ICollection,
        System::Collections::Generic::IEnumerable<Value>,
        System::Collections::Generic::ICollection<Value>
    { ..... };
```

#### <a name="parameters"></a>Parametreler

*Pi*<br/>
Sarmalanan yineleyiciler ile ilişkili tür.

### <a name="members"></a>Üyeler

|Üye İşlevi|Açıklama|
|---------------------|-----------------|
|[range_adapter::range_adapter (STL/CLR)](#range_adapter_range_adapter)|Bir bağdaştırıcı nesnesi oluşturur.|

|İşleç|Açıklama|
|--------------|-----------------|
|[range_adapter::operator= (STL/CLR)](#range_adapter_op_eq)|Saklı Yineleyici çiftinin yerini alır.|

### <a name="interfaces"></a>Arabirimler

|Arabirim|Açıklama|
|---------------|-----------------|
|<xref:System.Collections.IEnumerable>|Koleksiyondaki öğeleri dolaşır.|
|<xref:System.Collections.ICollection>|Bir öğe grubunu tutar.|
|<xref:System.Collections.Generic.IEnumerable%601>|Koleksiyonda yazılı öğeler arasında dolaşır...|
|<xref:System.Collections.Generic.ICollection%601>|Bir tür öğe grubunu tutar.|

### <a name="remarks"></a>Açıklamalar

Range_adapter bir çift yineleyiciler depolar, bu da bir öğe dizisini sınırlandıran bir çiftdir. Nesnesi, öğeleri sırayla yinelemenize olanak sağlayan dört BCL arabirimini uygular. Bu şablon sınıfını, BCL kapsayıcılarına benzer STL/CLR aralıklarını işlemek için kullanırsınız.

## <a name="range_adapteroperator-stlclr"></a><a name="range_adapter_op_eq"></a> range_adapter:: operator = (STL/CLR)

Saklı Yineleyici çiftinin yerini alır.

### <a name="syntax"></a>Sözdizimi

```cpp
range_adapter<Iter>% operator=(range_adapter<Iter>% right);
```

#### <a name="parameters"></a>Parametreler

*Right*<br/>
Kopyalanacak bağdaştırıcı.

### <a name="remarks"></a>Açıklamalar

Üye işleci nesnesine *sağ* kopyalar ve ardından döndürür **`*this`** . Saklı Yineleyici çiftinin kendisini, saklı Yineleyici çiftinin bir kopyasıyla değiştirmek için onu *kullanın.*

### <a name="example"></a>Örnek

```cpp
// cliext_range_adapter_operator_as.cpp
// compile with: /clr
#include <cliext/adapter>
#include <cliext/deque>

typedef cliext::deque<wchar_t> Mycont;
typedef cliext::range_adapter<Mycont::iterator> Myrange;
int main()
{
    cliext::deque<wchar_t> d1;
    d1.push_back(L'a');
    d1.push_back(L'b');
    d1.push_back(L'c');
    Myrange c1(d1.begin(), d1.end());

    // display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // assign to a new container
    Myrange c2;
    c2 = c1;
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
}
```

```Output
a b c
a b c
```

## <a name="range_adapterrange_adapter-stlclr"></a><a name="range_adapter_range_adapter"></a> range_adapter:: range_adapter (STL/CLR)

Bir bağdaştırıcı nesnesi oluşturur.

### <a name="syntax"></a>Sözdizimi

```cpp
range_adapter();
range_adapter(range_adapter<Iter>% right);
range_adapter(range_adapter<Iter>^ right);
range_adapter(Iter first, Iter last);
```

#### <a name="parameters"></a>Parametreler

*adı*<br/>
Kaydıracağı ilk Yineleyici.

*soyadına*<br/>
Sarılacağı ikinci Yineleyici.

*Right*<br/>
Kopyalanacak nesne.

### <a name="remarks"></a>Açıklamalar

Oluşturucu:

`range_adapter();`

saklı Yineleyici çiftini varsayılan oluşturulmuş yineleyiciler ile başlatır.

Oluşturucu:

`range_adapter(range_adapter<Iter>% right);`

*sağ tarafta* depolanan çifti kopyalayarak, saklı Yineleyici çiftini başlatır.

Oluşturucu:

`range_adapter(range_adapter<Iter>^ right);`

depolanan yineleyici çiftini, içinde depolanan çifti kopyalayarak başlatır `*right` .

Oluşturucu:

`range_adapter(Iter^ first, last);`

depolanan yineleyici çiftini *ilk* ve *son* ile başlatır.

### <a name="example"></a>Örnek

```cpp
// cliext_range_adapter_construct.cpp
// compile with: /clr
#include <cliext/adapter>
#include <cliext/deque>

typedef cliext::deque<wchar_t> Mycont;
typedef cliext::range_adapter<Mycont::iterator> Myrange;
int main()
{
    cliext::deque<wchar_t> d1;
    d1.push_back(L'a');
    d1.push_back(L'b');
    d1.push_back(L'c');

    // construct an empty adapter
    Myrange c1;

    // construct with an iterator pair
    Myrange c2(d1.begin(), d1.end());
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct by copying another adapter
    Myrange c3(c2);
    for each (wchar_t elem in c3)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct by copying an adapter handle
    Myrange c4(%c3);
    for each (wchar_t elem in c4)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    return (0);
}
```

```Output
a b c
a b c
a b c
```
