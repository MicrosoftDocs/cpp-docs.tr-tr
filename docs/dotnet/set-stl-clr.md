---
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
ms.openlocfilehash: 38b0a3278efd10ef5cc989a5fc900bf82d377eae
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81320316"
---
# <a name="set-stlclr"></a>set (STL/CLR)

Şablon sınıfı, çift yönlü erişimi olan öğelerin değişen uzunluktaki dizisini kontrol eden bir nesneyi açıklar. Kapsayıcıyı, `set` her biri bir öğeyi depolayan (neredeyse) dengeli sıralı bir düğüm ağacı olarak bir dizi öğeyi yönetmek için kullanırsınız.

Aşağıdaki `GValue` açıklamada, ikincisi bir `GKey`ref türü *olmadığı* sürece, bu durumda anahtar ile `Key^`aynıdır.

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

*Anahtar*<br/>
Denetlenmeyen dizideki bir öğenin anahtar bileşeninin türü.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** \<cliext/set>

**Ad alanı:** cliext

## <a name="declarations"></a>Bildirimler

|Tür Tanımlaması|Açıklama|
|---------------------|-----------------|
|[set::const_iterator (STL/CLR)](#const_iterator)|Denetlenen dizi için bir sabit yineleyici türü.|
|[set::const_reference (STL/CLR)](#const_reference)|Bir öğe için sabit bir başvuru türü.|
|[set::const_reverse_iterator (STL/CLR)](#const_reverse_iterator)|Denetlenmeyen dizi için sabit bir ters yineleyici türü.|
|[set::difference_type (STL/CLR)](#difference_type)|İki öğe arasındaki (büyük olasılıkla imzalanmış) uzaklık türü.|
|[set::generic_container (STL/CLR)](#generic_container)|Kapsayıcı için genel arabirimin türü.|
|[set::generic_iterator (STL/CLR)](#generic_iterator)|Kapsayıcının genel arabirimi için bir yineleyici türü.|
|[set::generic_reverse_iterator (STL/CLR)](#generic_reverse_iterator)|Kapsayıcının genel arabirimi için ters yineleyici türü.|
|[set::generic_value (STL/CLR)](#generic_value)|Kapsayıcı için genel arabirim için bir öğetürü.|
|[set::iterator (STL/CLR)](#iterator)|Denetlenen dizi için bir yineleyici türü.|
|[set::key_compare (STL/CLR)](#key_compare)|İki anahtar için sipariş temsilcisi.|
|[set::key_type (STL/CLR)](#key_type)|Bir sıralama anahtarının türü.|
|[set::reference (STL/CLR)](#reference)|Bir öğe için bir başvuru türü.|
|[set::reverse_iterator (STL/CLR)](#reverse_iterator)|Denetlenen dizi için ters yineleyici türü.|
|[set::size_type (STL/CLR)](#size_type)|İki öğe arasındaki (negatif olmayan) uzaklık türü.|
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
|[set::key_comp (STL/CLR)](#key_comp)|İki anahtar için sipariş temsilcisini kopyalar.|
|[set::lower_bound (STL/CLR)](#lower_bound)|Belirtilen bir anahtarla eşleşen aralığın başlangıcını bulur.|
|[set::make_value (STL/CLR)](#make_value)|Bir değer nesnesi oluşturuyor.|
|[set::rbegin (STL/CLR)](#rbegin)|Ters denetimli dizinin başlangıcını belirler.|
|[set::rend (STL/CLR)](#rend)|Ters denetimli dizinin sonunu belirler.|
|[set::set (STL/CLR)](#set)|Bir kapsayıcı nesnesi oluşturur.|
|[set::size (STL/CLR)](#size)|Öğe sayısını sayar.|
|[set::swap (STL/CLR)](#swap)|İki kapsayıcının içeriğinin yerini değiştirir.|
|[set::to_array (STL/CLR)](#to_array)|Denetedilen sırayı yeni bir diziye kopyalar.|
|[set::upper_bound (STL/CLR)](#upper_bound)|Belirtilen bir anahtarla eşleşen aralık sonu bulur.|
|[set::value_comp (STL/CLR)](#value_comp)|İki öğe değeri için sipariş temsilcisini kopyalar.|

|İşleç|Açıklama|
|--------------|-----------------|
|[set::operator= (STL/CLR)](#op_as)|Denetedilen sırayı değiştirir.|
|[işleç!= (set) (STL/CLR)](#op_neq)|Bir nesnenin `set` başka `set` bir nesneye eşit olup olmadığını belirler.|
|[operatör< (set) (STL/CLR)](#op_lt)|Bir nesnenin `set` başka `set` bir nesneden küçük olup olmadığını belirler.|
|[işleç<= (set) (STL/CLR)](#op_lteq)|Bir nesnenin `set` başka `set` bir nesneden küçük veya eşit olup olmadığını belirler.|
|[işleci== (set) (STL/CLR)](#op_eq)|Bir nesnenin `set` başka `set` bir nesneye eşit olup olmadığını belirler.|
|[operatör> (set) (STL/CLR)](#op_gt)|Bir nesnenin `set` başka `set` bir nesneden büyük olup olmadığını belirler.|
|[operator>= (set) (STL/CLR)](#op_gteq)|Bir nesnenin `set` başka `set` bir nesneden büyük mü yoksa eşit mi olduğunu belirler.|

## <a name="interfaces"></a>Arabirimler

|Arabirim|Açıklama|
|---------------|-----------------|
|<xref:System.ICloneable>|Bir nesneyi çoğaltma.|
|<xref:System.Collections.IEnumerable>|Elementler arasında sırala.|
|<xref:System.Collections.ICollection>|Elementler grubunu koruyun.|
|<xref:System.Collections.Generic.IEnumerable%601>|Yazılan öğeler arasında sıralanır.|
|<xref:System.Collections.Generic.ICollection%601>|Yazılan öğelergrubunu koruyun.|
|ITree\<Anahtarı, Değer>|Genel kapsayıcıyı koruyun.|

## <a name="remarks"></a>Açıklamalar

Nesne, tek tek düğümler olarak denetlenen dizi için depolama yı ayırır ve boşaltır. Düğümler arasındaki bağlantıları değiştirerek, bir düğümün içeriğini diğerine kopyalayarak asla düzenli tuttuğu (neredeyse) dengeli bir ağaca öğeleri ekler. Bu, kalan öğeleri rahatsız etmeden öğeleri serbestçe ekebileceğiniz ve kaldırabileceğiniz anlamına gelir.

Nesne, denetlenen sırayı, tür kümesinin depolanmış bir temsilci nesnesini çağırarak [sıralar:key_compare (STL/CLR)](../dotnet/set-key-compare-stl-clr.md). Kümeyi oluştursanız depolanan temsilci nesnesini belirtebilirsiniz; temsilci nesnesi belirtmezseniz, varsayılan `operator<(key_type, key_type)`değer karşılaştırmadır. Bu depolanan nesneye üye işlev kümesini çağırarak erişebilirsiniz::key_comp [(STL/CLR)](../dotnet/set-key-comp-stl-clr.md)`()`.

Böyle bir temsilci nesnesi, tür kümesi tuşlarına katı bir zayıf sıralama empoze [etmelidir::key_type (STL/CLR)](../dotnet/set-key-type-stl-clr.md). Yani, herhangi bir `X` iki `Y`anahtar için ve:

`key_comp()(X, Y)`her çağrıda aynı Boolean sonucunu döndürür.

Eğer `key_comp()(X, Y)` doğruysa, `key_comp()(Y, X)` o zaman yanlış olmalıdır.

Eğer `key_comp()(X, Y)` doğruysa, `X` o zaman önce `Y`sipariş olduğu söyleniyor .

Eğer `!key_comp()(X, Y) && !key_comp()(Y, X)` doğruysa, `X` o `Y` zaman ve eşdeğer sipariş olduğu söyleniyor.

Denetlenir `X` sırada önce `Y` herhangi bir `key_comp()(Y, X)` öğe için, yanlıştır. (Varsayılan temsilci nesnesi için anahtarlar hiçbir zaman değerde azalmaz.) Şablon sınıf [kümesinin](../dotnet/set-stl-clr.md)aksine, `set` şablon sınıfının bir nesnesi tüm öğeler için anahtarların benzersiz olduğunu gerektirmez. (İki veya daha fazla anahtar eşdeğer sipariş olabilir.)

Her öğe hem bir ey hem de bir değer olarak hizmet vermektedir. Dizi, dizideki (logaritmik zaman) öğe sayısının logaritması ile orantılı bir dizi işlemle rasgele bir öğenin aramaya, eklenmesine ve kaldırılmasına izin veren bir şekilde temsil edilir. Ayrıca, bir öğe eklenmesi hiçbir yineleyiciyi geçersiz kılmaz; bir öğenin kaldırılması yalnızca bu kaldırılan öğeyi gösteren yineleyicileri geçersiz kılar.

Bir küme çift yönlü yineleyicileri destekler, bu da denetitilen dizideki bir öğeyi belirleyen bir yineleyici verilen bitişik öğelere adım atabileceğiniz anlamına gelir. Özel bir kafa düğümü, ayarla döndürülen yineleyiciye karşılık [gelir::end (STL/CLR)](../dotnet/set-end-stl-clr.md)`()`. Varsa, bu yineleyiciyi denetitilen dizideki son öğeye ulaşmak için atayabilirsiniz. Kafa düğümüne ulaşmak için bir ayar yineleyici yiyebilirsiniz ve daha sonra `end()`'a eşit. Ancak, döndürülen `end()`yineleyiciyi dereference yapamazsınız.

Rasgele erişim yinelemesi gerektiren sayısal konumu göz önüne alındığında, bir küme öğesine doğrudan başvuramayacağınızı unutmayın.

Küme yineleyici, bir tutamacı ilişkili küme düğümüne depolar ve bu da bir tutamacı ilişkili kapsayıcısına depolar. Yineleyicileri yalnızca ilişkili kapsayıcı nesneleri ile kullanabilirsiniz. Bir küme yineleyici, ilişkili küme düğümü bazı kümelerle ilişkili olduğu sürece geçerli kalır. Dahası, geçerli bir yineleyici dereferencable - erişmek veya belirlediği öğe değerini değiştirmek için `end()`kullanabilirsiniz - sürece eşit değildir .

Bir öğeyi silme veya kaldırma, depolanan değeri için yıkıcı çağırır. Kapsayıcıyı yok etmek tüm öğeleri siler. Böylece, eleman türü ref sınıfı olan bir kapsayıcı, hiçbir öğenin kapsayıcıdan daha uzun yaşamamasını sağlar. Ancak, bir tutamaçların kapsayıcısının öğelerini yok *etmediğini* unutmayın.

## <a name="members"></a>Üyeler

## <a name="setbegin-stlclr"></a><a name="begin"></a>set::begin (STL/CLR)

Denetlenen dizinin başlangıcını belirtir.

### <a name="syntax"></a>Sözdizimi

```cpp
iterator begin();
```

### <a name="remarks"></a>Açıklamalar

Üye işlev, denetlenmeyen dizinin ilk öğesini veya boş bir dizinin sonunun hemen ötesini belirleyen çift yönlü bir yineleme döndürür. Bunu, denetlenen dizinin başlangıcını `current` belirleyen bir yineleyici elde etmek için kullanırsınız, ancak denetlenen dizinin uzunluğu değişirse durumu değişebilir.

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

## <a name="setclear-stlclr"></a><a name="clear"></a>set::clear (STL/CLR)

Tüm öğeleri kaldırır.

### <a name="syntax"></a>Sözdizimi

```cpp
void clear();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi etkin bir şekilde [set çağırır::sil (STL/CLR)](../dotnet/set-erase-stl-clr.md) `(` [kümesi::begin (STL/CLR)](../dotnet/set-begin-stl-clr.md) `(),` [kümesi::end (STL/CLR)](../dotnet/set-end-stl-clr.md)`())`. Denetlenen dizinin boş olduğundan emin olmak için kullanırsınız.

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

## <a name="setconst_iterator-stlclr"></a><a name="const_iterator"></a>set::const_iterator (STL/CLR)

Denetlenen dizi için bir sabit yineleyici türü.

### <a name="syntax"></a>Sözdizimi

```cpp
typedef T2 const_iterator;
```

### <a name="remarks"></a>Açıklamalar

Tür, denetlenen dizi `T2` için sabit bir çift yönlü yineleme olarak hizmet verebilir belirtilmemiş türünde bir nesne açıklar.

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

## <a name="setconst_reference-stlclr"></a><a name="const_reference"></a>set::const_reference (STL/CLR)

Bir öğe için sabit bir başvuru türü.

### <a name="syntax"></a>Sözdizimi

```cpp
typedef value_type% const_reference;
```

### <a name="remarks"></a>Açıklamalar

Tür, bir öğeye sabit bir başvuru açıklar.

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

## <a name="setconst_reverse_iterator-stlclr"></a><a name="const_reverse_iterator"></a>set::const_reverse_iterator (STL/CLR)

Denetlenmeyen dizi için sabit bir ters yineleyici türü...

### <a name="syntax"></a>Sözdizimi

```cpp
typedef T4 const_reverse_iterator;
```

### <a name="remarks"></a>Açıklamalar

Tür, denetlenen dizi `T4` için sabit bir ters yineleyici olarak hizmet verebilen belirtilmemiş türde bir nesneyi açıklar.

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

## <a name="setcount-stlclr"></a><a name="count"></a>set::count (STL/CLR)

Belirtilen bir anahtar ile eşleşen öğe sayısını bulur.

### <a name="syntax"></a>Sözdizimi

```cpp
size_type count(key_type key);
```

#### <a name="parameters"></a>Parametreler

*anahtar*<br/>
Aranacak anahtar değer.

### <a name="remarks"></a>Açıklamalar

Üye işlev, *anahtarla*eşdeğer sıraya sahip kontrollü dizideki eleman sayısını döndürür. Belirli bir anahtarla eşleşen denetitilmiş sırada bulunan öğe sayısını belirlemek için kullanırsınız.

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

## <a name="setdifference_type-stlclr"></a><a name="difference_type"></a>set::difference_type (STL/CLR)

İki öğe arasındaki imzalı uzaklık türleri.

### <a name="syntax"></a>Sözdizimi

```cpp
typedef int difference_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, büyük olasılıkla negatif öğe sayısını açıklar.

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

## <a name="setempty-stlclr"></a><a name="empty"></a>set::boş (STL/CLR)

Bir öğe olup olmadığını sınar.

### <a name="syntax"></a>Sözdizimi

```cpp
bool empty();
```

### <a name="remarks"></a>Açıklamalar

Üye işlev boş bir kontrollü dizi için doğru döndürür. Bu set [eşdeğerdir::boyutu (STL / CLR)](../dotnet/set-size-stl-clr.md)`() == 0`. Kümenin boş olup olmadığını sınamak için kullanırsınız.

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

## <a name="setend-stlclr"></a><a name="end"></a>set::end (STL/CLR)

Denetlenen dizinin bitişini belirtir.

### <a name="syntax"></a>Sözdizimi

```cpp
iterator end();
```

### <a name="remarks"></a>Açıklamalar

Üye işlev, denetite edilen dizinin sonundan hemen ötesine işaret eden çift yönlü bir yineleme döndürür. Bunu, denetlenen dizinin sonunu belirleyen bir yineleyici elde etmek için kullanırsınız; denetitilen dizinin uzunluğu değişirse durumu değişmez.

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

## <a name="setequal_range-stlclr"></a><a name="equal_range"></a>set::equal_range (STL/CLR)

Belirtilen bir anahtarla eşleşen aralığı bulur.

### <a name="syntax"></a>Sözdizimi

```cpp
cliext::pair<iterator, iterator> equal_range(key_type key);
```

#### <a name="parameters"></a>Parametreler

*anahtar*<br/>
Aranacak anahtar değer.

### <a name="remarks"></a>Açıklamalar

Üye işlev `cliext::pair<iterator, iterator>(` [kümesi::lower_bound (STL/CLR)](../dotnet/set-lower-bound-stl-clr.md) `(key),` [kümesi::upper_bound (STL/CLR) kümesini](../dotnet/set-upper-bound-stl-clr.md)`(key))`döndürür. Belirli bir anahtarla eşleşen denetitilmiş sırada bulunan öğelerin aralığını belirlemek için kullanırsınız.

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

## <a name="seterase-stlclr"></a><a name="erase"></a>set::silme (STL/CLR)

Belirtilen konumlardaki öğeleri kaldırır.

### <a name="syntax"></a>Sözdizimi

```cpp
iterator erase(iterator where);
iterator erase(iterator first, iterator last);
size_type erase(key_type key)
```

#### <a name="parameters"></a>Parametreler

*Ilk*<br/>
Silmek için aralığın başlangıcı.

*anahtar*<br/>
Silmek için anahtar değeri.

*Son*<br/>
Silmek için aralığın sonu.

*Nerede*<br/>
Silecek öğe.

### <a name="remarks"></a>Açıklamalar

İlk üye işlev, işaret edilen kontrollü dizinin *where*öğesini nerede işaret eder ve kaldırılan öğenin ötesinde kalan ilk öğeyi belirleyen bir yineleyici döndürür veya böyle bir öğe [yoksa:end (STL/CLR)](../dotnet/set-end-stl-clr.md) `()` kümesini belirler. Tek bir öğeyi kaldırmak için kullanırsınız.

İkinci üye işlev,`first`[, `last`) aralığındaki kontrollü dizinin öğelerini kaldırır ve kaldırılan öğelerin ötesinde kalan ilk öğeyi belirleyen veya `end()` böyle bir öğe yoksa... Sıfır veya daha fazla bitişik öğeyi kaldırmak için kullanabilirsiniz.

Üçüncü üye işlev, anahtara eşdeğer sıralama olan kontrollü *key*dizinin herhangi bir öğesini kaldırır ve kaldırılan öğe sayısının sayısını döndürür. Belirli bir anahtarla eşleşen tüm öğeleri kaldırmak ve saymak için kullanırsınız.

Her öğe silme, kontrol edilen dizideki eleman sayısının logaritması ile orantılı zaman alır.

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

## <a name="setfind-stlclr"></a><a name="find"></a>set::bul (STL/CLR)

Belirtilen bir anahtarla eşleşen bir öğeyi bulur.

### <a name="syntax"></a>Sözdizimi

```cpp
iterator find(key_type key);
```

#### <a name="parameters"></a>Parametreler

*anahtar*<br/>
Aranacak anahtar değer.

### <a name="remarks"></a>Açıklamalar

Denetlenmeyen sırada en az bir öğe *anahtarla*eşdeğer sıralamaya sahipse, üye işlev bu öğelerden birini atayan bir yineleyici döndürür; aksi takdirde [ayarlanır döndürür::end (STL/CLR)](../dotnet/set-end-stl-clr.md)`()`. Belirli bir anahtarla eşleşen denetimli sırada bulunan bir öğeyi bulmak için kullanabilirsiniz.

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

## <a name="setgeneric_container-stlclr"></a><a name="generic_container"></a>set::generic_container (STL/CLR)

Kapsayıcı için genel arabirimin türü.

### <a name="syntax"></a>Sözdizimi

```cpp
typedef Microsoft::VisualC::StlClr::
    ITree<GKey, GValue>
    generic_container;
```

### <a name="remarks"></a>Açıklamalar

Tür, bu şablon kapsayıcı sınıfının genel arabirimini açıklar.

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

## <a name="setgeneric_iterator-stlclr"></a><a name="generic_iterator"></a>set::generic_iterator (STL/CLR)

Kapsayıcının genel arabirimiyle kullanılmak üzere bir yineleyici türü.

### <a name="syntax"></a>Sözdizimi

```cpp
typedef Microsoft::VisualC::StlClr::Generic::
    ContainerBidirectionalIterator<generic_value>
    generic_iterator;
```

### <a name="remarks"></a>Açıklamalar

Tür, bu şablon kapsayıcı sınıfı nın genel arabirimiyle kullanılabilecek genel bir yineleyiciyi açıklar.

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

## <a name="setgeneric_reverse_iterator-stlclr"></a><a name="generic_reverse_iterator"></a>set::generic_reverse_iterator (STL/CLR)

Kapsayıcının genel arabirimiyle kullanılmak üzere ters yineleyici türü.

### <a name="syntax"></a>Sözdizimi

```cpp
typedef Microsoft::VisualC::StlClr::Generic::
    ReverseRandomAccessIterator<generic_value>
    generic_reverse_iterator;
```

### <a name="remarks"></a>Açıklamalar

Tür, bu şablon kapsayıcı sınıfının genel arabirimiyle kullanılabilecek genel bir ters yineleyiciyi açıklar.

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

## <a name="setgeneric_value-stlclr"></a><a name="generic_value"></a>set::generic_value (STL/CLR)

Kapsayıcının genel arabirimiyle kullanılmak üzere bir öğenin türü.

### <a name="syntax"></a>Sözdizimi

```cpp
typedef GValue generic_value;
```

### <a name="remarks"></a>Açıklamalar

Tür, bu şablon `GValue` kapsayıcı sınıfının genel arabirimiyle kullanılmak üzere depolanan öğe değerini açıklayan bir tür nesnesini açıklar.

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

## <a name="setinsert-stlclr"></a><a name="insert"></a>set::insert (STL/CLR)

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

*Ilk*<br/>
Eklemek için aralığın başlangıcı.

*Son*<br/>
Eklenecek aralık sonu.

*Doğru*<br/>
Ekleme için numaralandırma.

*Val*<br/>
Eklemek için anahtar değeri.

*Nerede*<br/>
Eklemek için kapsayıcıda nerede (yalnızca ipucu).

### <a name="remarks"></a>Açıklamalar

Üye işlevlerin her biri kalan operandlar tarafından belirtilen bir dizi ekler.

İlk üye işlev değer *val'i*olan bir öğe eklemeye `X`çalışır ve bir çift değer verir. Doğruysa, `X.second` `X.first` yeni eklenen öğeyi belirler; aksi `X.first` takdirde, eşdeğer sıralamaya sahip bir öğe belirler ve yeni bir öğe eklenmez. Tek bir öğe eklemek için kullanabilirsiniz.

İkinci üye işlev, bir ipucu olarak (performansı artırmak için) *kullanarak* değer *val'i*olan bir öğe ekler ve yeni eklenen öğeyi belirleyen bir yineleyici döndürür. Bildiğiniz bir öğeye bitişik olabilecek tek bir öğe eklemek için kullanırsınız.

Üçüncü üye işlev diziekler [`first` `last`, ). Başka bir diziden kopyalanan sıfır veya daha fazla öğe eklemek için kullanırsınız.

Dördüncü üye *işlev, sağ*tarafından belirlenen sırayı ekler. Bir sayıcı tarafından açıklanan bir sıra eklemek için kullanabilirsiniz.

Her öğe ekleme, kontrol edilen dizideki eleman sayısının logaritması ile orantılı zaman alır. Ekleme, ekleme noktasına bitişik bir öğe belirleyen bir ipucu verilen, amortismana tabi sabit zaman oluşabilir.

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

## <a name="setiterator-stlclr"></a><a name="iterator"></a>set::yineleyici (STL/CLR)

Denetlenen dizi için bir yineleyici türü.

### <a name="syntax"></a>Sözdizimi

```cpp
typedef T1 iterator;
```

### <a name="remarks"></a>Açıklamalar

Tür, denetlenen dizi `T1` için çift yönlü bir yineleme olarak hizmet verebilen belirtilmemiş türde bir nesneyi açıklar.

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

## <a name="setkey_comp-stlclr"></a><a name="key_comp"></a>set::key_comp (STL/CLR)

İki anahtar için sipariş temsilcisini kopyalar.

### <a name="syntax"></a>Sözdizimi

```cpp
key_compare^key_comp();
```

### <a name="remarks"></a>Açıklamalar

Üye işlev, denetlenen sırayı sıralamak için kullanılan sıralama temsilcisini döndürür. İki anahtarı karşılaştırmak için kullanırsın.

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

## <a name="setkey_compare-stlclr"></a><a name="key_compare"></a>set::key_compare (STL/CLR)

İki anahtar için sipariş temsilcisi.

### <a name="syntax"></a>Sözdizimi

```cpp
Microsoft::VisualC::StlClr::BinaryDelegate<GKey, GKey, bool>
    key_compare;
```

### <a name="remarks"></a>Açıklamalar

Tür, anahtar bağımsız değişkenlerinin sırasını belirleyen temsilcinin eşanlamlısa.

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

## <a name="setkey_type-stlclr"></a><a name="key_type"></a>set::key_type (STL/CLR)

Bir sıralama anahtarının türü.

### <a name="syntax"></a>Sözdizimi

```cpp
typedef Key key_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, şablon parametresi *Anahtarı*ile eş anlamlıdır.

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

## <a name="setlower_bound-stlclr"></a><a name="lower_bound"></a>set::lower_bound (STL/CLR)

Belirtilen bir anahtarla eşleşen aralığın başlangıcını bulur.

### <a name="syntax"></a>Sözdizimi

```cpp
iterator lower_bound(key_type key);
```

#### <a name="parameters"></a>Parametreler

*anahtar*<br/>
Aranacak anahtar değer.

### <a name="remarks"></a>Açıklamalar

Üye işlev, anahtara `X` eşdeğer sıralama olan kontrollü dizideki ilk *öğeyi*belirler. Böyle bir öğe yoksa, [kümesi döndürür::end (STL/CLR)](../dotnet/set-end-stl-clr.md)`()`; aksi takdirde belirleyen `X`bir yineleyici döndürür. Belirli bir anahtarla eşleşen denetimli sırada bulunan öğeler dizisinin başlangıcını bulmak için kullanırsınız.

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

## <a name="setmake_value-stlclr"></a><a name="make_value"></a>set::make_value (STL/CLR)

Bir değer nesnesi oluşturuyor.

### <a name="syntax"></a>Sözdizimi

```cpp
static value_type make_value(key_type key);
```

#### <a name="parameters"></a>Parametreler

*anahtar*<br/>
Kullanılacak anahtar değer.

### <a name="remarks"></a>Açıklamalar

Üye işlev, `value_type` anahtarı *anahtar*olan bir nesneyi döndürür. Diğer birkaç üye işlevle kullanıma uygun bir nesne oluşturmak için kullanırsınız.

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

## <a name="setoperator-stlclr"></a><a name="op_as"></a>set::operator= (STL/CLR)

Denetedilen sırayı değiştirir.

### <a name="syntax"></a>Sözdizimi

```cpp
set<Key>% operator=(set<Key>% right);
```

#### <a name="parameters"></a>Parametreler

*Doğru*<br/>
Kopyalanması gereken konteyner.

### <a name="remarks"></a>Açıklamalar

Üye işleç *nesneye doğru* kopyalar, sonra döndürür. `*this` Bunu, denetlenir sırayı *sağdaki*kontrollü dizinin bir kopyasıyla değiştirmek için kullanırsınız.

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

## <a name="setrbegin-stlclr"></a><a name="rbegin"></a>set::rbegin (STL/CLR)

Ters denetimli dizinin başlangıcını belirler.

### <a name="syntax"></a>Sözdizimi

```cpp
reverse_iterator rbegin();
```

### <a name="remarks"></a>Açıklamalar

Üye işlev, denetlenen dizinin son öğesini veya boş bir dizinin başlangıcının hemen ötesini belirleyen bir ters yineleyici döndürür. Bu nedenle, ters `beginning` sırayı belirler. Ters sırada görülen denetlenen dizinin `current` başlangıcını belirleyen bir yineleyici elde etmek için kullanabilirsiniz, ancak denetlenen dizinin uzunluğu değişirse durumu değişebilir.

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

## <a name="setreference-stlclr"></a><a name="reference"></a>set::referans (STL/CLR)

Bir öğe için bir başvuru türü.

### <a name="syntax"></a>Sözdizimi

```cpp
typedef value_type% reference;
```

### <a name="remarks"></a>Açıklamalar

Tür, bir öğeye başvuru açıklar.

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

## <a name="setrend-stlclr"></a><a name="rend"></a>set::rend (STL/CLR)

Ters denetimli dizinin sonunu belirler.

### <a name="syntax"></a>Sözdizimi

```cpp
reverse_iterator rend();
```

### <a name="remarks"></a>Açıklamalar

Üye işlev, denetitilen dizinin başlangıcının hemen ötesine işaret eden bir ters yineleyici döndürür. Bu nedenle, ters `end` sırayı belirler. Ters sırada görülen denetlenen dizinin `current` sonunu belirleyen bir yineleyici elde etmek için kullanabilirsiniz, ancak denetlenen dizinin uzunluğu değişirse durumu değişebilir.

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

## <a name="setreverse_iterator-stlclr"></a><a name="reverse_iterator"></a>set::reverse_iterator (STL/CLR)

Denetlenen dizi için ters yineleyici türü.

### <a name="syntax"></a>Sözdizimi

```cpp
typedef T3 reverse_iterator;
```

### <a name="remarks"></a>Açıklamalar

Tür, denetlenen dizi `T3` için ters yineleyici olarak hizmet verebilen belirtilmemiş türde bir nesneyi açıklar.

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

## <a name="setset-stlclr"></a><a name="set"></a>set::set (STL/CLR)

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

*Ilk*<br/>
Eklemek için aralığın başlangıcı.

*Son*<br/>
Eklenecek aralık sonu.

*Pred*<br/>
Denetlenen sıra için yüklem sıralama.

*Doğru*<br/>
Eklemek için nesne veya aralık.

### <a name="remarks"></a>Açıklamalar

Yapıcı:

`set();`

varsayılan sıralama yüklemi `key_compare()`ile, hiçbir öğe ile denetlenmeyen sırayı başlatir. Varsayılan sıralama yüklemi ile boş bir ilk denetim sırası belirtmek için kullanabilirsiniz.

Yapıcı:

`explicit set(key_compare^ pred);`

sıralama yüklemi *pred*ile, hiçbir öğe ile kontrollü dizi başlatir. Belirtilen sıralama yüklemi ile boş bir ilk denetim sırası belirtmek için kullanabilirsiniz.

Yapıcı:

`set(set<Key>% right);`

varsayılan sıralama yüklemi ile`right.begin()`[, `right.end()`), ile denetitilen sırayı başlatir. Varsayılan sıralama yüklemi ile küme nesnesi *sağ*tarafından denetlenir dizi bir kopyası olan bir ilk denetimsırası belirtmek için kullanabilirsiniz.

Yapıcı:

`set(set<Key>^ right);`

varsayılan sıralama yüklemi ile`right->begin()`[, `right->end()`), ile denetitilen sırayı başlatir. Varsayılan sıralama yüklemi ile küme nesnesi *sağ*tarafından denetlenir dizi bir kopyası olan bir ilk denetimsırası belirtmek için kullanabilirsiniz.

Yapıcı:

`template<typename InIter> set(InIter first, InIter last);`

varsayılan sıralama yüklemi ile`first`[, `last`), ile denetitilen sırayı başlatir. Denetlenir sırayı varsayılan sıralama yüklemi ile başka bir dizinin kopyası yapmak için kullanırsınız.

Yapıcı:

`template<typename InIter> set(InIter first, InIter last, key_compare^ pred);`

sıralama yüklemi *pred*ile`first` `last`[, ), ile kontrollü sırayı başlatir. Denetedilen sırayı, belirtilen sıralama yüklemi yle birlikte başka bir dizinin kopyası yapmak için kullanırsınız.

Yapıcı:

`set(System::Collections::Generic::IEnumerable<Key>^ right);`

varsayılan sıralama yüklemi ile, enumerator *sağ*tarafından belirlenen sıra ile kontrollü sırayı başlatir. Denetedilen sırayı, varsayılan sıralama yüklemi ile bir yerumerator tarafından açıklanan başka bir dizinin bir kopyasını yapmak için kullanabilirsiniz.

Yapıcı:

`set(System::Collections::Generic::IEnumerable<Key>^ right, key_compare^ pred);`

hadis idamı ile, sıralama yüklemi *pred'i*ile, sayısallaştırıcı *sağ*tarafından belirlenen sıra ile kontrollü sırayı başlatir. Denetedilen sırayı, belirtilen sıralama yüklemi yle bir yerumerator tarafından açıklanan başka bir dizinin bir kopyasını yapmak için kullanırsınız.

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

## <a name="setsize-stlclr"></a><a name="size"></a>set::boyut (STL/CLR)

Öğe sayısını sayar.

### <a name="syntax"></a>Sözdizimi

```cpp
size_type size();
```

### <a name="remarks"></a>Açıklamalar

Üye işlev, denetitilen dizinin uzunluğunu döndürür. Şu anda denetlenmeyen sırada bulunan öğe sayısını belirlemek için kullanırsınız. Tek umursadığınız dizinin sıfır olmayan boyuta sahip olup olmadığıysa, [bkz.](../dotnet/set-empty-stl-clr.md)`()`

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

## <a name="setsize_type-stlclr"></a><a name="size_type"></a>set::size_type (STL/CLR)

İki öğe arasındaki imzalı uzaklık türü.

### <a name="syntax"></a>Sözdizimi

```cpp
typedef int size_type;
```

### <a name="remarks"></a>Açıklamalar

Tür negatif olmayan öğe sayısını açıklar.

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

## <a name="setswap-stlclr"></a><a name="swap"></a>set::swap (STL/CLR)

İki kapsayıcının içeriğinin yerini değiştirir.

### <a name="syntax"></a>Sözdizimi

```cpp
void swap(set<Key>% right);
```

#### <a name="parameters"></a>Parametreler

*Doğru*<br/>
İçeriği takas etmek için konteyner.

### <a name="remarks"></a>Açıklamalar

Üye işlev, kontrollü dizileri `this` sağ ve *arasındaki*sıraları değiştirir. Bunu sürekli zaman içinde yapar ve hiçbir istisna atar. İki kapsayıcının içeriğini değiştirmek için hızlı bir yol olarak kullanabilirsiniz.

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

## <a name="setto_array-stlclr"></a><a name="to_array"></a>set::to_array (STL/CLR)

Denetedilen sırayı yeni bir diziye kopyalar.

### <a name="syntax"></a>Sözdizimi

```cpp
cli::array<value_type>^ to_array();
```

### <a name="remarks"></a>Açıklamalar

Üye işlev, denetitilmiş sırayı içeren bir dizi döndürür. Bunu, denetitilmiş dizinin dizi biçiminde bir kopyasını elde etmek için kullanırsınız.

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

## <a name="setupper_bound-stlclr"></a><a name="upper_bound"></a>set::upper_bound (STL/CLR)

Belirtilen bir anahtarla eşleşen aralık sonu bulur.

### <a name="syntax"></a>Sözdizimi

```cpp
iterator upper_bound(key_type key);
```

#### <a name="parameters"></a>Parametreler

*anahtar*<br/>
Aranacak anahtar değer.

### <a name="remarks"></a>Açıklamalar

Üye işlev, anahtara `X` eşdeğer sıralama olan kontrollü dizideki son *öğeyi*belirler. Böyle bir öğe yoksa `X` veya denetlenir dizideki son öğe [ise, set::end (STL/CLR)](../dotnet/set-end-stl-clr.md)`()`döndürür; aksi takdirde, ötesindeki `X`ilk öğeyi belirleyen bir yineleyici döndürür. Belirli bir anahtarla eşleşen denetimli dizideki şu anda bir dizi öğenin sonunu bulmak için kullanırsınız.

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

## <a name="setvalue_comp-stlclr"></a><a name="value_comp"></a>set::value_comp (STL/CLR)

İki öğe değeri için sipariş temsilcisini kopyalar.

### <a name="syntax"></a>Sözdizimi

```cpp
value_compare^ value_comp();
```

### <a name="remarks"></a>Açıklamalar

Üye işlev, denetlenen sırayı sıralamak için kullanılan sıralama temsilcisini döndürür. İki öğe değerlerini karşılaştırmak için kullanırsınız.

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

## <a name="setvalue_compare-stlclr"></a><a name="value_compare"></a>set::value_compare (STL/CLR)

İki öğe değeri için sıralama temsilcisi.

### <a name="syntax"></a>Sözdizimi

```cpp
Microsoft::VisualC::StlClr::BinaryDelegate<generic_value, generic_value, bool>
    value_compare;
```

### <a name="remarks"></a>Açıklamalar

Tür, değer bağımsız değişkenlerinin sırasını belirleyen temsilcinin eşanlamlısa.

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

## <a name="setvalue_type-stlclr"></a><a name="value_type"></a>set::value_type (STL/CLR)

Öğenin türü.

### <a name="syntax"></a>Sözdizimi

```cpp
typedef generic_value value_type;
```

### <a name="remarks"></a>Açıklamalar

Türü için `generic_value`eşanlamlıdır.

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

## <a name="operator-set-stlclr"></a><a name="op_neq"></a>işleç!= (set) (STL/CLR)

Eşit karşılaştırma değil liste.

### <a name="syntax"></a>Sözdizimi

```cpp
template<typename Key>
    bool operator!=(set<Key>% left,
        set<Key>% right);
```

#### <a name="parameters"></a>Parametreler

*Sol*<br/>
Karşılaştırmak için sol konteyner.

*Doğru*<br/>
Karşılaştırmak için doğru konteyner.

### <a name="remarks"></a>Açıklamalar

Operatör işlevi `!(left == right)`döndürür. İki küme öğeile karşılaştırıldığında sağ *olarak* aynı sıralı *olup* olmadığını test etmek için kullanabilirsiniz.

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

## <a name="operatorlt-set-stlclr"></a><a name="op_lt"></a>işleç&lt; (set) (STL/CLR)

Karşılaştırmadan daha az liste.

### <a name="syntax"></a>Sözdizimi

```cpp
template<typename Key>
    bool operator<(set<Key>% left,
        set<Key>% right);
```

#### <a name="parameters"></a>Parametreler

*Sol*<br/>
Karşılaştırmak için sol konteyner.

*Doğru*<br/>
Karşılaştırmak için doğru konteyner.

### <a name="remarks"></a>Açıklamalar

Operatör işlevi, en düşük pozisyon `i` için `!(right[i] < left[i])` de doğru ysa `left[i] < right[i]`doğru döndürür. Aksi takdirde, `left->size() < right->size()` iki küme öğe ile karşılaştırıldığında sağ *önce* *sol* sıralanır olup olmadığını test etmek için kullanabilirsiniz döndürür.

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

## <a name="operatorlt-set-stlclr"></a><a name="op_lteq"></a>işleç&lt;= (set) (STL/CLR)

Daha az veya eşit karşılaştırma listele.

### <a name="syntax"></a>Sözdizimi

```cpp
template<typename Key>
    bool operator<=(set<Key>% left,
        set<Key>% right);
```

#### <a name="parameters"></a>Parametreler

*Sol*<br/>
Karşılaştırmak için sol konteyner.

*Doğru*<br/>
Karşılaştırmak için doğru konteyner.

### <a name="remarks"></a>Açıklamalar

Operatör işlevi `!(right < left)`döndürür. İki küme öğeile karşılaştırıldığında *sağdan* sonra sol sıralanıp sıralanmadığını *left* test etmek için kullanabilirsiniz.

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

## <a name="operator-set-stlclr"></a><a name="op_eq"></a>işleci== (set) (STL/CLR)

Eşit karşılaştırmayı listele.

### <a name="syntax"></a>Sözdizimi

```cpp
template<typename Key>
    bool operator==(set<Key>% left,
        set<Key>% right);
```

#### <a name="parameters"></a>Parametreler

*Sol*<br/>
Karşılaştırmak için sol konteyner.

*Doğru*<br/>
Karşılaştırmak için doğru konteyner.

### <a name="remarks"></a>Açıklamalar

İşleç işlevi yalnızca *sol* ve *sağ* tarafından denetlenen diziler `i`aynı `left[i] ==` `right[i]`uzunluğa sahipse ve her pozisyon için doğru döndürür. İki küme öğeile karşılaştırıldığında sağ *olarak* aynı sıralı *olup* olmadığını test etmek için kullanabilirsiniz.

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

## <a name="operatorgt-set-stlclr"></a><a name="op_gt"></a>işleç&gt; (set) (STL/CLR)

Karşılaştırmadan daha büyük liste.

### <a name="syntax"></a>Sözdizimi

```cpp
template<typename Key>
    bool operator>(set<Key>% left,
        set<Key>% right);
```

#### <a name="parameters"></a>Parametreler

*Sol*<br/>
Karşılaştırmak için sol konteyner.

*Doğru*<br/>
Karşılaştırmak için doğru konteyner.

### <a name="remarks"></a>Açıklamalar

Operatör işlevi `right` `<` `left`döndürür. İki küme öğeile karşılaştırıldığında *sağdan* sonra sol sıralanıp sıralanmadığını *left* test etmek için kullanabilirsiniz.

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

## <a name="operatorgt-set-stlclr"></a><a name="op_gteq"></a>işleç&gt;= (set) (STL/CLR)

Karşılaştırmadan büyük veya eşit olarak listele.

### <a name="syntax"></a>Sözdizimi

```cpp
template<typename Key>
    bool operator>=(set<Key>% left,
        set<Key>% right);
```

#### <a name="parameters"></a>Parametreler

*Sol*<br/>
Karşılaştırmak için sol konteyner.

*Doğru*<br/>
Karşılaştırmak için doğru konteyner.

### <a name="remarks"></a>Açıklamalar

Operatör işlevi `!(left < right)`döndürür. İki küme öğeile karşılaştırıldığında sağ *önce* sol sıralı *olup* olmadığını test etmek için kullanabilirsiniz.

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
