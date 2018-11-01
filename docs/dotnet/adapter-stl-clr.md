---
title: bağdaştırıcı (STL/CLR)
ms.date: 06/15/2018
ms.topic: reference
f1_keywords:
- <cliext/adapter>
- cliext::collection_adapter
- cliext::collection_adapter::base
- cliext::collection_adapter::begin
- cliext::collection_adapter
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
ms.openlocfilehash: d5c554439d9bb418b9b62484ee10cd6917cf1777
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50436164"
---
# <a name="adapter-stlclr"></a>bağdaştırıcı (STL/CLR)

STL/CLR üstbilgi `<cliext/adapter>` iki şablon sınıfları belirtir (`collection_adapter` ve `range_adapter`) ve şablon işlevi `make_collection`.

## <a name="syntax"></a>Sözdizimi

```cpp
#include <cliext/adapter>
```

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<cliext/bağdaştırıcısı >

**Namespace:** cliext

## <a name="declarations"></a>Bildirimler

|örneği|Açıklama|
|-----------|-----------------|
|[collection_adapter (STL/CLR)](#collection_adapter)|Temel sınıf kitaplığı (BCL) koleksiyon aralığı olarak sarmalar.|
|[range_adapter (STL/CLR)](#range_adapter)|Aralığın BCL koleksiyonu olarak sarmalar.|

|İşlev|Açıklama|
|--------------|-----------------|
|[make_collection (STL/CLR)](#make_collection)|Bir yineleyici çifti kullanarak bir aralık bağdaştırıcısı oluşturur.|

## <a name="members"></a>Üyeler

## <a name="collection_adapter"></a> collection_adapter (STL/CLR)

Bir .NET koleksiyonunun bir STL/CLR kapsayıcısı olarak kullanılmak üzere sarmalar. A `collection_adapter` basit bir STL/CLR kapsayıcı nesnesini tanımlayan bir şablon sınıfıdır. Bir temel sınıf kitaplığı (BCL) arabirimini sarmalar ve denetlenen dizideki yönetmek için kullandığınız bir yineleyici çifti döndürür.

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
Sarmalanan koleksiyonun türü.

### <a name="specializations"></a>Uzmanlıklar

|Özelleştirme|Açıklama|
|--------------------|-----------------|
|IEnumerable|Öğeleri aracılığıyla sıralar.|
|ICollection|Öğeleri bir grup tutar.|
|IList|Sıralı bir öğe grubunu tutar.|
|IDictionary|{Değer, key} kümesini bulundurmak çiftleri.|
|IEnumerable\<değer >|Türü belirlenmiş öğeleri aracılığıyla sıralar.|
|ICollection\<değer >|Türü belirtilmiş öğelerini bir grup tutar.|
|IList\<değer >|Türü belirtilmiş öğelerin sıralı bir grup tutar.|
|IDictionary\<değer >|Bir dizi türü belirlenmiş {key, değer} tutar çiftleri.|

### <a name="members"></a>Üyeler

|Tür Tanımlaması|Açıklama|
|---------------------|-----------------|
|[collection_adapter::difference_type (STL/CLR)](#difference_type)|İki öğe arasındaki işaretli mesafenin türü.|
|[collection_adapter::iterator (STL/CLR)](#iterator)|Denetlenen dizi için bir yineleyici türü.|
|[collection_adapter::key_type (STL/CLR)](#key_type)|Sözlük anahtarı türü.|
|[collection_adapter::mapped_type (STL/CLR)](#mapped_type)|Sözlük değeri türü.|
|[collection_adapter::reference (STL/CLR)](#reference)|Bir öğe için bir başvuru türü.|
|[collection_adapter::size_type (STL/CLR)](#size_type)|İki öğe arasındaki işaretli mesafenin türü.|
|[collection_adapter::value_type (STL/CLR)](#value_type)|Öğenin türü.|

|Üye İşlevi|Açıklama|
|---------------------|-----------------|
|[collection_adapter::base (STL/CLR)](#base)|Sarmalanan BCL arabirimi belirtir.|
|[collection_adapter::begin (STL/CLR)](#begin)|Denetlenen dizinin başlangıcını belirtir.|
|[collection_adapter::collection_adapter (STL/CLR)](#collection_adapter_collection_adapter)|Bir bağdaştırıcı nesne oluşturur.|
|[collection_adapter::end (STL/CLR)](#end)|Denetlenen dizinin bitişini belirtir.|
|[collection_adapter::size (STL/CLR)](#size)|Öğe sayısını sayar.|
|[collection_adapter::swap (STL/CLR)](#swap)|İki kapsayıcının içeriğinin yerini değiştirir.|

|İşleç|Açıklama|
|--------------|-----------------|
|[collection_adapter::operator= (STL/CLR)](#op_eq)|Saklı BCL tanıtıcı değiştirir.|

### <a name="remarks"></a>Açıklamalar

Bu şablon sınıfının BCL kapsayıcı bir STL/CLR kapsayıcı olarak yönetmek için kullanın. `collection_adapter` Sırayla bir dizi öğe denetleyen bir BCL arabirimi için bir tanıtıcı depolar. A `collection_adapter` nesne `X` giriş Yineleyicilerin bir çiftini döndürür `X.begin()` ve `X.end()` öğeleri sırayla ziyaret etmek için kullanın. Bazı uzmanlıkları da yazmanıza izin `X.size()` denetlenen dizinin uzunluğu belirlemek için.

## <a name="base"></a> collection_adapter::Base (STL/CLR)

Sarmalanan BCL arabirimi belirtir.

### <a name="syntax"></a>Sözdizimi

```cpp
Coll^ base();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, depolanan BCL arabirimi tanıtıcısını döndürür.

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

## <a name="begin"></a> collection_adapter::Begin (STL/CLR)

Denetlenen dizinin başlangıcını belirtir.

### <a name="syntax"></a>Sözdizimi

```cpp
iterator begin();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, denetlenen dizinin ya da boş bir dizi bitiminin ötesinde yalnızca ilk öğeyi belirleyen bir giriş yineleyici döndürür.

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

## <a name="collection_adapter_collection_adapter"></a> collection_adapter::collection_adapter (STL/CLR)

Bir bağdaştırıcı nesne oluşturur.

### <a name="syntax"></a>Sözdizimi

```cpp
collection_adapter();
collection_adapter(collection_adapter<Coll>% right);
collection_adapter(collection_adapter<Coll>^ right);
collection_adapter(Coll^ collection);
```

#### <a name="parameters"></a>Parametreler

*Koleksiyon*<br/>
Sarılacak BCL tanıtıcısı.

*sağ*<br/>
Kopyalanacak nesneye.

### <a name="remarks"></a>Açıklamalar

Oluşturucu:

`collection_adapter();`

saklı tanıtıcısı ile başlatır `nullptr`.

Oluşturucu:

`collection_adapter(collection_adapter<Coll>% right);`

saklı tanıtıcısı ile başlatır `right.` [collection_adapter::base (STL/CLR)](../dotnet/collection-adapter-base-stl-clr.md)`()`.

Oluşturucu:

`collection_adapter(collection_adapter<Coll>^ right);`

saklı tanıtıcısı ile başlatır `right->` [collection_adapter::base (STL/CLR)](../dotnet/collection-adapter-base-stl-clr.md)`()`.

Oluşturucu:

`collection_adapter(Coll^ collection);`

saklı tanıtıcısı ile başlatır `collection`.

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

## <a name="difference_type"></a> collection_adapter::difference_type (STL/CLR)

İki öğe arasındaki işaretli mesafenin türü.

### <a name="syntax"></a>Sözdizimi

```cpp
typedef int difference_type;
```

### <a name="remarks"></a>Açıklamalar

İmzalı öğe sayısını tanımlayan bir tür.

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

## <a name="end"></a> collection_adapter::End (STL/CLR)

Denetlenen dizinin bitişini belirtir.

### <a name="syntax"></a>Sözdizimi

```cpp
iterator end();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, denetlenen dizinin sonuna hemen ötesine işaret eden bir giriş yineleyici döndürür.

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

## <a name="iterator"></a> collection_adapter::iterator (STL/CLR)

Denetlenen dizi için bir yineleyici türü.

### <a name="syntax"></a>Sözdizimi

```cpp
typedef T1 iterator;
```

### <a name="remarks"></a>Açıklamalar

Bilinmeyen türde bir nesne tanımlayan bir tür `T1` denetlenen dizi için bir giriş yineleyici olarak verebilir.

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

## <a name="key_type"></a> collection_adapter::key_type (STL/CLR)

Sözlük anahtarı türü.

### <a name="syntax"></a>Sözdizimi

```cpp
typedef Key key_type;
```

### <a name="remarks"></a>Açıklamalar

Şablon parametresi için bir eşanlamlı türüdür `Key`, özelleştirmesi için `IDictionary` veya `IDictionary<Value>`; Aksi takdirde tanımlanmamış.

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

## <a name="mapped_type"></a> collection_adapter::mapped_type (STL/CLR)

Sözlük değeri türü.

### <a name="syntax"></a>Sözdizimi

```cpp
typedef Value mapped_type;
```

### <a name="remarks"></a>Açıklamalar

Şablon parametresi için bir eşanlamlı türüdür `Value`, özelleştirmesi için `IDictionary` veya `IDictionary<Value>`; Aksi takdirde tanımlanmamış.

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

## <a name="op_eq"></a> collection_adapter::operator (STL/CLR) =

Saklı BCL tanıtıcı değiştirir.

### <a name="syntax"></a>Sözdizimi

```cpp
collection_adapter<Coll>% operator=(collection_adapter<Coll>% right);
```

#### <a name="parameters"></a>Parametreler

*sağ*<br/>
Kopyalanacak bağdaştırıcısı.

### <a name="remarks"></a>Açıklamalar

Üye işleci kopyaları *doğru* ardından nesneye döndürür `*this`. Bir kopya saklı BCL tutamacın saklı BCL tanıtıcı değiştirmek için kullandığınız *doğru*.

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

## <a name="reference"></a> collection_adapter::Reference (STL/CLR)

Bir öğe için bir başvuru türü.

### <a name="syntax"></a>Sözdizimi

```cpp
typedef value_type% reference;
```

### <a name="remarks"></a>Açıklamalar

Öğeye bir başvuru türü açıklar.

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

## <a name="size"></a> collection_adapter::size (STL/CLR)

Öğe sayısını sayar.

### <a name="syntax"></a>Sözdizimi

```cpp
size_type size();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, denetlenen dizinin uzunluğunu döndürür. İçin bir özelleştirmesi'içinde tanımlanmayan `IEnumerable` veya `IEnumerable<Value>`.

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

## <a name="size_type"></a> collection_adapter::size_type (STL/CLR)

İki öğe arasındaki işaretli mesafenin türü.

### <a name="syntax"></a>Sözdizimi

```cpp
typedef int size_type;
```

### <a name="remarks"></a>Açıklamalar

Bir negatif olmayan öğe sayısını tanımlayan bir tür.

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

## <a name="swap"></a> collection_adapter::Swap (STL/CLR)

İki kapsayıcının içeriğinin yerini değiştirir.

### <a name="syntax"></a>Sözdizimi

```cpp
void swap(collection_adapter<Coll>% right);
```

#### <a name="parameters"></a>Parametreler

*sağ*<br/>
Kapsayıcı içeriğini değiştirmek için.

### <a name="remarks"></a>Açıklamalar

Üye işlevi arasındaki depolanan BCL tutamaçları değiştirir `*this` ve *doğru*.

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

## <a name="value_type"></a> collection_adapter::value_type (STL/CLR)

Öğenin türü.

### <a name="syntax"></a>Sözdizimi

```cpp
typedef Value value_type;
```

### <a name="remarks"></a>Açıklamalar

Şablon parametresi için bir eşanlamlı türüdür *değer*, varsa uzmanlıktaki; Aksi takdirde, eşanlamlıdır `System::Object^`.

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

## <a name="make_collection"></a> make_collection (STL/CLR)

Olun bir `range_adapter` gelen bir yineleyici çifti.

### <a name="syntax"></a>Sözdizimi

```cpp
template<typename Iter>
    range_adapter<Iter> make_collection(Iter first, Iter last);
```

#### <a name="parameters"></a>Parametreler

*Iter*<br/>
Sarmalanan yineleyici türü.

*ilk*<br/>
Kaydırmak için ilk yineleyicisi.

*Son*<br/>
Kaydırmak için ikinci yineleyicisi.

### <a name="remarks"></a>Açıklamalar

Şablon işlevinin döndürdüğü `gcnew range_adapter<Iter>(first, last)`. Oluşturmak için kullandığınız bir `range_adapter<Iter>` Yineleyicilerin bir çifti nesnesi.

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

## <a name="range_adapter"></a> range_adapter (STL/CLR)

Birkaç temel sınıf kitaplığı (BCL) arabirimlerini uygulamak için kullanılan Yineleyicilerin bir çiftini sarmalayan bir şablon sınıfı. Range_adapter BCL koleksiyonu değilmiş gibi bir STL/CLR aralığını değiştirmek için kullanın.

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

*Iter*<br/>
Sarmalanan yineleyicilerle ilişkili tür.

### <a name="members"></a>Üyeler

|Üye İşlevi|Açıklama|
|---------------------|-----------------|
|[range_adapter::range_adapter (STL/CLR)](#range_adapter_range_adapter)|Bir bağdaştırıcı nesne oluşturur.|

|İşleç|Açıklama|
|--------------|-----------------|
|[range_adapter::operator= (STL/CLR)](#range_adapter_op_eq)|Depolanmış yineleyiciyi çiftini değiştirir.|

### <a name="interfaces"></a>Arabirimler

|Arabirim|Açıklama|
|---------------|-----------------|
|<xref:System.Collections.IEnumerable>|Bir koleksiyondaki öğeleri aracılığıyla yinelenir.|
|<xref:System.Collections.ICollection>|Öğeleri bir grup tutar.|
|<xref:System.Collections.Generic.IEnumerable%601>|Koleksiyondaki yazılmış öğeler üzerinden yinelenir...|
|<xref:System.Collections.Generic.ICollection%601>|Türü belirtilmiş öğelerini bir grup tutar.|

### <a name="remarks"></a>Açıklamalar

Range_adapter hangi sırayla bir dizi öğe sınırlandırmak Yineleyicilerin bir çiftini depolar. Nesne öğeleri sırayla yinelemek olanak tanıyan dört BCL arabirimlerini uygular. Bu şablon sınıfının, STL/CLR aralıkları gibi BCL kapsayıcıları yönetmek için kullanın.

## <a name="range_adapter_op_eq"></a> range_adapter::operator (STL/CLR) =

Depolanmış yineleyiciyi çiftini değiştirir.

### <a name="syntax"></a>Sözdizimi

```cpp
range_adapter<Iter>% operator=(range_adapter<Iter>% right);
```

#### <a name="parameters"></a>Parametreler

*sağ*<br/>
Kopyalanacak bağdaştırıcısı.

### <a name="remarks"></a>Açıklamalar

Üye işleci kopyaları *doğru* ardından nesneye döndürür `*this`. Depolanmış yineleyiciyi çifti depolanmış yineleyiciyi çiftinin bir kopyasını değiştirmek için kullandığınız *doğru*.

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

## <a name="range_adapter_range_adapter"></a> range_adapter::range_adapter (STL/CLR)

Bir bağdaştırıcı nesne oluşturur.

### <a name="syntax"></a>Sözdizimi

```cpp
range_adapter();
range_adapter(range_adapter<Iter>% right);
range_adapter(range_adapter<Iter>^ right);
range_adapter(Iter first, Iter last);
```

#### <a name="parameters"></a>Parametreler

*ilk*<br/>
Kaydırmak için ilk yineleyicisi.

*Son*<br/>
Kaydırmak için ikinci yineleyicisi.

*sağ*<br/>
Kopyalanacak nesneye.

### <a name="remarks"></a>Açıklamalar

Oluşturucu:

`range_adapter();`

Varsayılan oluşturulan Yineleyicilerin depolanmış yineleyiciyi çiftiyle başlatır.

Oluşturucu:

`range_adapter(range_adapter<Iter>% right);`

depolanmış yineleyiciyi çifti depolanan çifti kopyalayarak başlatır *doğru*.

Oluşturucu:

`range_adapter(range_adapter<Iter>^ right);`

depolanmış yineleyiciyi çifti depolanan çifti kopyalayarak başlatır `*right`.

Oluşturucu:

`range_adapter(Iter^ first, last);`

depolanmış yineleyiciyi çifti ile başlatır *ilk* ve *son*.

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
