---
description: 'Daha fazla bilgi edinin: set (STL/CLR)'
title: set (STL/CLR)
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- cliext::set
- cliext::set::begin
- cliext::set::clear
- cliext::set::const_iterator
- cliext::set::const_reference
- cliext::set::const_reverse_iterator
- cliext::set::count
- cliext::set::difference_type
- cliext::set::empty
- cliext::set::end
- cliext::set::equal_range
- cliext::set::erase
- cliext::set::find
- cliext::set::generic_container
- cliext::set::generic_iterator
- cliext::set::generic_reverse_iterator
- cliext::set::generic_value
- cliext::set::insert
- cliext::set::iterator
- cliext::set::key_comp
- cliext::set::key_compare
- cliext::set::key_type
- cliext::set::lower_bound
- cliext::set::make_value
- cliext::set::operator=
- cliext::set::rbegin
- cliext::set::reference
- cliext::set::rend
- cliext::set::reverse_iterator
- cliext::set::set
- cliext::set::size
- cliext::set::size_type
- cliext::set::swap
- cliext::set::to_array
- cliext::set::upper_bound
- cliext::set::value_comp
- cliext::set::value_compare
- cliext::set::value_type
helpviewer_keywords:
- <cliext/set> header [STL/CLR]
- <set> header [STL/CLR]
- set class [STL/CLR]
- operator!= (set) member [STL/CLR]
- operator< (set) member [STL/CLR]
- operator<= (set) member [STL/CLR]
- operator== (set) member [STL/CLR]
- operator> (set) member [STL/CLR]
- operator>= (set) member [STL/CLR]
- begin member [STL/CLR]
- clear member [STL/CLR]
- const_iterator member [STL/CLR]
- const_reference member [STL/CLR]
- const_reverse_iterator member [STL/CLR]
- count member [STL/CLR]
- difference_type member [STL/CLR]
- empty member [STL/CLR]
- end member [STL/CLR]
- equal_range member [STL/CLR]
- erase member [STL/CLR]
- find member [STL/CLR]
- generic_container member [STL/CLR]
- generic_iterator member [STL/CLR]
- generic_reverse_iterator member [STL/CLR]
- generic_value member [STL/CLR]
- insert member [STL/CLR]
- iterator member [STL/CLR]
- key_comp member [STL/CLR]
- key_compare member [STL/CLR]
- key_type member [STL/CLR]
- lower_bound member [STL/CLR]
- make_value member [STL/CLR]
- operator= member [STL/CLR]
- rbegin member [STL/CLR]
- reference member [STL/CLR]
- rend member [STL/CLR]
- reverse_iterator member [STL/CLR]
- set member [STL/CLR]
- size member [STL/CLR]
- size_type member [STL/CLR]
- swap member [STL/CLR]
- to_array member [STL/CLR]
- upper_bound member [STL/CLR]
- value_comp member [STL/CLR]
- value_compare member [STL/CLR]
- value_type member [STL/CLR]
ms.assetid: 27d3628c-741a-43a7-bef1-5085536f679e
ms.openlocfilehash: 38d02576b270d41e0a21076c92d16f8349d54ecb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97335367"
---
# <a name="set-stlclr"></a>set (STL/CLR)

Şablon sınıfı, çift yönlü erişime sahip olan öğelerin değişen uzunluklu bir dizisini denetleyen bir nesneyi tanımlar. Öğe `set` dizisini, her biri bir öğe depolayan (neredeyse) dengeli sıralı düğüm ağacı olarak yönetmek için kapsayıcısını kullanırsınız.

Aşağıdaki açıklamada, `GValue` ile aynı şekilde, `GKey` İkincisi bir başvuru türü olmadığı sürece *anahtarla* aynı olur ve bu durumda olur `Key^` .

## <a name="syntax"></a>Sözdizimi

```cpp
template<typename Key>
    ref class set
        :   public
        System::ICloneable,
        System::Collections::IEnumerable,
        System::Collections::ICollection,
        System::Collections::Generic::IEnumerable<GValue>,
        System::Collections::Generic::ICollection<GValue>,
        System::Collections::Generic::IList<GValue>,
        Microsoft::VisualC::StlClr::ITree<Gkey, GValue>
    { ..... };
```

### <a name="parameters"></a>Parametreler

*Key*<br/>
Denetlenen dizideki bir öğenin anahtar bileşeni türü.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<cliext/set>

**Ad alanı:** cliext

## <a name="declarations"></a>Bildirimler

|Tür Tanımı|Açıklama|
|---------------------|-----------------|
|[set::const_iterator (STL/CLR)](#const_iterator)|Denetlenen dizi için bir sabit yineleyici türü.|
|[set::const_reference (STL/CLR)](#const_reference)|Bir öğe için sabit bir başvuru türü.|
|[set::const_reverse_iterator (STL/CLR)](#const_reverse_iterator)|Denetlenen sıra için bir sabit ters yineleyicinin türü.|
|[set::difference_type (STL/CLR)](#difference_type)|İki öğe arasındaki mesafe (muhtemelen imzalı) türü.|
|[set::generic_container (STL/CLR)](#generic_container)|Kapsayıcının genel arabiriminin türü.|
|[set::generic_iterator (STL/CLR)](#generic_iterator)|Kapsayıcının genel arabirimi için bir yineleyici türü.|
|[set::generic_reverse_iterator (STL/CLR)](#generic_reverse_iterator)|Kapsayıcının genel arabirimi için ters yineleyicinin türü.|
|[set::generic_value (STL/CLR)](#generic_value)|Kapsayıcının genel arabirimi için bir öğenin türü.|
|[set::iterator (STL/CLR)](#iterator)|Denetlenen dizi için bir yineleyici türü.|
|[set::key_compare (STL/CLR)](#key_compare)|İki anahtar için sıralama temsilcisi.|
|[set::key_type (STL/CLR)](#key_type)|Bir sıralama anahtarının türü.|
|[set::reference (STL/CLR)](#reference)|Bir öğe için bir başvuru türü.|
|[set::reverse_iterator (STL/CLR)](#reverse_iterator)|Denetlenen sıra için ters yineleyicinin türü.|
|[set::size_type (STL/CLR)](#size_type)|İki öğe arasındaki (negatif olmayan) bir mesafe türü.|
|[set::value_compare (STL/CLR)](#value_compare)|İki öğe değeri için sıralama temsilcisi.|
|[set::value_type (STL/CLR)](#value_type)|Öğenin türü.|

|Üye İşlevi|Açıklama|
|---------------------|-----------------|
|[set::begin (STL/CLR)](#begin)|Denetlenen dizinin başlangıcını belirtir.|
|[set::clear (STL/CLR)](#clear)|Tüm öğeleri kaldırır.|
|[set::count (STL/CLR)](#count)|Belirtilen bir anahtarla eşleşen öğeleri sayar.|
|[set::empty (STL/CLR)](#empty)|Bir öğe olup olmadığını sınar.|
|[set::end (STL/CLR)](#end)|Denetlenen dizinin bitişini belirtir.|
|[set::equal_range (STL/CLR)](#equal_range)|Belirtilen bir anahtarla eşleşen aralığı bulur.|
|[set::erase (STL/CLR)](#erase)|Belirtilen konumlardaki öğeleri kaldırır.|
|[set::find (STL/CLR)](#find)|Belirtilen bir anahtarla eşleşen bir öğeyi bulur.|
|[set::insert (STL/CLR)](#insert)|Öğeleri ekler.|
|[set::key_comp (STL/CLR)](#key_comp)|Sıralama temsilcisini iki anahtar için kopyalar.|
|[set::lower_bound (STL/CLR)](#lower_bound)|Belirtilen anahtarla eşleşen aralığın başlangıcını bulur.|
|[set::make_value (STL/CLR)](#make_value)|Değer nesnesi oluşturur.|
|[set::rbegin (STL/CLR)](#rbegin)|Ters denetlenen sıranın başlangıcını belirtir.|
|[set::rend (STL/CLR)](#rend)|Ters denetlenen sıranın sonunu belirtir.|
|[set::set (STL/CLR)](#set)|Bir kapsayıcı nesnesi oluşturur.|
|[set::size (STL/CLR)](#size)|Öğe sayısını sayar.|
|[set::swap (STL/CLR)](#swap)|İki kapsayıcının içeriğinin yerini değiştirir.|
|[set::to_array (STL/CLR)](#to_array)|Denetimli sırayı yeni bir diziye kopyalar.|
|[set::upper_bound (STL/CLR)](#upper_bound)|Belirtilen anahtarla eşleşen aralığın sonunu bulur.|
|[set::value_comp (STL/CLR)](#value_comp)|İki öğe değeri için sıralama temsilcisini kopyalar.|

|İşleç|Açıklama|
|--------------|-----------------|
|[set::operator= (STL/CLR)](#op_as)|Denetlenen sırayı değiştirir.|
|[operator! = (set) (STL/CLR)](#op_neq)|Bir `set` nesnenin başka bir nesneye eşit olup olmadığını belirler `set` .|
|[işleç< (küme) (STL/CLR)](#op_lt)|Bir `set` nesnenin başka bir nesneden daha az olup olmadığını belirler `set` .|
|[işleç<= (küme) (STL/CLR)](#op_lteq)|Bir `set` nesnenin başka bir nesneden küçük veya ona eşit olup olmadığını belirler `set` .|
|[operator = = (set) (STL/CLR)](#op_eq)|Bir `set` nesnenin başka bir nesneye eşit olup olmadığını belirler `set` .|
|[işleç> (küme) (STL/CLR)](#op_gt)|Bir `set` nesnenin başka bir nesneden daha büyük olup olmadığını belirler `set` .|
|[operator>= (set) (STL/CLR)](#op_gteq)|Bir `set` nesnenin başka bir nesneden büyük veya ona eşit olup olmadığını belirler `set` .|

## <a name="interfaces"></a>Arabirimler

|Arabirim|Açıklama|
|---------------|-----------------|
|<xref:System.ICloneable>|Bir nesneyi çoğaltın.|
|<xref:System.Collections.IEnumerable>|Öğeler aracılığıyla sıralama.|
|<xref:System.Collections.ICollection>|Öğe grubunu saklayın.|
|<xref:System.Collections.Generic.IEnumerable%601>|Yazılı öğeler aracılığıyla sıralama.|
|<xref:System.Collections.Generic.ICollection%601>|Türü belirtilmiş öğelerin grubunu koruyun.|
|Iree\<Key, Value>|Genel kapsayıcıyı koruyun.|

## <a name="remarks"></a>Açıklamalar

Nesnesi, tek tek düğümler olarak denetlediği sıra için depolamayı ayırır ve boşaltır. Tek bir düğümün içeriğini başka bir düğüme kopyalayarak düğümler arasındaki bağlantıları değiştirerek sıralı bir (neredeyse) dengeli ağaca öğe ekler. Diğer bir deyişle, daha fazla Bing, kalan öğeleri etkilemeden öğeleri ekleyebileceğiniz ve kaldırabileceğiniz anlamına gelir.

Nesnesi, [set:: key_compare (STL/CLR)](#key_compare)türünde depolanan bir temsilci nesnesi çağırarak denetlediği diziyi sıralar. Kümeyi oluştururken depolanan temsilci nesnesini belirtebilirsiniz; temsilci nesnesi belirtmezseniz, varsayılan değer karşılaştırmayla belirlenir `operator<(key_type, key_type)` . Bu saklı nesneye, [set:: key_comp (STL/CLR)](#key_comp)üye işlevini çağırarak erişirsiniz `()` .

Bu tür bir temsilci nesnesi, [set:: key_type (STL/CLR)](#key_type)türündeki anahtarlar üzerinde katı zayıf bir sıralama getirmelidir. Yani, her iki anahtar için `X` ve `Y` :

`key_comp()(X, Y)` her çağrıda aynı Boole sonucunu döndürür.

`key_comp()(X, Y)`True ise, false olmalıdır `key_comp()(Y, X)` .

`key_comp()(X, Y)`True ise, daha `X` önce sipariş olarak kabul edilir `Y` .

`!key_comp()(X, Y) && !key_comp()(Y, X)`True ise, `X` ve `Y` eşdeğer sıralamaya sahip olarak kabul edilir.

`X`Denetlenen dizide önündeki tüm öğeler için `Y` `key_comp()(Y, X)` false olur. (Varsayılan temsilci nesnesi için, anahtarlar hiçbir şekilde değerde azalmayın.) Şablon sınıfı [kümesinden](../dotnet/set-stl-clr.md)farklı olarak, şablon sınıfının bir nesnesi `set` tüm öğeler için anahtarların benzersiz olmasını gerektirmez. (İki veya daha fazla anahtarın eşdeğer sıralaması olabilir.)

Her öğe hem bir ey hem de bir değer görevi görür. Sıra, dizi içindeki öğe sayısının logaritmasına orantılı bir şekilde bir dizi işlem içeren rastgele bir öğenin aranması, eklenmesine ve kaldırılmasına izin veren bir şekilde temsil edilir. Ayrıca, bir öğe eklenmesi hiçbir yineleyiciyi geçersiz kılmaz; bir öğenin kaldırılması yalnızca bu kaldırılan öğeyi gösteren yineleyicileri geçersiz kılar.

Bir küme çift yönlü yineleyiciler destekler, bu, denetlenen dizide bir öğe atayan bir yineleyici verilen bitişik öğelere adım adım yol açabilir. Özel bir baş düğüm, [set:: End (STL/CLR)](#end)tarafından döndürülen Yineleyici öğesine karşılık gelir `()` . Varsa, denetlenen sıradaki son öğeye ulaşmak için bu yineleyiciyi azaltamazsınız. Baş düğüme ulaşmak için bir küme yineleyicisini arttırıp daha sonra eşit olarak karşılaştırılacağını sağlayabilirsiniz `end()` . Ancak tarafından döndürülen Yineleyici için başvuru oluşturamazsınız `end()` .

Bir küme öğesine, bir rastgele erişim Yineleyici gerektiren sayısal konumuna doğrudan başvurmayacağınızı unutmayın.

Bir küme Yineleyici, ilişkili kapsayıcısına bir tutamacı depolayan bir tutamacı ilişkili küme düğümüne depolar. Yineleyiciler yalnızca ilişkili kapsayıcı nesneleriyle birlikte kullanabilirsiniz. Bir küme yineleyicisi, ilişkili küme düğümü bazı bir ayarla ilişkili olduğu sürece geçerli kalır. Üstelik, geçerli bir yineleyici bir şekilde gönderilir--bunu, oluşturduğu öğe değerine erişmek veya değiştirmek için kullanabilirsiniz. buna eşit olmadığı sürece `end()` .

Bir öğeyi silme veya kaldırma, kendi saklı değeri için yıkıcıyı çağırır. Kapsayıcının yok edilmesi tüm öğeleri siler. Bu nedenle, öğe türü bir başvuru sınıfı olan bir kapsayıcı, kapsayıcının hiçbir öğenin etkin olmamasını sağlar. Ancak, bir işleç kapsayıcısının *öğelerini yok ettiğini* unutmayın.

## <a name="members"></a>Üyeler

## <a name="setbegin-stlclr"></a><a name="begin"></a> Set:: Begin (STL/CLR)

Denetlenen dizinin başlangıcını belirtir.

### <a name="syntax"></a>Syntax

```cpp
iterator begin();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, denetimli sıranın ilk öğesini veya boş bir dizinin sonunun ötesinde bir çift yönlü yineleyiciyi döndürür. Denetlenen dizinin başlangıcını atayan bir yineleyici elde etmek için bunu kullanırsınız `current` , ancak denetlenen sıranın uzunluğu değişirse durum değişebilir.

### <a name="example"></a>Örnek

```cpp
// cliext_set_begin.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// inspect first two items
    Myset::iterator it = c1.begin();
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

## <a name="setclear-stlclr"></a><a name="clear"></a> Set:: Clear (STL/CLR)

Tüm öğeleri kaldırır.

### <a name="syntax"></a>Syntax

```cpp
void clear();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, [set:: Erase (STL/CLR)](#erase) set:: `(` [BEGIN (STL/CLR)](#begin) `(),` [set:: End (STL/CLR](#end)) öğesini etkin bir şekilde çağırır `())` . Denetlenen sıranın boş olduğundan emin olmak için bunu kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// cliext_set_clear.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// clear the container and reinspect
    c1.clear();
    System::Console::WriteLine("size() = {0}", c1.size());

// add elements and clear again
    c1.insert(L'a');
    c1.insert(L'b');

    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    c1.clear();
    System::Console::WriteLine("size() = {0}", c1.size());
    return (0);
    }
```

```Output
a b c
size() = 0
a b
size() = 0
```

## <a name="setconst_iterator-stlclr"></a><a name="const_iterator"></a> Set:: const_iterator (STL/CLR)

Denetlenen dizi için bir sabit yineleyici türü.

### <a name="syntax"></a>Syntax

```cpp
typedef T2 const_iterator;
```

### <a name="remarks"></a>Açıklamalar

Türü, `T2` Denetlenen dizi için bir sabit çift yönlü yineleyiciyi görebilecek belirtilmemiş türdeki bir nesneyi tanımlar.

### <a name="example"></a>Örnek

```cpp
// cliext_set_const_iterator.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display contents " a b c"
    Myset::const_iterator cit = c1.begin();
    for (; cit != c1.end(); ++cit)
        System::Console::Write("{0} ", *cit);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="setconst_reference-stlclr"></a><a name="const_reference"></a> Set:: const_reference (STL/CLR)

Bir öğe için sabit bir başvuru türü.

### <a name="syntax"></a>Syntax

```cpp
typedef value_type% const_reference;
```

### <a name="remarks"></a>Açıklamalar

Türü bir öğeye sabit bir başvuru tanımlar.

### <a name="example"></a>Örnek

```cpp
// cliext_set_const_reference.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display initial contents " a b c"
    Myset::const_iterator cit = c1.begin();
    for (; cit != c1.end(); ++cit)
        {   // get a const reference to an element
        Myset::const_reference cref = *cit;
        System::Console::Write("{0} ", cref);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="setconst_reverse_iterator-stlclr"></a><a name="const_reverse_iterator"></a> Set:: const_reverse_iterator (STL/CLR)

Denetlenen sıra için bir sabit ters yineleyicinin türü..

### <a name="syntax"></a>Syntax

```cpp
typedef T4 const_reverse_iterator;
```

### <a name="remarks"></a>Açıklamalar

Türü, `T4` denetimli sıra için sabit bir ters Yineleyici işlevi görebilecek belirtilmemiş türdeki bir nesneyi tanımlar.

### <a name="example"></a>Örnek

```cpp
// cliext_set_const_reverse_iterator.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display contents " a b c" reversed
    Myset::const_reverse_iterator crit = c1.rbegin();
    for (; crit != c1.rend(); ++crit)
        System::Console::Write("{0} ", *crit);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
c b a
```

## <a name="setcount-stlclr"></a><a name="count"></a> Set:: Count (STL/CLR)

Belirtilen bir anahtar ile eşleşen öğe sayısını bulur.

### <a name="syntax"></a>Sözdizimi

```cpp
size_type count(key_type key);
```

#### <a name="parameters"></a>Parametreler

*anahtar*<br/>
Aranacak anahtar değer.

### <a name="remarks"></a>Açıklamalar

Member işlevi, *anahtar* ile eşdeğer sıralamaya sahip olan denetimli dizideki öğe sayısını döndürür. Belirtilen bir anahtarla eşleşen denetimli dizide bulunan öğe sayısını öğrenmek için bunu kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// cliext_set_count.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    System::Console::WriteLine("count(L'A') = {0}", c1.count(L'A'));
    System::Console::WriteLine("count(L'b') = {0}", c1.count(L'b'));
    System::Console::WriteLine("count(L'C') = {0}", c1.count(L'C'));
    return (0);
    }
```

```Output
a b c
count(L'A') = 0
count(L'b') = 1
count(L'C') = 0
```

## <a name="setdifference_type-stlclr"></a><a name="difference_type"></a> ayarla::d ifference_type (STL/CLR)

İki öğe arasındaki işaretli bir mesafe türü.

### <a name="syntax"></a>Syntax

```cpp
typedef int difference_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, büyük olasılıkla negatif bir öğe sayısını tanımlar.

### <a name="example"></a>Örnek

```cpp
// cliext_set_difference_type.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// compute positive difference
    Myset::difference_type diff = 0;
    for (Myset::iterator it = c1.begin(); it != c1.end(); ++it)
        ++diff;
    System::Console::WriteLine("end()-begin() = {0}", diff);

// compute negative difference
    diff = 0;
    for (Myset::iterator it = c1.end(); it != c1.begin(); --it)
        --diff;
    System::Console::WriteLine("begin()-end() = {0}", diff);
    return (0);
    }
```

```Output
a b c
end()-begin() = 3
begin()-end() = -3
```

## <a name="setempty-stlclr"></a><a name="empty"></a> Set:: Empty (STL/CLR)

Bir öğe olup olmadığını sınar.

### <a name="syntax"></a>Syntax

```cpp
bool empty();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi boş bir denetlenen dizi için true döndürür. [Set:: size (STL/CLR)](#size)ile eşdeğerdir `() == 0` . Bu ayarı, kümesinin boş olup olmadığını test etmek için kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// cliext_set_empty.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    System::Console::WriteLine("size() = {0}", c1.size());
    System::Console::WriteLine("empty() = {0}", c1.empty());

// clear the container and reinspect
    c1.clear();
    System::Console::WriteLine("size() = {0}", c1.size());
    System::Console::WriteLine("empty() = {0}", c1.empty());
    return (0);
    }
```

```Output
a b c
size() = 3
empty() = False
size() = 0
empty() = True
```

## <a name="setend-stlclr"></a><a name="end"></a> Set:: End (STL/CLR)

Denetlenen dizinin bitişini belirtir.

### <a name="syntax"></a>Syntax

```cpp
iterator end();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, denetimli dizinin sonunun hemen ötesinde işaret eden çift yönlü bir yineleyici döndürür. Denetlenen dizinin sonunu atayan bir yineleyici elde etmek için bunu kullanırsınız; denetlenen sıranın uzunluğu değişirse, durumu değişmez.

### <a name="example"></a>Örnek

```cpp
// cliext_set_end.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// inspect last two items
    Myset::iterator it = c1.end();
    --it;
    System::Console::WriteLine("*-- --end() = {0}", *--it);
    System::Console::WriteLine("*--end() = {0}", *++it);
    return (0);
    }
```

```Output
a b c
*-- --end() = b
*--end() = c
```

## <a name="setequal_range-stlclr"></a><a name="equal_range"></a> Set:: equal_range (STL/CLR)

Belirtilen bir anahtarla eşleşen aralığı bulur.

### <a name="syntax"></a>Sözdizimi

```cpp
cliext::pair<iterator, iterator> equal_range(key_type key);
```

#### <a name="parameters"></a>Parametreler

*anahtar*<br/>
Aranacak anahtar değer.

### <a name="remarks"></a>Açıklamalar

Üye işlevi bir çift yineleyiciler `cliext::pair<iterator, iterator>(` [kümesi döndürür:: lower_bound (STL/CLR)](#lower_bound) `(key),` [set:: upper_bound (STL/CLR)](#upper_bound) `(key))` . Belirli bir anahtarla eşleşen denetimli dizide bulunan öğe aralığını öğrenmek için bunu kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// cliext_set_equal_range.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
typedef Myset::pair_iter_iter Pairii;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// display results of failed search
    Pairii pair1 = c1.equal_range(L'x');
    System::Console::WriteLine("equal_range(L'x') empty = {0}",
        pair1.first == pair1.second);

// display results of successful search
    pair1 = c1.equal_range(L'b');
    for (; pair1.first != pair1.second; ++pair1.first)
        System::Console::Write("{0} ", *pair1.first);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
equal_range(L'x') empty = True
b
```

## <a name="seterase-stlclr"></a><a name="erase"></a> Set:: Erase (STL/CLR)

Belirtilen konumlardaki öğeleri kaldırır.

### <a name="syntax"></a>Sözdizimi

```cpp
iterator erase(iterator where);
iterator erase(iterator first, iterator last);
size_type erase(key_type key)
```

#### <a name="parameters"></a>Parametreler

*adı*<br/>
Silinecek aralığın başlangıcı.

*anahtar*<br/>
Silinecek anahtar değer.

*soyadına*<br/>
Silinecek aralığın sonu.

*olmadığı*<br/>
Silinecek öğe.

### <a name="remarks"></a>Açıklamalar

İlk üye *işlevi, öğesinin* işaret ettiği denetlenen sıranın öğesini kaldırır ve kaldırılan öğenin ötesinde ilk öğeyi atayan bir yineleyici döndürür ya da böyle bir öğe yoksa, [:: End (STL/CLR) ayarlayın](#end) `()` . Tek bir öğeyi kaldırmak için bunu kullanırsınız.

İkinci üye işlevi, [,) aralığındaki denetimli sıranın öğelerini kaldırır `first` `last` ve kaldırılan tüm öğelerin ötesinde kalan ilk öğeyi veya böyle bir öğe yoksa bir yineleyici döndürür `end()` . Sıfır veya daha fazla bitişik öğeyi kaldırmak için bunu kullanırsınız.

Üçüncü üye işlevi, anahtarı *anahtara* denk sıralama değerine sahip denetimli dizinin herhangi bir öğesini kaldırır ve kaldırılan öğe sayısının sayısını döndürür. Bu anahtarı, belirtilen bir anahtarla eşleşen tüm öğeleri kaldırmak ve saymak için kullanırsınız.

Her bir öğe, denetlenen dizideki öğelerin sayısının logaritması ile orantılı bir zaman alır.

### <a name="example"></a>Örnek

```cpp
// cliext_set_erase.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// erase an element and reinspect
    System::Console::WriteLine("erase(begin()) = {0}",
        *c1.erase(c1.begin()));

// add elements and display " b c d e"
    c1.insert(L'd');
    c1.insert(L'e');
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// erase all but end
    Myset::iterator it = c1.end();
    System::Console::WriteLine("erase(begin(), end()-1) = {0}",
        *c1.erase(c1.begin(), --it));
    System::Console::WriteLine("size() = {0}", c1.size());
    return (0);
    }
```

```Output
a b c
erase(begin()) = b
b c d e
erase(begin(), end()-1) = e
size() = 1
```

## <a name="setfind-stlclr"></a><a name="find"></a> Set:: Find (STL/CLR)

Belirtilen bir anahtarla eşleşen bir öğeyi bulur.

### <a name="syntax"></a>Sözdizimi

```cpp
iterator find(key_type key);
```

#### <a name="parameters"></a>Parametreler

*anahtar*<br/>
Aranacak anahtar değer.

### <a name="remarks"></a>Açıklamalar

Denetlenen dizide en az bir öğe *anahtar* ile eşdeğer sıralamaya sahipse, üye işlevi bu öğelerden birini tanımlayarak bir yineleyici döndürür; Aksi takdirde [set:: End (STL/CLR)](#end)döndürür `()` . Belirtilen bir anahtarla eşleşen denetimli dizide bulunan bir öğeyi bulmak için bunu kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// cliext_set_find.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    System::Console::WriteLine("find {0} = {1}",
        L'A', c1.find(L'A') != c1.end());
    System::Console::WriteLine("find {0} = {1}",
        L'b', *c1.find(L'b'));
    System::Console::WriteLine("find {0} = {1}",
        L'C', c1.find(L'C') != c1.end());
    return (0);
    }
```

```Output
a b c
find A = False
find b = b
find C = False
```

## <a name="setgeneric_container-stlclr"></a><a name="generic_container"></a> Set:: generic_container (STL/CLR)

Kapsayıcının genel arabiriminin türü.

### <a name="syntax"></a>Syntax

```cpp
typedef Microsoft::VisualC::StlClr::
    ITree<GKey, GValue>
    generic_container;
```

### <a name="remarks"></a>Açıklamalar

Tür, bu şablon kapsayıcı sınıfı için genel arabirimi tanımlar.

### <a name="example"></a>Örnek

```cpp
// cliext_set_generic_container.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// construct a generic container
    Myset::generic_container^ gc1 = %c1;
    for each (wchar_t elem in gc1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// modify generic and display original
    gc1->insert(L'd');
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// modify original and display generic
    c1.insert(L'e');
    for each (wchar_t elem in gc1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
a b c
a b c d
a b c d e
```

## <a name="setgeneric_iterator-stlclr"></a><a name="generic_iterator"></a> Set:: generic_iterator (STL/CLR)

Kapsayıcı için genel arabirimle birlikte kullanılacak bir yineleyici türü.

### <a name="syntax"></a>Syntax

```cpp
typedef Microsoft::VisualC::StlClr::Generic::
    ContainerBidirectionalIterator<generic_value>
    generic_iterator;
```

### <a name="remarks"></a>Açıklamalar

Tür, bu şablon kapsayıcı sınıfı için genel arabirim ile kullanılabilen genel bir yineleyiciyi açıklar.

### <a name="example"></a>Örnek

```cpp
// cliext_set_generic_iterator.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// construct a generic container
    Myset::generic_container^ gc1 = %c1;
    for each (wchar_t elem in gc1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// get an element and display it
    Myset::generic_iterator gcit = gc1->begin();
    Myset::generic_value gcval = *gcit;
    System::Console::WriteLine("{0} ", gcval);
    return (0);
    }
```

```Output
a b c
a b c
a
```

## <a name="setgeneric_reverse_iterator-stlclr"></a><a name="generic_reverse_iterator"></a> Set:: generic_reverse_iterator (STL/CLR)

Kapsayıcı için genel arabirimle birlikte kullanılacak ters yineleyicinin türü.

### <a name="syntax"></a>Syntax

```cpp
typedef Microsoft::VisualC::StlClr::Generic::
    ReverseRandomAccessIterator<generic_value>
    generic_reverse_iterator;
```

### <a name="remarks"></a>Açıklamalar

Tür, bu şablon kapsayıcı sınıfı için genel arabirimle birlikte kullanılabilecek bir genel ters yineleyici tanımlar.

### <a name="example"></a>Örnek

```cpp
// cliext_set_generic_reverse_iterator.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// construct a generic container
    Myset::generic_container^ gc1 = %c1;
    for each (wchar_t elem in gc1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// get an element and display it
    Myset::generic_reverse_iterator gcit = gc1->rbegin();
    Myset::generic_value gcval = *gcit;
    System::Console::WriteLine("{0} ", gcval);
    return (0);
    }
```

```Output
a b c
a b c
c
```

## <a name="setgeneric_value-stlclr"></a><a name="generic_value"></a> Set:: generic_value (STL/CLR)

Kapsayıcının genel arabirimiyle kullanılacak öğe türü.

### <a name="syntax"></a>Syntax

```cpp
typedef GValue generic_value;
```

### <a name="remarks"></a>Açıklamalar

Tür, `GValue` Bu şablon kapsayıcı sınıfı için genel arabirimle birlikte kullanılacak saklı öğe değerini açıklayan türünde bir nesne tanımlar.

### <a name="example"></a>Örnek

```cpp
// cliext_set_generic_value.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// construct a generic container
    Myset::generic_container^ gc1 = %c1;
    for each (wchar_t elem in gc1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// get an element and display it
    Myset::generic_iterator gcit = gc1->begin();
    Myset::generic_value gcval = *gcit;
    System::Console::WriteLine("{0} ", gcval);
    return (0);
    }
```

```Output
a b c
a b c
a
```

## <a name="setinsert-stlclr"></a><a name="insert"></a> Set:: insert (STL/CLR)

Öğeleri ekler.

### <a name="syntax"></a>Sözdizimi

```cpp
cliext::pair<iterator, bool> insert(value_type val);
iterator insert(iterator where, value_type val);
template<typename InIter>
    void insert(InIter first, InIter last);
void insert(System::Collections::Generic::IEnumerable<value_type>^ right);
```

#### <a name="parameters"></a>Parametreler

*adı*<br/>
Eklenecek aralığın başlangıcı.

*soyadına*<br/>
Eklenecek aralığın sonu.

*Right*<br/>
Eklenecek sabit listesi.

*Acil*<br/>
Eklenecek anahtar değer.

*olmadığı*<br/>
Kapsayıcının ekleneceği yer (yalnızca ipucu).

### <a name="remarks"></a>Açıklamalar

Üye işlevlerinin her biri, kalan işlenenler tarafından belirtilen bir sıra ekler.

İlk üye işlevi, value değeri olan bir öğe eklemek için endeavors ve bir *çift değer döndürür* `X` . `X.second`True ise, `X.first` yeni eklenen öğeyi belirtir; Aksi takdirde, `X.first` zaten var olan ve yeni bir öğe eklenmemiş eşdeğer sıralamaya sahip bir öğe atar. Tek bir öğe eklemek için bunu kullanırsınız.

İkinci üye işlevi, bir ipucu olarak *WHERE* (performansı artırmak için) ve yeni eklenen öğeyi atayan bir yineleyici döndüren bir *değer değeri olan* bir öğe ekler. Bildiğiniz bir öğeye bitişik olabilecek tek bir öğe eklemek için bunu kullanırsınız.

Üçüncü üye işlevi [,) dizisini ekler `first` `last` . Başka bir dizide kopyalanmış sıfır veya daha fazla öğe eklemek için bunu kullanırsınız.

Dördüncü üye işlevi, *sağ* tarafından belirlenen diziyi ekler. Bir Numaralandırıcı tarafından tanımlanan bir sıra eklemek için bunu kullanırsınız.

Her öğe ekleme, denetlenen dizideki öğelerin sayısının logaritması ile orantılı bir zaman alır. Ekleme noktası, ekleme noktasına bitişik bir öğe atayan bir ipucu verildiğinde, sabit zamanlı olarak ekleme yapılabilir.

### <a name="example"></a>Örnek

```cpp
// cliext_set_insert.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
typedef Myset::pair_iter_bool Pairib;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// insert a single value, unique and duplicate
    Pairib pair1 = c1.insert(L'x');
    System::Console::WriteLine("insert(L'x') = [{0} {1}]",
        *pair1.first, pair1.second);

    pair1 = c1.insert(L'b');
    System::Console::WriteLine("insert(L'b') = [{0} {1}]",
        *pair1.first, pair1.second);

    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// insert a single value with hint
    System::Console::WriteLine("insert(begin(), L'y') = {0}",
        *c1.insert(c1.begin(), L'y'));
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// insert an iterator range
    Myset c2;
    Myset::iterator it = c1.end();
    c2.insert(c1.begin(), --it);
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// insert an enumeration
    Myset c3;
    c3.insert(   // NOTE: cast is not needed
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c1);
    for each (wchar_t elem in c3)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
insert(L'x') = [x True]
insert(L'b') = [b False]
a b c x
insert(begin(), L'y') = y
a b c x y
a b c x
a b c x y
```

## <a name="setiterator-stlclr"></a><a name="iterator"></a> Set:: yineleyici (STL/CLR)

Denetlenen dizi için bir yineleyici türü.

### <a name="syntax"></a>Syntax

```cpp
typedef T1 iterator;
```

### <a name="remarks"></a>Açıklamalar

Türü, `T1` denetimli sıra için çift yönlü bir yineleyici olarak kullanılabilecek belirtilmemiş türdeki bir nesneyi tanımlar.

### <a name="example"></a>Örnek

```cpp
// cliext_set_iterator.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display contents " a b c"
    Myset::iterator it = c1.begin();
    for (; it != c1.end(); ++it)
        System::Console::Write("{0} ", *it);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="setkey_comp-stlclr"></a><a name="key_comp"></a> Set:: key_comp (STL/CLR)

Sıralama temsilcisini iki anahtar için kopyalar.

### <a name="syntax"></a>Syntax

```cpp
key_compare^key_comp();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, denetimli sırayı sıralamak için kullanılan sıralama temsilcisini döndürür. İki anahtarı karşılaştırmak için bunu kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// cliext_set_key_comp.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    Myset::key_compare^ kcomp = c1.key_comp();

    System::Console::WriteLine("compare(L'a', L'a') = {0}",
        kcomp(L'a', L'a'));
    System::Console::WriteLine("compare(L'a', L'b') = {0}",
        kcomp(L'a', L'b'));
    System::Console::WriteLine("compare(L'b', L'a') = {0}",
        kcomp(L'b', L'a'));
    System::Console::WriteLine();

// test a different ordering rule
    Myset c2 = cliext::greater<wchar_t>();
    kcomp = c2.key_comp();

    System::Console::WriteLine("compare(L'a', L'a') = {0}",
        kcomp(L'a', L'a'));
    System::Console::WriteLine("compare(L'a', L'b') = {0}",
        kcomp(L'a', L'b'));
    System::Console::WriteLine("compare(L'b', L'a') = {0}",
        kcomp(L'b', L'a'));
    return (0);
    }
```

```Output
compare(L'a', L'a') = False
compare(L'a', L'b') = True
compare(L'b', L'a') = False

compare(L'a', L'a') = False
compare(L'a', L'b') = False
compare(L'b', L'a') = True
```

## <a name="setkey_compare-stlclr"></a><a name="key_compare"></a> Set:: key_compare (STL/CLR)

İki anahtar için sıralama temsilcisi.

### <a name="syntax"></a>Syntax

```cpp
Microsoft::VisualC::StlClr::BinaryDelegate<GKey, GKey, bool>
    key_compare;
```

### <a name="remarks"></a>Açıklamalar

Tür, anahtar bağımsız değişkenlerinin sıralamasını belirleyen temsilcinin eşanlamlısıdır.

### <a name="example"></a>Örnek

```cpp
// cliext_set_key_compare.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    Myset::key_compare^ kcomp = c1.key_comp();

    System::Console::WriteLine("compare(L'a', L'a') = {0}",
        kcomp(L'a', L'a'));
    System::Console::WriteLine("compare(L'a', L'b') = {0}",
        kcomp(L'a', L'b'));
    System::Console::WriteLine("compare(L'b', L'a') = {0}",
        kcomp(L'b', L'a'));
    System::Console::WriteLine();

// test a different ordering rule
    Myset c2 = cliext::greater<wchar_t>();
    kcomp = c2.key_comp();

    System::Console::WriteLine("compare(L'a', L'a') = {0}",
        kcomp(L'a', L'a'));
    System::Console::WriteLine("compare(L'a', L'b') = {0}",
        kcomp(L'a', L'b'));
    System::Console::WriteLine("compare(L'b', L'a') = {0}",
        kcomp(L'b', L'a'));
    return (0);
    }
```

```Output
compare(L'a', L'a') = False
compare(L'a', L'b') = True
compare(L'b', L'a') = False

compare(L'a', L'a') = False
compare(L'a', L'b') = False
compare(L'b', L'a') = True
```

## <a name="setkey_type-stlclr"></a><a name="key_type"></a> Set:: key_type (STL/CLR)

Bir sıralama anahtarının türü.

### <a name="syntax"></a>Syntax

```cpp
typedef Key key_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, şablon parametre *anahtarı* için bir eş anlamlı.

### <a name="example"></a>Örnek

```cpp
// cliext_set_key_type.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display contents " a b c" using key_type
    for (Myset::iterator it = c1.begin(); it != c1.end(); ++it)
        {   // store element in key_type object
        Myset::key_type val = *it;

        System::Console::Write("{0} ", val);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="setlower_bound-stlclr"></a><a name="lower_bound"></a> Set:: lower_bound (STL/CLR)

Belirtilen anahtarla eşleşen aralığın başlangıcını bulur.

### <a name="syntax"></a>Sözdizimi

```cpp
iterator lower_bound(key_type key);
```

#### <a name="parameters"></a>Parametreler

*anahtar*<br/>
Aranacak anahtar değer.

### <a name="remarks"></a>Açıklamalar

Üye işlevi, `X` denetimli dizideki, *anahtara* denk sıralamaya sahip ilk öğeyi belirler. Böyle bir öğe yoksa, [set:: End (STL/CLR)](#end)döndürür `()` ; Aksi takdirde, öğesini atayan bir yineleyici döndürür `X` . Belirtilen bir anahtarla eşleşen, denetlenen dizide bulunan bir öğe dizisinin başlangıcını bulmak için bunu kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// cliext_set_lower_bound.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    System::Console::WriteLine("lower_bound(L'x')==end() = {0}",
        c1.lower_bound(L'x') == c1.end());

    System::Console::WriteLine("*lower_bound(L'a') = {0}",
        *c1.lower_bound(L'a'));
    System::Console::WriteLine("*lower_bound(L'b') = {0}",
        *c1.lower_bound(L'b'));
    return (0);
    }
```

```Output
a b c
lower_bound(L'x')==end() = True
*lower_bound(L'a') = a
*lower_bound(L'b') = b
```

## <a name="setmake_value-stlclr"></a><a name="make_value"></a> Set:: make_value (STL/CLR)

Değer nesnesi oluşturur.

### <a name="syntax"></a>Sözdizimi

```cpp
static value_type make_value(key_type key);
```

#### <a name="parameters"></a>Parametreler

*anahtar*<br/>
Kullanılacak anahtar değer.

### <a name="remarks"></a>Açıklamalar

Üye işlevi, `value_type` anahtarı *anahtar* olan bir nesne döndürür. Diğer birçok üye işlevi ile kullanmak üzere uygun bir nesne oluşturmak için bunu kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// cliext_set_make_value.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(Myset::make_value(L'a'));
    c1.insert(Myset::make_value(L'b'));
    c1.insert(Myset::make_value(L'c'));

// display contents " a b c"
    for each (Myset::value_type elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="setoperator-stlclr"></a><a name="op_as"></a> Set:: operator = (STL/CLR)

Denetlenen sırayı değiştirir.

### <a name="syntax"></a>Sözdizimi

```cpp
set<Key>% operator=(set<Key>% right);
```

#### <a name="parameters"></a>Parametreler

*Right*<br/>
Kopyalanacak kapsayıcı.

### <a name="remarks"></a>Açıklamalar

Üye işleci nesnesine *sağ* kopyalar ve ardından döndürür **`*this`** . Denetlenen diziyi, denetimli sıranın bir kopyasıyla değiştirmek için bunu *kullanırsınız.*

### <a name="example"></a>Örnek

```cpp
// cliext_set_operator_as.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display contents " a b c"
    for each (Myset::value_type elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// assign to a new container
    Myset c2;
    c2 = c1;
// display contents " a b c"
    for each (Myset::value_type elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
a b c
```

## <a name="setrbegin-stlclr"></a><a name="rbegin"></a> Set:: rbegin (STL/CLR)

Ters denetlenen sıranın başlangıcını belirtir.

### <a name="syntax"></a>Syntax

```cpp
reverse_iterator rbegin();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, denetimli sıranın son öğesini veya boş bir dizinin başlangıcının ötesinde bir ters yineleyici döndürür. Bu nedenle, `beginning` ters sıranın öğesini belirler. Doğru sırada görülen denetimli sıranın başlangıcını atayan bir yineleyici elde etmek için bunu kullanırsınız `current` , ancak denetlenen sıranın uzunluğu değişirse durum değişebilir.

### <a name="example"></a>Örnek

```cpp
// cliext_set_rbegin.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// inspect first two items in reversed sequence
    Myset::reverse_iterator rit = c1.rbegin();
    System::Console::WriteLine("*rbegin() = {0}", *rit);
    System::Console::WriteLine("*++rbegin() = {0}", *++rit);
    return (0);
    }
```

```Output
a b c
*rbegin() = c
*++rbegin() = b
```

## <a name="setreference-stlclr"></a><a name="reference"></a> Set:: Reference (STL/CLR)

Bir öğe için bir başvuru türü.

### <a name="syntax"></a>Syntax

```cpp
typedef value_type% reference;
```

### <a name="remarks"></a>Açıklamalar

Türü bir öğesi başvurusunu tanımlar.

### <a name="example"></a>Örnek

```cpp
// cliext_set_reference.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display initial contents " a b c"
    Myset::iterator it = c1.begin();
    for (; it != c1.end(); ++it)
        {   // get a reference to an element
        Myset::reference ref = *it;
        System::Console::Write("{0} ", ref);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="setrend-stlclr"></a><a name="rend"></a> Set:: rend (STL/CLR)

Ters denetlenen sıranın sonunu belirtir.

### <a name="syntax"></a>Syntax

```cpp
reverse_iterator rend();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, denetimli sıranın başlangıcının hemen ötesinde bir ters yineleyici döndürür. Bu nedenle, `end` ters sıranın öğesini belirler. Bu uygulamayı, `current` geriye doğru sırada görülen denetlenen sıranın sonunu atayan bir yineleyici elde etmek için kullanırsınız, ancak denetlenen sıranın uzunluğu değişirse durum değişebilir.

### <a name="example"></a>Örnek

```cpp
// cliext_set_rend.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// inspect first two items
    Myset::reverse_iterator rit = c1.rend();
    --rit;
    System::Console::WriteLine("*-- --rend() = {0}", *--rit);
    System::Console::WriteLine("*--rend() = {0}", *++rit);
    return (0);
    }
```

```Output
a b c
*-- --rend() = b
*--rend() = a
```

## <a name="setreverse_iterator-stlclr"></a><a name="reverse_iterator"></a> Set:: reverse_iterator (STL/CLR)

Denetlenen sıra için ters yineleyicinin türü.

### <a name="syntax"></a>Syntax

```cpp
typedef T3 reverse_iterator;
```

### <a name="remarks"></a>Açıklamalar

Tür, `T3` denetlenen sıra için ters Yineleyici olarak işlev görebilecek belirtilmemiş türdeki bir nesneyi tanımlar.

### <a name="example"></a>Örnek

```cpp
// cliext_set_reverse_iterator.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display contents " a b c" reversed
    Myset::reverse_iterator rit = c1.rbegin();
    for (; rit != c1.rend(); ++rit)
        System::Console::Write("{0} ", *rit);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
c b a
```

## <a name="setset-stlclr"></a><a name="set"></a> Set:: set (STL/CLR)

Bir kapsayıcı nesnesi oluşturur.

### <a name="syntax"></a>Sözdizimi

```cpp
set();
explicit set(key_compare^ pred);
set(set<Key>% right);
set(set<Key>^ right);
template<typename InIter>
    setset(InIter first, InIter last);
template<typename InIter>
    set(InIter first, InIter last,
        key_compare^ pred);
set(System::Collections::Generic::IEnumerable<GValue>^ right);
set(System::Collections::Generic::IEnumerable<GValue>^ right,
    key_compare^ pred);
```

#### <a name="parameters"></a>Parametreler

*adı*<br/>
Eklenecek aralığın başlangıcı.

*soyadına*<br/>
Eklenecek aralığın sonu.

*pred*<br/>
Denetlenen sıra için sıralama koşulu.

*Right*<br/>
Eklenecek nesne veya Aralık.

### <a name="remarks"></a>Açıklamalar

Oluşturucu:

`set();`

Varsayılan sıralama koşulu ile denetimli sırayı öğesi olmadan başlatır `key_compare()` . Varsayılan sıralama koşulu ile boş bir ilk denetimli sıra belirtmek için bunu kullanırsınız.

Oluşturucu:

`explicit set(key_compare^ pred);`

denetlenen sırayı, sıralama koşulu *Pred* ile birlikte hiçbir öğe olmadan başlatır. Belirtilen sıralama koşulu ile boş bir ilk denetimli sıra belirtmek için bunu kullanırsınız.

Oluşturucu:

`set(set<Key>% right);`

[,) sırası ile denetlenen sırayı `right.begin()` `right.end()` varsayılan sıralama koşulu ile başlatır. Varsayılan sıralama koşulu ile, *küme nesnesi tarafından* denetlenen sıranın bir kopyası olan ilk denetimli bir sıra belirtmek için bunu kullanırsınız.

Oluşturucu:

`set(set<Key>^ right);`

[,) sırası ile denetlenen sırayı `right->begin()` `right->end()` varsayılan sıralama koşulu ile başlatır. Varsayılan sıralama koşulu ile, *küme nesnesi tarafından* denetlenen sıranın bir kopyası olan ilk denetimli bir sıra belirtmek için bunu kullanırsınız.

Oluşturucu:

`template<typename InIter> set(InIter first, InIter last);`

[,) sırası ile denetlenen sırayı `first` `last` varsayılan sıralama koşulu ile başlatır. Varsayılan sıralama koşulu ile, denetimli diziyi başka bir dizinin bir kopyası yapmak için kullanabilirsiniz.

Oluşturucu:

`template<typename InIter> set(InIter first, InIter last, key_compare^ pred);`

[,) sırası ile denetlenen sırayı `first` `last` , sıralama koşulu *Pred* ile başlatır. Belirtilen sıralama koşulu ile, denetimli diziyi başka bir dizinin bir kopyası yapmak için kullanabilirsiniz.

Oluşturucu:

`set(System::Collections::Generic::IEnumerable<Key>^ right);`

denetlenen sırayı, varsayılan sıralama koşulu ile Numaralandırıcı *hakkı* tarafından belirlenen sırayla başlatır. Denetim, varsayılan sıralama koşulu ile, bir Numaralandırıcı tarafından tanımlanan başka bir dizinin kopyasını oluşturmak için kullanılır.

Oluşturucu:

`set(System::Collections::Generic::IEnumerable<Key>^ right, key_compare^ pred);`

denetlenen diziyi Numaralandırıcı *hakkı* ile belirlenen sıra ile başlatır, sıralama koşulu *Pred*. Denetim, belirtilen sıralama koşulu ile bir Numaralandırıcı tarafından tanımlanan başka bir dizinin bir kopyasını oluşturmak için kullanılır.

### <a name="example"></a>Örnek

```cpp
// cliext_set_construct.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
// construct an empty container
    Myset c1;
    System::Console::WriteLine("size() = {0}", c1.size());

    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// construct with an ordering rule
    Myset c2 = cliext::greater_equal<wchar_t>();
    System::Console::WriteLine("size() = {0}", c2.size());

    c2.insert(c1.begin(), c1.end());
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// construct with an iterator range
    Myset c3(c1.begin(), c1.end());
    for each (wchar_t elem in c3)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// construct with an iterator range and an ordering rule
    Myset c4(c1.begin(), c1.end(),
        cliext::greater_equal<wchar_t>());
    for each (wchar_t elem in c4)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// construct with an enumeration
    Myset c5(   // NOTE: cast is not needed
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c3);
    for each (wchar_t elem in c5)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// construct with an enumeration and an ordering rule
    Myset c6(   // NOTE: cast is not needed
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c3,
            cliext::greater_equal<wchar_t>());
    for each (wchar_t elem in c6)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// construct from a generic container
    Myset c7(c4);
    for each (wchar_t elem in c7)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// construct by copying another container
    Myset c8(%c3);
    for each (wchar_t elem in c8)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
size() = 0
a b c
size() = 0
c b a
a b c
c b a
a b c
c b a
c b a
a b c
```

## <a name="setsize-stlclr"></a><a name="size"></a> Set:: size (STL/CLR)

Öğe sayısını sayar.

### <a name="syntax"></a>Syntax

```cpp
size_type size();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi denetlenen sıranın uzunluğunu döndürür. Bu, şu anda denetlenen dizideki öğelerin sayısını tespit etmek için kullanılır. Her şey için, sıranın sıfır dışında bir boyuta sahip olup olmadığı, bkz. [set:: Empty (STL/CLR)](#empty) `()` .

### <a name="example"></a>Örnek

```cpp
// cliext_set_size.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    System::Console::WriteLine("size() = {0} starting with 3", c1.size());

// clear the container and reinspect
    c1.clear();
    System::Console::WriteLine("size() = {0} after clearing", c1.size());

// add elements and clear again
    c1.insert(L'a');
    c1.insert(L'b');
    System::Console::WriteLine("size() = {0} after adding 2", c1.size());
    return (0);
    }
```

```Output
a b c
size() = 3 starting with 3
size() = 0 after clearing
size() = 2 after adding 2
```

## <a name="setsize_type-stlclr"></a><a name="size_type"></a> Set:: size_type (STL/CLR)

İki öğe arasındaki işaretli bir mesafe türü.

### <a name="syntax"></a>Syntax

```cpp
typedef int size_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, negatif olmayan bir öğe sayısını tanımlar.

### <a name="example"></a>Örnek

```cpp
// cliext_set_size_type.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// compute positive difference
    Myset::size_type diff = 0;
    for (Myset::iterator it = c1.begin(); it != c1.end(); ++it)
        ++diff;
    System::Console::WriteLine("end()-begin() = {0}", diff);
    return (0);
    }
```

```Output
a b c
end()-begin() = 3
```

## <a name="setswap-stlclr"></a><a name="swap"></a> Set:: swap (STL/CLR)

İki kapsayıcının içeriğinin yerini değiştirir.

### <a name="syntax"></a>Sözdizimi

```cpp
void swap(set<Key>% right);
```

#### <a name="parameters"></a>Parametreler

*Right*<br/>
İçeriği takas eden kapsayıcı.

### <a name="remarks"></a>Açıklamalar

Üye işlevi, ve sağ arasındaki denetlenen dizileri **`this`** değiştirir . Bu, sabit zamanlı olarak yapar ve özel durum oluşturmaz. Bunu iki kapsayıcının içeriğini değiş tokuş etmek için hızlı bir yol olarak kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// cliext_set_swap.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// construct another container with repetition of values
    Myset c2;
    c2.insert(L'd');
    c2.insert(L'e');
    c2.insert(L'f');
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
d e f
d e f
a b c
```

## <a name="setto_array-stlclr"></a><a name="to_array"></a> Set:: to_array (STL/CLR)

Denetimli sırayı yeni bir diziye kopyalar.

### <a name="syntax"></a>Syntax

```cpp
cli::array<value_type>^ to_array();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi denetlenen sırayı içeren bir dizi döndürür. Dizi biçiminde denetlenen sıranın bir kopyasını almak için bunu kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// cliext_set_to_array.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// copy the container and modify it
    cli::array<wchar_t>^ a1 = c1.to_array();

    c1.insert(L'd');
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// display the earlier array copy
    for each (wchar_t elem in a1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c d
a b c
```

## <a name="setupper_bound-stlclr"></a><a name="upper_bound"></a> Set:: upper_bound (STL/CLR)

Belirtilen anahtarla eşleşen aralığın sonunu bulur.

### <a name="syntax"></a>Sözdizimi

```cpp
iterator upper_bound(key_type key);
```

#### <a name="parameters"></a>Parametreler

*anahtar*<br/>
Aranacak anahtar değer.

### <a name="remarks"></a>Açıklamalar

Üye işlevi, denetimli dizideki en son öğeyi, `X` *anahtara* denk sıralama olarak belirler. Böyle bir öğe yoksa veya `X` denetlenen dizideki son öğe ise, [set:: End (STL/CLR)](#end)döndürür `()` ; Aksi takdirde ilk öğeyi daha sonra atayan bir yineleyici döndürür `X` . Belirtilen bir anahtarla eşleşen denetimli dizide bulunan bir öğe dizisinin sonunu bulmak için bunu kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// cliext_set_upper_bound.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    System::Console::WriteLine("upper_bound(L'x')==end() = {0}",
        c1.upper_bound(L'x') == c1.end());

    System::Console::WriteLine("*upper_bound(L'a') = {0}",
        *c1.upper_bound(L'a'));
    System::Console::WriteLine("*upper_bound(L'b') = {0}",
        *c1.upper_bound(L'b'));
    return (0);
    }
```

```Output
a b c
upper_bound(L'x')==end() = True
*upper_bound(L'a') = b
*upper_bound(L'b') = c
```

## <a name="setvalue_comp-stlclr"></a><a name="value_comp"></a> Set:: value_comp (STL/CLR)

İki öğe değeri için sıralama temsilcisini kopyalar.

### <a name="syntax"></a>Syntax

```cpp
value_compare^ value_comp();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, denetimli sırayı sıralamak için kullanılan sıralama temsilcisini döndürür. İki öğe değerini karşılaştırmak için bunu kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// cliext_set_value_comp.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    Myset::value_compare^ kcomp = c1.value_comp();

    System::Console::WriteLine("compare(L'a', L'a') = {0}",
        kcomp(L'a', L'a'));
    System::Console::WriteLine("compare(L'a', L'b') = {0}",
        kcomp(L'a', L'b'));
    System::Console::WriteLine("compare(L'b', L'a') = {0}",
        kcomp(L'b', L'a'));
    System::Console::WriteLine();
    return (0);
    }
```

```Output
compare(L'a', L'a') = False
compare(L'a', L'b') = True
compare(L'b', L'a') = False
```

## <a name="setvalue_compare-stlclr"></a><a name="value_compare"></a> Set:: value_compare (STL/CLR)

İki öğe değeri için sıralama temsilcisi.

### <a name="syntax"></a>Syntax

```cpp
Microsoft::VisualC::StlClr::BinaryDelegate<generic_value, generic_value, bool>
    value_compare;
```

### <a name="remarks"></a>Açıklamalar

Tür, değer bağımsız değişkenlerinin sıralamasını belirleyen temsilcinin eşanlamlısıdır.

### <a name="example"></a>Örnek

```cpp
// cliext_set_value_compare.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    Myset::value_compare^ kcomp = c1.value_comp();

    System::Console::WriteLine("compare(L'a', L'a') = {0}",
        kcomp(L'a', L'a'));
    System::Console::WriteLine("compare(L'a', L'b') = {0}",
        kcomp(L'a', L'b'));
    System::Console::WriteLine("compare(L'b', L'a') = {0}",
        kcomp(L'b', L'a'));
    System::Console::WriteLine();
    return (0);
    }
```

```Output
compare(L'a', L'a') = False
compare(L'a', L'b') = True
compare(L'b', L'a') = False
```

## <a name="setvalue_type-stlclr"></a><a name="value_type"></a> Set:: value_type (STL/CLR)

Öğenin türü.

### <a name="syntax"></a>Syntax

```cpp
typedef generic_value value_type;
```

### <a name="remarks"></a>Açıklamalar

Tür için bir eş anlamlı `generic_value` .

### <a name="example"></a>Örnek

```cpp
// cliext_set_value_type.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display contents " a b c" using value_type
    for (Myset::iterator it = c1.begin(); it != c1.end(); ++it)
        {   // store element in value_type object
        Myset::value_type val = *it;

        System::Console::Write("{0} ", val);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="operator-set-stlclr"></a><a name="op_neq"></a> operator! = (set) (STL/CLR)

Liste eşit değildir karşılaştırması.

### <a name="syntax"></a>Sözdizimi

```cpp
template<typename Key>
    bool operator!=(set<Key>% left,
        set<Key>% right);
```

#### <a name="parameters"></a>Parametreler

*tarafta*<br/>
Karşılaştırılacak sol kapsayıcı.

*Right*<br/>
Karşılaştırılacak doğru kapsayıcı.

### <a name="remarks"></a>Açıklamalar

İşleç işlevi döndürülür `!(left == right)` . İki küme öğe öğesine göre karşılaştırıldığı zaman *solinin* *doğru* olarak sıralanmadığını test etmek için bunu kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// cliext_set_operator_ne.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// assign to a new container
    Myset c2;
    c2.insert(L'a');
    c2.insert(L'b');
    c2.insert(L'd');

// display contents " a b d"
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    System::Console::WriteLine("[a b c] != [a b c] is {0}",
        c1 != c1);
    System::Console::WriteLine("[a b c] != [a b d] is {0}",
        c1 != c2);
    return (0);
    }
```

```Output
a b c
a b d
[a b c] != [a b c] is False
[a b c] != [a b d] is True
```

## <a name="operatorlt-set-stlclr"></a><a name="op_lt"></a> işleç &lt; (küme) (STL/CLR)

Liste karşılaştırmadan daha az.

### <a name="syntax"></a>Sözdizimi

```cpp
template<typename Key>
    bool operator<(set<Key>% left,
        set<Key>% right);
```

#### <a name="parameters"></a>Parametreler

*tarafta*<br/>
Karşılaştırılacak sol kapsayıcı.

*Right*<br/>
Karşılaştırılacak doğru kapsayıcı.

### <a name="remarks"></a>Açıklamalar

İşleç işlevi, `i` `!(right[i] < left[i])` bunun da doğru olduğu en düşük konum için true değerini döndürür `left[i] < right[i]` . Aksi takdirde, `left->size() < right->size()` iki küme öğe öğesine göre karşılaştırıldığı zaman, *sol taraftan ayrılmadığını* test etmek için bunu kullanır. 

### <a name="example"></a>Örnek

```cpp
// cliext_set_operator_lt.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// assign to a new container
    Myset c2;
    c2.insert(L'a');
    c2.insert(L'b');
    c2.insert(L'd');

// display contents " a b d"
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    System::Console::WriteLine("[a b c] < [a b c] is {0}",
        c1 < c1);
    System::Console::WriteLine("[a b c] < [a b d] is {0}",
        c1 < c2);
    return (0);
    }
```

```Output
a b c
a b d
[a b c] < [a b c] is False
[a b c] < [a b d] is True
```

## <a name="operatorlt-set-stlclr"></a><a name="op_lteq"></a> operator &lt; = (set) (STL/CLR)

Küçüktür veya eşit karşılaştırma listesi.

### <a name="syntax"></a>Sözdizimi

```cpp
template<typename Key>
    bool operator<=(set<Key>% left,
        set<Key>% right);
```

#### <a name="parameters"></a>Parametreler

*tarafta*<br/>
Karşılaştırılacak sol kapsayıcı.

*Right*<br/>
Karşılaştırılacak doğru kapsayıcı.

### <a name="remarks"></a>Açıklamalar

İşleç işlevi döndürülür `!(right < left)` . İki küme öğe öğesine göre karşılaştırıldığı zaman *farenin sağ* *tarafında* sıralı olup olmadığını test etmek için bunu kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// cliext_set_operator_le.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// assign to a new container
    Myset c2;
    c2.insert(L'a');
    c2.insert(L'b');
    c2.insert(L'd');

// display contents " a b d"
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    System::Console::WriteLine("[a b c] <= [a b c] is {0}",
        c1 <= c1);
    System::Console::WriteLine("[a b d] <= [a b c] is {0}",
        c2 <= c1);
    return (0);
    }
```

```Output
a b c
a b d
[a b c] <= [a b c] is True
[a b d] <= [a b c] is False
```

## <a name="operator-set-stlclr"></a><a name="op_eq"></a> operator = = (set) (STL/CLR)

Liste eşit karşılaştırması.

### <a name="syntax"></a>Sözdizimi

```cpp
template<typename Key>
    bool operator==(set<Key>% left,
        set<Key>% right);
```

#### <a name="parameters"></a>Parametreler

*tarafta*<br/>
Karşılaştırılacak sol kapsayıcı.

*Right*<br/>
Karşılaştırılacak doğru kapsayıcı.

### <a name="remarks"></a>Açıklamalar

İşleç işlevi yalnızca *sol* ve *sağ* tarafından denetlenen diziler aynı uzunlukta ve her bir konum için aynı uzunluğa sahip olursa true değerini döndürür `i` `left[i] ==` `right[i]` . İki küme öğe öğesine göre karşılaştırıldığı zaman *solinin* *doğru* olup olmadığını test etmek için bunu kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// cliext_set_operator_eq.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// assign to a new container
    Myset c2;
    c2.insert(L'a');
    c2.insert(L'b');
    c2.insert(L'd');

// display contents " a b d"
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    System::Console::WriteLine("[a b c] == [a b c] is {0}",
        c1 == c1);
    System::Console::WriteLine("[a b c] == [a b d] is {0}",
        c1 == c2);
    return (0);
    }
```

```Output
a b c
a b d
[a b c] == [a b c] is True
[a b c] == [a b d] is False
```

## <a name="operatorgt-set-stlclr"></a><a name="op_gt"></a> işleç &gt; (küme) (STL/CLR)

Karşılaştırmadan daha büyük bir liste.

### <a name="syntax"></a>Sözdizimi

```cpp
template<typename Key>
    bool operator>(set<Key>% left,
        set<Key>% right);
```

#### <a name="parameters"></a>Parametreler

*tarafta*<br/>
Karşılaştırılacak sol kapsayıcı.

*Right*<br/>
Karşılaştırılacak doğru kapsayıcı.

### <a name="remarks"></a>Açıklamalar

İşleç işlevi döndürülür `right` `<` `left` . İki küme öğe öğesine göre karşılaştırıldığı zaman, *sol* *taraftaki bir* değer olup olmadığını test etmek için bunu kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// cliext_set_operator_gt.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// assign to a new container
    Myset c2;
    c2.insert(L'a');
    c2.insert(L'b');
    c2.insert(L'd');

// display contents " a b d"
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    System::Console::WriteLine("[a b c] > [a b c] is {0}",
        c1 > c1);
    System::Console::WriteLine("[a b d] > [a b c] is {0}",
        c2 > c1);
    return (0);
    }
```

```Output
a b c
a b d
[a b c] > [a b c] is False
[a b d] > [a b c] is True
```

## <a name="operatorgt-set-stlclr"></a><a name="op_gteq"></a> operator &gt; = (set) (STL/CLR)

Büyük veya eşit karşılaştırmayı listele.

### <a name="syntax"></a>Sözdizimi

```cpp
template<typename Key>
    bool operator>=(set<Key>% left,
        set<Key>% right);
```

#### <a name="parameters"></a>Parametreler

*tarafta*<br/>
Karşılaştırılacak sol kapsayıcı.

*Right*<br/>
Karşılaştırılacak doğru kapsayıcı.

### <a name="remarks"></a>Açıklamalar

İşleç işlevi döndürülür `!(left < right)` . İki küme öğe öğesine göre karşılaştırıldığı zaman *sağdan* *sola* doğru sıralanmadığını test etmek için bunu kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// cliext_set_operator_ge.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// assign to a new container
    Myset c2;
    c2.insert(L'a');
    c2.insert(L'b');
    c2.insert(L'd');

// display contents " a b d"
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    System::Console::WriteLine("[a b c] >= [a b c] is {0}",
        c1 >= c1);
    System::Console::WriteLine("[a b c] >= [a b d] is {0}",
        c1 >= c2);
    return (0);
    }
```

```Output
a b c
a b d
[a b c] >= [a b c] is True
[a b c] >= [a b d] is False
```
