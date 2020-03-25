---
title: eşle (STL/CLR)
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- cliext::map
- cliext::map::begin
- cliext::map::clear
- cliext::map::const_iterator
- cliext::map::const_reference
- cliext::map::const_reverse_iterator
- cliext::map::count
- cliext::map::difference_type
- cliext::map::empty
- cliext::map::end
- cliext::map::equal_range
- cliext::map::erase
- cliext::map::find
- cliext::map::generic_container
- cliext::map::generic_iterator
- cliext::map::generic_reverse_iterator
- cliext::map::generic_value
- cliext::map::insert
- cliext::map::iterator
- cliext::map::key_comp
- cliext::map::key_compare
- cliext::map::key_type
- cliext::map::lower_bound
- cliext::map::make_value
- cliext::map::map
- cliext::map::mapped_type
- cliext::map::operator=
- cliext::map::operator
- cliext::map::rbegin
- cliext::map::reference
- cliext::map::rend
- cliext::map::reverse_iterator
- cliext::map::size
- cliext::map::size_type
- cliext::map::swap
- cliext::map::to_array
- cliext::map::upper_bound
- cliext::map::value_comp
- cliext::map::value_compare
- cliext::map::value_type
- cliext::operator!= (map)
- cliext::operator< (map)
- cliext::operator<= (map)
- cliext::operator== (map)
- cliext::operator> (map)
- cliext::operator>= (map)
helpviewer_keywords:
- <map> header [STL/CLR]
- map class [STL/CLR]
- <cliext/map> header [STL/CLR]
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
- operator!= (map) member [STL/CLR]
- operator< (map) member [STL/CLR]
- operator<= (map) member [STL/CLR]
- operator== (map) member [STL/CLR]
- operator> (map) member [STL/CLR]
- operator>= (map) member [STL/CLR]
ms.assetid: 8b0a7764-b5e4-4175-a802-82b72eb8662a
ms.openlocfilehash: 19b450e256a428769ca6588227e9249e4e21f51d
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80208554"
---
# <a name="map-stlclr"></a>eşle (STL/CLR)

Şablon sınıfı, çift yönlü erişime sahip olan öğelerin değişen uzunluklu bir dizisini denetleyen bir nesneyi tanımlar. Öğe dizisini, her biri bir öğe depolayan (neredeyse) dengeli sıralı düğüm ağacı olarak yönetmek için kapsayıcı `map` kullanırsınız. Bir öğesi, sırası sıralamak için bir anahtardan ve Ride için bir eşlenen değer içerir.

Aşağıdaki açıklamada `GValue` şöyle olur:

`Microsoft::VisualC::StlClr::GenericPair<GKey, GMapped>`

burada:

`GKey`, ikinci değer bir başvuru türü olmadığı sürece *anahtarla* aynıdır, bu durumda `Key^`

`GMapped`, ikincisi bir başvuru türü olmadığı sürece *eşlenir* ile aynıdır, bu durumda `Mapped^`

## <a name="syntax"></a>Sözdizimi

```cpp
template<typename Key,
    typename Mapped>
    ref class map
        :   public
        System::ICloneable,
        System::Collections::IEnumerable,
        System::Collections::ICollection,
        System::Collections::Generic::IEnumerable<GValue>,
        System::Collections::Generic::ICollection<GValue>,
        System::Collections::Generic::IList<GValue>,
        System::Collections::Generic::IDictionary<Gkey, GMapped>,
        Microsoft::VisualC::StlClr::ITree<Gkey, GValue>
    { ..... };
```

### <a name="parameters"></a>Parametreler

*Anahtar*<br/>
Denetlenen dizideki bir öğenin anahtar bileşeni türü.

*Eşlendiği*<br/>
Denetlenen dizideki bir öğenin ek bileşen türü.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** \<clienext/Map >

**Ad alanı:** cliext

## <a name="declarations"></a>Bildirimler

|Tür Tanımlaması|Açıklama|
|---------------------|-----------------|
|[map::const_iterator (STL/CLR)](#const_iterator)|Denetlenen dizi için bir sabit yineleyici türü.|
|[map::const_reference (STL/CLR)](#const_reference)|Bir öğe için sabit bir başvuru türü.|
|[map::const_reverse_iterator (STL/CLR)](#const_reverse_iterator)|Denetlenen sıra için bir sabit ters yineleyicinin türü.|
|[map::difference_type (STL/CLR)](#difference_type)|İki öğe arasındaki mesafe (muhtemelen imzalı) türü.|
|[map::generic_container (STL/CLR)](#generic_container)|Kapsayıcının genel arabiriminin türü.|
|[map::generic_iterator (STL/CLR)](#generic_iterator)|Kapsayıcının genel arabirimi için bir yineleyici türü.|
|[map::generic_reverse_iterator (STL/CLR)](#generic_reverse_iterator)|Kapsayıcının genel arabirimi için ters yineleyicinin türü.|
|[map::generic_value (STL/CLR)](#generic_value)|Kapsayıcının genel arabirimi için bir öğenin türü.|
|[map::iterator (STL/CLR)](#iterator)|Denetlenen dizi için bir yineleyici türü.|
|[map::key_compare (STL/CLR)](#key_compare)|İki anahtar için sıralama temsilcisi.|
|[map::key_type (STL/CLR)](#key_type)|Bir sıralama anahtarının türü.|
|[map::mapped_type (STL/CLR)](#mapped_type)|Her anahtarla ilişkili eşlenen değerin türü.|
|[map::reference (STL/CLR)](#reference)|Bir öğe için bir başvuru türü.|
|[map::reverse_iterator (STL/CLR)](#reverse_iterator)|Denetlenen sıra için ters yineleyicinin türü.|
|[map::size_type (STL/CLR)](#size_type)|İki öğe arasındaki (negatif olmayan) bir mesafe türü.|
|[map::value_compare (STL/CLR)](#value_compare)|İki öğe değeri için sıralama temsilcisi.|
|[map::value_type (STL/CLR)](#value_type)|Öğenin türü.|

|Üye İşlevi|Açıklama|
|---------------------|-----------------|
|[map::begin (STL/CLR)](#begin)|Denetlenen dizinin başlangıcını belirtir.|
|[map::clear (STL/CLR)](#clear)|Tüm öğeleri kaldırır.|
|[map::count (STL/CLR)](#count)|Belirtilen bir anahtarla eşleşen öğeleri sayar.|
|[map::empty (STL/CLR)](#empty)|Bir öğe olup olmadığını sınar.|
|[map::end (STL/CLR)](#end)|Denetlenen dizinin bitişini belirtir.|
|[map::equal_range (STL/CLR)](#equal_range)|Belirtilen bir anahtarla eşleşen aralığı bulur.|
|[map::erase (STL/CLR)](#erase)|Belirtilen konumlardaki öğeleri kaldırır.|
|[map::find (STL/CLR)](#find)|Belirtilen bir anahtarla eşleşen bir öğeyi bulur.|
|[map::insert (STL/CLR)](#insert)|Öğeleri ekler.|
|[map::key_comp (STL/CLR)](#key_comp)|Sıralama temsilcisini iki anahtar için kopyalar.|
|[map::lower_bound (STL/CLR)](#lower_bound)|Belirtilen anahtarla eşleşen aralığın başlangıcını bulur.|
|[map::make_value (STL/CLR)](#make_value)|Değer nesnesi oluşturur.|
|[map::map (STL/CLR)](#map)|Bir kapsayıcı nesnesi oluşturur.|
|[map::rbegin (STL/CLR)](#rbegin)|Ters denetlenen sıranın başlangıcını belirtir.|
|[map::rend (STL/CLR)](#rend)|Ters denetlenen sıranın sonunu belirtir.|
|[map::size (STL/CLR)](#size)|Öğe sayısını sayar.|
|[map::swap (STL/CLR)](#swap)|İki kapsayıcının içeriğinin yerini değiştirir.|
|[map::to_array (STL/CLR)](#to_array)|Denetimli sırayı yeni bir diziye kopyalar.|
|[map::upper_bound (STL/CLR)](#upper_bound)|Belirtilen anahtarla eşleşen aralığın sonunu bulur.|
|[map::value_comp (STL/CLR)](#value_comp)|İki öğe değeri için sıralama temsilcisini kopyalar.|

|İşleç|Açıklama|
|--------------|-----------------|
|[map::operator= (STL/CLR)](#op_as)|Denetlenen sırayı değiştirir.|
|[map::operator(STL/CLR)](#op)|Bir anahtarı ilişkili eşlenmiş değerine eşler.|
|[operator!= (map) (STL/CLR)](#op_neq)|`map` nesnenin başka bir `map` nesnesine eşit olup olmadığını belirler.|
|[operator< (map) (STL/CLR)](#op_lt)|`map` nesnenin başka bir `map` nesnesinden küçük olup olmadığını belirler.|
|[operator<= (map) (STL/CLR)](#op_lteq)|`map` nesnenin başka bir `map` nesnesinden küçük veya ona eşit olup olmadığını belirler.|
|[operator== (map) (STL/CLR)](#op_eq)|`map` nesnenin başka bir `map` nesnesine eşit olup olmadığını belirler.|
|[operator> (map) (STL/CLR)](#op_gt)|`map` nesnenin başka bir `map` nesnesinden büyük olup olmadığını belirler.|
|[operator>= (map) (STL/CLR)](#op_gteq)|`map` nesnenin başka bir `map` nesnesinden büyük veya ona eşit olup olmadığını belirler.|

## <a name="interfaces"></a>Arabirimler

|Arabirim|Açıklama|
|---------------|-----------------|
|<xref:System.ICloneable>|Bir nesneyi çoğaltın.|
|<xref:System.Collections.IEnumerable>|Öğeler aracılığıyla sıralama.|
|<xref:System.Collections.ICollection>|Öğe grubunu saklayın.|
|<xref:System.Collections.Generic.IEnumerable%601>|Yazılı öğeler aracılığıyla sıralama.|
|<xref:System.Collections.Generic.ICollection%601>|Türü belirtilmiş öğelerin grubunu koruyun.|
|<xref:System.Collections.Generic.IDictionary%602>|{Key, value} çiftlerinin grubunu koruyun.|
|< Anahtar, değer >|Genel kapsayıcıyı koruyun.|

## <a name="remarks"></a>Açıklamalar

Nesnesi, tek tek düğümler olarak denetlediği sıra için depolamayı ayırır ve boşaltır. Tek bir düğümün içeriğini başka bir düğüme kopyalayarak düğümler arasındaki bağlantıları değiştirerek sıralı bir (neredeyse) dengeli ağaca öğe ekler. Diğer bir deyişle, daha fazla Bing, kalan öğeleri etkilemeden öğeleri ekleyebileceğiniz ve kaldırabileceğiniz anlamına gelir.

Nesnesi, [map:: key_compare (STL/CLR)](../dotnet/map-key-compare-stl-clr.md)türünde depolanan bir temsilci nesnesi çağırarak denetlediği diziyi sıralar. Eşlemeyi oluştururken depolanan temsilci nesnesini belirtebilirsiniz; temsilci nesnesi belirtmezseniz, varsayılan değer karşılaştırma `operator<(key_type, key_type)`. Bu saklı nesneye, [map:: key_comp (STL/CLR)](../dotnet/map-key-comp-stl-clr.md)`()`üye işlevini çağırarak erişirsiniz.

Bu tür bir temsilci nesnesi, [map:: key_type (STL/CLR)](../dotnet/map-key-type-stl-clr.md)türündeki anahtarlar üzerinde katı zayıf bir sıralama getirmelidir. Yani, her iki anahtar için `X` ve `Y`:

`key_comp()(X, Y)` her çağrıda aynı Boole sonucunu döndürür.

`key_comp()(X, Y)` true ise, `key_comp()(Y, X)` false olmalıdır.

`key_comp()(X, Y)` true ise, `X` `Y`önce sipariş olarak kabul edilir.

`!key_comp()(X, Y) && !key_comp()(Y, X)` true ise, `X` ve `Y` eşdeğer sıralamaya sahip olarak kabul edilir.

Denetlenen dizide `Y` önce gelen herhangi bir öğe `X` için, `key_comp()(Y, X)` false olur. (Varsayılan temsilci nesnesi için, anahtarlar hiçbir şekilde değerde azalmayın.) Şablon sınıfı [eşlemesinin](../dotnet/map-stl-clr.md)aksine, `map` şablon sınıfının bir nesnesi tüm öğeler için anahtarların benzersiz olmasını gerektirmez. (İki veya daha fazla anahtarın eşdeğer sıralaması olabilir.)

Her öğe ayrı bir anahtar ve eşlenmiş bir değer içerir. Sıra, dizi içindeki öğe sayısının logaritmasına orantılı bir şekilde bir dizi işlem içeren rastgele bir öğenin aranması, eklenmesine ve kaldırılmasına izin veren bir şekilde temsil edilir. Ayrıca, bir öğe eklenmesi hiçbir yineleyiciyi geçersiz kılmaz; bir öğenin kaldırılması yalnızca bu kaldırılan öğeyi gösteren yineleyicileri geçersiz kılar.

Bir harita çift yönlü yineleyiciler destekler, bu, denetlenen dizide bir öğe atayan bir yineleyici verilen bitişik öğelere adım adım yol açabilir. Özel bir baş düğüm, [map:: End (STL/CLR)](../dotnet/map-end-stl-clr.md)`()`tarafından döndürülen Yineleyici öğesine karşılık gelir. Varsa, denetlenen sıradaki son öğeye ulaşmak için bu yineleyiciyi azaltamazsınız. Baş düğüme ulaşmak için bir harita yineleyicisini arttırıp, daha sonra `end()`şuna eşit olacak. Ancak `end()`tarafından döndürülen yineleyici başvurusu oluşturamazsınız.

Bir harita öğesine, doğrudan sayısal konumu verildiğinde (rastgele erişim Yineleyici gerektiren) başvurmayacağınızı unutmayın.

Bir harita Yineleyici ilişkili eşleme düğümüne bir tanıtıcı depolar, bu da ilişkili kapsayıcısına bir tutamacı depolar. Yineleyiciler yalnızca ilişkili kapsayıcı nesneleriyle birlikte kullanabilirsiniz. Eşleme yineleyicisi, ilişkili eşleme düğümü bazı eşlemelerle ilişkilendirildiği sürece geçerli kalır. Ayrıca, geçerli bir yineleyici bir şekilde başvurulmasını sağlar--bunu, oluşturduğu öğe değerine erişmek veya değiştirmek için kullanabilirsiniz. `end()`eşit olmadığı sürece.

Bir öğeyi silme veya kaldırma, kendi saklı değeri için yıkıcıyı çağırır. Kapsayıcının yok edilmesi tüm öğeleri siler. Bu nedenle, öğe türü bir başvuru sınıfı olan bir kapsayıcı, kapsayıcının hiçbir öğenin etkin olmamasını sağlar. Ancak, bir işleç kapsayıcısının *öğelerini yok ettiğini* unutmayın.

## <a name="members"></a>Üyeler

## <a name="mapbegin-stlclr"></a><a name="begin"></a>Map:: Begin (STL/CLR)

Denetlenen dizinin başlangıcını belirtir.

### <a name="syntax"></a>Sözdizimi

```cpp
iterator begin();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, denetimli sıranın ilk öğesini veya boş bir dizinin sonunun ötesinde bir çift yönlü yineleyiciyi döndürür. Denetlenen sıranın başlangıcını `current` atayan bir yineleyici elde etmek için bunu kullanırsınız, ancak denetlenen sıranın uzunluğu değişirse durumu değişebilir.

### <a name="example"></a>Örnek

```cpp
// cliext_map_begin.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
int main()
    {
    Mymap c1;
    c1.insert(Mymap::make_value(L'a', 1));
    c1.insert(Mymap::make_value(L'b', 2));
    c1.insert(Mymap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Mymap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // inspect first two items
    Mymap::iterator it = c1.begin();
    System::Console::WriteLine("*begin() = [{0} {1}]",
        it->first, it->second);
    ++it;
    System::Console::WriteLine("*++begin() = [{0} {1}]",
        it->first, it->second);
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
*begin() = [a 1]
*++begin() = [b 2]
```

## <a name="mapclear-stlclr"></a><a name="clear"></a>Map:: Clear (STL/CLR)

Tüm öğeleri kaldırır.

### <a name="syntax"></a>Sözdizimi

```cpp
void clear();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi etkin bir şekilde [map:: Erase](../dotnet/map-erase-stl-clr.md) (stl/clr)`(` [map:: BEGIN (STL/CLR](../dotnet/map-begin-stl-clr.md) )`(),` [map:: End (STL/CLR)](../dotnet/map-end-stl-clr.md)`())`çağırır. Denetlenen sıranın boş olduğundan emin olmak için bunu kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// cliext_map_clear.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
int main()
    {
    Mymap c1;
    c1.insert(Mymap::make_value(L'a', 1));
    c1.insert(Mymap::make_value(L'b', 2));
    c1.insert(Mymap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Mymap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // clear the container and reinspect
    c1.clear();
    System::Console::WriteLine("size() = {0}", c1.size());

    c1.insert(Mymap::make_value(L'a', 1));
    c1.insert(Mymap::make_value(L'b', 2));

    // display contents " [a 1] [b 2]"
    for each (Mymap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();
    c1.clear();
    System::Console::WriteLine("size() = {0}", c1.size());
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
size() = 0
[a 1] [b 2]
size() = 0
```

## <a name="mapconst_iterator-stlclr"></a><a name="const_iterator"></a>Map:: const_iterator (STL/CLR)

Denetlenen dizi için bir sabit yineleyici türü.

### <a name="syntax"></a>Sözdizimi

```cpp
typedef T2 const_iterator;
```

### <a name="remarks"></a>Açıklamalar

Türü, denetlenen dizi için bir sabit çift yönlü Yineleyici olarak kullanılabilecek belirtilmemiş türdeki bir nesneyi tanımlar `T2`.

### <a name="example"></a>Örnek

```cpp
// cliext_map_const_iterator.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
int main()
    {
    Mymap c1;
    c1.insert(Mymap::make_value(L'a', 1));
    c1.insert(Mymap::make_value(L'b', 2));
    c1.insert(Mymap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    Mymap::const_iterator cit = c1.begin();
    for (; cit != c1.end(); ++cit)
        System::Console::Write("[{0} {1}] ", cit->first, cit->second);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
```

## <a name="mapconst_reference-stlclr"></a><a name="const_reference"></a>Map:: const_reference (STL/CLR)

Bir öğe için sabit bir başvuru türü.

### <a name="syntax"></a>Sözdizimi

```cpp
typedef value_type% const_reference;
```

### <a name="remarks"></a>Açıklamalar

Türü bir öğeye sabit bir başvuru tanımlar.

### <a name="example"></a>Örnek

```cpp
// cliext_map_const_reference.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
int main()
    {
    Mymap c1;
    c1.insert(Mymap::make_value(L'a', 1));
    c1.insert(Mymap::make_value(L'b', 2));
    c1.insert(Mymap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    Mymap::const_iterator cit = c1.begin();
    for (; cit != c1.end(); ++cit)
        {   // get a const reference to an element
        Mymap::const_reference cref = *cit;
        System::Console::Write("[{0} {1}] ", cref->first, cref->second);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
```

## <a name="mapconst_reverse_iterator-stlclr"></a><a name="const_reverse_iterator"></a>Map:: const_reverse_iterator (STL/CLR)

Denetlenen sıra için bir sabit ters yineleyicinin türü..

### <a name="syntax"></a>Sözdizimi

```cpp
typedef T4 const_reverse_iterator;
```

### <a name="remarks"></a>Açıklamalar

Türü, denetimli sıra için sabit bir ters Yineleyici olarak kullanılabilecek belirtilmemiş türde `T4` bir nesne tanımlar.

### <a name="example"></a>Örnek

```cpp
// cliext_map_const_reverse_iterator.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
int main()
    {
    Mymap c1;
    c1.insert(Mymap::make_value(L'a', 1));
    c1.insert(Mymap::make_value(L'b', 2));
    c1.insert(Mymap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]" reversed
    Mymap::const_reverse_iterator crit = c1.rbegin();
    for (; crit != c1.rend(); ++crit)
        System::Console::Write("[{0} {1}] ", crit->first, crit->second);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
[c 3] [b 2] [a 1]
```

## <a name="mapcount-stlclr"></a><a name="count"></a>Map:: Count (STL/CLR)

Belirtilen bir anahtar ile eşleşen öğe sayısını bulur.

### <a name="syntax"></a>Sözdizimi

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
// cliext_map_count.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
int main()
    {
    Mymap c1;
    c1.insert(Mymap::make_value(L'a', 1));
    c1.insert(Mymap::make_value(L'b', 2));
    c1.insert(Mymap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Mymap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    System::Console::WriteLine("count(L'A') = {0}", c1.count(L'A'));
    System::Console::WriteLine("count(L'b') = {0}", c1.count(L'b'));
    System::Console::WriteLine("count(L'C') = {0}", c1.count(L'C'));
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
count(L'A') = 0
count(L'b') = 1
count(L'C') = 0
```

## <a name="mapdifference_type-stlclr"></a><a name="difference_type"></a>eşleme::d ifference_type (STL/CLR)

İki öğe arasındaki işaretli bir mesafe türü.

### <a name="syntax"></a>Sözdizimi

```cpp
typedef int difference_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, büyük olasılıkla negatif bir öğe sayısını tanımlar.

### <a name="example"></a>Örnek

```cpp
// cliext_map_difference_type.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
int main()
    {
    Mymap c1;
    c1.insert(Mymap::make_value(L'a', 1));
    c1.insert(Mymap::make_value(L'b', 2));
    c1.insert(Mymap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Mymap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // compute positive difference
    Mymap::difference_type diff = 0;
    for (Mymap::iterator it = c1.begin(); it != c1.end(); ++it)
        ++diff;
    System::Console::WriteLine("end()-begin() = {0}", diff);

    // compute negative difference
    diff = 0;
    for (Mymap::iterator it = c1.end(); it != c1.begin(); --it)
        --diff;
    System::Console::WriteLine("begin()-end() = {0}", diff);
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
end()-begin() = 3
begin()-end() = -3
```

## <a name="mapempty-stlclr"></a><a name="empty"></a>Map:: Empty (STL/CLR)

Bir öğe olup olmadığını sınar.

### <a name="syntax"></a>Sözdizimi

```cpp
bool empty();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi boş bir denetlenen dizi için true döndürür. [Map:: size (STL/CLR)](../dotnet/map-size-stl-clr.md)`() == 0`eşdeğerdir. Bu, eşlemenin boş olup olmadığını test etmek için kullanılır.

### <a name="example"></a>Örnek

```cpp
// cliext_map_empty.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
int main()
    {
    Mymap c1;
    c1.insert(Mymap::make_value(L'a', 1));
    c1.insert(Mymap::make_value(L'b', 2));
    c1.insert(Mymap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Mymap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
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
[a 1] [b 2] [c 3]
size() = 3
empty() = False
size() = 0
empty() = True
```

## <a name="mapend-stlclr"></a><a name="end"></a>Map:: End (STL/CLR)

Denetlenen dizinin bitişini belirtir.

### <a name="syntax"></a>Sözdizimi

```cpp
iterator end();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, denetimli dizinin sonunun hemen ötesinde işaret eden çift yönlü bir yineleyici döndürür. Denetlenen dizinin sonunu atayan bir yineleyici elde etmek için bunu kullanırsınız; denetlenen sıranın uzunluğu değişirse, durumu değişmez.

### <a name="example"></a>Örnek

```cpp
// cliext_map_end.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
int main()
    {
    Mymap c1;
    c1.insert(Mymap::make_value(L'a', 1));
    c1.insert(Mymap::make_value(L'b', 2));
    c1.insert(Mymap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Mymap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // inspect last two items
    Mymap::iterator it = c1.end();
    --it;
    --it;
    System::Console::WriteLine("*-- --end() = [{0} {1}]",
        it->first, it->second);
    ++it;
    System::Console::WriteLine("*--end() = [{0} {1}]",
        it->first, it->second);
    return (0);
    }
```

## <a name="mapequal_range-stlclr"></a><a name="equal_range"></a>Map:: equal_range (STL/CLR)

Belirtilen bir anahtarla eşleşen aralığı bulur.

### <a name="syntax"></a>Sözdizimi

```cpp
cliext::pair<iterator, iterator> equal_range(key_type key);
```

#### <a name="parameters"></a>Parametreler

*anahtar*<br/>
Aranacak anahtar değer.

### <a name="remarks"></a>Açıklamalar

Üye işlevi yineleyicilerin bir çiftini döndürür `cliext::pair<iterator, iterator>(` map:: [lower_bound (STL/CLR)](../dotnet/map-lower-bound-stl-clr.md)`(key),` [map:: upper_bound (STL/CLR)](../dotnet/map-upper-bound-stl-clr.md)`(key))`. Belirli bir anahtarla eşleşen denetimli dizide bulunan öğe aralığını öğrenmek için bunu kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// cliext_map_equal_range.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
typedef Mymap::pair_iter_iter Pairii;
int main()
    {
    Mymap c1;
    c1.insert(Mymap::make_value(L'a', 1));
    c1.insert(Mymap::make_value(L'b', 2));
    c1.insert(Mymap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Mymap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // display results of failed search
    Pairii pair1 = c1.equal_range(L'x');
    System::Console::WriteLine("equal_range(L'x') empty = {0}",
        pair1.first == pair1.second);

    // display results of successful search
    pair1 = c1.equal_range(L'b');
    for (; pair1.first != pair1.second; ++pair1.first)
        System::Console::Write("[{0} {1}] ",
            pair1.first->first, pair1.first->second);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
equal_range(L'x') empty = True
[b 2]
```

## <a name="maperase-stlclr"></a><a name="erase"></a>Map:: Erase (STL/CLR)

Belirtilen konumlardaki öğeleri kaldırır.

### <a name="syntax"></a>Sözdizimi

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

İlk üye *işlevi, öğesinin*işaret ettiği denetimli sıranın öğesini kaldırır ve kaldırılan öğenin ötesinde ilk öğeyi atayan bir yineleyici döndürür ya da böyle bir öğe yoksa [map:: End (STL/CLR)](../dotnet/map-end-stl-clr.md)`()`. Tek bir öğeyi kaldırmak için bunu kullanırsınız.

İkinci üye işlevi, [`first`, `last`) aralığındaki denetimli sıranın öğelerini kaldırır ve kaldırılan tüm öğelerin ötesinde kalan ilk öğeyi atayan bir yineleyici döndürür veya böyle bir öğe yoksa `end()`. Sıfır veya daha fazla bitişik öğeyi kaldırmak için bunu kullanırsınız.

Üçüncü üye işlevi, anahtarı *anahtara*denk sıralama değerine sahip denetimli dizinin herhangi bir öğesini kaldırır ve kaldırılan öğe sayısının sayısını döndürür. Bu anahtarı, belirtilen bir anahtarla eşleşen tüm öğeleri kaldırmak ve saymak için kullanırsınız.

Her bir öğe, denetlenen dizideki öğelerin sayısının logaritması ile orantılı bir zaman alır.

### <a name="example"></a>Örnek

```cpp
// cliext_map_erase.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
int main()
    {
    cliext::map<wchar_t, int> c1;
    c1.insert(cliext::map<wchar_t, int>::make_value(L'a', 1));
    c1.insert(cliext::map<wchar_t, int>::make_value(L'b', 2));
    c1.insert(cliext::map<wchar_t, int>::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (cliext::map<wchar_t, int>::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // erase an element and reinspect
    cliext::map<wchar_t, int>::iterator it =
        c1.erase(c1.begin());
    System::Console::WriteLine("erase(begin()) = [{0} {1}]",
        it->first, it->second);

    // add elements and display " b c d e"
    c1.insert(cliext::map<wchar_t, int>::make_value(L'd', 4));
    c1.insert(cliext::map<wchar_t, int>::make_value(L'e', 5));
    for each (cliext::map<wchar_t, int>::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // erase all but end
    it = c1.end();
    it = c1.erase(c1.begin(), --it);
    System::Console::WriteLine("erase(begin(), end()-1) = [{0} {1}]",
        it->first, it->second);
    System::Console::WriteLine("size() = {0}", c1.size());

    // erase end
    System::Console::WriteLine("erase(L'x') = {0}", c1.erase(L'x'));
    System::Console::WriteLine("erase(L'e') = {0}", c1.erase(L'e'));
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
erase(begin()) = [b 2]
[b 2] [c 3] [d 4] [e 5]
erase(begin(), end()-1) = [e 5]
size() = 1
erase(L'x') = 0
erase(L'e') = 1
```

## <a name="mapfind-stlclr"></a><a name="find"></a>Map:: Find (STL/CLR)

Belirtilen bir anahtarla eşleşen bir öğeyi bulur.

### <a name="syntax"></a>Sözdizimi

```cpp
iterator find(key_type key);
```

#### <a name="parameters"></a>Parametreler

*anahtar*<br/>
Aranacak anahtar değer.

### <a name="remarks"></a>Açıklamalar

Denetlenen dizide en az bir öğe *anahtar*ile eşdeğer sıralamaya sahipse, üye işlevi bu öğelerden birini tanımlayarak bir yineleyici döndürür; Aksi halde [map:: End (STL/CLR)](../dotnet/map-end-stl-clr.md)`()`döndürür. Belirtilen bir anahtarla eşleşen denetimli dizide bulunan bir öğeyi bulmak için bunu kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// cliext_map_find.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
int main()
    {
    Mymap c1;
    c1.insert(Mymap::make_value(L'a', 1));
    c1.insert(Mymap::make_value(L'b', 2));
    c1.insert(Mymap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Mymap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    System::Console::WriteLine("find {0} = {1}",
        L'A', c1.find(L'A') != c1.end());

    Mymap::iterator it = c1.find(L'b');
    System::Console::WriteLine("find {0} = [{1} {2}]",
        L'b', it->first, it->second);

    System::Console::WriteLine("find {0} = {1}",
        L'C', c1.find(L'C') != c1.end());
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
find A = False
find b = [b 2]
find C = False
```

## <a name="mapgeneric_container-stlclr"></a><a name="generic_container"></a>Map:: generic_container (STL/CLR)

Kapsayıcının genel arabiriminin türü.

### <a name="syntax"></a>Sözdizimi

```cpp
typedef Microsoft::VisualC::StlClr::
    ITree<GKey, GValue>
    generic_container;
```

### <a name="remarks"></a>Açıklamalar

Tür, bu şablon kapsayıcı sınıfı için genel arabirimi tanımlar.

### <a name="example"></a>Örnek

```cpp
// cliext_map_generic_container.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
int main()
    {
    Mymap c1;
    c1.insert(Mymap::make_value(L'a', 1));
    c1.insert(Mymap::make_value(L'b', 2));
    c1.insert(Mymap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Mymap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // construct a generic container
    Mymap::generic_container^ gc1 = %c1;
    for each (Mymap::value_type elem in gc1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // modify generic and display original
    gc1->insert(Mymap::make_value(L'd', 4));
    for each (Mymap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // modify original and display generic
    c1.insert(Mymap::make_value(L'e', 5));
    for each (Mymap::value_type elem in gc1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
[a 1] [b 2] [c 3]
[a 1] [b 2] [c 3] [d 4]
[a 1] [b 2] [c 3] [d 4] [e 5]
```

## <a name="mapgeneric_iterator-stlclr"></a><a name="generic_iterator"></a>Map:: generic_iterator (STL/CLR)

Kapsayıcı için genel arabirimle birlikte kullanılacak bir yineleyici türü.

### <a name="syntax"></a>Sözdizimi

```cpp
typedef Microsoft::VisualC::StlClr::Generic::
    ContainerBidirectionalIterator<generic_value>
    generic_iterator;
```

### <a name="remarks"></a>Açıklamalar

Tür, bu şablon kapsayıcı sınıfı için genel arabirim ile kullanılabilen genel bir yineleyiciyi açıklar.

### <a name="example"></a>Örnek

```cpp
// cliext_map_generic_iterator.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
int main()
    {
    Mymap c1;
    c1.insert(Mymap::make_value(L'a', 1));
    c1.insert(Mymap::make_value(L'b', 2));
    c1.insert(Mymap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Mymap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // construct a generic container
    Mymap::generic_container^ gc1 = %c1;
    for each (Mymap::value_type elem in gc1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // get an element and display it
    Mymap::generic_iterator gcit = gc1->begin();
    Mymap::generic_value gcval = *gcit;
    System::Console::Write("[{0} {1}] ", gcval->first, gcval->second);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
[a 1] [b 2] [c 3]
[a 1]
```

## <a name="mapgeneric_reverse_iterator-stlclr"></a><a name="generic_reverse_iterator"></a>Map:: generic_reverse_iterator (STL/CLR)

Kapsayıcı için genel arabirimle birlikte kullanılacak ters yineleyicinin türü.

### <a name="syntax"></a>Sözdizimi

```cpp
typedef Microsoft::VisualC::StlClr::Generic::
    ReverseRandomAccessIterator<generic_value>
    generic_reverse_iterator;
```

### <a name="remarks"></a>Açıklamalar

Tür, bu şablon kapsayıcı sınıfı için genel arabirimle birlikte kullanılabilecek bir genel ters yineleyici tanımlar.

### <a name="example"></a>Örnek

```cpp
// cliext_map_generic_reverse_iterator.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
int main()
    {
    Mymap c1;
    c1.insert(Mymap::make_value(L'a', 1));
    c1.insert(Mymap::make_value(L'b', 2));
    c1.insert(Mymap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Mymap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // construct a generic container
    Mymap::generic_container^ gc1 = %c1;
    for each (Mymap::value_type elem in gc1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // get an element and display it
    Mymap::generic_reverse_iterator gcit = gc1->rbegin();
    Mymap::generic_value gcval = *gcit;
    System::Console::WriteLine("[{0} {1}] ", gcval->first, gcval->second);
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
[a 1] [b 2] [c 3]
[c 3]
```

## <a name="mapgeneric_value-stlclr"></a><a name="generic_value"></a>Map:: generic_value (STL/CLR)

Kapsayıcının genel arabirimiyle kullanılacak öğe türü.

### <a name="syntax"></a>Sözdizimi

```cpp
typedef GValue generic_value;
```

### <a name="remarks"></a>Açıklamalar

Tür, bu şablon kapsayıcı sınıfı için genel arabirimle birlikte kullanılacak saklı öğe değerini açıklayan `GValue` türünde bir nesne tanımlar.

### <a name="example"></a>Örnek

```cpp
// cliext_map_generic_value.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
int main()
    {
    Mymap c1;
    c1.insert(Mymap::make_value(L'a', 1));
    c1.insert(Mymap::make_value(L'b', 2));
    c1.insert(Mymap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Mymap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // construct a generic container
    Mymap::generic_container^ gc1 = %c1;
    for each (Mymap::value_type elem in gc1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // get an element and display it
    Mymap::generic_iterator gcit = gc1->begin();
    Mymap::generic_value gcval = *gcit;
    System::Console::WriteLine("[{0} {1}] ", gcval->first, gcval->second);
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
[a 1] [b 2] [c 3]
[a 1]
```

## <a name="mapinsert-stlclr"></a><a name="insert"></a>Map:: Insert (STL/CLR)

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

İlk üye işlevi, value değeri olan bir öğe eklemek için endeavors ve `X`bir *çift değer döndürür*. `X.second` true ise, `X.first` yeni ekli öğeyi belirtir; Aksi takdirde `X.first`, zaten var olan ve yeni bir öğe eklenmemiş eşdeğer sıralamaya sahip bir öğe belirler. Tek bir öğe eklemek için bunu kullanırsınız.

İkinci üye işlevi, bir ipucu olarak *WHERE* (performansı artırmak için) ve yeni eklenen öğeyi atayan bir yineleyici döndüren bir *değer değeri olan*bir öğe ekler. Bildiğiniz bir öğeye bitişik olabilecek tek bir öğe eklemek için bunu kullanırsınız.

Üçüncü üye işlevi [`first`, `last`) dizisini ekler. Başka bir dizide kopyalanmış sıfır veya daha fazla öğe eklemek için bunu kullanırsınız.

Dördüncü üye işlevi, *sağ*tarafından belirlenen diziyi ekler. Bir Numaralandırıcı tarafından tanımlanan bir sıra eklemek için bunu kullanırsınız.

Her öğe ekleme, denetlenen dizideki öğelerin sayısının logaritması ile orantılı bir zaman alır. Ekleme noktası, ekleme noktasına bitişik bir öğe atayan bir ipucu verildiğinde, sabit zamanlı olarak ekleme yapılabilir.

### <a name="example"></a>Örnek

```cpp
// cliext_map_insert.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
typedef Mymap::pair_iter_bool Pairib;
int main()
    {
    Mymap c1;
    c1.insert(Mymap::make_value(L'a', 1));
    c1.insert(Mymap::make_value(L'b', 2));
    c1.insert(Mymap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Mymap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // insert a single value, unique and duplicate
// insert a single value, success and failure
    Pairib pair1 = c1.insert(Mymap::make_value(L'x', 24));
    System::Console::WriteLine("insert([L'x' 24]) = [[{0} {1}] {2}]",
        pair1.first->first, pair1.first->second, pair1.second);

    pair1 = c1.insert(Mymap::make_value(L'b', 2));
    System::Console::WriteLine("insert([L'b' 2]) = [[{0} {1}] {2}]",
        pair1.first->first, pair1.first->second, pair1.second);

    for each (Mymap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // insert a single value with hint
    Mymap::iterator it =
        c1.insert(c1.begin(), Mymap::make_value(L'y', 25));
    System::Console::WriteLine("insert(begin(), [L'y' 25]) = [{0} {1}]",
        it->first, it->second);
    for each (Mymap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // insert an iterator range
    Mymap c2;
    it = c1.end();
    c2.insert(c1.begin(), --it);
    for each (Mymap::value_type elem in c2)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // insert an enumeration
    Mymap c3;
    c3.insert(   // NOTE: cast is not needed
        (System::Collections::Generic::
            IEnumerable<Mymap::value_type>^)%c1);
    for each (Mymap::value_type elem in c3)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
insert([L'x' 24]) = [[x 24] True]
insert([L'b' 2]) = [[b 2] False]
[a 1] [b 2] [c 3] [x 24]
insert(begin(), [L'y' 25]) = [y 25]
[a 1] [b 2] [c 3] [x 24] [y 25]
[a 1] [b 2] [c 3] [x 24]
[a 1] [b 2] [c 3] [x 24] [y 25]
```

## <a name="mapiterator-stlclr"></a><a name="iterator"></a>Map:: yineleyici (STL/CLR)

Denetlenen dizi için bir yineleyici türü.

### <a name="syntax"></a>Sözdizimi

```cpp
typedef T1 iterator;
```

### <a name="remarks"></a>Açıklamalar

Türü, denetimli sıra için çift yönlü bir yineleyici olarak kullanılabilecek belirtilmemiş türde `T1` bir nesne tanımlar.

### <a name="example"></a>Örnek

```cpp
// cliext_map_iterator.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
int main()
    {
    Mymap c1;
    c1.insert(Mymap::make_value(L'a', 1));
    c1.insert(Mymap::make_value(L'b', 2));
    c1.insert(Mymap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    Mymap::iterator it = c1.begin();
    for (; it != c1.end(); ++it)
        System::Console::Write("[{0} {1}] ", it->first, it->second);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
```

## <a name="mapkey_comp-stlclr"></a><a name="key_comp"></a>Map:: key_comp (STL/CLR)

Sıralama temsilcisini iki anahtar için kopyalar.

### <a name="syntax"></a>Sözdizimi

```cpp
key_compare^key_comp();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, denetimli sırayı sıralamak için kullanılan sıralama temsilcisini döndürür. İki anahtarı karşılaştırmak için bunu kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// cliext_map_key_comp.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
int main()
    {
    Mymap c1;
    Mymap::key_compare^ kcomp = c1.key_comp();

    System::Console::WriteLine("compare(L'a', L'a') = {0}",
        kcomp(L'a', L'a'));
    System::Console::WriteLine("compare(L'a', L'b') = {0}",
        kcomp(L'a', L'b'));
    System::Console::WriteLine("compare(L'b', L'a') = {0}",
        kcomp(L'b', L'a'));
    System::Console::WriteLine();

    // test a different ordering rule
    Mymap c2 = cliext::greater<wchar_t>();
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

## <a name="mapkey_compare-stlclr"></a><a name="key_compare"></a>Map:: key_compare (STL/CLR)

İki anahtar için sıralama temsilcisi.

### <a name="syntax"></a>Sözdizimi

```cpp
Microsoft::VisualC::StlClr::BinaryDelegate<GKey, GKey, bool>
    key_compare;
```

### <a name="remarks"></a>Açıklamalar

Tür, anahtar bağımsız değişkenlerinin sıralamasını belirleyen temsilcinin eşanlamlısıdır.

### <a name="example"></a>Örnek

```cpp
// cliext_map_key_compare.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
int main()
    {
    Mymap c1;
    Mymap::key_compare^ kcomp = c1.key_comp();

    System::Console::WriteLine("compare(L'a', L'a') = {0}",
        kcomp(L'a', L'a'));
    System::Console::WriteLine("compare(L'a', L'b') = {0}",
        kcomp(L'a', L'b'));
    System::Console::WriteLine("compare(L'b', L'a') = {0}",
        kcomp(L'b', L'a'));
    System::Console::WriteLine();

    // test a different ordering rule
    Mymap c2 = cliext::greater<wchar_t>();
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

## <a name="mapkey_type-stlclr"></a><a name="key_type"></a>Map:: key_type (STL/CLR)

Bir sıralama anahtarının türü.

### <a name="syntax"></a>Sözdizimi

```cpp
typedef Key key_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, şablon parametre *anahtarı*için bir eş anlamlı.

### <a name="example"></a>Örnek

```cpp
// cliext_map_key_type.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
int main()
    {
    Mymap c1;
    c1.insert(Mymap::make_value(L'a', 1));
    c1.insert(Mymap::make_value(L'b', 2));
    c1.insert(Mymap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]" using key_type
    for (Mymap::iterator it = c1.begin(); it != c1.end(); ++it)
        {   // store element in key_type object
        Mymap::key_type val = it->first;

        System::Console::Write("{0} ", val);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="maplower_bound-stlclr"></a><a name="lower_bound"></a>Map:: lower_bound (STL/CLR)

Belirtilen anahtarla eşleşen aralığın başlangıcını bulur.

### <a name="syntax"></a>Sözdizimi

```cpp
iterator lower_bound(key_type key);
```

#### <a name="parameters"></a>Parametreler

*anahtar*<br/>
Aranacak anahtar değer.

### <a name="remarks"></a>Açıklamalar

Üye işlevi, *anahtara*denk sıralamaya sahip olan denetimli dizideki ilk öğeyi `X` belirler. Böyle bir öğe yoksa, [map:: End (STL/CLR)](../dotnet/map-end-stl-clr.md)`()`döndürür; Aksi takdirde, `X`atayan bir yineleyici döndürür. Belirtilen bir anahtarla eşleşen, denetlenen dizide bulunan bir öğe dizisinin başlangıcını bulmak için bunu kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// cliext_map_lower_bound.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
int main()
    {
    Mymap c1;
    c1.insert(Mymap::make_value(L'a', 1));
    c1.insert(Mymap::make_value(L'b', 2));
    c1.insert(Mymap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Mymap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    System::Console::WriteLine("lower_bound(L'x')==end() = {0}",
        c1.lower_bound(L'x') == c1.end());

    Mymap::iterator it = c1.lower_bound(L'a');
    System::Console::WriteLine("*lower_bound(L'a') = [{0} {1}]",
        it->first, it->second);
    it = c1.lower_bound(L'b');
    System::Console::WriteLine("*lower_bound(L'b') = [{0} {1}]",
        it->first, it->second);
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
lower_bound(L'x')==end() = True
*lower_bound(L'a') = [a 1]
*lower_bound(L'b') = [b 2]
```

## <a name="mapmake_value-stlclr"></a><a name="make_value"></a>Map:: make_value (STL/CLR)

Değer nesnesi oluşturur.

### <a name="syntax"></a>Sözdizimi

```cpp
static value_type make_value(key_type key, mapped_type mapped);
```

#### <a name="parameters"></a>Parametreler

*anahtar*<br/>
Kullanılacak anahtar değer.

*eşlendiği*<br/>
Aranacak eşlenen değer.

### <a name="remarks"></a>Açıklamalar

Üye işlevi, anahtarı *anahtar* olan ve eşlenmiş değeri *eşlenmiş*bir `value_type` nesnesi döndürür. Diğer birçok üye işlevi ile kullanmak üzere uygun bir nesne oluşturmak için bunu kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// cliext_map_make_value.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
int main()
    {
    Mymap c1;
    c1.insert(Mymap::make_value(L'a', 1));
    c1.insert(Mymap::make_value(L'b', 2));
    c1.insert(Mymap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Mymap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
```

## <a name="mapmap-stlclr"></a><a name="map"></a>Map:: Map (STL/CLR)

Bir kapsayıcı nesnesi oluşturur.

### <a name="syntax"></a>Sözdizimi

```cpp
map();
explicit map(key_compare^ pred);
map(map<Key, Mapped>% right);
map(map<Key, Mapped>^ right);
template<typename InIter>
    mapmap(InIter first, InIter last);
template<typename InIter>
    map(InIter first, InIter last,
        key_compare^ pred);
map(System::Collections::Generic::IEnumerable<GValue>^ right);
map(System::Collections::Generic::IEnumerable<GValue>^ right,
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

`map();`

denetlenen sırayı, varsayılan sıralama koşulu `key_compare()`, hiçbir öğesi olmadan başlatır. Varsayılan sıralama koşulu ile boş bir ilk denetimli sıra belirtmek için bunu kullanırsınız.

Oluşturucu:

`explicit map(key_compare^ pred);`

denetlenen sırayı, sıralama koşulu *Pred*ile birlikte hiçbir öğe olmadan başlatır. Belirtilen sıralama koşulu ile boş bir ilk denetimli sıra belirtmek için bunu kullanırsınız.

Oluşturucu:

`map(map<Key, Mapped>% right);`

[`right.begin()`, `right.end()`) sırası ile denetimli sırayı varsayılan sıralama koşulu ile başlatır. Varsayılan sıralama koşulu ile, *Map nesnesi tarafından*denetlenen sıranın bir kopyası olan ilk denetimli bir sıra belirtmek için bunu kullanırsınız.

Oluşturucu:

`map(map<Key, Mapped>^ right);`

[`right->begin()`, `right->end()`) sırası ile denetimli sırayı varsayılan sıralama koşulu ile başlatır. Varsayılan sıralama koşulu ile, *Map nesnesi tarafından*denetlenen sıranın bir kopyası olan ilk denetimli bir sıra belirtmek için bunu kullanırsınız.

Oluşturucu:

`template<typename InIter> map(InIter first, InIter last);`

[`first`, `last`) sırası ile denetimli sırayı varsayılan sıralama koşulu ile başlatır. Varsayılan sıralama koşulu ile, denetimli diziyi başka bir dizinin bir kopyası yapmak için kullanabilirsiniz.

Oluşturucu:

`template<typename InIter> map(InIter first, InIter last, key_compare^ pred);`

[`first`, `last`) sırası ile denetimli sırayı, sıralama koşulu *Pred*ile başlatır. Belirtilen sıralama koşulu ile, denetimli diziyi başka bir dizinin bir kopyası yapmak için kullanabilirsiniz.

Oluşturucu:

`map(System::Collections::Generic::IEnumerable<Key>^ right);`

denetlenen sırayı, varsayılan sıralama koşulu ile Numaralandırıcı *hakkı*tarafından belirlenen sırayla başlatır. Denetim, varsayılan sıralama koşulu ile, bir Numaralandırıcı tarafından tanımlanan başka bir dizinin kopyasını oluşturmak için kullanılır.

Oluşturucu:

`map(System::Collections::Generic::IEnumerable<Key>^ right, key_compare^ pred);`

denetlenen diziyi Numaralandırıcı *hakkı*ile belirlenen sıra ile başlatır, sıralama koşulu *Pred*. Denetim, belirtilen sıralama koşulu ile bir Numaralandırıcı tarafından tanımlanan başka bir dizinin bir kopyasını oluşturmak için kullanılır.

### <a name="example"></a>Örnek

```cpp
// cliext_map_construct.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
int main()
    {
// construct an empty container
    Mymap c1;
    System::Console::WriteLine("size() = {0}", c1.size());

    c1.insert(Mymap::make_value(L'a', 1));
    c1.insert(Mymap::make_value(L'b', 2));
    c1.insert(Mymap::make_value(L'c', 3));
    for each (Mymap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // construct with an ordering rule
    Mymap c2 = cliext::greater_equal<wchar_t>();
    System::Console::WriteLine("size() = {0}", c2.size());

    c2.insert(c1.begin(), c1.end());
    for each (Mymap::value_type elem in c2)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // construct with an iterator range
    Mymap c3(c1.begin(), c1.end());
    for each (Mymap::value_type elem in c3)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // construct with an iterator range and an ordering rule
    Mymap c4(c1.begin(), c1.end(),
        cliext::greater_equal<wchar_t>());
    for each (Mymap::value_type elem in c4)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // construct with an enumeration
    Mymap c5(   // NOTE: cast is not needed
        (System::Collections::Generic::IEnumerable<
            Mymap::value_type>^)%c3);
    for each (Mymap::value_type elem in c5)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // construct with an enumeration and an ordering rule
    Mymap c6(   // NOTE: cast is not needed
        (System::Collections::Generic::IEnumerable<
            Mymap::value_type>^)%c3,
                cliext::greater_equal<wchar_t>());
    for each (Mymap::value_type elem in c6)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // construct by copying another container
    Mymap c7(c4);
    for each (Mymap::value_type elem in c7)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // construct by copying a container handle
    Mymap c8(%c3);
    for each (Mymap::value_type elem in c8)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
size() = 0
[a 1] [b 2] [c 3]
size() = 0
[c 3] [b 2] [a 1]
[a 1] [b 2] [c 3]
[c 3] [b 2] [a 1]
[a 1] [b 2] [c 3]
[c 3] [b 2] [a 1]
[c 3] [b 2] [a 1]
[a 1] [b 2] [c 3]
```

## <a name="mapmapped_type-stlclr"></a><a name="mapped_type"></a>Map:: mapped_type (STL/CLR)

Her bir anahtar ile ilişkili bir eşlenen değer türü.

### <a name="syntax"></a>Sözdizimi

```cpp
typedef Mapped mapped_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, *eşlenen*şablon parametresinin bir eş anlamlısıdır.

### <a name="example"></a>Örnek

```cpp
// cliext_map_mapped_type.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
int main()
    {
    Mymap c1;
    c1.insert(Mymap::make_value(L'a', 1));
    c1.insert(Mymap::make_value(L'b', 2));
    c1.insert(Mymap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]" using mapped_type
    for (Mymap::iterator it = c1.begin(); it != c1.end(); ++it)
        {   // store element in mapped_type object
        Mymap::mapped_type val = it->second;

        System::Console::Write("{0} ", val);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
1 2 3
```

## <a name="mapoperator-stlclr"></a><a name="op_as"></a>Map:: operator = (STL/CLR)

Denetlenen sırayı değiştirir.

### <a name="syntax"></a>Sözdizimi

```cpp
map<Key, Mapped>% operator=(map<Key, Mapped>% right);
```

#### <a name="parameters"></a>Parametreler

*Right*<br/>
Kopyalanacak kapsayıcı.

### <a name="remarks"></a>Açıklamalar

Üye işleci nesnesine *sağ* kopyalar ve ardından `*this`döndürür. Denetlenen diziyi, denetimli sıranın bir kopyasıyla değiştirmek için bunu *kullanırsınız.*

### <a name="example"></a>Örnek

```cpp
// cliext_map_operator_as.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
int main()
    {
    Mymap c1;
    c1.insert(Mymap::make_value(L'a', 1));
    c1.insert(Mymap::make_value(L'b', 2));
    c1.insert(Mymap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Mymap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // assign to a new container
    Mymap c2;
    c2 = c1;
    // display contents " [a 1] [b 2] [c 3]"
    for each (Mymap::value_type elem in c2)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
[a 1] [b 2] [c 3]
```

## <a name="mapoperatorstlclr"></a><a name="op"></a>Map:: operator (STL/CLR)

Bir anahtarı ilişkili eşlenmiş değerine eşler.

### <a name="syntax"></a>Sözdizimi

```cpp
mapped_type operator[](key_type key);
```

#### <a name="parameters"></a>Parametreler

*anahtar*<br/>
Aranacak anahtar değer.

### <a name="remarks"></a>Açıklamalar

Üye işlevleri, *anahtara*denk sıralama içeren bir öğe bulmak için endeavors. Bir bulursa, ilişkili eşlenmiş değeri döndürür; Aksi takdirde, `value_type(key, mapped_type())` ekler ve ilişkili (varsayılan) eşlenmiş değeri döndürür. Onunla ilişkili anahtarı verilen eşlenmiş bir değere bakmak ya da hiçbiri bulunmazsa anahtar için bir girdinin mevcut olduğundan emin olmak için bunu kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// cliext_map_operator_sub.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
int main()
    {
    Mymap c1;
    c1.insert(Mymap::make_value(L'a', 1));
    c1.insert(Mymap::make_value(L'b', 2));
    c1.insert(Mymap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Mymap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    System::Console::WriteLine("c1[{0}] = {1}",
        L'A', c1[L'A']);
    System::Console::WriteLine("c1[{0}] = {1}",
        L'b', c1[L'b']);

    // redisplay altered contents
    for each (Mymap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // alter mapped values and redisplay
    c1[L'A'] = 10;
    c1[L'c'] = 13;
    for each (Mymap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
c1[A] = 0
c1[b] = 2
[A 0] [a 1] [b 2] [c 3]
[A 10] [a 1] [b 2] [c 13]
```

## <a name="maprbegin-stlclr"></a><a name="rbegin"></a>Map:: rbegin (STL/CLR)

Ters denetlenen sıranın başlangıcını belirtir.

### <a name="syntax"></a>Sözdizimi

```cpp
reverse_iterator rbegin();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, denetimli sıranın son öğesini veya boş bir dizinin başlangıcının ötesinde bir ters yineleyici döndürür. Bu nedenle, ters sıranın `beginning` belirler. Bu uygulamayı, geriye doğru sırada görülen denetlenen sıranın başlangıcını `current` atayan bir yineleyici elde etmek için kullanırsınız, ancak denetlenen sıranın uzunluğu değişirse durum değişebilir.

### <a name="example"></a>Örnek

```cpp
// cliext_map_rbegin.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
int main()
    {
    Mymap c1;
    c1.insert(Mymap::make_value(L'a', 1));
    c1.insert(Mymap::make_value(L'b', 2));
    c1.insert(Mymap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Mymap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // inspect first two items in reversed sequence
    Mymap::reverse_iterator rit = c1.rbegin();
    System::Console::WriteLine("*rbegin() = [{0} {1}]",
        rit->first, rit->second);
    ++rit;
    System::Console::WriteLine("*++rbegin() = [{0} {1}]",
        rit->first, rit->second);
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
*rbegin() = [c 3]
*++rbegin() = [b 2]
```

## <a name="mapreference-stlclr"></a><a name="reference"></a>Map:: Reference (STL/CLR)

Bir öğe için bir başvuru türü.

### <a name="syntax"></a>Sözdizimi

```cpp
typedef value_type% reference;
```

### <a name="remarks"></a>Açıklamalar

Türü bir öğesi başvurusunu tanımlar.

### <a name="example"></a>Örnek

```cpp
// cliext_map_reference.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
int main()
    {
    Mymap c1;
    c1.insert(Mymap::make_value(L'a', 1));
    c1.insert(Mymap::make_value(L'b', 2));
    c1.insert(Mymap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    Mymap::iterator it = c1.begin();
    for (; it != c1.end(); ++it)
        {   // get a reference to an element
        Mymap::reference ref = *it;
        System::Console::Write("[{0} {1}] ", ref->first, ref->second);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
```

## <a name="maprend-stlclr"></a><a name="rend"></a>Map:: rend (STL/CLR)

Ters denetlenen sıranın sonunu belirtir.

### <a name="syntax"></a>Sözdizimi

```cpp
reverse_iterator rend();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, denetimli sıranın başlangıcının hemen ötesinde bir ters yineleyici döndürür. Bu nedenle, ters sıranın `end` belirler. Bu uygulamayı, geriye doğru sırada görülen denetlenen sıranın `current` sonunu atayan bir yineleyici elde etmek için kullanırsınız, ancak denetlenen sıranın uzunluğu değişirse durum değişebilir.

### <a name="example"></a>Örnek

```cpp
// cliext_map_rend.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
int main()
    {
    Mymap c1;
    c1.insert(Mymap::make_value(L'a', 1));
    c1.insert(Mymap::make_value(L'b', 2));
    c1.insert(Mymap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Mymap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // inspect first two items in reversed sequence
    Mymap::reverse_iterator rit = c1.rend();
    --rit;
    --rit;
    System::Console::WriteLine("*-- --rend() = [{0} {1}]",
        rit->first, rit->second);
    ++rit;
    System::Console::WriteLine("*--rend() = [{0} {1}]",
        rit->first, rit->second);
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
*-- --rend() = [b 2]
*--rend() = [a 1]
```

## <a name="mapreverse_iterator-stlclr"></a><a name="reverse_iterator"></a>Map:: reverse_iterator (STL/CLR)

Denetlenen sıra için ters yineleyicinin türü.

### <a name="syntax"></a>Sözdizimi

```
typedef T3 reverse_iterator;
```

### <a name="remarks"></a>Açıklamalar

Tür, denetlenen sıra için ters Yineleyici olarak kullanılabilecek belirtilmemiş türdeki bir nesneyi tanımlar `T3`.

### <a name="example"></a>Örnek

```cpp
// cliext_map_reverse_iterator.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
int main()
    {
    Mymap c1;
    c1.insert(Mymap::make_value(L'a', 1));
    c1.insert(Mymap::make_value(L'b', 2));
    c1.insert(Mymap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]" reversed
    Mymap::reverse_iterator rit = c1.rbegin();
    for (; rit != c1.rend(); ++rit)
        System::Console::Write("[{0} {1}] ", rit->first, rit->second);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
[c 3] [b 2] [a 1]
```

## <a name="mapsize-stlclr"></a><a name="size"></a>Map:: size (STL/CLR)

Öğe sayısını sayar.

### <a name="syntax"></a>Sözdizimi

```cpp
size_type size();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi denetlenen sıranın uzunluğunu döndürür. Bu, şu anda denetlenen dizideki öğelerin sayısını tespit etmek için kullanılır. Her şey için, sıranın sıfır dışında bir boyuta sahip olup olmadığı hakkında bilgi için bkz. [map:: Empty (STL/CLR)](../dotnet/map-empty-stl-clr.md)`()`.

### <a name="example"></a>Örnek

```cpp
// cliext_map_size.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
int main()
    {
    Mymap c1;
    c1.insert(Mymap::make_value(L'a', 1));
    c1.insert(Mymap::make_value(L'b', 2));
    c1.insert(Mymap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Mymap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // clear the container and reinspect
    c1.clear();
    System::Console::WriteLine("size() = {0} after clearing", c1.size());

    // add elements and clear again
    c1.insert(Mymap::make_value(L'd', 4));
    c1.insert(Mymap::make_value(L'e', 5));
    System::Console::WriteLine("size() = {0} after adding 2", c1.size());
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
size() = 0 after clearing
size() = 2 after adding 2
```

## <a name="mapsize_type-stlclr"></a><a name="size_type"></a>Map:: size_type (STL/CLR)

İki öğe arasındaki işaretli bir mesafe türü.

### <a name="syntax"></a>Sözdizimi

```cpp
typedef int size_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, negatif olmayan bir öğe sayısını tanımlar.

### <a name="example"></a>Örnek

```cpp
// cliext_map_size_type.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
int main()
    {
    Mymap c1;
    c1.insert(Mymap::make_value(L'a', 1));
    c1.insert(Mymap::make_value(L'b', 2));
    c1.insert(Mymap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Mymap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // compute positive difference
    Mymap::size_type diff = 0;
    for (Mymap::iterator it = c1.begin(); it != c1.end(); ++it)
        ++diff;
    System::Console::WriteLine("end()-begin() = {0}", diff);
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
end()-begin() = 3
```

## <a name="mapswap-stlclr"></a><a name="swap"></a>Map:: swap (STL/CLR)

İki kapsayıcının içeriğinin yerini değiştirir.

### <a name="syntax"></a>Sözdizimi

```cpp
void swap(map<Key, Mapped>% right);
```

#### <a name="parameters"></a>Parametreler

*Right*<br/>
İçeriği takas eden kapsayıcı.

### <a name="remarks"></a>Açıklamalar

Üye işlevi, `this` ve *sağ*arasındaki denetlenen dizileri değiştirir. Bu, sabit zamanlı olarak yapar ve özel durum oluşturmaz. Bunu iki kapsayıcının içeriğini değiş tokuş etmek için hızlı bir yol olarak kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// cliext_map_swap.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
int main()
    {
    Mymap c1;
    c1.insert(Mymap::make_value(L'a', 1));
    c1.insert(Mymap::make_value(L'b', 2));
    c1.insert(Mymap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Mymap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // construct another container with repetition of values
    Mymap c2;
    c2.insert(Mymap::make_value(L'd', 4));
    c2.insert(Mymap::make_value(L'e', 5));
    c2.insert(Mymap::make_value(L'f', 6));
    for each (Mymap::value_type elem in c2)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // swap and redisplay
    c1.swap(c2);
    for each (Mymap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    for each (Mymap::value_type elem in c2)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
[d 4] [e 5] [f 6]
[d 4] [e 5] [f 6]
[a 1] [b 2] [c 3]
```

## <a name="mapto_array-stlclr"></a><a name="to_array"></a>Map:: to_array (STL/CLR)

Denetimli sırayı yeni bir diziye kopyalar.

### <a name="syntax"></a>Sözdizimi

```cpp
cli::array<value_type>^ to_array();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi denetlenen sırayı içeren bir dizi döndürür. Dizi biçiminde denetlenen sıranın bir kopyasını almak için bunu kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// cliext_map_to_array.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
int main()
    {
    Mymap c1;
    c1.insert(Mymap::make_value(L'a', 1));
    c1.insert(Mymap::make_value(L'b', 2));
    c1.insert(Mymap::make_value(L'c', 3));

    // copy the container and modify it
    cli::array<Mymap::value_type>^ a1 = c1.to_array();

    c1.insert(Mymap::make_value(L'd', 4));
    for each (Mymap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // display the earlier array copy
    for each (Mymap::value_type elem in a1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3] [d 4]
[a 1] [b 2] [c 3]
```

## <a name="mapupper_bound-stlclr"></a><a name="upper_bound"></a>Map:: upper_bound (STL/CLR)

Belirtilen anahtarla eşleşen aralığın sonunu bulur.

### <a name="syntax"></a>Sözdizimi

```cpp
iterator upper_bound(key_type key);
```

#### <a name="parameters"></a>Parametreler

*anahtar*<br/>
Aranacak anahtar değer.

### <a name="remarks"></a>Açıklamalar

Üye işlevi, *anahtara*denk sıralama içeren kontrollü dizide `X` son öğeyi belirler. Böyle bir öğe yoksa veya denetlenen dizideki son öğe `X`, [map:: End (STL/CLR)](../dotnet/map-end-stl-clr.md)`()`döndürür. Aksi takdirde, `X`ötesinde ilk öğeyi atayan bir yineleyici döndürür. Belirtilen bir anahtarla eşleşen denetimli dizide bulunan bir öğe dizisinin sonunu bulmak için bunu kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// cliext_map_upper_bound.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
int main()
    {
    Mymap c1;
    c1.insert(Mymap::make_value(L'a', 1));
    c1.insert(Mymap::make_value(L'b', 2));
    c1.insert(Mymap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Mymap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    System::Console::WriteLine("upper_bound(L'x')==end() = {0}",
        c1.upper_bound(L'x') == c1.end());

    Mymap::iterator it = c1.upper_bound(L'a');
    System::Console::WriteLine("*upper_bound(L'a') = [{0} {1}]",
        it->first, it->second);
    it = c1.upper_bound(L'b');
    System::Console::WriteLine("*upper_bound(L'b') = [{0} {1}]",
        it->first, it->second);
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
upper_bound(L'x')==end() = True
*upper_bound(L'a') = [b 2]
*upper_bound(L'b') = [c 3]
```

## <a name="mapvalue_comp-stlclr"></a><a name="value_comp"></a>Map:: value_comp (STL/CLR)

İki öğe değeri için sıralama temsilcisini kopyalar.

### <a name="syntax"></a>Sözdizimi

```cpp
value_compare^ value_comp();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, denetimli sırayı sıralamak için kullanılan sıralama temsilcisini döndürür. İki öğe değerini karşılaştırmak için bunu kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// cliext_map_value_comp.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
int main()
    {
    Mymap c1;
    Mymap::value_compare^ kcomp = c1.value_comp();

    System::Console::WriteLine("compare([L'a', 1], [L'a', 1]) = {0}",
        kcomp(Mymap::make_value(L'a', 1),
            Mymap::make_value(L'a', 1)));
    System::Console::WriteLine("compare([L'a', 1], [L'b', 2]) = {0}",
        kcomp(Mymap::make_value(L'a', 1),
            Mymap::make_value(L'b', 2)));
    System::Console::WriteLine("compare([L'b', 2], [L'a', 1]) = {0}",
        kcomp(Mymap::make_value(L'b', 2),
            Mymap::make_value(L'a', 1)));
    System::Console::WriteLine();
    return (0);
    }
```

```Output
compare([L'a', 1], [L'a', 1]) = False
compare([L'a', 1], [L'b', 2]) = True
compare([L'b', 2], [L'a', 1]) = False
```

## <a name="mapvalue_compare-stlclr"></a><a name="value_compare"></a>Map:: value_compare (STL/CLR)

İki öğe değeri için sıralama temsilcisi.

### <a name="syntax"></a>Sözdizimi

```cpp
Microsoft::VisualC::StlClr::BinaryDelegate<generic_value, generic_value, bool>
    value_compare;
```

### <a name="remarks"></a>Açıklamalar

Tür, değer bağımsız değişkenlerinin sıralamasını belirleyen temsilcinin eşanlamlısıdır.

### <a name="example"></a>Örnek

```cpp
// cliext_map_value_compare.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
int main()
    {
    Mymap c1;
    Mymap::value_compare^ kcomp = c1.value_comp();

    System::Console::WriteLine("compare([L'a', 1], [L'a', 1]) = {0}",
        kcomp(Mymap::make_value(L'a', 1),
            Mymap::make_value(L'a', 1)));
    System::Console::WriteLine("compare([L'a', 1], [L'b', 2]) = {0}",
        kcomp(Mymap::make_value(L'a', 1),
            Mymap::make_value(L'b', 2)));
    System::Console::WriteLine("compare([L'b', 2], [L'a', 1]) = {0}",
        kcomp(Mymap::make_value(L'b', 2),
            Mymap::make_value(L'a', 1)));
    System::Console::WriteLine();
    return (0);
    }
```

```Output
compare([L'a', 1], [L'a', 1]) = False
compare([L'a', 1], [L'b', 2]) = True
compare([L'b', 2], [L'a', 1]) = False
```

## <a name="mapvalue_type-stlclr"></a><a name="value_type"></a>Map:: value_type (STL/CLR)

Öğenin türü.

### <a name="syntax"></a>Sözdizimi

```cpp
typedef generic_value value_type;
```

### <a name="remarks"></a>Açıklamalar

Tür `generic_value`için bir eş anlamlı.

### <a name="example"></a>Örnek

```cpp
// cliext_map_value_type.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
int main()
    {
    Mymap c1;
    c1.insert(Mymap::make_value(L'a', 1));
    c1.insert(Mymap::make_value(L'b', 2));
    c1.insert(Mymap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]" using value_type
    for (Mymap::iterator it = c1.begin(); it != c1.end(); ++it)
        {   // store element in value_type object
        Mymap::value_type val = *it;
        System::Console::Write("[{0} {1}] ", val->first, val->second);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
```

## <a name="operator-map-stlclr"></a><a name="op_neq"></a>işleç! = (eşleme) (STL/CLR)

Liste eşit değildir karşılaştırması.

### <a name="syntax"></a>Sözdizimi

```cpp
template<typename Key,
    typename Mapped>
    bool operator!=(map<Key, Mapped>% left,
        map<Key, Mapped>% right);
```

#### <a name="parameters"></a>Parametreler

*tarafta*<br/>
Karşılaştırılacak sol kapsayıcı.

*Right*<br/>
Karşılaştırılacak doğru kapsayıcı.

### <a name="remarks"></a>Açıklamalar

İşleç işlevi `!(left == right)`döndürür. İki harita öğe öğesine göre karşılaştırıldığı zaman, *sol* öğenin *doğru* şekilde sıralı olup olmadığını test etmek için kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// cliext_map_operator_ne.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
int main()
    {
    Mymap c1;
    c1.insert(Mymap::make_value(L'a', 1));
    c1.insert(Mymap::make_value(L'b', 2));
    c1.insert(Mymap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Mymap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // assign to a new container
    Mymap c2;
    c2.insert(Mymap::make_value(L'a', 1));
    c2.insert(Mymap::make_value(L'b', 2));
    c2.insert(Mymap::make_value(L'd', 4));

    // display contents " [a 1] [b 2] [d 4]"
    for each (Mymap::value_type elem in c2)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    System::Console::WriteLine("[a b c] != [a b c] is {0}",
        c1 != c1);
    System::Console::WriteLine("[a b c] != [a b d] is {0}",
        c1 != c2);
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
[a 1] [b 2] [d 4]
[a b c] != [a b c] is False
[a b c] != [a b d] is True
```

## <a name="operatorlt-map-stlclr"></a><a name="op_lt"></a>işleç&lt; (eşleme) (STL/CLR)

Liste karşılaştırmadan daha az.

### <a name="syntax"></a>Sözdizimi

```cpp
template<typename Key,
    typename Mapped>
    bool operator<(map<Key, Mapped>% left,
        map<Key, Mapped>% right);
```

#### <a name="parameters"></a>Parametreler

*tarafta*<br/>
Karşılaştırılacak sol kapsayıcı.

*Right*<br/>
Karşılaştırılacak doğru kapsayıcı.

### <a name="remarks"></a>Açıklamalar

İşleç işlevi true değerini döndürür, en düşük konum için de bu `!(right[i] < left[i])` `left[i] < right[i]`true `i`. Aksi takdirde, bu, iki harita öğe öğesine göre karşılaştırıldığı zaman, *sol taraftaki sola* *doğru sıralı* olup olmadığını test etmek için onu `left->size() < right->size()` döndürür.

### <a name="example"></a>Örnek

```cpp
// cliext_map_operator_lt.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
int main()
    {
    Mymap c1;
    c1.insert(Mymap::make_value(L'a', 1));
    c1.insert(Mymap::make_value(L'b', 2));
    c1.insert(Mymap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Mymap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // assign to a new container
    Mymap c2;
    c2.insert(Mymap::make_value(L'a', 1));
    c2.insert(Mymap::make_value(L'b', 2));
    c2.insert(Mymap::make_value(L'd', 4));

    // display contents " [a 1] [b 2] [d 4]"
    for each (Mymap::value_type elem in c2)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    System::Console::WriteLine("[a b c] < [a b c] is {0}",
        c1 < c1);
    System::Console::WriteLine("[a b c] < [a b d] is {0}",
        c1 < c2);
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
[a 1] [b 2] [d 4]
[a b c] < [a b c] is False
[a b c] < [a b d] is True
```

## <a name="operatorlt-map-stlclr"></a><a name="op_lteq"></a>işleç&lt;= (eşleme) (STL/CLR)

Küçüktür veya eşit karşılaştırma listesi.

### <a name="syntax"></a>Sözdizimi

```cpp
template<typename Key,
    typename Mapped>
    bool operator<=(map<Key, Mapped>% left,
        map<Key, Mapped>% right);
```

#### <a name="parameters"></a>Parametreler

*tarafta*<br/>
Karşılaştırılacak sol kapsayıcı.

*Right*<br/>
Karşılaştırılacak doğru kapsayıcı.

### <a name="remarks"></a>Açıklamalar

İşleç işlevi `!(right < left)`döndürür. Bu, iki harita öğe öğesine göre karşılaştırıldığı zaman *farenin sağ* *tarafında* sıralanmadığını test etmek için kullanılır.

### <a name="example"></a>Örnek

```cpp
// cliext_map_operator_le.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
int main()
    {
    Mymap c1;
    c1.insert(Mymap::make_value(L'a', 1));
    c1.insert(Mymap::make_value(L'b', 2));
    c1.insert(Mymap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Mymap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // assign to a new container
    Mymap c2;
    c2.insert(Mymap::make_value(L'a', 1));
    c2.insert(Mymap::make_value(L'b', 2));
    c2.insert(Mymap::make_value(L'd', 4));

    // display contents " [a 1] [b 2] [d 4]"
    for each (Mymap::value_type elem in c2)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    System::Console::WriteLine("[a b c] <= [a b c] is {0}",
        c1 <= c1);
    System::Console::WriteLine("[a b d] <= [a b c] is {0}",
        c2 <= c1);
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
[a 1] [b 2] [d 4]
[a b c] <= [a b c] is True
[a b d] <= [a b c] is False
```

## <a name="operator-map-stlclr"></a><a name="op_eq"></a>operator = = (Map) (STL/CLR)

Liste eşit karşılaştırması.

### <a name="syntax"></a>Sözdizimi

```cpp
template<typename Key,
    typename Mapped>
    bool operator==(map<Key, Mapped>% left,
        map<Key, Mapped>% right);
```

#### <a name="parameters"></a>Parametreler

*tarafta*<br/>
Karşılaştırılacak sol kapsayıcı.

*Right*<br/>
Karşılaştırılacak doğru kapsayıcı.

### <a name="remarks"></a>Açıklamalar

İşleç işlevi yalnızca *sol* ve *sağ* tarafından denetlenen diziler aynı uzunlukta ve her konum için `i``left[i] ==` `right[i]`için true değerini döndürür. İki harita öğe öğesine göre karşılaştırıldığı zaman *solinin* *doğru* olup olmadığını test etmek için bunu kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// cliext_map_operator_eq.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
int main()
    {
    Mymap c1;
    c1.insert(Mymap::make_value(L'a', 1));
    c1.insert(Mymap::make_value(L'b', 2));
    c1.insert(Mymap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Mymap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // assign to a new container
    Mymap c2;
    c2.insert(Mymap::make_value(L'a', 1));
    c2.insert(Mymap::make_value(L'b', 2));
    c2.insert(Mymap::make_value(L'd', 4));

    // display contents " [a 1] [b 2] [d 4]"
    for each (Mymap::value_type elem in c2)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    System::Console::WriteLine("[a b c] == [a b c] is {0}",
        c1 == c1);
    System::Console::WriteLine("[a b c] == [a b d] is {0}",
        c1 == c2);
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
[a 1] [b 2] [d 4]
[a b c] == [a b c] is True
[a b c] == [a b d] is False
```

## <a name="operatorgt-map-stlclr"></a><a name="op_gt"></a>işleç&gt; (eşleme) (STL/CLR)

Karşılaştırmadan daha büyük bir liste.

### <a name="syntax"></a>Sözdizimi

```cpp
template<typename Key,
    typename Mapped>
    bool operator>(map<Key, Mapped>% left,
        map<Key, Mapped>% right);
```

#### <a name="parameters"></a>Parametreler

*tarafta*<br/>
Karşılaştırılacak sol kapsayıcı.

*Right*<br/>
Karşılaştırılacak doğru kapsayıcı.

### <a name="remarks"></a>Açıklamalar

İşleç işlevi `right` `<` `left`döndürüyor. İki harita öğe öğesine göre karşılaştırıldığı zaman, *sol* *taraftaki bir* değer olup olmadığını test etmek için bunu kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// cliext_map_operator_gt.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
int main()
    {
    Mymap c1;
    c1.insert(Mymap::make_value(L'a', 1));
    c1.insert(Mymap::make_value(L'b', 2));
    c1.insert(Mymap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Mymap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // assign to a new container
    Mymap c2;
    c2.insert(Mymap::make_value(L'a', 1));
    c2.insert(Mymap::make_value(L'b', 2));
    c2.insert(Mymap::make_value(L'd', 4));

    // display contents " [a 1] [b 2] [d 4]"
    for each (Mymap::value_type elem in c2)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    System::Console::WriteLine("[a b c] > [a b c] is {0}",
        c1 > c1);
    System::Console::WriteLine("[a b d] > [a b c] is {0}",
        c2 > c1);
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
[a 1] [b 2] [d 4]
[a b c] > [a b c] is False
[a b d] > [a b c] is True
```

## <a name="operatorgt-map-stlclr"></a><a name="op_gteq"></a>işleç&gt;= (eşleme) (STL/CLR)

Büyük veya eşit karşılaştırmayı listele.

### <a name="syntax"></a>Sözdizimi

```cpp
template<typename Key,
    typename Mapped>
    bool operator>=(map<Key, Mapped>% left,
        map<Key, Mapped>% right);
```

#### <a name="parameters"></a>Parametreler

*tarafta*<br/>
Karşılaştırılacak sol kapsayıcı.

*Right*<br/>
Karşılaştırılacak doğru kapsayıcı.

### <a name="remarks"></a>Açıklamalar

İşleç işlevi `!(left` `<` `right)`döndürüyor. İki harita öğe öğesine göre karşılaştırıldığı zaman *sağdan* *sola* doğru sıralanmadığını test etmek için bunu kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// cliext_map_operator_ge.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
int main()
    {
    Mymap c1;
    c1.insert(Mymap::make_value(L'a', 1));
    c1.insert(Mymap::make_value(L'b', 2));
    c1.insert(Mymap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Mymap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // assign to a new container
    Mymap c2;
    c2.insert(Mymap::make_value(L'a', 1));
    c2.insert(Mymap::make_value(L'b', 2));
    c2.insert(Mymap::make_value(L'd', 4));

    // display contents " [a 1] [b 2] [d 4]"
    for each (Mymap::value_type elem in c2)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    System::Console::WriteLine("[a b c] >= [a b c] is {0}",
        c1 >= c1);
    System::Console::WriteLine("[a b c] >= [a b d] is {0}",
        c1 >= c2);
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
[a 1] [b 2] [d 4]
[a b c] >= [a b c] is True
[a b c] >= [a b d] is False
```
