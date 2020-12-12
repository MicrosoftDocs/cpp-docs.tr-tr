---
description: 'Daha fazla bilgi edinin: çoklu küme (STL/CLR)'
title: çoklu set (STL/CLR)
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- cliext::multiset
- cliext::multiset::begin
- cliext::multiset::clear
- cliext::multiset::const_iterator
- cliext::multiset::const_reference
- cliext::multiset::const_reverse_iterator
- cliext::multiset::count
- cliext::multiset::difference_type
- cliext::multiset::empty
- cliext::multiset::end
- cliext::multiset::equal_range
- cliext::multiset::erase
- cliext::multiset::find
- cliext::multiset::generic_container
- cliext::multiset::generic_iterator
- cliext::multiset::generic_reverse_iterator
- cliext::multiset::generic_value
- cliext::multiset::insert
- cliext::multiset::iterator
- cliext::multiset::key_comp
- cliext::multiset::key_compare
- cliext::multiset::key_type
- cliext::multiset::lower_bound
- cliext::multiset::make_value
- cliext::multiset::multiset
- cliext::multiset::operator=
- cliext::multiset::rbegin
- cliext::multiset::reference
- cliext::multiset::rend
- cliext::multiset::reverse_iterator
- cliext::multiset::size
- cliext::multiset::size_type
- cliext::multiset::swap
- cliext::multiset::to_array
- cliext::multiset::upper_bound
- cliext::multiset::value_comp
- cliext::multiset::value_compare
- cliext::multiset::value_type
- cliext::multiset::operator!=
- cliext::multiset::operator<
- cliext::multiset::operator<=
- cliext::multiset::operator==
- cliext::multiset::operator>
- cliext::multiset::operator>=
helpviewer_keywords:
- <cliext/set> header [STL/CLR]
- <set> header [STL/CLR]
- multiset class [STL/CLR]
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
- map member [STL/CLR]
- mapped_type member [STL/CLR]
- operator= member [STL/CLR]
- operator member [STL/CLR]
- rbegin member [STL/CLR]
- reference member [STL/CLR]
- rend member [STL/CLR]
- reverse_iterator member [STL/CLR]
- size member [STL/CLR]
- size_type member [STL/CLR]
- swap member [STL/CLR]
- to_array member [STL/CLR]
- upper_bound member [STL/CLR]
- value_comp member [STL/CLR]
- value_compare member [STL/CLR]
- value_type member [STL/CLR]
- operator!= member [STL/CLR]
- operator< member [STL/CLR]
- operator<= member [STL/CLR]
- operator== member [STL/CLR]
- operator> member [STL/CLR]
- operator>= member [STL/CLR]
ms.assetid: 7c46e2b4-cd88-49b7-a9e6-63ad5ae7feb5
ms.openlocfilehash: 1b2300fe7b856e989dd470f47da559496374961b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97255658"
---
# <a name="multiset-stlclr"></a>çoklu set (STL/CLR)

Şablon sınıfı, çift yönlü erişime sahip olan öğelerin değişen uzunluklu bir dizisini denetleyen bir nesneyi tanımlar. Öğe `multiset` dizisini, her biri bir öğe depolayan (neredeyse) dengeli sıralı düğüm ağacı olarak yönetmek için kapsayıcısını kullanırsınız.

Aşağıdaki açıklamada, `GValue` ile aynı şekilde, `GKey` İkincisi bir başvuru türü olmadığı sürece *anahtarla* aynı olur ve bu durumda olur `Key^` .

## <a name="syntax"></a>Sözdizimi

```cpp
template<typename Key>
    ref class multiset
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
|[multiset::const_iterator (STL/CLR)](#const_iterator)|Denetlenen dizi için bir sabit yineleyici türü.|
|[multiset::const_reference (STL/CLR)](#const_reference)|Bir öğe için sabit bir başvuru türü.|
|[multiset::const_reverse_iterator (STL/CLR)](#const_reverse_iterator)|Denetlenen sıra için bir sabit ters yineleyicinin türü.|
|[multiset::difference_type (STL/CLR)](#difference_type)|İki öğe arasındaki mesafe (muhtemelen imzalı) türü.|
|[multiset::generic_container (STL/CLR)](#generic_container)|Kapsayıcının genel arabiriminin türü.|
|[multiset::generic_iterator (STL/CLR)](#generic_iterator)|Kapsayıcının genel arabirimi için bir yineleyici türü.|
|[multiset::generic_reverse_iterator (STL/CLR)](#generic_reverse_iterator)|Kapsayıcının genel arabirimi için ters yineleyicinin türü.|
|[multiset::generic_value (STL/CLR)](#generic_value)|Kapsayıcının genel arabirimi için bir öğenin türü.|
|[multiset::iterator (STL/CLR)](#iterator)|Denetlenen dizi için bir yineleyici türü.|
|[multiset::key_compare (STL/CLR)](#key_compare)|İki anahtar için sıralama temsilcisi.|
|[multiset::key_type (STL/CLR)](#key_type)|Bir sıralama anahtarının türü.|
|[multiset::reference (STL/CLR)](#reference)|Bir öğe için bir başvuru türü.|
|[multiset::reverse_iterator (STL/CLR)](#reverse_iterator)|Denetlenen sıra için ters yineleyicinin türü.|
|[multiset::size_type (STL/CLR)](#size_type)|İki öğe arasındaki (negatif olmayan) bir mesafe türü.|
|[multiset::value_compare (STL/CLR)](#value_compare)|İki öğe değeri için sıralama temsilcisi.|
|[multiset::value_type (STL/CLR)](#value_type)|Öğenin türü.|

|Üye İşlevi|Açıklama|
|---------------------|-----------------|
|[multiset::begin (STL/CLR)](#begin)|Denetlenen dizinin başlangıcını belirtir.|
|[multiset::clear (STL/CLR)](#clear)|Tüm öğeleri kaldırır.|
|[multiset::count (STL/CLR)](#count)|Belirtilen bir anahtarla eşleşen öğeleri sayar.|
|[multiset::empty (STL/CLR)](#empty)|Bir öğe olup olmadığını sınar.|
|[multiset::end (STL/CLR)](#end)|Denetlenen dizinin bitişini belirtir.|
|[multiset::equal_range (STL/CLR)](#equal_range)|Belirtilen bir anahtarla eşleşen aralığı bulur.|
|[multiset::erase (STL/CLR)](#erase)|Belirtilen konumlardaki öğeleri kaldırır.|
|[multiset::find (STL/CLR)](#find)|Belirtilen bir anahtarla eşleşen bir öğeyi bulur.|
|[multiset::insert (STL/CLR)](#insert)|Öğeleri ekler.|
|[multiset::key_comp (STL/CLR)](#key_comp)|Sıralama temsilcisini iki anahtar için kopyalar.|
|[multiset::lower_bound (STL/CLR)](#lower_bound)|Belirtilen anahtarla eşleşen aralığın başlangıcını bulur.|
|[multiset::make_value (STL/CLR)](#make_value)|Değer nesnesi oluşturur.|
|[multiset::multiset (STL/CLR)](#multiset)|Bir kapsayıcı nesnesi oluşturur.|
|[multiset::rbegin (STL/CLR)](#rbegin)|Ters denetlenen sıranın başlangıcını belirtir.|
|[multiset::rend (STL/CLR)](#rend)|Ters denetlenen sıranın sonunu belirtir.|
|[multiset::size (STL/CLR)](#size)|Öğe sayısını sayar.|
|[multiset::swap (STL/CLR)](#swap)|İki kapsayıcının içeriğinin yerini değiştirir.|
|[multiset::to_array (STL/CLR)](#to_array)|Denetimli sırayı yeni bir diziye kopyalar.|
|[multiset::upper_bound (STL/CLR)](#upper_bound)|Belirtilen anahtarla eşleşen aralığın sonunu bulur.|
|[multiset::value_comp (STL/CLR)](#value_comp)|İki öğe değeri için sıralama temsilcisini kopyalar.|

|İşleç|Açıklama|
|--------------|-----------------|
|[multiset::operator= (STL/CLR)](#op_as)|Denetlenen sırayı değiştirir.|
|[işleç! = (çoklu küme) (STL/CLR)](#op_neq)|Bir `multiset` nesnenin başka bir nesneye eşit olup olmadığını belirler `multiset` .|
|[işleç< (çoklu küme) (STL/CLR)](#op_lt)|Bir `multiset` nesnenin başka bir nesneden daha az olup olmadığını belirler `multiset` .|
|[işleç<= (çoklu küme) (STL/CLR)](#op_lteq)|Bir `multiset` nesnenin başka bir nesneden küçük veya ona eşit olup olmadığını belirler `multiset` .|
|[işleç = = (çoklu küme) (STL/CLR)](#op_eq)|Bir `multiset` nesnenin başka bir nesneye eşit olup olmadığını belirler `multiset` .|
|[işleç> (çoklu küme) (STL/CLR)](#op_gt)|Bir `multiset` nesnenin başka bir nesneden daha büyük olup olmadığını belirler `multiset` .|
|[operator>= (multiset) (STL/CLR)](#op_gteq)|Bir `multiset` nesnenin başka bir nesneden büyük veya ona eşit olup olmadığını belirler `multiset` .|

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

Nesnesi, çok [kümeli:: key_compare (STL/CLR)](#key_compare)türünde depolanan bir temsilci nesnesi çağırarak denetlediği diziyi sıralar. Çoklu küme oluştururken depolanan temsilci nesnesini belirtebilirsiniz; temsilci nesnesi belirtmezseniz, varsayılan değer karşılaştırmayla belirlenir `operator<(key_type, key_type)` . Bu saklı nesneye çok [kümeli:: key_comp (STL/CLR)](#key_comp)üye işlevini çağırarak erişirsiniz `()` .

Bu tür bir temsilci nesnesi, [multıset:: key_type (STL/CLR)](#key_type)türündeki anahtarlar üzerinde katı zayıf bir sıralama getirmelidir. Yani, her iki anahtar için `X` ve `Y` :

`key_comp()(X, Y)` her çağrıda aynı Boole sonucunu döndürür.

`key_comp()(X, Y)`True ise, false olmalıdır `key_comp()(Y, X)` .

`key_comp()(X, Y)`True ise, daha `X` önce sipariş olarak kabul edilir `Y` .

`!key_comp()(X, Y) && !key_comp()(Y, X)`True ise, `X` ve `Y` eşdeğer sıralamaya sahip olarak kabul edilir.

`X`Denetlenen dizide önündeki tüm öğeler için `Y` `key_comp()(Y, X)` false olur. (Varsayılan temsilci nesnesi için, anahtarlar hiçbir şekilde değerde azalmayın.) Şablon sınıfı [kümesinden (STL/CLR)](../dotnet/set-stl-clr.md)farklı olarak, şablon sınıfının bir nesnesi `multiset` tüm öğeler için anahtarların benzersiz olmasını gerektirmez. (İki veya daha fazla anahtarın eşdeğer sıralaması olabilir.)

Her öğe hem bir ey hem de bir değer görevi görür. Sıra, dizi içindeki öğe sayısının logaritmasına orantılı bir şekilde bir dizi işlem içeren rastgele bir öğenin aranması, eklenmesine ve kaldırılmasına izin veren bir şekilde temsil edilir. Ayrıca, bir öğe eklenmesi hiçbir yineleyiciyi geçersiz kılmaz; bir öğenin kaldırılması yalnızca bu kaldırılan öğeyi gösteren yineleyicileri geçersiz kılar.

Çoklu küme çift yineleyiciler destekler, bu, denetlenen dizide bir öğe atayan bir yineleyici verilen bitişik öğelere adım adım yol açabilir. Özel bir baş düğüm, çok [kümeli:: End (STL/CLR)](#end)tarafından döndürülen Yineleyici öğesine karşılık gelir `()` . Varsa, denetlenen sıradaki son öğeye ulaşmak için bu yineleyiciyi azaltamazsınız. Baş düğüme ulaşmak için bir çoklu küme yineleyicisini arttırıp daha sonra eşit olarak karşılaştırılacağını sağlayabilirsiniz `end()` . Ancak tarafından döndürülen Yineleyici için başvuru oluşturamazsınız `end()` .

Önceden kümeli bir öğeye, rastgele erişim Yineleyici gerektiren, kendi sayısal konumuna doğrudan başvurmayacağınızı unutmayın.

Çoklu küme Yineleyici, ilişkili kapsayıcı düğümüne bir tanıtıcı depolar, bu da ilişkili kapsayıcısına bir tutamacı depolar. Yineleyiciler yalnızca ilişkili kapsayıcı nesneleriyle birlikte kullanabilirsiniz. Bir çoklu küme Yineleyici, ilişkili çoklu küme düğümü bazı çoklu kümeli ile ilişkilendirildiği sürece geçerli kalır. Üstelik, geçerli bir yineleyici bir şekilde gönderilir--bunu, oluşturduğu öğe değerine erişmek veya değiştirmek için kullanabilirsiniz. buna eşit olmadığı sürece `end()` .

Bir öğeyi silme veya kaldırma, kendi saklı değeri için yıkıcıyı çağırır. Kapsayıcının yok edilmesi tüm öğeleri siler. Bu nedenle, öğe türü bir başvuru sınıfı olan bir kapsayıcı, kapsayıcının hiçbir öğenin etkin olmamasını sağlar. Ancak, bir işleç kapsayıcısının *öğelerini yok ettiğini* unutmayın.

## <a name="members"></a>Üyeler

## <a name="multisetbegin-stlclr"></a><a name="begin"></a> Çoklu küme:: Begin (STL/CLR)

Denetlenen dizinin başlangıcını belirtir.

### <a name="syntax"></a>Syntax

```cpp
iterator begin();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, denetimli sıranın ilk öğesini veya boş bir dizinin sonunun ötesinde bir çift yönlü yineleyiciyi döndürür. Denetlenen dizinin başlangıcını atayan bir yineleyici elde etmek için bunu kullanırsınız `current` , ancak denetlenen sıranın uzunluğu değişirse durum değişebilir.

### <a name="example"></a>Örnek

```cpp
// cliext_multiset_begin.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::multiset<wchar_t> Mymultiset;
int main()
    {
    Mymultiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // inspect first two items
    Mymultiset::iterator it = c1.begin();
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

## <a name="multisetclear-stlclr"></a><a name="clear"></a> Çoklu küme:: Clear (STL/CLR)

Tüm öğeleri kaldırır.

### <a name="syntax"></a>Syntax

```cpp
void clear();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi etkin olmayan [Çoklu küme:: Erase (STL/CLR)](#erase) çoklu küme: `(` [: Begin (STL/CLR)](#begin) `(),` [Çoklu küme:: End (STL/CLR)](#end)çağırır `())` . Denetlenen sıranın boş olduğundan emin olmak için bunu kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// cliext_multiset_clear.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::multiset<wchar_t> Mymultiset;
int main()
    {
    Mymultiset c1;
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

## <a name="multisetconst_iterator-stlclr"></a><a name="const_iterator"></a> Çoklu küme:: const_iterator (STL/CLR)

Denetlenen dizi için bir sabit yineleyici türü.

### <a name="syntax"></a>Syntax

```cpp
typedef T2 const_iterator;
```

### <a name="remarks"></a>Açıklamalar

Türü, `T2` Denetlenen dizi için bir sabit çift yönlü yineleyiciyi görebilecek belirtilmemiş türdeki bir nesneyi tanımlar.

### <a name="example"></a>Örnek

```cpp
// cliext_multiset_const_iterator.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::multiset<wchar_t> Mymultiset;
int main()
    {
    Mymultiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display contents " a b c"
    Mymultiset::const_iterator cit = c1.begin();
    for (; cit != c1.end(); ++cit)
        System::Console::Write("{0} ", *cit);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="multisetconst_reference-stlclr"></a><a name="const_reference"></a> Çoklu küme:: const_reference (STL/CLR)

Bir öğe için sabit bir başvuru türü.

### <a name="syntax"></a>Syntax

```cpp
typedef value_type% const_reference;
```

### <a name="remarks"></a>Açıklamalar

Türü bir öğeye sabit bir başvuru tanımlar.

### <a name="example"></a>Örnek

```cpp
// cliext_multiset_const_reference.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::multiset<wchar_t> Mymultiset;
int main()
    {
    Mymultiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    Mymultiset::const_iterator cit = c1.begin();
    for (; cit != c1.end(); ++cit)
        {   // get a const reference to an element
        Mymultiset::const_reference cref = *cit;
        System::Console::Write("{0} ", cref);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="multisetconst_reverse_iterator-stlclr"></a><a name="const_reverse_iterator"></a> Çoklu küme:: const_reverse_iterator (STL/CLR)

Denetlenen sıra için bir sabit ters yineleyicinin türü..

### <a name="syntax"></a>Syntax

```cpp
typedef T4 const_reverse_iterator;
```

### <a name="remarks"></a>Açıklamalar

Türü, `T4` denetimli sıra için sabit bir ters Yineleyici işlevi görebilecek belirtilmemiş türdeki bir nesneyi tanımlar.

### <a name="example"></a>Örnek

```cpp
// cliext_multiset_const_reverse_iterator.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::multiset<wchar_t> Mymultiset;
int main()
    {
    Mymultiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display contents " a b c" reversed
    Mymultiset::const_reverse_iterator crit = c1.rbegin();
    for (; crit != c1.rend(); ++crit)
        System::Console::Write("{0} ", *crit);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
c b a
```

## <a name="multisetcount-stlclr"></a><a name="count"></a> Çoklu küme:: Count (STL/CLR)

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
// cliext_multiset_count.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::multiset<wchar_t> Mymultiset;
int main()
    {
    Mymultiset c1;
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

## <a name="multisetdifference_type-stlclr"></a><a name="difference_type"></a> Çoklu küme::d ifference_type (STL/CLR)

İki öğe arasındaki işaretli bir mesafe türü.

### <a name="syntax"></a>Syntax

```cpp
typedef int difference_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, büyük olasılıkla negatif bir öğe sayısını tanımlar.

### <a name="example"></a>Örnek

```cpp
// cliext_multiset_difference_type.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::multiset<wchar_t> Mymultiset;
int main()
    {
    Mymultiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // compute positive difference
    Mymultiset::difference_type diff = 0;
    for (Mymultiset::iterator it = c1.begin(); it != c1.end(); ++it)
        ++diff;
    System::Console::WriteLine("end()-begin() = {0}", diff);

    // compute negative difference
    diff = 0;
    for (Mymultiset::iterator it = c1.end(); it != c1.begin(); --it)
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

## <a name="multisetempty-stlclr"></a><a name="empty"></a> Çoklu küme:: Empty (STL/CLR)

Bir öğe olup olmadığını sınar.

### <a name="syntax"></a>Syntax

```cpp
bool empty();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi boş bir denetlenen dizi için true döndürür. [Çoklu küme:: size (STL/CLR)](#size)eşdeğerdir `() == 0` . Bu, çok kümeli bir boş değer olup olmadığını test etmek için kullanılır.

### <a name="example"></a>Örnek

```cpp
// cliext_multiset_empty.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::multiset<wchar_t> Mymultiset;
int main()
    {
    Mymultiset c1;
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

## <a name="multisetend-stlclr"></a><a name="end"></a> multıset:: End (STL/CLR)

Denetlenen dizinin bitişini belirtir.

### <a name="syntax"></a>Syntax

```cpp
iterator end();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, denetimli dizinin sonunun hemen ötesinde işaret eden çift yönlü bir yineleyici döndürür. Denetlenen dizinin sonunu atayan bir yineleyici elde etmek için bunu kullanırsınız; denetlenen sıranın uzunluğu değişirse, durumu değişmez.

### <a name="example"></a>Örnek

```cpp
// cliext_multiset_end.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::multiset<wchar_t> Mymultiset;
int main()
    {
    Mymultiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // inspect last two items
    Mymultiset::iterator it = c1.end();
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

## <a name="multisetequal_range-stlclr"></a><a name="equal_range"></a> Çoklu küme:: equal_range (STL/CLR)

Belirtilen bir anahtarla eşleşen aralığı bulur.

### <a name="syntax"></a>Sözdizimi

```cpp
cliext::pair<iterator, iterator> equal_range(key_type key);
```

#### <a name="parameters"></a>Parametreler

*anahtar*<br/>
Aranacak anahtar değer.

### <a name="remarks"></a>Açıklamalar

Üye işlevi yineleyicilerin bir çiftini döndürür `cliext::pair<iterator, iterator>(` [:: lower_bound (STL/CLR)](#lower_bound) `(key),` [Çoklu küme:: upper_bound (STL/CLR)](#upper_bound) `(key))` . Belirli bir anahtarla eşleşen denetimli dizide bulunan öğe aralığını öğrenmek için bunu kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// cliext_multiset_equal_range.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::multiset<wchar_t> Mymultiset;
typedef Mymultiset::pair_iter_iter Pairii;
int main()
    {
    Mymultiset c1;
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

## <a name="multiseterase-stlclr"></a><a name="erase"></a> Çoklu küme:: Erase (STL/CLR)

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

İlk üye *işlevi, öğesinin* işaret ettiği denetlenen sıranın öğesini kaldırır ve kaldırılan öğenin ötesinde ilk öğeyi belirten bir yineleyici döndürür ya da böyle bir öğe yoksa, çok [kümeli:: End (STL/CLR)](#end) `()` . Tek bir öğeyi kaldırmak için bunu kullanırsınız.

İkinci üye işlevi, [,) aralığındaki denetimli sıranın öğelerini kaldırır `first` `last` ve kaldırılan tüm öğelerin ötesinde kalan ilk öğeyi veya böyle bir öğe yoksa bir yineleyici döndürür `end()` . Sıfır veya daha fazla bitişik öğeyi kaldırmak için bunu kullanırsınız.

Üçüncü üye işlevi, anahtarı *anahtara* denk sıralama değerine sahip denetimli dizinin herhangi bir öğesini kaldırır ve kaldırılan öğe sayısının sayısını döndürür. Bu anahtarı, belirtilen bir anahtarla eşleşen tüm öğeleri kaldırmak ve saymak için kullanırsınız.

Her bir öğe, denetlenen dizideki öğelerin sayısının logaritması ile orantılı bir zaman alır.

### <a name="example"></a>Örnek

```cpp
// cliext_multiset_erase.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::multiset<wchar_t> Mymultiset;
int main()
    {
    Mymultiset c1;
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
    Mymultiset::iterator it = c1.end();
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

## <a name="multisetfind-stlclr"></a><a name="find"></a> Çoklu küme:: Find (STL/CLR)

Belirtilen bir anahtarla eşleşen bir öğeyi bulur.

### <a name="syntax"></a>Sözdizimi

```cpp
iterator find(key_type key);
```

#### <a name="parameters"></a>Parametreler

*anahtar*<br/>
Aranacak anahtar değer.

### <a name="remarks"></a>Açıklamalar

Denetlenen dizide en az bir öğe *anahtar* ile eşdeğer sıralamaya sahipse, üye işlevi bu öğelerden birini tanımlayarak bir yineleyici döndürür; Aksi takdirde, çok [kümeli:: End (STL/CLR)](#end)döndürür `()` . Belirtilen bir anahtarla eşleşen denetimli dizide bulunan bir öğeyi bulmak için bunu kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// cliext_multiset_find.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::multiset<wchar_t> Mymultiset;
int main()
    {
    Mymultiset c1;
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

## <a name="multisetgeneric_container-stlclr"></a><a name="generic_container"></a> Çoklu küme:: generic_container (STL/CLR)

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
// cliext_multiset_generic_container.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::multiset<wchar_t> Mymultiset;
int main()
    {
    Mymultiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct a generic container
    Mymultiset::generic_container^ gc1 = %c1;
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

## <a name="multisetgeneric_iterator-stlclr"></a><a name="generic_iterator"></a> Çoklu küme:: generic_iterator (STL/CLR)

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
// cliext_multiset_generic_iterator.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::multiset<wchar_t> Mymultiset;
int main()
    {
    Mymultiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct a generic container
    Mymultiset::generic_container^ gc1 = %c1;
    for each (wchar_t elem in gc1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // get an element and display it
    Mymultiset::generic_iterator gcit = gc1->begin();
    Mymultiset::generic_value gcval = *gcit;
    System::Console::WriteLine("{0} ", gcval);
    return (0);
    }
```

```Output
a b c
a b c
a
```

## <a name="multisetgeneric_reverse_iterator-stlclr"></a><a name="generic_reverse_iterator"></a> Çoklu küme:: generic_reverse_iterator (STL/CLR)

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
// cliext_multiset_generic_reverse_iterator.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::multiset<wchar_t> Mymultiset;
int main()
    {
    Mymultiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct a generic container
    Mymultiset::generic_container^ gc1 = %c1;
    for each (wchar_t elem in gc1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // get an element and display it
    Mymultiset::generic_reverse_iterator gcit = gc1->rbegin();
    Mymultiset::generic_value gcval = *gcit;
    System::Console::WriteLine("{0} ", gcval);
    return (0);
    }
```

```Output
a b c
a b c
c
```

## <a name="multisetgeneric_value-stlclr"></a><a name="generic_value"></a> Çoklu küme:: generic_value (STL/CLR)

Kapsayıcının genel arabirimiyle kullanılacak öğe türü.

### <a name="syntax"></a>Syntax

```cpp
typedef GValue generic_value;
```

### <a name="remarks"></a>Açıklamalar

Tür, `GValue` Bu şablon kapsayıcı sınıfı için genel arabirimle birlikte kullanılacak saklı öğe değerini açıklayan türünde bir nesne tanımlar.

### <a name="example"></a>Örnek

```cpp
// cliext_multiset_generic_value.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::multiset<wchar_t> Mymultiset;
int main()
    {
    Mymultiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct a generic container
    Mymultiset::generic_container^ gc1 = %c1;
    for each (wchar_t elem in gc1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // get an element and display it
    Mymultiset::generic_iterator gcit = gc1->begin();
    Mymultiset::generic_value gcval = *gcit;
    System::Console::WriteLine("{0} ", gcval);
    return (0);
    }
```

```Output
a b c
a b c
a
```

## <a name="multisetinsert-stlclr"></a><a name="insert"></a> Çoklu küme:: Insert (STL/CLR)

Öğeleri ekler.

### <a name="syntax"></a>Sözdizimi

```cpp
iterator insert(value_type val);
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

İlk üye işlevi *, value değeri* olan bir öğe ekler ve yeni eklenen öğeyi atayan bir yineleyici döndürür. Tek bir öğe eklemek için bunu kullanırsınız.

İkinci üye işlevi, bir ipucu olarak *WHERE* (performansı artırmak için) ve yeni eklenen öğeyi atayan bir yineleyici döndüren bir *değer değeri olan* bir öğe ekler. Bildiğiniz bir öğeye bitişik olabilecek tek bir öğe eklemek için bunu kullanırsınız.

Üçüncü üye işlevi [,) dizisini ekler `first` `last` . Başka bir dizide kopyalanmış sıfır veya daha fazla öğe eklemek için bunu kullanırsınız.

Dördüncü üye işlevi, *sağ* tarafından belirlenen diziyi ekler. Bir Numaralandırıcı tarafından tanımlanan bir sıra eklemek için bunu kullanırsınız.

Her öğe ekleme, denetlenen dizideki öğelerin sayısının logaritması ile orantılı bir zaman alır. Ekleme noktası, ekleme noktasına bitişik bir öğe atayan bir ipucu verildiğinde, sabit zamanlı olarak ekleme yapılabilir.

### <a name="example"></a>Örnek

```cpp
// cliext_multiset_insert.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::multiset<wchar_t> Mymultiset;
int main()
    {
    Mymultiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // insert a single value, unique and duplicate
    System::Console::WriteLine("insert(L'x') = {0}",
        *c1.insert(L'x'));

    System::Console::WriteLine("insert(L'b') = {0}",
        *c1.insert(L'b'));

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
    Mymultiset c2;
    Mymultiset::iterator it = c1.end();
    c2.insert(c1.begin(), --it);
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // insert an enumeration
    Mymultiset c3;
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
insert(L'x') = x
insert(L'b') = b
a b b c x
insert(begin(), L'y') = y
a b b c x y
a b b c x
a b b c x y
```

## <a name="multisetiterator-stlclr"></a><a name="iterator"></a> Çoklu küme:: yineleyici (STL/CLR)

Denetlenen dizi için bir yineleyici türü.

### <a name="syntax"></a>Syntax

```cpp
typedef T1 iterator;
```

### <a name="remarks"></a>Açıklamalar

Türü, `T1` denetimli sıra için çift yönlü bir yineleyici olarak kullanılabilecek belirtilmemiş türdeki bir nesneyi tanımlar.

### <a name="example"></a>Örnek

```cpp
// cliext_multiset_iterator.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::multiset<wchar_t> Mymultiset;
int main()
    {
    Mymultiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display contents " a b c"
    Mymultiset::iterator it = c1.begin();
    for (; it != c1.end(); ++it)
        System::Console::Write("{0} ", *it);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="multisetkey_comp-stlclr"></a><a name="key_comp"></a> Çoklu küme:: key_comp (STL/CLR)

Sıralama temsilcisini iki anahtar için kopyalar.

### <a name="syntax"></a>Syntax

```cpp
key_compare^key_comp();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, denetimli sırayı sıralamak için kullanılan sıralama temsilcisini döndürür. İki anahtarı karşılaştırmak için bunu kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// cliext_multiset_key_comp.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::multiset<wchar_t> Mymultiset;
int main()
    {
    Mymultiset c1;
    Mymultiset::key_compare^ kcomp = c1.key_comp();

    System::Console::WriteLine("compare(L'a', L'a') = {0}",
        kcomp(L'a', L'a'));
    System::Console::WriteLine("compare(L'a', L'b') = {0}",
        kcomp(L'a', L'b'));
    System::Console::WriteLine("compare(L'b', L'a') = {0}",
        kcomp(L'b', L'a'));
    System::Console::WriteLine();

    // test a different ordering rule
    Mymultiset c2 = cliext::greater<wchar_t>();
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

## <a name="multisetkey_compare-stlclr"></a><a name="key_compare"></a> Çoklu küme:: key_compare (STL/CLR)

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
// cliext_multiset_key_compare.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::multiset<wchar_t> Mymultiset;
int main()
    {
    Mymultiset c1;
    Mymultiset::key_compare^ kcomp = c1.key_comp();

    System::Console::WriteLine("compare(L'a', L'a') = {0}",
        kcomp(L'a', L'a'));
    System::Console::WriteLine("compare(L'a', L'b') = {0}",
        kcomp(L'a', L'b'));
    System::Console::WriteLine("compare(L'b', L'a') = {0}",
        kcomp(L'b', L'a'));
    System::Console::WriteLine();

    // test a different ordering rule
    Mymultiset c2 = cliext::greater<wchar_t>();
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

## <a name="multisetkey_type-stlclr"></a><a name="key_type"></a> Çoklu küme:: key_type (STL/CLR)

Bir sıralama anahtarının türü.

### <a name="syntax"></a>Syntax

```cpp
typedef Key key_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, şablon parametre *anahtarı* için bir eş anlamlı.

### <a name="example"></a>Örnek

```cpp
// cliext_multiset_key_type.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::multiset<wchar_t> Mymultiset;
int main()
    {
    Mymultiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display contents " a b c" using key_type
    for (Mymultiset::iterator it = c1.begin(); it != c1.end(); ++it)
        {   // store element in key_type object
        Mymultiset::key_type val = *it;

        System::Console::Write("{0} ", val);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="multisetlower_bound-stlclr"></a><a name="lower_bound"></a> Çoklu küme:: lower_bound (STL/CLR)

Belirtilen anahtarla eşleşen aralığın başlangıcını bulur.

### <a name="syntax"></a>Sözdizimi

```cpp
iterator lower_bound(key_type key);
```

#### <a name="parameters"></a>Parametreler

*anahtar*<br/>
Aranacak anahtar değer.

### <a name="remarks"></a>Açıklamalar

Üye işlevi, `X` denetimli dizideki, *anahtara* denk sıralamaya sahip ilk öğeyi belirler. Böyle bir öğe yoksa, çok [kümeli:: End (STL/CLR)](#end)döndürür `()` ; Aksi takdirde, öğesini atayan bir yineleyici döndürür `X` . Belirtilen bir anahtarla eşleşen, denetlenen dizide bulunan bir öğe dizisinin başlangıcını bulmak için bunu kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// cliext_multiset_lower_bound.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::multiset<wchar_t> Mymultiset;
int main()
    {
    Mymultiset c1;
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

## <a name="multisetmake_value-stlclr"></a><a name="make_value"></a> Çoklu küme:: make_value (STL/CLR)

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
// cliext_multiset_make_value.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::multiset<wchar_t> Mymultiset;
int main()
    {
    Mymultiset c1;
    c1.insert(Mymultiset::make_value(L'a'));
    c1.insert(Mymultiset::make_value(L'b'));
    c1.insert(Mymultiset::make_value(L'c'));

    // display contents " a b c"
    for each (Mymultiset::value_type elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="multisetmultiset-stlclr"></a><a name="multiset"></a> Çoklu küme:: çoklu küme (STL/CLR)

Bir kapsayıcı nesnesi oluşturur.

### <a name="syntax"></a>Sözdizimi

```cpp
multiset();
explicit multiset(key_compare^ pred);
multiset(multiset<Key>% right);
multiset(multiset<Key>^ right);
template<typename InIter>
    multisetmultiset(InIter first, InIter last);
template<typename InIter>
    multiset(InIter first, InIter last,
        key_compare^ pred);
multiset(System::Collections::Generic::IEnumerable<GValue>^ right);
multiset(System::Collections::Generic::IEnumerable<GValue>^ right,
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

`multiset();`

Varsayılan sıralama koşulu ile denetimli sırayı öğesi olmadan başlatır `key_compare()` . Varsayılan sıralama koşulu ile boş bir ilk denetimli sıra belirtmek için bunu kullanırsınız.

Oluşturucu:

`explicit multiset(key_compare^ pred);`

denetlenen sırayı, sıralama koşulu *Pred* ile birlikte hiçbir öğe olmadan başlatır. Belirtilen sıralama koşulu ile boş bir ilk denetimli sıra belirtmek için bunu kullanırsınız.

Oluşturucu:

`multiset(multiset<Key>% right);`

[,) sırası ile denetlenen sırayı `right.begin()` `right.end()` varsayılan sıralama koşulu ile başlatır. Varsayılan sıralama koşulu ile, çoklu *küme nesnesi tarafından* denetlenen sıranın bir kopyası olan ilk denetimli bir sıra belirtmek için bunu kullanırsınız.

Oluşturucu:

`multiset(multiset<Key>^ right);`

[,) sırası ile denetlenen sırayı `right->begin()` `right->end()` varsayılan sıralama koşulu ile başlatır. Varsayılan sıralama koşulu ile, çoklu *küme nesnesi tarafından* denetlenen sıranın bir kopyası olan ilk denetimli bir sıra belirtmek için bunu kullanırsınız.

Oluşturucu:

`template<typename InIter> multiset(InIter first, InIter last);`

[,) sırası ile denetlenen sırayı `first` `last` varsayılan sıralama koşulu ile başlatır. Varsayılan sıralama koşulu ile, denetimli diziyi başka bir dizinin bir kopyası yapmak için kullanabilirsiniz.

Oluşturucu:

`template<typename InIter> multiset(InIter first, InIter last, key_compare^ pred);`

[,) sırası ile denetlenen sırayı `first` `last` , sıralama koşulu *Pred* ile başlatır. Belirtilen sıralama koşulu ile, denetimli diziyi başka bir dizinin bir kopyası yapmak için kullanabilirsiniz.

Oluşturucu:

`multiset(System::Collections::Generic::IEnumerable<Key>^ right);`

denetlenen sırayı, varsayılan sıralama koşulu ile Numaralandırıcı *hakkı* tarafından belirlenen sırayla başlatır. Denetim, varsayılan sıralama koşulu ile, bir Numaralandırıcı tarafından tanımlanan başka bir dizinin kopyasını oluşturmak için kullanılır.

Oluşturucu:

`multiset(System::Collections::Generic::IEnumerable<Key>^ right, key_compare^ pred);`

denetlenen diziyi Numaralandırıcı *hakkı* ile belirlenen sıra ile başlatır, sıralama koşulu *Pred*. Denetim, belirtilen sıralama koşulu ile bir Numaralandırıcı tarafından tanımlanan başka bir dizinin bir kopyasını oluşturmak için kullanılır.

### <a name="example"></a>Örnek

```cpp
// cliext_multiset_construct.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::multiset<wchar_t> Mymultiset;
int main()
    {
// construct an empty container
    Mymultiset c1;
    System::Console::WriteLine("size() = {0}", c1.size());

    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct with an ordering rule
    Mymultiset c2 = cliext::greater_equal<wchar_t>();
    System::Console::WriteLine("size() = {0}", c2.size());

    c2.insert(c1.begin(), c1.end());
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct with an iterator range
    Mymultiset c3(c1.begin(), c1.end());
    for each (wchar_t elem in c3)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct with an iterator range and an ordering rule
    Mymultiset c4(c1.begin(), c1.end(),
        cliext::greater_equal<wchar_t>());
    for each (wchar_t elem in c4)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct with an enumeration
    Mymultiset c5(   // NOTE: cast is not needed
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c3);
    for each (wchar_t elem in c5)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct with an enumeration and an ordering rule
    Mymultiset c6(   // NOTE: cast is not needed
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c3,
            cliext::greater_equal<wchar_t>());
    for each (wchar_t elem in c6)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct from a generic container
    Mymultiset c7(c4);
    for each (wchar_t elem in c7)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct by copying another container
    Mymultiset c8(%c3);
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

## <a name="multisetoperator-stlclr"></a><a name="op_as"></a> Çoklu küme:: operator = (STL/CLR)

Denetlenen sırayı değiştirir.

### <a name="syntax"></a>Sözdizimi

```cpp
multiset<Key>% operator=(multiset<Key>% right);
```

#### <a name="parameters"></a>Parametreler

*Right*<br/>
Kopyalanacak kapsayıcı.

### <a name="remarks"></a>Açıklamalar

Üye işleci nesnesine *sağ* kopyalar ve ardından döndürür **`*this`** . Denetlenen diziyi, denetimli sıranın bir kopyasıyla değiştirmek için bunu *kullanırsınız.*

### <a name="example"></a>Örnek

```cpp
// cliext_multiset_operator_as.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::multiset<wchar_t> Mymultiset;
int main()
    {
    Mymultiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display contents " a b c"
    for each (Mymultiset::value_type elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // assign to a new container
    Mymultiset c2;
    c2 = c1;
// display contents " a b c"
    for each (Mymultiset::value_type elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
a b c
```

## <a name="multisetrbegin-stlclr"></a><a name="rbegin"></a> Çoklu küme:: rbegin (STL/CLR)

Ters denetlenen sıranın başlangıcını belirtir.

### <a name="syntax"></a>Syntax

```cpp
reverse_iterator rbegin();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, denetimli sıranın son öğesini veya boş bir dizinin başlangıcının ötesinde bir ters yineleyici döndürür. Bu nedenle, `beginning` ters sıranın öğesini belirler. Doğru sırada görülen denetimli sıranın başlangıcını atayan bir yineleyici elde etmek için bunu kullanırsınız `current` , ancak denetlenen sıranın uzunluğu değişirse durum değişebilir.

### <a name="example"></a>Örnek

```cpp
// cliext_multiset_rbegin.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::multiset<wchar_t> Mymultiset;
int main()
    {
    Mymultiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // inspect first two items in reversed sequence
    Mymultiset::reverse_iterator rit = c1.rbegin();
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

## <a name="multisetreference-stlclr"></a><a name="reference"></a> Çoklu küme:: Reference (STL/CLR)

Bir öğe için bir başvuru türü.

### <a name="syntax"></a>Syntax

```cpp
typedef value_type% reference;
```

### <a name="remarks"></a>Açıklamalar

Türü bir öğesi başvurusunu tanımlar.

### <a name="example"></a>Örnek

```cpp
// cliext_multiset_reference.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::multiset<wchar_t> Mymultiset;
int main()
    {
    Mymultiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    Mymultiset::iterator it = c1.begin();
    for (; it != c1.end(); ++it)
        {   // get a reference to an element
        Mymultiset::reference ref = *it;
        System::Console::Write("{0} ", ref);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="multisetrend-stlclr"></a><a name="rend"></a> Çoklu küme:: rend (STL/CLR)

Ters denetlenen sıranın sonunu belirtir.

### <a name="syntax"></a>Syntax

```cpp
reverse_iterator rend();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, denetimli sıranın başlangıcının hemen ötesinde bir ters yineleyici döndürür. Bu nedenle, `end` ters sıranın öğesini belirler. Bu uygulamayı, `current` geriye doğru sırada görülen denetlenen sıranın sonunu atayan bir yineleyici elde etmek için kullanırsınız, ancak denetlenen sıranın uzunluğu değişirse durum değişebilir.

### <a name="example"></a>Örnek

```cpp
// cliext_multiset_rend.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::multiset<wchar_t> Mymultiset;
int main()
    {
    Mymultiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // inspect first two items
    Mymultiset::reverse_iterator rit = c1.rend();
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

## <a name="multisetreverse_iterator-stlclr"></a><a name="reverse_iterator"></a> Çoklu küme:: reverse_iterator (STL/CLR)

Denetlenen sıra için ters yineleyicinin türü.

### <a name="syntax"></a>Syntax

```cpp
typedef T3 reverse_iterator;
```

### <a name="remarks"></a>Açıklamalar

Tür, `T3` denetlenen sıra için ters Yineleyici olarak işlev görebilecek belirtilmemiş türdeki bir nesneyi tanımlar.

### <a name="example"></a>Örnek

```cpp
// cliext_multiset_reverse_iterator.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::multiset<wchar_t> Mymultiset;
int main()
    {
    Mymultiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display contents " a b c" reversed
    Mymultiset::reverse_iterator rit = c1.rbegin();
    for (; rit != c1.rend(); ++rit)
        System::Console::Write("{0} ", *rit);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
c b a
```

## <a name="multisetsize-stlclr"></a><a name="size"></a> Çoklu küme:: size (STL/CLR)

Öğe sayısını sayar.

### <a name="syntax"></a>Syntax

```cpp
size_type size();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi denetlenen sıranın uzunluğunu döndürür. Bu, şu anda denetlenen dizideki öğelerin sayısını tespit etmek için kullanılır. Her şey için, sıranın sıfır dışında bir boyuta sahip olup olmadığı, bkz. [Çoklu küme:: boş (STL/CLR)](#empty) `()` .

### <a name="example"></a>Örnek

```cpp
// cliext_multiset_size.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::multiset<wchar_t> Mymultiset;
int main()
    {
    Mymultiset c1;
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

## <a name="multisetsize_type-stlclr"></a><a name="size_type"></a> Çoklu küme:: size_type (STL/CLR)

İki öğe arasındaki işaretli bir mesafe türü.

### <a name="syntax"></a>Syntax

```cpp
typedef int size_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, negatif olmayan bir öğe sayısını tanımlar.

### <a name="example"></a>Örnek

```cpp
// cliext_multiset_size_type.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::multiset<wchar_t> Mymultiset;
int main()
    {
    Mymultiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // compute positive difference
    Mymultiset::size_type diff = 0;
    for (Mymultiset::iterator it = c1.begin(); it != c1.end(); ++it)
        ++diff;
    System::Console::WriteLine("end()-begin() = {0}", diff);
    return (0);
    }
```

```Output
a b c
end()-begin() = 3
```

## <a name="multisetswap-stlclr"></a><a name="swap"></a> Çoklu küme:: swap (STL/CLR)

İki kapsayıcının içeriğinin yerini değiştirir.

### <a name="syntax"></a>Sözdizimi

```cpp
void swap(multiset<Key>% right);
```

#### <a name="parameters"></a>Parametreler

*Right*<br/>
İçeriği takas eden kapsayıcı.

### <a name="remarks"></a>Açıklamalar

Üye işlevi, ve sağ arasındaki denetlenen dizileri **`this`** değiştirir . Bu, sabit zamanlı olarak yapar ve özel durum oluşturmaz. Bunu iki kapsayıcının içeriğini değiş tokuş etmek için hızlı bir yol olarak kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// cliext_multiset_swap.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::multiset<wchar_t> Mymultiset;
int main()
    {
    Mymultiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct another container with repetition of values
    Mymultiset c2;
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

## <a name="multisetto_array-stlclr"></a><a name="to_array"></a> Çoklu küme:: to_array (STL/CLR)

Denetimli sırayı yeni bir diziye kopyalar.

### <a name="syntax"></a>Syntax

```cpp
cli::array<value_type>^ to_array();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi denetlenen sırayı içeren bir dizi döndürür. Dizi biçiminde denetlenen sıranın bir kopyasını almak için bunu kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// cliext_multiset_to_array.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::multiset<wchar_t> Mymultiset;
int main()
    {
    Mymultiset c1;
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

## <a name="multisetupper_bound-stlclr"></a><a name="upper_bound"></a> Çoklu küme:: upper_bound (STL/CLR)

Belirtilen anahtarla eşleşen aralığın sonunu bulur.

### <a name="syntax"></a>Sözdizimi

```cpp
iterator upper_bound(key_type key);
```

#### <a name="parameters"></a>Parametreler

*anahtar*<br/>
Aranacak anahtar değer.

### <a name="remarks"></a>Açıklamalar

Üye işlevi, denetimli dizideki en son öğeyi, `X` *anahtara* denk sıralama olarak belirler. Böyle bir öğe yoksa veya `X` denetlenen dizideki son öğe ise, çok [kümeli:: End (STL/CLR)](#end)döndürür `()` ; Aksi takdirde ilk öğeyi daha sonra atayan bir yineleyici döndürür `X` . Belirtilen bir anahtarla eşleşen denetimli dizide bulunan bir öğe dizisinin sonunu bulmak için bunu kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// cliext_multiset_upper_bound.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::multiset<wchar_t> Mymultiset;
int main()
    {
    Mymultiset c1;
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

## <a name="multisetvalue_comp-stlclr"></a><a name="value_comp"></a> Çoklu küme:: value_comp (STL/CLR)

İki öğe değeri için sıralama temsilcisini kopyalar.

### <a name="syntax"></a>Syntax

```cpp
value_compare^ value_comp();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, denetimli sırayı sıralamak için kullanılan sıralama temsilcisini döndürür. İki öğe değerini karşılaştırmak için bunu kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// cliext_multiset_value_comp.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::multiset<wchar_t> Mymultiset;
int main()
    {
    Mymultiset c1;
    Mymultiset::value_compare^ kcomp = c1.value_comp();

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

## <a name="multisetvalue_compare-stlclr"></a><a name="value_compare"></a> Çoklu küme:: value_compare (STL/CLR)

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
// cliext_multiset_value_compare.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::multiset<wchar_t> Mymultiset;
int main()
    {
    Mymultiset c1;
    Mymultiset::value_compare^ kcomp = c1.value_comp();

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

## <a name="multisetvalue_type-stlclr"></a><a name="value_type"></a> Çoklu küme:: value_type (STL/CLR)

Öğenin türü.

### <a name="syntax"></a>Syntax

```cpp
typedef generic_value value_type;
```

### <a name="remarks"></a>Açıklamalar

Tür için bir eş anlamlı `generic_value` .

### <a name="example"></a>Örnek

```cpp
// cliext_multiset_value_type.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::multiset<wchar_t> Mymultiset;
int main()
    {
    Mymultiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display contents " a b c" using value_type
    for (Mymultiset::iterator it = c1.begin(); it != c1.end(); ++it)
        {   // store element in value_type object
        Mymultiset::value_type val = *it;

        System::Console::Write("{0} ", val);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="operator-multiset-stlclr"></a><a name="op_neq"></a> işleç! = (çoklu küme) (STL/CLR)

Liste eşit değildir karşılaştırması.

### <a name="syntax"></a>Sözdizimi

```cpp
template<typename Key>
    bool operator!=(multiset<Key>% left,
        multiset<Key>% right);
```

#### <a name="parameters"></a>Parametreler

*tarafta*<br/>
Karşılaştırılacak sol kapsayıcı.

*Right*<br/>
Karşılaştırılacak doğru kapsayıcı.

### <a name="remarks"></a>Açıklamalar

İşleç işlevi döndürülür `!(left == right)` . İki multisets öğesi öğesine göre karşılaştırıldığı zaman, *sol* öğenin *doğru* şekilde sıralı olup olmadığını test etmek için kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// cliext_multiset_operator_ne.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::multiset<wchar_t> Mymultiset;
int main()
    {
    Mymultiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // assign to a new container
    Mymultiset c2;
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

## <a name="operatorlt-multiset-stlclr"></a><a name="op_lt"></a> işleç &lt; (çoklu küme) (STL/CLR)

Liste karşılaştırmadan daha az.

### <a name="syntax"></a>Sözdizimi

```cpp
template<typename Key>
    bool operator<(multiset<Key>% left,
        multiset<Key>% right);
```

#### <a name="parameters"></a>Parametreler

*tarafta*<br/>
Karşılaştırılacak sol kapsayıcı.

*Right*<br/>
Karşılaştırılacak doğru kapsayıcı.

### <a name="remarks"></a>Açıklamalar

İşleç işlevi, `i` `!(right[i] < left[i])` bunun da doğru olduğu en düşük konum için true değerini döndürür `left[i] < right[i]` . Aksi takdirde, `left->size() < right->size()` iki multisets öğesi öğesine göre karşılaştırıldığı zaman, sol  taraftaki bir süre önce *sola* doğru sıralı olup olmadığını test etmek için bunu kullanır.

### <a name="example"></a>Örnek

```cpp
// cliext_multiset_operator_lt.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::multiset<wchar_t> Mymultiset;
int main()
    {
    Mymultiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // assign to a new container
    Mymultiset c2;
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

## <a name="operatorlt-multiset-stlclr"></a><a name="op_lteq"></a> operator &lt; = (çoklu küme) (STL/CLR)

Küçüktür veya eşit karşılaştırma listesi.

### <a name="syntax"></a>Sözdizimi

```cpp
template<typename Key>
    bool operator<=(multiset<Key>% left,
        multiset<Key>% right);
```

#### <a name="parameters"></a>Parametreler

*tarafta*<br/>
Karşılaştırılacak sol kapsayıcı.

*Right*<br/>
Karşılaştırılacak doğru kapsayıcı.

### <a name="remarks"></a>Açıklamalar

İşleç işlevi döndürülür `!(right < left)` . İki multisets öğesi öğesi öğesine göre karşılaştırıldığı zaman *farenin sağ* *tarafında* sıralı olup olmadığını test etmek için bunu kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// cliext_multiset_operator_le.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::multiset<wchar_t> Mymultiset;
int main()
    {
    Mymultiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // assign to a new container
    Mymultiset c2;
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

## <a name="operator-multiset-stlclr"></a><a name="op_eq"></a> işleç = = (çoklu küme) (STL/CLR)

Liste eşit karşılaştırması.

### <a name="syntax"></a>Sözdizimi

```cpp
template<typename Key>
    bool operator==(multiset<Key>% left,
        multiset<Key>% right);
```

#### <a name="parameters"></a>Parametreler

*tarafta*<br/>
Karşılaştırılacak sol kapsayıcı.

*Right*<br/>
Karşılaştırılacak doğru kapsayıcı.

### <a name="remarks"></a>Açıklamalar

İşleç işlevi yalnızca *sol* ve *sağ* tarafından denetlenen diziler aynı uzunlukta ve her bir konum için aynı uzunluğa sahip olursa true değerini döndürür `i` `left[i] ==` `right[i]` . İki multisets öğesi öğesine göre karşılaştırıldığı zaman *solinin* *doğru* olup olmadığını test etmek için bunu kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// cliext_multiset_operator_eq.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::multiset<wchar_t> Mymultiset;
int main()
    {
    Mymultiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // assign to a new container
    Mymultiset c2;
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

## <a name="operatorgt-multiset-stlclr"></a><a name="op_gt"></a> işleç &gt; (çoklu küme) (STL/CLR)

Karşılaştırmadan daha büyük bir liste.

### <a name="syntax"></a>Sözdizimi

```cpp
template<typename Key>
    bool operator>(multiset<Key>% left,
        multiset<Key>% right);
```

#### <a name="parameters"></a>Parametreler

*tarafta*<br/>
Karşılaştırılacak sol kapsayıcı.

*Right*<br/>
Karşılaştırılacak doğru kapsayıcı.

### <a name="remarks"></a>Açıklamalar

İşleç işlevi döndürülür `right` `<` `left` . İki multisets öğe öğesine göre karşılaştırıldığı zaman, *sol* *taraftaki bir* değer olup olmadığını test etmek için bunu kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// cliext_multiset_operator_gt.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::multiset<wchar_t> Mymultiset;
int main()
    {
    Mymultiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // assign to a new container
    Mymultiset c2;
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

## <a name="operatorgt-multiset-stlclr"></a><a name="op_gteq"></a> operator &gt; = (çoklu küme) (STL/CLR)

Büyük veya eşit karşılaştırmayı listele.

### <a name="syntax"></a>Sözdizimi

```cpp
template<typename Key>
    bool operator>=(multiset<Key>% left,
        multiset<Key>% right);
```

#### <a name="parameters"></a>Parametreler

*tarafta*<br/>
Karşılaştırılacak sol kapsayıcı.

*Right*<br/>
Karşılaştırılacak doğru kapsayıcı.

### <a name="remarks"></a>Açıklamalar

İşleç işlevi döndürülür `!(left < right)` . İki multisets öğe öğesine göre karşılaştırıldığı zaman, *sol taraftan* *önce doğru* sıralanmadığını test etmek için bunu kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// cliext_multiset_operator_ge.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::multiset<wchar_t> Mymultiset;
int main()
    {
    Mymultiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // assign to a new container
    Mymultiset c2;
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
