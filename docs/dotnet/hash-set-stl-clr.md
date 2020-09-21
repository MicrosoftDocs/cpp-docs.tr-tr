---
title: hash_set (STL/CLR)
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- cliext::hash_set
- cliext::hash_set::begin
- cliext::hash_set::bucket_count
- cliext::hash_set::clear
- cliext::hash_set::const_iterator
- cliext::hash_set::const_reference
- cliext::hash_set::const_reverse_iterator
- cliext::hash_set::count
- cliext::hash_set::difference_type
- cliext::hash_set::empty
- cliext::hash_set::end
- cliext::hash_set::equal_range
- cliext::hash_set::erase
- cliext::hash_set::find
- cliext::hash_set::generic_container
- cliext::hash_set::generic_iterator
- cliext::hash_set::generic_reverse_iterator
- cliext::hash_set::generic_value
- cliext::hash_set::hash_delegate
- cliext::hash_set::hash_set
- cliext::hash_set::hasher
- cliext::hash_set::insert
- cliext::hash_set::iterator
- cliext::hash_set::key_comp
- cliext::hash_set::key_compare
- cliext::hash_set::key_type
- cliext::hash_set::load_factor
- cliext::hash_set::lower_bound
- cliext::hash_set::make_value
- cliext::hash_set::max_load_factor
- cliext::hash_set::operator=
- cliext::hash_set::rbegin
- cliext::hash_set::reference
- cliext::hash_set::rehash
- cliext::hash_set::rend
- cliext::hash_set::reverse_iterator
- cliext::hash_set::size
- cliext::hash_set::size_type
- cliext::hash_set::swap
- cliext::hash_set::to_array
- cliext::hash_set::upper_bound
- cliext::hash_set::value_comp
- cliext::hash_set::value_compare
- cliext::hash_set::value_type
helpviewer_keywords:
- <cliext/hash_set> header [STL/CLR]
- hash_set class [STL/CLR]
- <hash_set> header [STL/CLR]
- begin member [STL/CLR]
- bucket_count member [STL/CLR]
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
- hash_delegate member [STL/CLR]
- hash_set member [STL/CLR]
- hasher member [STL/CLR]
- insert member [STL/CLR]
- iterator member [STL/CLR]
- key_comp member [STL/CLR]
- key_compare member [STL/CLR]
- key_type member [STL/CLR]
- load_factor member [STL/CLR]
- lower_bound member [STL/CLR]
- make_value member [STL/CLR]
- max_load_factor member [STL/CLR]
- operator= member [STL/CLR]
- rbegin member [STL/CLR]
- reference member [STL/CLR]
- rehash member [STL/CLR]
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
ms.assetid: d110e356-ba3e-4e52-9e2d-d997bf975c96
ms.openlocfilehash: a7db6367ae7d5096c47666a1ea930720f061c9dd
ms.sourcegitcommit: 72161bcd21d1ad9cc3f12261aa84a5b026884afa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2020
ms.locfileid: "90743132"
---
# <a name="hash_set-stlclr"></a>hash_set (STL/CLR)

Şablon sınıfı, çift yönlü erişime sahip olan öğelerin değişen uzunluklu bir dizisini denetleyen bir nesneyi tanımlar. Bir `hash_set` dizi öğeyi bir karma tablo olarak yönetmek için kapsayıcıyı, çift yönlü bağlantılı düğümlerin bir listesini depolayan her tablo girişini ve bir öğeyi depolayan her düğümü kullanın. Her öğenin değeri, diziyi sıralamak için anahtar olarak kullanılır.

Aşağıdaki açıklamada, `GValue` ile aynı şekilde, `GKey` İkincisi bir başvuru türü olmadığı sürece *anahtarla* aynı olur ve bu durumda olur `Key^` .

## <a name="syntax"></a>Söz dizimi

```cpp
template<typename Key>
    ref class hash_set
        :   public
        System::ICloneable,
        System::Collections::IEnumerable,
        System::Collections::ICollection,
        System::Collections::Generic::IEnumerable<GValue>,
        System::Collections::Generic::ICollection<GValue>,
        System::Collections::Generic::IList<GValue>,
        Microsoft::VisualC::StlClr::IHash<Gkey, GValue>
    { ..... };
```

### <a name="parameters"></a>Parametreler

*Key*<br/>
Denetlenen dizideki bir öğenin anahtar bileşeni türü.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<cliext/hash_set>

**Ad alanı:** cliext

## <a name="declarations"></a>Bildirimler

|Tür Tanımı|Description|
|---------------------|-----------------|
|[hash_set::const_iterator (STL/CLR)](#const_iterator)|Denetlenen dizi için bir sabit yineleyici türü.|
|[hash_set::const_reference (STL/CLR)](#const_reference)|Bir öğe için sabit bir başvuru türü.|
|[hash_set::const_reverse_iterator (STL/CLR)](#const_reverse_iterator)|Denetlenen sıra için bir sabit ters yineleyicinin türü.|
|[hash_set::difference_type (STL/CLR)](#difference_type)|İki öğe arasındaki mesafe (muhtemelen imzalı) türü.|
|[hash_set::generic_container (STL/CLR)](#generic_container)|Kapsayıcının genel arabiriminin türü.|
|[hash_set::generic_iterator (STL/CLR)](#generic_iterator)|Kapsayıcının genel arabirimi için bir yineleyici türü.|
|[hash_set::generic_reverse_iterator (STL/CLR)](#generic_reverse_iterator)|Kapsayıcının genel arabirimi için ters yineleyicinin türü.|
|[hash_set::generic_value (STL/CLR)](#generic_value)|Kapsayıcının genel arabirimi için bir öğenin türü.|
|[hash_set::hasher (STL/CLR)](#hasher)|Bir anahtar için karma temsilcisi.|
|[hash_set::iterator (STL/CLR)](#iterator)|Denetlenen dizi için bir yineleyici türü.|
|[hash_set::key_compare (STL/CLR)](#key_compare)|İki anahtar için sıralama temsilcisi.|
|[hash_set::key_type (STL/CLR)](#key_type)|Bir sıralama anahtarının türü.|
|[hash_set::reference (STL/CLR)](#reference)|Bir öğe için bir başvuru türü.|
|[hash_set::reverse_iterator (STL/CLR)](#reverse_iterator)|Denetlenen sıra için ters yineleyicinin türü.|
|[hash_set::size_type (STL/CLR)](#size_type)|İki öğe arasındaki (negatif olmayan) bir mesafe türü.|
|[hash_set::value_compare (STL/CLR)](#value_compare)|İki öğe değeri için sıralama temsilcisi.|
|[hash_set::value_type (STL/CLR)](#value_type)|Öğenin türü.|

|Üye İşlevi|Description|
|---------------------|-----------------|
|[hash_set::begin (STL/CLR)](#begin)|Denetlenen dizinin başlangıcını belirtir.|
|[hash_set::bucket_count (STL/CLR)](#bucket_count)|Demetlerin sayısını sayar.|
|[hash_set::clear (STL/CLR)](#clear)|Tüm öğeleri kaldırır.|
|[hash_set::count (STL/CLR)](#count)|Belirtilen bir anahtarla eşleşen öğeleri sayar.|
|[hash_set::empty (STL/CLR)](#empty)|Bir öğe olup olmadığını sınar.|
|[hash_set::end (STL/CLR)](#end)|Denetlenen dizinin bitişini belirtir.|
|[hash_set::equal_range (STL/CLR)](#equal_range)|Belirtilen bir anahtarla eşleşen aralığı bulur.|
|[hash_set::erase (STL/CLR)](#erase)|Belirtilen konumlardaki öğeleri kaldırır.|
|[hash_set::find (STL/CLR)](#find)|Belirtilen bir anahtarla eşleşen bir öğeyi bulur.|
|[hash_set::hash_delegate (STL/CLR)](#hash_delegate)|Bir anahtar için karma temsilciyi kopyalar.|
|[hash_set::hash_set (STL/CLR)](#hash_set)|Bir kapsayıcı nesnesi oluşturur.|
|[hash_set::insert (STL/CLR)](#insert)|Öğeleri ekler.|
|[hash_set::key_comp (STL/CLR)](#key_comp)|Sıralama temsilcisini iki anahtar için kopyalar.|
|[hash_set::load_factor (STL/CLR)](#load_factor)|Demet başına ortalama öğeyi sayar.|
|[hash_set::lower_bound (STL/CLR)](#lower_bound)|Belirtilen anahtarla eşleşen aralığın başlangıcını bulur.|
|[hash_set::make_value (STL/CLR)](#make_value)|Değer nesnesi oluşturur.|
|[hash_set::max_load_factor (STL/CLR)](#max_load_factor)|Demet başına en yüksek öğe sayısını alır veya ayarlar.|
|[hash_set::rbegin (STL/CLR)](#rbegin)|Ters denetlenen sıranın başlangıcını belirtir.|
|[hash_set::rehash (STL/CLR)](#rehash)|Karma tabloyu yeniden oluşturur.|
|[hash_set::rend (STL/CLR)](#rend)|Ters denetlenen sıranın sonunu belirtir.|
|[hash_set::size (STL/CLR)](#size)|Öğe sayısını sayar.|
|[hash_set::swap (STL/CLR)](#swap)|İki kapsayıcının içeriğinin yerini değiştirir.|
|[hash_set::to_array (STL/CLR)](#to_array)|Denetimli sırayı yeni bir diziye kopyalar.|
|[hash_set::upper_bound (STL/CLR)](#upper_bound)|Belirtilen anahtarla eşleşen aralığın sonunu bulur.|
|[hash_set::value_comp (STL/CLR)](#value_comp)|İki öğe değeri için sıralama temsilcisini kopyalar.|

|İşleç|Açıklama|
|--------------|-----------------|
|[hash_set::operator= (STL/CLR)](#op)|Denetlenen sırayı değiştirir.|

## <a name="interfaces"></a>Arabirimler

|Arabirim|Description|
|---------------|-----------------|
|<xref:System.ICloneable>|Bir nesneyi çoğaltın.|
|<xref:System.Collections.IEnumerable>|Öğeler aracılığıyla sıralama.|
|<xref:System.Collections.ICollection>|Öğe grubunu saklayın.|
|<xref:System.Collections.Generic.IEnumerable%601>|Yazılı öğeler aracılığıyla sıralama.|
|<xref:System.Collections.Generic.ICollection%601>|Türü belirtilmiş öğelerin grubunu koruyun.|
|IHash\<Key, Value>|Genel kapsayıcıyı koruyun.|

## <a name="remarks"></a>Açıklamalar

Nesnesi, çift yönlü bağlantılı bir listede ayrı düğümler olarak denetlediği sıra için depolamayı ayırır ve boşaltır. Bu nesne, erişimi hızlandırmak için aynı zamanda listeye (karma tablo) farklı bir işaretçiler dizisi tutar ve tüm listeyi bir alt liste dizisi veya demetler olarak bir dizi olarak yönetir. Tek bir düğümün içeriğini başka bir düğüme kopyalayarak düğümler arasındaki bağlantıları değiştirerek sıralı tutan bir sepete öğe ekler. Diğer bir deyişle, daha fazla Bing, kalan öğeleri etkilemeden öğeleri ekleyebileceğiniz ve kaldırabileceğiniz anlamına gelir.

Nesne, [hash_set:: key_compare (STL/CLR)](../dotnet/hash-set-key-compare-stl-clr.md)türünde depolanan bir temsilci nesnesini çağırarak Denetim yaptığı her sepete sahiptir. Hash_set oluşturduğunuzda saklı temsilci nesnesini belirtebilirsiniz; temsilci nesnesi belirtmezseniz, varsayılan değer karşılaştırmayla belirlenir `operator<=(key_type, key_type)` .

Saklı temsilci nesnesine, [hash_set:: key_comp (STL/CLR)](../dotnet/hash-set-key-comp-stl-clr.md)üye işlevini çağırarak erişirsiniz `()` . Bu tür bir temsilci nesnesi [hash_set:: key_type (STL/CLR)](../dotnet/hash-set-key-type-stl-clr.md)türü anahtarlar arasında denk sıralama tanımlamalıdır. Yani, her iki anahtar için `X` ve `Y` :

`key_comp()(X, Y)` her çağrıda aynı Boole sonucunu döndürür.

`key_comp()(X, Y) && key_comp()(Y, X)`True ise, `X` ve `Y` eşdeğer sıralamaya sahip olarak kabul edilir.

Gibi davranan `operator<=(key_type, key_type)` `operator>=(key_type, key_type)` veya `operator==(key_type, key_type)` eqivalent sıralamasını tanımlayan herhangi bir sıralama kuralı.

Kapsayıcının yalnızca, anahtarları eşdeğer sıralama (ve aynı tamsayı değeri ile aynı karma değer) olan öğelerin bir demet içinde bitişik olduğunu garanti edin. Şablon sınıfının [hash_multiset (STL/CLR)](../dotnet/hash-multiset-stl-clr.md)aksine, şablon sınıfının bir nesnesi `hash_set` tüm öğeler için anahtarların benzersiz olmasını sağlar. (İki anahtarın eşdeğer sıralaması yoktur.)

Nesnesi, [hash_set:: hasher (STL/CLR)](../dotnet/hash-set-hasher-stl-clr.md)türünde depolanan bir temsilci nesnesini çağırarak, hangi demetini belirli bir sıralama anahtarı içermesi gerektiğini belirler. Bu saklı nesneye, anahtar değerine bağlı bir tamsayı değer elde etmek için [hash_set:: hash_delegate (STL/CLR)](../dotnet/hash-set-hash-delegate-stl-clr.md) üye işlevini çağırarak erişirsiniz `()` . Hash_set oluşturduğunuzda saklı temsilci nesnesini belirtebilirsiniz; temsilci nesnesi belirtmezseniz, varsayılan olarak işlevdir `System::Object::hash_value(key_type)` . Yani, tüm anahtarlar `X` ve `Y` :

`hash_delegate()(X)` her çağrıda aynı tamsayı sonucunu döndürür.

`X`Ve `Y` eşdeğer sıralamaya sahipseniz, ile `hash_delegate()(X)` aynı tamsayı sonucunu döndürmelidir `hash_delegate()(Y)` .

Her öğe hem bir anahtar hem de bir değer olarak hizmet verir. Sıra, dizi içindeki öğe sayısından (Sabit saat) bağımsız olan ve en iyi durumda en az sayıda işlem içeren, rastgele bir öğenin arama, ekleme ve kaldırılmasına izin veren bir şekilde temsil edilir. Ayrıca, bir öğe eklenmesi hiçbir yineleyiciyi geçersiz kılmaz; bir öğenin kaldırılması yalnızca bu kaldırılan öğeyi gösteren yineleyicileri geçersiz kılar.

Karma değerler her ikisi de dağıtılmadığından, karma bir tablo oluşturabilir. Extreme 'de, her zaman aynı değeri döndüren bir karma işlevi için--arama, ekleme ve kaldırma dizideki öğelerin sayısıyla orantılıdır (doğrusal saat). Kapsayıcı endeavors, makul bir karma işlevi, ortalama demet boyutu ve karma tablo boyutu (Toplam demet sayısı) seçmek için, ancak bu seçimlerin herhangi birini veya tümünü geçersiz kılabilirsiniz. Bkz. Örneğin, [hash_set:: max_load_factor (STL/CLR)](../dotnet/hash-set-max-load-factor-stl-clr.md) ve [hash_set:: REHASH (STL/CLR)](../dotnet/hash-set-rehash-stl-clr.md)işlevleri.

Hash_set çift yönlü yineleyiciler destekler, bu, denetlenen dizide bir öğe atayan bir yineleyici verilen bitişik öğelere adım adım yol açabilir. Özel bir baş düğüm [hash_set:: End (STL/CLR)](../dotnet/hash-set-end-stl-clr.md)tarafından döndürülen Yineleyici öğesine karşılık gelir `()` . Varsa, denetlenen sıradaki son öğeye ulaşmak için bu yineleyiciyi azaltamazsınız. Baş düğüme ulaşmak için bir hash_set yineleyicisini artırabilirsiniz ve daha sonra eşittir ile karşılaştırılır `end()` . Ancak tarafından döndürülen Yineleyici için başvuru oluşturamazsınız `end()` .

Bir hash_set öğesine, bir rastgele erişim Yineleyici gerektiren sayısal konumuna doğrudan başvurmayacağınızı unutmayın.

Hash_set yineleyici, ilişkili kapsayıcısına bir tutamacı depolayan bir tutamacı ilişkili hash_set düğümüne depolar. Yineleyiciler yalnızca ilişkili kapsayıcı nesneleriyle birlikte kullanabilirsiniz. Hash_set yineleyici, ilişkili hash_set düğümü bazı hash_set ilişkili olduğu sürece geçerli kalır. Üstelik, geçerli bir yineleyici bir şekilde gönderilir--bunu, oluşturduğu öğe değerine erişmek veya değiştirmek için kullanabilirsiniz. buna eşit olmadığı sürece `end()` .

Bir öğeyi silme veya kaldırma, kendi saklı değeri için yıkıcıyı çağırır. Kapsayıcının yok edilmesi tüm öğeleri siler. Bu nedenle, öğe türü bir başvuru sınıfı olan bir kapsayıcı, kapsayıcının hiçbir öğenin etkin olmamasını sağlar. Ancak, bir işleç kapsayıcısının *öğelerini yok ettiğini* unutmayın.

## <a name="members"></a>Üyeler

## <a name="hash_setbegin-stlclr"></a><a name="begin"></a> hash_set:: Begin (STL/CLR)

Denetlenen dizinin başlangıcını belirtir.

### <a name="syntax"></a>Syntax

```cpp
iterator begin();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, denetimli sıranın ilk öğesini veya boş bir dizinin sonunun ötesinde bir çift yönlü yineleyiciyi döndürür. Denetlenen dizinin başlangıcını atayan bir yineleyici elde etmek için bunu kullanırsınız `current` , ancak denetlenen sıranın uzunluğu değişirse durum değişebilir.

### <a name="example"></a>Örnek

```cpp
// cliext_hash_set_begin.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_set<wchar_t> Myhash_set;
int main()
    {
    Myhash_set c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // inspect first two items
    Myhash_set::iterator it = c1.begin();
    System::Console::WriteLine("*begin() = {0}", *it);
    System::Console::WriteLine("*++begin() = {0}", *++it);
    return (0);
    }
```

## <a name="hash_setbucket_count-stlclr"></a><a name="bucket_count"></a> hash_set:: bucket_count (STL/CLR)

Demetlerin sayısını sayar.

### <a name="syntax"></a>Syntax

```cpp
int bucket_count();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevleri, geçerli demet sayısını döndürür. Karma tablonun boyutunu öğrenmek için bunu kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// cliext_hash_set_bucket_count.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_set<wchar_t> Myhash_set;
int main()
    {
    Myhash_set c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // inspect current parameters
    System::Console::WriteLine("bucket_count() = {0}", c1.bucket_count());
    System::Console::WriteLine("load_factor() = {0}", c1.load_factor());
    System::Console::WriteLine("max_load_factor() = {0}",
        c1.max_load_factor());
    System::Console::WriteLine();

    // change max_load_factor and redisplay
    c1.max_load_factor(0.25f);
    System::Console::WriteLine("bucket_count() = {0}", c1.bucket_count());
    System::Console::WriteLine("load_factor() = {0}", c1.load_factor());
    System::Console::WriteLine("max_load_factor() = {0}",
        c1.max_load_factor());
    System::Console::WriteLine();

    // rehash and redisplay
    c1.rehash(100);
    System::Console::WriteLine("bucket_count() = {0}", c1.bucket_count());
    System::Console::WriteLine("load_factor() = {0}", c1.load_factor());
    System::Console::WriteLine("max_load_factor() = {0}",
        c1.max_load_factor());
    return (0);
    }
```

```Output
a b c
bucket_count() = 16
load_factor() = 0.1875
max_load_factor() = 4

bucket_count() = 16
load_factor() = 0.1875
max_load_factor() = 0.25

bucket_count() = 128
load_factor() = 0.0234375
max_load_factor() = 0.25
```

## <a name="hash_setclear-stlclr"></a><a name="clear"></a> hash_set:: Clear (STL/CLR)

Tüm öğeleri kaldırır.

### <a name="syntax"></a>Syntax

```cpp
void clear();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi [hash_set:: Erase (STL/CLR)](../dotnet/hash-set-erase-stl-clr.md) `(` [hash_set:: BEGIN (STL/CLR](../dotnet/hash-set-begin-stl-clr.md) ) `(),` [hash_set:: End (STL/CLR](../dotnet/hash-set-end-stl-clr.md)) öğesini etkin şekilde çağırır `())` . Denetlenen sıranın boş olduğundan emin olmak için bunu kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// cliext_hash_set_clear.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_set<wchar_t> Myhash_set;
int main()
    {
    Myhash_set c1;
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

## <a name="hash_setconst_iterator-stlclr"></a><a name="const_iterator"></a> hash_set:: const_iterator (STL/CLR)

Denetlenen dizi için bir sabit yineleyici türü.

### <a name="syntax"></a>Syntax

```cpp
typedef T2 const_iterator;
```

### <a name="remarks"></a>Açıklamalar

Türü, `T2` Denetlenen dizi için bir sabit çift yönlü yineleyiciyi görebilecek belirtilmemiş türdeki bir nesneyi tanımlar.

### <a name="example"></a>Örnek

```cpp
// cliext_hash_set_const_iterator.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_set<wchar_t> Myhash_set;
int main()
    {
    Myhash_set c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display contents " a b c"
    Myhash_set::const_iterator cit = c1.begin();
    for (; cit != c1.end(); ++cit)
        System::Console::Write("{0} ", *cit);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="hash_setconst_reference-stlclr"></a><a name="const_reference"></a> hash_set:: const_reference (STL/CLR)

Bir öğe için sabit bir başvuru türü.

### <a name="syntax"></a>Syntax

```cpp
typedef value_type% const_reference;
```

### <a name="remarks"></a>Açıklamalar

Türü bir öğeye sabit bir başvuru tanımlar.

### <a name="example"></a>Örnek

```cpp
// cliext_hash_set_const_reference.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_set<wchar_t> Myhash_set;
int main()
    {
    Myhash_set c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    Myhash_set::const_iterator cit = c1.begin();
    for (; cit != c1.end(); ++cit)
        {   // get a const reference to an element
        Myhash_set::const_reference cref = *cit;
        System::Console::Write("{0} ", cref);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="hash_setconst_reverse_iterator-stlclr"></a><a name="const_reverse_iterator"></a> hash_set:: const_reverse_iterator (STL/CLR)

Denetlenen sıra için bir sabit ters yineleyicinin türü..

### <a name="syntax"></a>Syntax

```cpp
typedef T4 const_reverse_iterator;
```

### <a name="remarks"></a>Açıklamalar

Türü, `T4` denetimli sıra için sabit bir ters Yineleyici işlevi görebilecek belirtilmemiş türdeki bir nesneyi tanımlar.

### <a name="example"></a>Örnek

```cpp
// cliext_hash_set_const_reverse_iterator.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_set<wchar_t> Myhash_set;
int main()
    {
    Myhash_set c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display contents " a b c" reversed
    Myhash_set::const_reverse_iterator crit = c1.rbegin();
    for (; crit != c1.rend(); ++crit)
        System::Console::Write("{0} ", *crit);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
c b a
```

## <a name="hash_setcount-stlclr"></a><a name="count"></a> hash_set:: Count (STL/CLR)

Belirtilen bir anahtar ile eşleşen öğe sayısını bulur.

### <a name="syntax"></a>Söz dizimi

```cpp
size_type count(key_type key);
```

#### <a name="parameters"></a>Parametreler

*anahtar*<br/>
Aranacak anahtar değer.

### <a name="remarks"></a>Açıklamalar

Member işlevi, *anahtar*ile eşdeğer sıralamaya sahip olan denetimli dizideki öğe sayısını döndürür. Belirtilen bir anahtarla eşleşen denetimli dizide bulunan öğe sayısını öğrenmek için bunu kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// cliext_hash_set_count.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_set<wchar_t> Myhash_set;
int main()
    {
    Myhash_set c1;
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

## <a name="hash_setdifference_type-stlclr"></a><a name="difference_type"></a> hash_set::d ifference_type (STL/CLR)

İki öğe arasındaki işaretli bir mesafe türü.

### <a name="syntax"></a>Syntax

```cpp
typedef int difference_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, büyük olasılıkla negatif bir öğe sayısını tanımlar.

### <a name="example"></a>Örnek

```cpp
// cliext_hash_set_difference_type.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_set<wchar_t> Myhash_set;
int main()
    {
    Myhash_set c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // compute positive difference
    Myhash_set::difference_type diff = 0;
    for (Myhash_set::iterator it = c1.begin(); it != c1.end(); ++it)
        ++diff;
    System::Console::WriteLine("end()-begin() = {0}", diff);

    // compute negative difference
    diff = 0;
    for (Myhash_set::iterator it = c1.end(); it != c1.begin(); --it)
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

## <a name="hash_setempty-stlclr"></a><a name="empty"></a> hash_set:: Empty (STL/CLR)

Bir öğe olup olmadığını sınar.

### <a name="syntax"></a>Syntax

```cpp
bool empty();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi boş bir denetlenen dizi için true döndürür. [Hash_set:: size (STL/CLR)](../dotnet/hash-set-size-stl-clr.md)eşdeğerdir `() == 0` . Hash_set boş olup olmadığını test etmek için kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// cliext_hash_set_empty.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_set<wchar_t> Myhash_set;
int main()
    {
    Myhash_set c1;
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

## <a name="hash_setend-stlclr"></a><a name="end"></a> hash_set:: End (STL/CLR)

Denetlenen dizinin bitişini belirtir.

### <a name="syntax"></a>Syntax

```cpp
iterator end();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, denetimli dizinin sonunun hemen ötesinde işaret eden çift yönlü bir yineleyici döndürür. Denetlenen dizinin sonunu atayan bir yineleyici elde etmek için bunu kullanırsınız; denetlenen sıranın uzunluğu değişirse, durumu değişmez.

### <a name="example"></a>Örnek

```cpp
// cliext_hash_set_end.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_set<wchar_t> Myhash_set;
int main()
    {
    Myhash_set c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // inspect last two items
    Myhash_set::iterator it = c1.end();
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

## <a name="hash_setequal_range-stlclr"></a><a name="equal_range"></a> hash_set:: equal_range (STL/CLR)

Belirtilen bir anahtarla eşleşen aralığı bulur.

### <a name="syntax"></a>Söz dizimi

```cpp
cliext::pair<iterator, iterator> equal_range(key_type key);
```

#### <a name="parameters"></a>Parametreler

*anahtar*<br/>
Aranacak anahtar değer.

### <a name="remarks"></a>Açıklamalar

Üye işlevi yineleyicilerin bir çiftini döndürür `cliext::pair<iterator, iterator>(` [hash_set:: lower_bound (STL/CLR)](../dotnet/hash-set-lower-bound-stl-clr.md) `(key),` [hash_set:: upper_bound (STL/CLR)](../dotnet/hash-set-upper-bound-stl-clr.md) `(key))` . Belirli bir anahtarla eşleşen denetimli dizide bulunan öğe aralığını öğrenmek için bunu kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// cliext_hash_set_equal_range.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_set<wchar_t> Myhash_set;
typedef Myhash_set::pair_iter_iter Pairii;
int main()
    {
    Myhash_set c1;
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

## <a name="hash_seterase-stlclr"></a><a name="erase"></a> hash_set:: Erase (STL/CLR)

Belirtilen konumlardaki öğeleri kaldırır.

### <a name="syntax"></a>Söz dizimi

```cpp
iterator erase(iterator where);
iterator erase(iterator first, iterator last);
bool erase(key_type key)
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

İlk üye *işlevi, öğesinin*işaret ettiği denetlenen sıranın öğesini kaldırır ve kaldırılan öğenin ötesinde ilk öğeyi atayan bir yineleyici döndürür ya da böyle bir öğe yoksa [hash_set:: End (STL/CLR)](../dotnet/hash-set-end-stl-clr.md) `()` . Tek bir öğeyi kaldırmak için bunu kullanırsınız.

İkinci üye işlevi, [,) aralığındaki denetimli sıranın öğelerini kaldırır `first` `last` ve kaldırılan tüm öğelerin ötesinde kalan ilk öğeyi veya böyle bir öğe yoksa bir yineleyici döndürür `end()` . Sıfır veya daha fazla bitişik öğeyi kaldırmak için bunu kullanırsınız.

Üçüncü üye işlevi, anahtarı *anahtara*denk sıralama değerine sahip denetimli dizinin herhangi bir öğesini kaldırır ve kaldırılan öğe sayısının sayısını döndürür. Bu anahtarı, belirtilen bir anahtarla eşleşen tüm öğeleri kaldırmak ve saymak için kullanırsınız.

Her bir öğe, denetlenen dizideki öğelerin sayısının logaritması ile orantılı bir zaman alır.

### <a name="example"></a>Örnek

```cpp
// cliext_hash_set_erase.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_set<wchar_t> Myhash_set;
int main()
    {
    Myhash_set c1;
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
    Myhash_set::iterator it = c1.end();
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

## <a name="hash_setfind-stlclr"></a><a name="find"></a> hash_set:: Find (STL/CLR)

Belirtilen bir anahtarla eşleşen bir öğeyi bulur.

### <a name="syntax"></a>Söz dizimi

```cpp
iterator find(key_type key);
```

#### <a name="parameters"></a>Parametreler

*anahtar*<br/>
Aranacak anahtar değer.

### <a name="remarks"></a>Açıklamalar

Denetlenen dizide en az bir öğe *anahtar*ile eşdeğer sıralamaya sahipse, üye işlevi bu öğelerden birini tanımlayarak bir yineleyici döndürür; Aksi takdirde [hash_set:: End (STL/CLR)](../dotnet/hash-set-end-stl-clr.md)döndürür `()` . Belirtilen bir anahtarla eşleşen denetimli dizide bulunan bir öğeyi bulmak için bunu kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// cliext_hash_set_find.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_set<wchar_t> Myhash_set;
int main()
    {
    Myhash_set c1;
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

## <a name="hash_setgeneric_container-stlclr"></a><a name="generic_container"></a> hash_set:: generic_container (STL/CLR)

Kapsayıcının genel arabiriminin türü.

### <a name="syntax"></a>Syntax

```cpp
typedef Microsoft::VisualC::StlClr::
    IHash<GKey, GValue>
    generic_container;
```

### <a name="remarks"></a>Açıklamalar

Tür, bu şablon kapsayıcı sınıfı için genel arabirimi tanımlar.

### <a name="example"></a>Örnek

```cpp
// cliext_hash_set_generic_container.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_set<wchar_t> Myhash_set;
int main()
    {
    Myhash_set c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct a generic container
    Myhash_set::generic_container^ gc1 = %c1;
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

## <a name="hash_setgeneric_iterator-stlclr"></a><a name="generic_iterator"></a> hash_set:: generic_iterator (STL/CLR)

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
// cliext_hash_set_generic_iterator.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_set<wchar_t> Myhash_set;
int main()
    {
    Myhash_set c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct a generic container
    Myhash_set::generic_container^ gc1 = %c1;
    for each (wchar_t elem in gc1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // get an element and display it
    Myhash_set::generic_iterator gcit = gc1->begin();
    Myhash_set::generic_value gcval = *gcit;
    System::Console::WriteLine("{0} ", gcval);
    return (0);
    }
```

```Output
a b c
a b c
a
```

## <a name="hash_setgeneric_reverse_iterator-stlclr"></a><a name="generic_reverse_iterator"></a> hash_set:: generic_reverse_iterator (STL/CLR)

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
// cliext_hash_set_generic_reverse_iterator.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_set<wchar_t> Myhash_set;
int main()
    {
    Myhash_set c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct a generic container
    Myhash_set::generic_container^ gc1 = %c1;
    for each (wchar_t elem in gc1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // get an element and display it
    Myhash_set::generic_reverse_iterator gcit = gc1->rbegin();
    Myhash_set::generic_value gcval = *gcit;
    System::Console::WriteLine("{0} ", gcval);
    return (0);
    }
```

```Output
a b c
a b c
c
```

## <a name="hash_setgeneric_value-stlclr"></a><a name="generic_value"></a> hash_set:: generic_value (STL/CLR)

Kapsayıcının genel arabirimiyle kullanılacak öğe türü.

### <a name="syntax"></a>Syntax

```cpp
typedef GValue generic_value;
```

### <a name="remarks"></a>Açıklamalar

Tür, `GValue` Bu şablon kapsayıcı sınıfı için genel arabirimle birlikte kullanılacak saklı öğe değerini açıklayan türünde bir nesne tanımlar.

### <a name="example"></a>Örnek

```cpp
// cliext_hash_set_generic_value.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_set<wchar_t> Myhash_set;
int main()
    {
    Myhash_set c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct a generic container
    Myhash_set::generic_container^ gc1 = %c1;
    for each (wchar_t elem in gc1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // get an element and display it
    Myhash_set::generic_iterator gcit = gc1->begin();
    Myhash_set::generic_value gcval = *gcit;
    System::Console::WriteLine("{0} ", gcval);
    return (0);
    }
```

```Output
a b c
a b c
a
```

## <a name="hash_sethash_delegate-stlclr"></a><a name="hash_delegate"></a> hash_set:: hash_delegate (STL/CLR)

Belirtilen bir anahtarla eşleşen bir öğeyi bulur.

### <a name="syntax"></a>Syntax

```cpp
hasher^ hash_delegate();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi bir anahtar değerini bir tamsayıya dönüştürmek için kullanılan temsilciyi döndürür. Bir anahtarı karma hale almak için kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// cliext_hash_set_hash_delegate.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_set<wchar_t> Myhash_set;
int main()
    {
    Myhash_set c1;
    Myhash_set::hasher^ myhash = c1.hash_delegate();

    System::Console::WriteLine("hash(L'a') = {0}", myhash(L'a'));
    System::Console::WriteLine("hash(L'b') = {0}", myhash(L'b'));
    return (0);
    }
```

```Output
hash(L'a') = 1616896120
hash(L'b') = 570892832
```

## <a name="hash_sethash_set-stlclr"></a><a name="hash_set"></a> hash_set:: hash_set (STL/CLR)

Bir kapsayıcı nesnesi oluşturur.

### <a name="syntax"></a>Söz dizimi

```cpp
hash_set();
explicit hash_set(key_compare^ pred);
hash_set(key_compare^ pred, hasher^ hashfn);
hash_set(hash_set<Key>% right);
hash_set(hash_set<Key>^ right);
template<typename InIter>
    hash_sethash_set(InIter first, InIter last);
template<typename InIter>
    hash_set(InIter first, InIter last,
        key_compare^ pred);
template<typename InIter>
    hash_set(InIter first, InIter last,
        key_compare^ pred, hasher^ hashfn);
hash_set(System::Collections::Generic::IEnumerable<GValue>^ right);
hash_set(System::Collections::Generic::IEnumerable<GValue>^ right,
    key_compare^ pred);
hash_set(System::Collections::Generic::IEnumerable<GValue>^ right,
    key_compare^ pred, hasher^ hashfn);
```

#### <a name="parameters"></a>Parametreler

*adı*<br/>
Eklenecek aralığın başlangıcı.

*diyez FN*<br/>
Anahtarları demetlere eşlemek için karma işlev.

*soyadına*<br/>
Eklenecek aralığın sonu.

*pred*<br/>
Denetlenen sıra için sıralama koşulu.

*Right*<br/>
Eklenecek nesne veya Aralık.

### <a name="remarks"></a>Açıklamalar

Oluşturucu:

`hash_set();`

denetlenen sırayı, varsayılan sıralama koşulu `key_compare()` ve varsayılan karma işlevi ile hiçbir öğe olmadan başlatır. Varsayılan sıralama koşulu ve karma işlevi ile boş bir ilk denetimli sıra belirtmek için bunu kullanırsınız.

Oluşturucu:

`explicit hash_set(key_compare^ pred);`

denetlenen sırayı, sıralama koşulu *Pred*ve varsayılan karma işlevi ile hiçbir öğe olmadan başlatır. Bu işlemi, belirtilen sıralama koşulu ve varsayılan karma işlevi ile birlikte boş bir ilk denetimli sıra belirtmek için kullanırsınız.

Oluşturucu:

`hash_set(key_compare^ pred, hasher^ hashfn);`

denetlenen sırayı, sıralama koşulu *Pred*ile ve *hashfn*karma işlevi ile birlikte hiçbir öğe olmadan başlatır. Belirtilen sıralama koşulu ve karma işleviyle birlikte boş bir ilk denetimli sıra belirtmek için bunu kullanırsınız.

Oluşturucu:

`hash_set(hash_set<Key>% right);`

denetlenen sırayı, `right.begin()` `right.end()` varsayılan sıralama koşulu ile ve varsayılan karma işlevle birlikte [,) sırasıyla başlatır. Bu, varsayılan sıralama koşulu ve karma işlevi ile *hash_set nesnesi tarafından*denetlenen sıranın bir kopyası olan bir ilk denetimli sıra belirtmek için kullanılır.

Oluşturucu:

`hash_set(hash_set<Key>^ right);`

denetlenen sırayı, `right->begin()` `right->end()` varsayılan sıralama koşulu ile ve varsayılan karma işlevle birlikte [,) sırasıyla başlatır. Bu, varsayılan sıralama koşulu ve karma işlevi ile *hash_set nesnesi tarafından*denetlenen sıranın bir kopyası olan bir ilk denetimli sıra belirtmek için kullanılır.

Oluşturucu:

`template<typename InIter> hash_set(InIter first, InIter last);`

denetlenen sırayı, `first` `last` varsayılan sıralama koşulu ile ve varsayılan karma işlevle birlikte [,) sırasıyla başlatır. Varsayılan sıralama koşulu ve karma işlevi ile, denetimli diziyi başka bir dizinin bir kopyası yapmak için kullanabilirsiniz.

Oluşturucu:

`template<typename InIter> hash_set(InIter first, InIter last, key_compare^ pred);`

[,) sırası ile denetimli sırayı, `first` `last` sıralama koşulu *Pred*ve varsayılan karma işlevi ile başlatır. Bu işlemi, denetimli diziyi, belirtilen sıralama koşulu ve varsayılan karma işlevi ile başka bir dizinin bir kopyası yapmak için kullanırsınız.

Oluşturucu:

`template<typename InIter> hash_set(InIter first, InIter last, key_compare^ pred, hasher^ hashfn);`

[,) sırası ile denetimli sırayı, `first` `last` sıralama koşulu *Pred*ile ve *hashfn*karma işlevi ile başlatır. Belirtilen sıralama koşulu ve karma işlevi ile, denetimli diziyi başka bir dizinin bir kopyası yapmak için kullanabilirsiniz.

Oluşturucu:

`hash_set(System::Collections::Generic::IEnumerable<Key>^ right);`

denetlenen sırayı, varsayılan sıralama koşulu ile ve varsayılan karma işlevle birlikte Numaralandırıcı *hakkı*tarafından belirlenen sırayla başlatır. Denetim, varsayılan sıralama koşulu ve karma işlevi ile, bir Numaralandırıcı tarafından tanımlanan başka bir dizinin kopyasını oluşturmak için kullanılır.

Oluşturucu:

`hash_set(System::Collections::Generic::IEnumerable<Key>^ right, key_compare^ pred);`

denetlenen diziyi, Numaralandırıcı *hakkı*ile, sıralama koşulu *Pred*ve varsayılan karma işlevi ile belirlenen sırayla başlatır. Denetim, belirtilen sıralama koşulu ve varsayılan karma işlevi ile bir Numaralandırıcı tarafından tanımlanan başka bir dizinin kopyasını oluşturmak için kullanılır.

Oluşturucu:

`hash_set(System::Collections::Generic::IEnumerable<Key>^ right, key_compare^ pred, hasher^ hashfn);`

denetlenen diziyi, Numaralandırıcı *hakkı*ile, sıralama koşulu *Pred*ve *diyez FN*karma işlevi ile belirlenen sırayla başlatır. Denetim, belirtilen sıralama koşulu ve karma işlevi ile bir Numaralandırıcı tarafından tanımlanan başka bir dizinin kopyasını oluşturmak için kullanılır.

### <a name="example"></a>Örnek

```cpp
// cliext_hash_set_construct.cpp
// compile with: /clr
#include <cliext/hash_set>

int myfun(wchar_t key)
    { // hash a key
    return (key ^ 0xdeadbeef);
    }

typedef cliext::hash_set<wchar_t> Myhash_set;
int main()
    {
// construct an empty container
    Myhash_set c1;
    System::Console::WriteLine("size() = {0}", c1.size());

    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct with an ordering rule
    Myhash_set c2 = cliext::greater_equal<wchar_t>();
    System::Console::WriteLine("size() = {0}", c2.size());

    c2.insert(c1.begin(), c1.end());
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct with an ordering rule and hash function
    Myhash_set c2h(cliext::greater_equal<wchar_t>(),
        gcnew Myhash_set::hasher(&myfun));
    System::Console::WriteLine("size() = {0}", c2h.size());

    c2h.insert(c1.begin(), c1.end());
    for each (wchar_t elem in c2h)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    System::Console::WriteLine();

    // construct with an iterator range
    Myhash_set c3(c1.begin(), c1.end());
    for each (wchar_t elem in c3)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct with an iterator range and an ordering rule
    Myhash_set c4(c1.begin(), c1.end(),
        cliext::greater_equal<wchar_t>());
    for each (wchar_t elem in c4)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct with an iterator range and an ordering rule and hash function
    Myhash_set c4h(c1.begin(), c1.end(),
        cliext::greater_equal<wchar_t>(),
        gcnew Myhash_set::hasher(&myfun));
    for each (wchar_t elem in c4h)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    System::Console::WriteLine();

    // construct with an enumeration
    Myhash_set c5(   // NOTE: cast is not needed
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c3);
    for each (wchar_t elem in c5)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct with an enumeration and an ordering rule
    Myhash_set c6(   // NOTE: cast is not needed
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c3,
            cliext::greater_equal<wchar_t>());
    for each (wchar_t elem in c6)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct with an enumeration and an ordering rule and hash function
    Myhash_set c6h(   // NOTE: cast is not needed
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c3,
            cliext::greater_equal<wchar_t>(),
                gcnew Myhash_set::hasher(&myfun));
    for each (wchar_t elem in c6h)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    System::Console::WriteLine();

    // construct from a generic container
    Myhash_set c7(c4);
    for each (wchar_t elem in c7)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct by copying another container
    Myhash_set c8(%c3);
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
a b c
size() = 0
c b a

a b c
a b c
c b a

a b c
a b c
c b a

a b c
a b c
```

## <a name="hash_sethasher-stlclr"></a><a name="hasher"></a> hash_set:: hasher (STL/CLR)

Bir anahtar için karma temsilcisi.

### <a name="syntax"></a>Syntax

```cpp
Microsoft::VisualC::StlClr::UnaryDelegate<GKey, int>
    hasher;
```

### <a name="remarks"></a>Açıklamalar

Türü bir anahtar değerini bir tamsayıya dönüştüren bir temsilciyi tanımlar.

### <a name="example"></a>Örnek

```cpp
// cliext_hash_set_hasher.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_set<wchar_t> Myhash_set;
int main()
    {
    Myhash_set c1;
    Myhash_set::hasher^ myhash = c1.hash_delegate();

    System::Console::WriteLine("hash(L'a') = {0}", myhash(L'a'));
    System::Console::WriteLine("hash(L'b') = {0}", myhash(L'b'));
    return (0);
    }
```

```Output
hash(L'a') = 1616896120
hash(L'b') = 570892832
```

## <a name="hash_setinsert-stlclr"></a><a name="insert"></a> hash_set:: Insert (STL/CLR)

Öğeleri ekler.

### <a name="syntax"></a>Söz dizimi

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

İkinci üye işlevi, bir ipucu olarak *WHERE* (performansı artırmak için) ve yeni eklenen öğeyi atayan bir yineleyici döndüren bir *değer değeri olan*bir öğe ekler. Bildiğiniz bir öğeye bitişik olabilecek tek bir öğe eklemek için bunu kullanırsınız.

Üçüncü üye işlevi [,) dizisini ekler `first` `last` . Başka bir dizide kopyalanmış sıfır veya daha fazla öğe eklemek için bunu kullanırsınız.

Dördüncü üye işlevi, *sağ*tarafından belirlenen diziyi ekler. Bir Numaralandırıcı tarafından tanımlanan bir sıra eklemek için bunu kullanırsınız.

Her öğe ekleme, denetlenen dizideki öğelerin sayısının logaritması ile orantılı bir zaman alır. Ekleme noktası, ekleme noktasına bitişik bir öğe atayan bir ipucu verildiğinde, sabit zamanlı olarak ekleme yapılabilir.

### <a name="example"></a>Örnek

```cpp
// cliext_hash_set_insert.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_set<wchar_t> Myhash_set;
typedef Myhash_set::pair_iter_bool Pairib;
int main()
    {
    Myhash_set c1;
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
    Myhash_set c2;
    Myhash_set::iterator it = c1.end();
    c2.insert(c1.begin(), --it);
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // insert an enumeration
    Myhash_set c3;
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

## <a name="hash_setiterator-stlclr"></a><a name="iterator"></a> hash_set:: yineleyici (STL/CLR)

Denetlenen dizi için bir yineleyici türü.

### <a name="syntax"></a>Syntax

```cpp
typedef T1 iterator;
```

### <a name="remarks"></a>Açıklamalar

Türü, `T1` denetimli sıra için çift yönlü bir yineleyici olarak kullanılabilecek belirtilmemiş türdeki bir nesneyi tanımlar.

### <a name="example"></a>Örnek

```cpp
// cliext_hash_set_iterator.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_set<wchar_t> Myhash_set;
int main()
    {
    Myhash_set c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display contents " a b c"
    Myhash_set::iterator it = c1.begin();
    for (; it != c1.end(); ++it)
        System::Console::Write("{0} ", *it);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="hash_setkey_comp-stlclr"></a><a name="key_comp"></a> hash_set:: key_comp (STL/CLR)

Sıralama temsilcisini iki anahtar için kopyalar.

### <a name="syntax"></a>Syntax

```cpp
key_compare^key_comp();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, denetimli sırayı sıralamak için kullanılan sıralama temsilcisini döndürür. İki anahtarı karşılaştırmak için bunu kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// cliext_hash_set_key_comp.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_set<wchar_t> Myhash_set;
int main()
    {
    Myhash_set c1;
    Myhash_set::key_compare^ kcomp = c1.key_comp();

    System::Console::WriteLine("compare(L'a', L'a') = {0}",
        kcomp(L'a', L'a'));
    System::Console::WriteLine("compare(L'a', L'b') = {0}",
        kcomp(L'a', L'b'));
    System::Console::WriteLine("compare(L'b', L'a') = {0}",
        kcomp(L'b', L'a'));
    System::Console::WriteLine();

    // test a different ordering rule
    Myhash_set c2 = cliext::greater<wchar_t>();
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
compare(L'a', L'a') = True
compare(L'a', L'b') = True
compare(L'b', L'a') = False

compare(L'a', L'a') = False
compare(L'a', L'b') = False
compare(L'b', L'a') = True
```

## <a name="hash_setkey_compare-stlclr"></a><a name="key_compare"></a> hash_set:: key_compare (STL/CLR)

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
// cliext_hash_set_key_compare.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_set<wchar_t> Myhash_set;
int main()
    {
    Myhash_set c1;
    Myhash_set::key_compare^ kcomp = c1.key_comp();

    System::Console::WriteLine("compare(L'a', L'a') = {0}",
        kcomp(L'a', L'a'));
    System::Console::WriteLine("compare(L'a', L'b') = {0}",
        kcomp(L'a', L'b'));
    System::Console::WriteLine("compare(L'b', L'a') = {0}",
        kcomp(L'b', L'a'));
    System::Console::WriteLine();

    // test a different ordering rule
    Myhash_set c2 = cliext::greater<wchar_t>();
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
compare(L'a', L'a') = True
compare(L'a', L'b') = True
compare(L'b', L'a') = False

compare(L'a', L'a') = False
compare(L'a', L'b') = False
compare(L'b', L'a') = True
```

## <a name="hash_setkey_type-stlclr"></a><a name="key_type"></a> hash_set:: key_type (STL/CLR)

Bir sıralama anahtarının türü.

### <a name="syntax"></a>Syntax

```cpp
typedef Key key_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, şablon parametre *anahtarı*için bir eş anlamlı.

### <a name="example"></a>Örnek

```cpp
// cliext_hash_set_key_type.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_set<wchar_t> Myhash_set;
int main()
    {
    Myhash_set c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display contents " a b c" using key_type
    for (Myhash_set::iterator it = c1.begin(); it != c1.end(); ++it)
        {   // store element in key_type object
        Myhash_set::key_type val = *it;

        System::Console::Write("{0} ", val);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="hash_setload_factor-stlclr"></a><a name="load_factor"></a> hash_set:: load_factor (STL/CLR)

Demet başına ortalama öğeyi sayar.

### <a name="syntax"></a>Syntax

```cpp
float load_factor();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi `(float)` [hash_set:: size (STL/CLR)](../dotnet/hash-set-size-stl-clr.md) `() /` [hash_set:: bucket_count (STL/CLR)](../dotnet/hash-set-bucket-count-stl-clr.md)döndürür `()` . Bu, ortalama demet boyutunu bulmak için kullanılır.

### <a name="example"></a>Örnek

```cpp
// cliext_hash_set_load_factor.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_set<wchar_t> Myhash_set;
int main()
    {
    Myhash_set c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // inspect current parameters
    System::Console::WriteLine("bucket_count() = {0}", c1.bucket_count());
    System::Console::WriteLine("load_factor() = {0}", c1.load_factor());
    System::Console::WriteLine("max_load_factor() = {0}",
        c1.max_load_factor());
    System::Console::WriteLine();

    // change max_load_factor and redisplay
    c1.max_load_factor(0.25f);
    System::Console::WriteLine("bucket_count() = {0}", c1.bucket_count());
    System::Console::WriteLine("load_factor() = {0}", c1.load_factor());
    System::Console::WriteLine("max_load_factor() = {0}",
        c1.max_load_factor());
    System::Console::WriteLine();

    // rehash and redisplay
    c1.rehash(100);
    System::Console::WriteLine("bucket_count() = {0}", c1.bucket_count());
    System::Console::WriteLine("load_factor() = {0}", c1.load_factor());
    System::Console::WriteLine("max_load_factor() = {0}",
        c1.max_load_factor());
    return (0);
    }
```

```Output
a b c
bucket_count() = 16
load_factor() = 0.1875
max_load_factor() = 4

bucket_count() = 16
load_factor() = 0.1875
max_load_factor() = 0.25

bucket_count() = 128
load_factor() = 0.0234375
max_load_factor() = 0.25
```

## <a name="hash_setlower_bound-stlclr"></a><a name="lower_bound"></a> hash_set:: lower_bound (STL/CLR)

Belirtilen anahtarla eşleşen aralığın başlangıcını bulur.

### <a name="syntax"></a>Söz dizimi

```cpp
iterator lower_bound(key_type key);
```

#### <a name="parameters"></a>Parametreler

*anahtar*<br/>
Aranacak anahtar değer.

### <a name="remarks"></a>Açıklamalar

Üye işlevi, denetimli dizideki ilk öğeyi, `X` *anahtar* ile aynı demetini karma hale getirir ve *anahtara*eşdeğer sıralama içerir. Böyle bir öğe yoksa [hash_set:: End (STL/CLR)](../dotnet/hash-set-end-stl-clr.md)döndürür `()` ; Aksi takdirde, öğesini atayan bir yineleyici döndürür `X` . Belirtilen bir anahtarla eşleşen, denetlenen dizide bulunan bir öğe dizisinin başlangıcını bulmak için bunu kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// cliext_hash_set_lower_bound.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_set<wchar_t> Myhash_set;
int main()
    {
    Myhash_set c1;
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

## <a name="hash_setmake_value-stlclr"></a><a name="make_value"></a> hash_set:: make_value (STL/CLR)

Değer nesnesi oluşturur.

### <a name="syntax"></a>Söz dizimi

```cpp
static value_type make_value(key_type key);
```

#### <a name="parameters"></a>Parametreler

*anahtar*<br/>
Kullanılacak anahtar değer.

### <a name="remarks"></a>Açıklamalar

Üye işlevi, `value_type` anahtarı *anahtar*olan bir nesne döndürür. Diğer birçok üye işlevi ile kullanmak üzere uygun bir nesne oluşturmak için bunu kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// cliext_hash_set_make_value.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_set<wchar_t> Myhash_set;
int main()
    {
    Myhash_set c1;
    c1.insert(Myhash_set::make_value(L'a'));
    c1.insert(Myhash_set::make_value(L'b'));
    c1.insert(Myhash_set::make_value(L'c'));

    // display contents " a b c"
    for each (Myhash_set::value_type elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="hash_setmax_load_factor-stlclr"></a><a name="max_load_factor"></a> hash_set:: max_load_factor (STL/CLR)

Demet başına en yüksek öğe sayısını alır veya ayarlar.

### <a name="syntax"></a>Söz dizimi

```cpp
float max_load_factor();
void max_load_factor(float new_factor);
```

#### <a name="parameters"></a>Parametreler

*new_factor*<br/>
Depolanacak yeni en fazla yük faktörü.

### <a name="remarks"></a>Açıklamalar

İlk üye işlevi, geçerli saklı maksimum yük faktörünü döndürür. En büyük ortalama demet boyutunu bulmak için bunu kullanırsınız.

İkinci üye işlevi, mağaza en fazla yük faktörünü *new_factor*ile değiştirir. Sonraki bir ekleme yapılıncaya kadar otomatik yeniden karma gerçekleşmez.

### <a name="example"></a>Örnek

```cpp
// cliext_hash_set_max_load_factor.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_set<wchar_t> Myhash_set;
int main()
    {
    Myhash_set c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // inspect current parameters
    System::Console::WriteLine("bucket_count() = {0}", c1.bucket_count());
    System::Console::WriteLine("load_factor() = {0}", c1.load_factor());
    System::Console::WriteLine("max_load_factor() = {0}",
        c1.max_load_factor());
    System::Console::WriteLine();

    // change max_load_factor and redisplay
    c1.max_load_factor(0.25f);
    System::Console::WriteLine("bucket_count() = {0}", c1.bucket_count());
    System::Console::WriteLine("load_factor() = {0}", c1.load_factor());
    System::Console::WriteLine("max_load_factor() = {0}",
        c1.max_load_factor());
    System::Console::WriteLine();

    // rehash and redisplay
    c1.rehash(100);
    System::Console::WriteLine("bucket_count() = {0}", c1.bucket_count());
    System::Console::WriteLine("load_factor() = {0}", c1.load_factor());
    System::Console::WriteLine("max_load_factor() = {0}",
        c1.max_load_factor());
    return (0);
    }
```

## <a name="hash_setoperator-stlclr"></a><a name="op"></a> hash_set:: operator = (STL/CLR)

Denetlenen sırayı değiştirir.

### <a name="syntax"></a>Söz dizimi

```cpp
hash_set<Key>% operator=(hash_set<Key>% right);
```

#### <a name="parameters"></a>Parametreler

*Right*<br/>
Kopyalanacak kapsayıcı.

### <a name="remarks"></a>Açıklamalar

Üye işleci nesnesine *sağ* kopyalar ve ardından döndürür **`*this`** . Denetlenen diziyi, denetimli sıranın bir kopyasıyla değiştirmek için bunu *kullanırsınız.*

### <a name="example"></a>Örnek

```cpp
// cliext_hash_set_operator_as.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_set<wchar_t> Myhash_set;
int main()
    {
    Myhash_set c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display contents " a b c"
    for each (Myhash_set::value_type elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // assign to a new container
    Myhash_set c2;
    c2 = c1;
// display contents " a b c"
    for each (Myhash_set::value_type elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
a b c
```

## <a name="hash_setrbegin-stlclr"></a><a name="rbegin"></a> hash_set:: rbegin (STL/CLR)

Ters denetlenen sıranın başlangıcını belirtir.

### <a name="syntax"></a>Syntax

```cpp
reverse_iterator rbegin();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, denetimli sıranın son öğesini veya boş bir dizinin başlangıcının ötesinde bir ters yineleyici döndürür. Bu nedenle, `beginning` ters sıranın öğesini belirler. Doğru sırada görülen denetimli sıranın başlangıcını atayan bir yineleyici elde etmek için bunu kullanırsınız `current` , ancak denetlenen sıranın uzunluğu değişirse durum değişebilir.

### <a name="example"></a>Örnek

```cpp
// cliext_hash_set_rbegin.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_set<wchar_t> Myhash_set;
int main()
    {
    Myhash_set c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // inspect first two items in reversed sequence
    Myhash_set::reverse_iterator rit = c1.rbegin();
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

## <a name="hash_setreference-stlclr"></a><a name="reference"></a> hash_set:: Reference (STL/CLR)

Bir öğe için bir başvuru türü.

### <a name="syntax"></a>Syntax

```cpp
typedef value_type% reference;
```

### <a name="remarks"></a>Açıklamalar

Türü bir öğesi başvurusunu tanımlar.

### <a name="example"></a>Örnek

```cpp
// cliext_hash_set_reference.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_set<wchar_t> Myhash_set;
int main()
    {
    Myhash_set c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    Myhash_set::iterator it = c1.begin();
    for (; it != c1.end(); ++it)
        {   // get a reference to an element
        Myhash_set::reference ref = *it;
        System::Console::Write("{0} ", ref);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="hash_setrehash-stlclr"></a><a name="rehash"></a> hash_set:: rehash (STL/CLR)

Karma tabloyu yeniden oluşturur.

### <a name="syntax"></a>Syntax

```cpp
void rehash();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi karma tabloyu yeniden oluşturur ve [hash_set:: load_factor (STL/CLR)](../dotnet/hash-set-load-factor-stl-clr.md) `() <=` [hash_set:: max_load_factor (STL/CLR)](../dotnet/hash-set-max-load-factor-stl-clr.md). Aksi takdirde, karma tablo, bir ekleme işleminden sonra gerektiğinde yalnızca boyut artar. (Boyut olarak hiçbir şekilde azalmayın.) Karma tablonun boyutunu ayarlamak için bunu kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// cliext_hash_set_rehash.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_set<wchar_t> Myhash_set;
int main()
    {
    Myhash_set c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // inspect current parameters
    System::Console::WriteLine("bucket_count() = {0}", c1.bucket_count());
    System::Console::WriteLine("load_factor() = {0}", c1.load_factor());
    System::Console::WriteLine("max_load_factor() = {0}",
        c1.max_load_factor());
    System::Console::WriteLine();

    // change max_load_factor and redisplay
    c1.max_load_factor(0.25f);
    System::Console::WriteLine("bucket_count() = {0}", c1.bucket_count());
    System::Console::WriteLine("load_factor() = {0}", c1.load_factor());
    System::Console::WriteLine("max_load_factor() = {0}",
        c1.max_load_factor());
    System::Console::WriteLine();

    // rehash and redisplay
    c1.rehash(100);
    System::Console::WriteLine("bucket_count() = {0}", c1.bucket_count());
    System::Console::WriteLine("load_factor() = {0}", c1.load_factor());
    System::Console::WriteLine("max_load_factor() = {0}",
        c1.max_load_factor());
    return (0);
    }
```

```Output
a b c
bucket_count() = 16
load_factor() = 0.1875
max_load_factor() = 4

bucket_count() = 16
load_factor() = 0.1875
max_load_factor() = 0.25

bucket_count() = 128
load_factor() = 0.0234375
max_load_factor() = 0.25
```

## <a name="hash_setrend-stlclr"></a><a name="rend"></a> hash_set:: rend (STL/CLR)

Ters denetlenen sıranın sonunu belirtir.

### <a name="syntax"></a>Syntax

```cpp
reverse_iterator rend();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, denetimli sıranın başlangıcının hemen ötesinde bir ters yineleyici döndürür. Bu nedenle, `end` ters sıranın öğesini belirler. Bu uygulamayı, `current` geriye doğru sırada görülen denetlenen sıranın sonunu atayan bir yineleyici elde etmek için kullanırsınız, ancak denetlenen sıranın uzunluğu değişirse durum değişebilir.

### <a name="example"></a>Örnek

```cpp
// cliext_hash_set_rend.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_set<wchar_t> Myhash_set;
int main()
    {
    Myhash_set c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // inspect first two items
    Myhash_set::reverse_iterator rit = c1.rend();
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

## <a name="hash_setreverse_iterator-stlclr"></a><a name="reverse_iterator"></a> hash_set:: reverse_iterator (STL/CLR)

Denetlenen sıra için ters yineleyicinin türü.

### <a name="syntax"></a>Syntax

```cpp
typedef T3 reverse_iterator;
```

### <a name="remarks"></a>Açıklamalar

Tür, `T3` denetlenen sıra için ters Yineleyici olarak işlev görebilecek belirtilmemiş türdeki bir nesneyi tanımlar.

### <a name="example"></a>Örnek

```cpp
// cliext_hash_set_reverse_iterator.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_set<wchar_t> Myhash_set;
int main()
    {
    Myhash_set c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display contents " a b c" reversed
    Myhash_set::reverse_iterator rit = c1.rbegin();
    for (; rit != c1.rend(); ++rit)
        System::Console::Write("{0} ", *rit);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
c b a
```

## <a name="hash_setsize-stlclr"></a><a name="size"></a> hash_set:: size (STL/CLR)

Öğe sayısını sayar.

### <a name="syntax"></a>Syntax

```cpp
size_type size();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi denetlenen sıranın uzunluğunu döndürür. Bu, şu anda denetlenen dizideki öğelerin sayısını tespit etmek için kullanılır. Her şey için, sıranın sıfır dışında bir boyut içerip içermediğini öğrenmek için bkz. [hash_set:: Empty (STL/CLR)](../dotnet/hash-set-empty-stl-clr.md) `()` .

### <a name="example"></a>Örnek

```cpp
// cliext_hash_set_size.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_set<wchar_t> Myhash_set;
int main()
    {
    Myhash_set c1;
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

## <a name="hash_setsize_type-stlclr"></a><a name="size_type"></a> hash_set:: size_type (STL/CLR)

İki öğe arasındaki işaretli bir mesafe türü.

### <a name="syntax"></a>Syntax

```cpp
typedef int size_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, negatif olmayan bir öğe sayısını tanımlar.

### <a name="example"></a>Örnek

```cpp
// cliext_hash_set_size_type.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_set<wchar_t> Myhash_set;
int main()
    {
    Myhash_set c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // compute positive difference
    Myhash_set::size_type diff = 0;
    for (Myhash_set::iterator it = c1.begin(); it != c1.end(); ++it)
        ++diff;
    System::Console::WriteLine("end()-begin() = {0}", diff);
    return (0);
    }
```

```Output
a b c
end()-begin() = 3
```

## <a name="hash_setswap-stlclr"></a><a name="swap"></a> hash_set:: swap (STL/CLR)

İki kapsayıcının içeriğinin yerini değiştirir.

### <a name="syntax"></a>Söz dizimi

```cpp
void swap(hash_set<Key>% right);
```

#### <a name="parameters"></a>Parametreler

*Right*<br/>
İçeriği takas eden kapsayıcı.

### <a name="remarks"></a>Açıklamalar

Üye işlevi, ve sağ arasındaki denetlenen dizileri **`this`** değiştirir *right*. Bu, sabit zamanlı olarak yapar ve özel durum oluşturmaz. Bunu iki kapsayıcının içeriğini değiş tokuş etmek için hızlı bir yol olarak kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// cliext_hash_set_swap.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_set<wchar_t> Myhash_set;
int main()
    {
    Myhash_set c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct another container with repetition of values
    Myhash_set c2;
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

## <a name="hash_setto_array-stlclr"></a><a name="to_array"></a> hash_set:: to_array (STL/CLR)

Denetimli sırayı yeni bir diziye kopyalar.

### <a name="syntax"></a>Syntax

```cpp
cli::array<value_type>^ to_array();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi denetlenen sırayı içeren bir dizi döndürür. Dizi biçiminde denetlenen sıranın bir kopyasını almak için bunu kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// cliext_hash_set_to_array.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_set<wchar_t> Myhash_set;
int main()
    {
    Myhash_set c1;
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

## <a name="hash_setupper_bound-stlclr"></a><a name="upper_bound"></a> hash_set:: upper_bound (STL/CLR)

Belirtilen anahtarla eşleşen aralığın sonunu bulur.

### <a name="syntax"></a>Söz dizimi

```cpp
iterator upper_bound(key_type key);
```

#### <a name="parameters"></a>Parametreler

*anahtar*<br/>
Aranacak anahtar değer.

### <a name="remarks"></a>Açıklamalar

Üye işlevi, denetimli dizideki son öğeyi, `X` *anahtar* ile aynı demetini karma hale getirir ve *anahtara*denk sıralama içerir. Böyle bir öğe yoksa veya `X` denetlenen dizideki son öğe ise [hash_set:: End (STL/CLR)](../dotnet/hash-set-end-stl-clr.md)döndürür `()` ; Aksi takdirde ilk öğeyi daha sonra atayan bir yineleyici döndürür `X` . Belirtilen bir anahtarla eşleşen denetimli dizide bulunan bir öğe dizisinin sonunu bulmak için bunu kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// cliext_hash_set_upper_bound.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_set<wchar_t> Myhash_set;
int main()
    {
    Myhash_set c1;
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

## <a name="hash_setvalue_comp-stlclr"></a><a name="value_comp"></a> hash_set:: value_comp (STL/CLR)

İki öğe değeri için sıralama temsilcisini kopyalar.

### <a name="syntax"></a>Syntax

```cpp
value_compare^ value_comp();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, denetimli sırayı sıralamak için kullanılan sıralama temsilcisini döndürür. İki öğe değerini karşılaştırmak için bunu kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// cliext_hash_set_value_comp.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_set<wchar_t> Myhash_set;
int main()
    {
    Myhash_set c1;
    Myhash_set::value_compare^ kcomp = c1.value_comp();

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
compare(L'a', L'a') = True
compare(L'a', L'b') = True
compare(L'b', L'a') = False
```

## <a name="hash_setvalue_compare-stlclr"></a><a name="value_compare"></a> hash_set:: value_compare (STL/CLR)

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
// cliext_hash_set_value_compare.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_set<wchar_t> Myhash_set;
int main()
    {
    Myhash_set c1;
    Myhash_set::value_compare^ kcomp = c1.value_comp();

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
compare(L'a', L'a') = True
compare(L'a', L'b') = True
compare(L'b', L'a') = False
```

## <a name="hash_setvalue_type-stlclr"></a><a name="value_type"></a> hash_set:: value_type (STL/CLR)

Öğenin türü.

### <a name="syntax"></a>Syntax

```cpp
typedef generic_value value_type;
```

### <a name="remarks"></a>Açıklamalar

Tür için bir eş anlamlı `generic_value` .

### <a name="example"></a>Örnek

```cpp
// cliext_hash_set_value_type.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_set<wchar_t> Myhash_set;
int main()
    {
    Myhash_set c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display contents " a b c" using value_type
    for (Myhash_set::iterator it = c1.begin(); it != c1.end(); ++it)
        {   // store element in value_type object
        Myhash_set::value_type val = *it;

        System::Console::Write("{0} ", val);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```
