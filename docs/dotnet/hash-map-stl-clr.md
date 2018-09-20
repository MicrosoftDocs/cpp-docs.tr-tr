---
title: hash_map (STL/CLR) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::hash_map
- cliext::hash_map::begin
- cliext::hash_map::bucket_count
- cliext::hash_map::clear
- cliext::hash_map::const_iterator
- cliext::hash_map::const_reference
- cliext::hash_map::const_reverse_iterator
- cliext::hash_map::count
- cliext::hash_map::difference_type
- cliext::hash_map::empty
- cliext::hash_map::end
- cliext::hash_map::equal_range
- cliext::hash_map::erase
- cliext::hash_map::find
- cliext::hash_map::generic_container
- cliext::hash_map::generic_iterator
- cliext::hash_map::generic_reverse_iterator
- cliext::hash_map::generic_value
- cliext::hash_map::hash_delegate
- cliext::hash_map::hash_map
- cliext::hash_map::hasher
- cliext::hash_map::insert
- cliext::hash_map::iterator
- cliext::hash_map::key_comp
- cliext::hash_map::key_compare
- cliext::hash_map::key_type
- cliext::hash_map::load_factor
- cliext::hash_map::lower_bound
- cliext::hash_map::make_value
- cliext::hash_map::mapped_type
- cliext::hash_map::max_load_factor
- cliext::hash_map::operator=
- cliext::hash_map::operator
- cliext::hash_map::rbegin
- cliext::hash_map::reference
- cliext::hash_map::rehash
- cliext::hash_map::rend
- cliext::hash_map::reverse_iterator
- cliext::hash_map::size
- cliext::hash_map::size_type
- cliext::hash_map::swap
- cliext::hash_map::to_array
- cliext::hash_map::upper_bound
- cliext::hash_map::value_comp
- cliext::hash_map::value_compare
- cliext::hash_map::value_type
dev_langs:
- C++
helpviewer_keywords:
- <cliext/hash_map> header [STL/CLR]
- <hash_map> header [STL/CLR]
- hash_map class [STL/CLR]
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
- hash_map member [STL/CLR]
- hasher member [STL/CLR]
- insert member [STL/CLR]
- iterator member [STL/CLR]
- key_comp member [STL/CLR]
- key_compare member [STL/CLR]
- key_type member [STL/CLR]
- load_factor member [STL/CLR]
- lower_bound member [STL/CLR]
- make_value member [STL/CLR]
- mapped_type member [STL/CLR]
- max_load_factor member [STL/CLR]
- operator= member [STL/CLR]
- operator member [STL/CLR]
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
ms.assetid: c3cfc69b-04c6-42ae-a30e-0eda953fe883
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 6c36f47f37809ff7e1aef6bf26b5c02043153ac3
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46404546"
---
# <a name="hashmap-stlclr"></a>hash_map (STL/CLR)

Şablon sınıfı, iki yönlü erişime sahip öğelerin değişen uzunluktaki dizisini denetleyen bir nesneyi tanımlar. Kapsayıcı kullandığınız `hash_map` öğeleri dizisi olarak bir karma tablo yönetmek için iki yönlü bir depolama her bir tablo girişi bağlı düğümleri ve bir öğe depolama her düğüm listesi. Bir öğe dizisi ve için kılma gider bir eşlenen değer sıralama için bir anahtar oluşur.

Aşağıdaki açıklamada `GValue` aynıdır:

`Microsoft::VisualC::StlClr::GenericPair<GKey, GMapped>`

burada:

`GKey` aynı `Key` ikinci bir başvuru türü olmadığı sürece olduğu durumda `Key^`

`GMapped` aynı `Mapped` ikinci bir başvuru türü olmadığı sürece olduğu durumda `Mapped^`

## <a name="syntax"></a>Sözdizimi

```cpp
template<typename Key,
    typename Mapped>
    ref class hash_map
        :   public
        System::ICloneable,
        System::Collections::IEnumerable,
        System::Collections::ICollection,
        System::Collections::Generic::IEnumerable<GValue>,
        System::Collections::Generic::ICollection<GValue>,
        System::Collections::Generic::IList<GValue>,
        System::Collections::Generic::IDictionary<Gkey, GMapped>,
        Microsoft::VisualC::StlClr::IHash<Gkey, GValue>
    { ..... };
```

### <a name="parameters"></a>Parametreler

*Key*<br/>
Denetlenen sıradaki öğenin anahtar bileşen türü.

*Eşlenen*<br/>
Ek bileşen denetlenen sıradaki öğenin türü.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<cliext/hash_map >

**Namespace:** cliext

## <a name="declarations"></a>Bildirimler

|Tür Tanımlaması|Açıklama|
|---------------------|-----------------|
|[hash_map::const_iterator (STL/CLR)](#const_iterator)|Denetlenen dizi için bir sabit yineleyici türü.|
|[hash_map::const_reference (STL/CLR)](#const_reference)|Bir öğe için sabit bir başvuru türü.|
|[hash_map::const_reverse_iterator (STL/CLR)](#const_reverse_iterator)|Denetlenen dizi için bir sabit ters yineleyici türü.|
|[hash_map::difference_type (STL/CLR)](#difference_type)|İki öğe arasındaki (büyük olasılıkla işaretli) mesafenin türü.|
|[hash_map::generic_container (STL/CLR)](#generic_container)|Kapsayıcı için genel arabirim türü.|
|[hash_map::generic_iterator (STL/CLR)](#generic_iterator)|Kapsayıcı için genel arabirimi için bir yineleyici türü.|
|[hash_map::generic_reverse_iterator (STL/CLR)](#generic_reverse_iterator)|Kapsayıcı için genel arabirimi için ters yineleyici türü.|
|[hash_map::generic_value (STL/CLR)](#generic_value)|Kapsayıcı için genel arabirimi için bir öğe türü.|
|[hash_map::hasher (STL/CLR)](#hasher)|Bir anahtarı karma temsilcisi.|
|[hash_map::iterator (STL/CLR)](#iterator)|Denetlenen dizi için bir yineleyici türü.|
|[hash_map::key_compare (STL/CLR)](#key_compare)|İki anahtar sıralama temsilcisi.|
|[hash_map::key_type (STL/CLR)](#key_type)|Bir sıralama anahtarının türü.|
|[hash_map::mapped_type (STL/CLR)](#mapped_type)|Her bir anahtar ile ilişkili bir eşlenen değer türü.|
|[hash_map::reference (STL/CLR)](#reference)|Bir öğe için bir başvuru türü.|
|[hash_map::reverse_iterator (STL/CLR)](#reverse_iterator)|Denetlenen dizi için bir ters yineleyici türü.|
|[hash_map::size_type (STL/CLR)](#size_type)|İki öğe arasındaki bir (negatif) mesafenin türü.|
|[hash_map::value_compare (STL/CLR)](#value_compare)|İki öğenin değerlerini sıralama temsilcisi.|
|[hash_map::value_type (STL/CLR)](#value_type)|Öğenin türü.|

|Üye İşlevi|Açıklama|
|---------------------|-----------------|
|[hash_map::begin (STL/CLR)](#begin)|Denetlenen dizinin başlangıcını belirtir.|
|[hash_map::bucket_count (STL/CLR)](#bucket_count)|Demet sayısını sayar.|
|[hash_map::clear (STL/CLR)](#clear)|Tüm öğeleri kaldırır.|
|[hash_map::count (STL/CLR)](#count)|Belirtilen bir anahtarla eşleşen öğeleri sayar.|
|[hash_map::empty (STL/CLR)](#empty)|Bir öğe olup olmadığını sınar.|
|[hash_map::end (STL/CLR)](#end)|Denetlenen dizinin bitişini belirtir.|
|[hash_map::equal_range (STL/CLR)](#equal_range)|Belirtilen bir anahtarla eşleşen aralığı bulur.|
|[hash_map::erase (STL/CLR)](#erase)|Belirtilen konumlardaki öğeleri kaldırır.|
|[hash_map::find (STL/CLR)](#find)|Belirtilen bir anahtarla eşleşen bir öğeyi bulur.|
|[hash_map::hash_delegate (STL/CLR)](#hash_delegate)|Bir anahtarı karma temsilcisi kopyalar.|
|[hash_map::hash_map (STL/CLR)](#hash_map)|Bir kapsayıcı nesnesi oluşturur.|
|[hash_map::insert (STL/CLR)](#insert)|Öğeleri ekler.|
|[hash_map::key_comp (STL/CLR)](#key_comp)|İki anahtar sıralama temsilcisi kopyalar.|
|[hash_map::load_factor (STL/CLR)](#load_factor)|Demet başına ortalama öğeyi sayar.|
|[hash_map::lower_bound (STL/CLR)](#lower_bound)|Belirtilen bir anahtarla eşleşen aralığı başlangıcını bulur.|
|[hash_map::make_value (STL/CLR)](#make_value)|Değer bir nesne oluşturur.|
|[hash_map::max_load_factor (STL/CLR)](#max_load_factor)|Demet başına en yüksek öğe sayısını alır veya ayarlar.|
|[hash_map::rbegin (STL/CLR)](#rbegin)|Ters çevrilen denetlenen dizinin başlangıç belirler.|
|[hash_map::rehash (STL/CLR)](#rehash)|Karma tabloyu yeniden oluşturur.|
|[hash_map::rend (STL/CLR)](#rend)|Ters çevrilen denetlenen dizinin sonuna belirler.|
|[hash_map::size (STL/CLR)](#size)|Öğe sayısını sayar.|
|[hash_map::swap (STL/CLR)](#swap)|İki kapsayıcının içeriğinin yerini değiştirir.|
|[hash_map::to_array (STL/CLR)](#to_array)|Denetlenen dizideki, yeni bir diziye kopyalar.|
|[hash_map::upper_bound (STL/CLR)](#upper_bound)|Belirtilen bir anahtarla eşleşen aralığı sonu bulur.|
|[hash_map::value_comp (STL/CLR)](#value_comp)|İki öğenin değerlerini sıralama temsilcisi kopyalar.|

|İşleç|Açıklama|
|--------------|-----------------|
|[hash_map::operator= (STL/CLR)](#op_as)|Denetlenen dizi değiştirir.|
|[hash_map::operator(STL/CLR)](#op)|Bir anahtar için ilişkili eşlenen değeri eşler.|

## <a name="interfaces"></a>Arabirimler

|Arabirim|Açıklama|
|---------------|-----------------|
|<xref:System.ICloneable>|Bir nesne çoğaltın.|
|<xref:System.Collections.IEnumerable>|Öğeleri dizisi.|
|<xref:System.Collections.ICollection>|Öğe grubunu koruyun.|
|<xref:System.Collections.Generic.IEnumerable%601>|Türü belirtilmiş öğelerini dizisi.|
|<xref:System.Collections.Generic.ICollection%601>|Türü belirtilmiş bir öğe grubunu koruyun.|
|<xref:System.Collections.Generic.IDictionary%602>|{Değer, key} grubu korumak çiftleri.|
|IHash < anahtar, değer >|Genel kapsayıcı korur.|

## <a name="remarks"></a>Açıklamalar

Nesne ayırır ve depolama için bağlı bir çift yönlü bir liste içinde tek tek düğümleri olarak diziyi serbest bırakır. Erişim hızlandırmak için nesne de listesinin tümünü alt listelerin, bir dizi etkin şekilde yönetme işaretçileri (karma tablosu), listeye bir değişen uzunluktaki dizisini korur veya demetlerine. Sıralı tutan bir düğüm içeriğini diğerine kopyalama tarafından hiçbir zaman düğümleri arasındaki bağlantıları değiştirerek bir demet öğeleri ekler. Bu, ekleyin ve özgürce rahatsız edici kalan öğeleri olmadan öğeleri kaldırın anlamına gelir.

Nesne türünde bir saklı temsilci nesnesi çağırarak denetlediği her bir demete siparişleri [hash_set::key_compare (STL/CLR)](../dotnet/hash-set-key-compare-stl-clr.md). Hash_set oluştururken saklı temsilci nesnesi belirtebilirsiniz; hiçbir temsilci nesnesi belirtirseniz, karşılaştırma varsayılandır `operator<=(key_type, key_type)`.

Üye işlevini çağırarak depolanan temsilci nesneye erişim [hash_set::key_comp (STL/CLR)](../dotnet/hash-set-key-comp-stl-clr.md)`()`. Bu tür bir temsilci nesnesinin anahtarları türünde arasında eşdeğer sıralamaya tanımlamalıdır [hash_set::key_type (STL/CLR)](../dotnet/hash-set-key-type-stl-clr.md). Anlamına gelir, için iki anahtar `X` ve `Y`:

`key_comp()(X, Y)` Her çağrıda aynı Boolean sonucu döndürür.

Varsa `key_comp()(X, Y) && key_comp()(Y, X)` true ise `X` ve `Y` eşdeğer sıralamaya olduğu söylenir.

Gibi davranan bir sıralama kuralı `operator<=(key_type, key_type)`, `operator>=(key_type, key_type)` veya `operator==(key_type, key_type)` eqivalent sıralamasını tanımlar.

Kapsayıcı yalnızca öğeleri anahtarları, eşdeğer sıralamaya sahip (ve hangi karma aynı tam sayı değerine) bir demette bitişik olmasını sağlar, unutmayın. Şablon sınıfının aksine [hash_multimap (STL/CLR)](../dotnet/hash-multimap-stl-clr.md), şablon sınıfın bir nesnesi `hash_map` anahtarları tüm öğeler için benzersiz olmasını sağlar. (Hiçbir iki anahtarları, eşdeğer sıralamaya sahip.)

Hangi demet türü depolanan bir temsilci nesnesinin çağırarak belirli bir sıralama anahtarı içermelidir nesneyi belirleyen [hash_set::hasher (STL/CLR)](../dotnet/hash-set-hasher-stl-clr.md). Üye işlevini çağırarak depolanan bu nesne erişim [hash_set::hash_delegate (STL/CLR)](../dotnet/hash-set-hash-delegate-stl-clr.md) `()` anahtar değerine bağlı bir tamsayı değeri elde edilir. Hash_set oluştururken saklı temsilci nesnesi belirtebilirsiniz; hiçbir temsilci nesnesi belirtirseniz, varsayılan işlevi olduğu `System::Object::hash_value(key_type)`. Anlamına gelir, herhangi bir anahtarı `X` ve `Y`:

`hash_delegate()(X)` Her çağrıda aynı tamsayı sonuç döndürür.

Varsa `X` ve `Y` eşdeğer, ardından sıralamaya sahip `hash_delegate()(X)` aynı tamsayı sonucu döndürmelidir `hash_delegate()(Y)`.

Her öğe ayrı bir anahtar ve eşleşen bir değer içerir. Sıra, arama, ekleme ve kaldırma örneklerinin en iyisi, (sabit zaman)--dizideki öğelerin sayısından bağımsız olan en az bir dizi işlemi ile rastgele bir öğenin izin veren bir şekilde temsil edilir. Ayrıca, bir öğe eklenmesi hiçbir yineleyiciyi geçersiz kılmaz; bir öğenin kaldırılması yalnızca bu kaldırılan öğeyi gösteren yineleyicileri geçersiz kılar.

Karma değerler aynı şekilde dağıtılmaz, ancak bir karma tablo bozuk. Extreme--her zaman aynı değer döndüren bir karma işlevi için arama, ekleme ve kaldırma orantılı dizideki (doğrusal zaman) öğelerin sayısı. Makul bir karma işlevi, ortalama kova boyutu seçmek kapsayıcı endeavors ve karma tablo boyutu (toplam demet sayısı), ancak bu seçenek bir bölümünü veya tamamını geçersiz kılabilirsiniz. Örneğin, işlevleri görmek [hash_set::max_load_factor (STL/CLR)](../dotnet/hash-set-max-load-factor-stl-clr.md) ve [hash_set::rehash (STL/CLR)](../dotnet/hash-set-rehash-stl-clr.md).

Denetlenen dizideki bir öğeyi belirleyen bir yineleyici verilen bitişik öğelere adım anlamına gelir. bir hash_map, çift yönlü yineleyiciler destekler. Özel bir baş düğüm tarafından döndürülen yineleyici karşılık gelen [hash_map::end (STL/CLR)](../dotnet/hash-map-end-stl-clr.md)`()`. Denetlenen dizi içindeki son öğeden ulaşmak için bu yineleyici varsa azaltma. Baş düğüm ulaşmaya hash_map yineleyici artırabilirsiniz ve bu sonra eşittir karşılaştıracağız `end()`. Ancak tarafından döndürülen yineleyici başvurulamıyor `end()`.

Doğrudan bir rastgele erişim yineleyici gerektiren sayısal konumunu--verilen hash_map öğesine başvuramaz unutmayın.

Sırayla ilişkilendirilmiş kapsayıcısı için bir tanıtıcı depolar, ilişkili hash_map düğümü için bir tanıtıcı hash_map yineleyici depolar. Yineleyiciler yalnızca ilişkili kapsayıcı nesneleri ile kullanabilirsiniz. Hash_map Yineleyici, onun ilişkili hash_map düğümü bazı hash_map ile ilişkili olduğu sürece geçerli kalır. Ayrıca, geçerli bir yineleyici yineleyicisine--erişmek veya eşit değildir sürece bu atayan--öğe değeri değiştirmek için kullanabilirsiniz `end()`.

Silme veya bir öğenin kaldırılması için depolanan değerine yıkıcı çağırır. Kapsayıcı yok etme tüm öğelerini siler. Bu nedenle, hiçbir öğe'nin kapsayıcı daha uzun sürmesi başvuru sınıfı, öğe türü olan bir kapsayıcı sağlar. Ancak, bir kapsayıcı tutamaçlarından yaptığı unutmayın *değil* öğelerini yok edin.

## <a name="members"></a>Üyeler

## <a name="begin"></a> hash_map::Begin (STL/CLR)

Denetlenen dizinin başlangıcını belirtir.

### <a name="syntax"></a>Sözdizimi

```cpp
iterator begin();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, denetlenen dizinin ya da boş bir dizi bitiminin ötesinde yalnızca ilk öğeyi belirleyen çift yönlü bir yineleyici döndürür. Gösteren bir yineleyici almak için kullandığınız `current` denetlenen dizideki ancak durumu başına denetlenen dizinin uzunluğu değişirse değiştirebilirsiniz.

### <a name="example"></a>Örnek

```cpp
// cliext_hash_map_begin.cpp
// compile with: /clr
#include <cliext/hash_map>

typedef cliext::hash_map<wchar_t, int> Myhash_map;
int main()
    {
    Myhash_map c1;
    c1.insert(Myhash_map::make_value(L'a', 1));
    c1.insert(Myhash_map::make_value(L'b', 2));
    c1.insert(Myhash_map::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Myhash_map::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // inspect first two items
    Myhash_map::iterator it = c1.begin();
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

## <a name="bucket_count"></a> hash_map::bucket_count (STL/CLR)

Demet sayısını sayar.

### <a name="syntax"></a>Sözdizimi

```cpp
int bucket_count();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevleri, geçerli demet sayısını döndürür. Karma tablo boyutunu belirlemek için kullanın.

### <a name="example"></a>Örnek

```cpp
// cliext_hash_map_bucket_count.cpp
// compile with: /clr
#include <cliext/hash_map>

typedef cliext::hash_map<wchar_t, int> Myhash_map;
int main()
    {
    Myhash_map c1 = gcnew Myhash_map;
    c1.insert(Myhash_map::make_value(L'a', 1));
    c1.insert(Myhash_map::make_value(L'b', 2));
    c1.insert(Myhash_map::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Myhash_map::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
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
[a 1] [b 2] [c 3]
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

## <a name="clear"></a> hash_map::Clear (STL/CLR)

Tüm öğeleri kaldırır.

### <a name="syntax"></a>Sözdizimi

```cpp
void clear();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi etkili bir şekilde çağıran [hash_map::erase (STL/CLR)](../dotnet/hash-map-erase-stl-clr.md) `(` [hash_map::begin (STL/CLR)](../dotnet/hash-map-begin-stl-clr.md) `(),` [hash_map::end (STL/CLR)](../dotnet/hash-map-end-stl-clr.md) `())`. Denetlenen dizi boş olduğundan emin olmak için kullanın.

### <a name="example"></a>Örnek

```cpp
// cliext_hash_map_clear.cpp
// compile with: /clr
#include <cliext/hash_map>

typedef cliext::hash_map<wchar_t, int> Myhash_map;
int main()
    {
    Myhash_map c1;
    c1.insert(Myhash_map::make_value(L'a', 1));
    c1.insert(Myhash_map::make_value(L'b', 2));
    c1.insert(Myhash_map::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Myhash_map::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // clear the container and reinspect
    c1.clear();
    System::Console::WriteLine("size() = {0}", c1.size());

    c1.insert(Myhash_map::make_value(L'a', 1));
    c1.insert(Myhash_map::make_value(L'b', 2));

    // display contents " [a 1] [b 2]"
    for each (Myhash_map::value_type elem in c1)
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

## <a name="const_iterator"></a> hash_map::const_iterator (STL/CLR)

Denetlenen dizi için bir sabit yineleyici türü.

### <a name="syntax"></a>Sözdizimi

```cpp
typedef T2 const_iterator;
```

### <a name="remarks"></a>Açıklamalar

Bilinmeyen türde bir nesne tanımlayan bir tür `T2` denetlenen dizi için sabit bir çift yönlü bir yineleyici olarak verebilir.

### <a name="example"></a>Örnek

```cpp
// cliext_hash_map_const_iterator.cpp
// compile with: /clr
#include <cliext/hash_map>

typedef cliext::hash_map<wchar_t, int> Myhash_map;
int main()
    {
    Myhash_map c1;
    c1.insert(Myhash_map::make_value(L'a', 1));
    c1.insert(Myhash_map::make_value(L'b', 2));
    c1.insert(Myhash_map::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    Myhash_map::const_iterator cit = c1.begin();
    for (; cit != c1.end(); ++cit)
        System::Console::Write("[{0} {1}] ", cit->first, cit->second);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
```

## <a name="const_reference"></a> hash_map::const_reference (STL/CLR)

Bir öğe için sabit bir başvuru türü.

### <a name="syntax"></a>Sözdizimi

```cpp
typedef value_type% const_reference;
```

### <a name="remarks"></a>Açıklamalar

Bir öğe için sabit bir başvuru türü açıklar.

### <a name="example"></a>Örnek

```cpp
// cliext_hash_map_const_reference.cpp
// compile with: /clr
#include <cliext/hash_map>

typedef cliext::hash_map<wchar_t, int> Myhash_map;
int main()
    {
    Myhash_map c1;
    c1.insert(Myhash_map::make_value(L'a', 1));
    c1.insert(Myhash_map::make_value(L'b', 2));
    c1.insert(Myhash_map::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    Myhash_map::const_iterator cit = c1.begin();
    for (; cit != c1.end(); ++cit)
        {   // get a const reference to an element
        Myhash_map::const_reference cref = *cit;
        System::Console::Write("[{0} {1}] ", cref->first, cref->second);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
```

## <a name="const_reverse_iterator"></a> hash_map::const_reverse_iterator (STL/CLR)

Denetlenen dizi için bir sabit ters yineleyici türü...

### <a name="syntax"></a>Sözdizimi

```cpp
typedef T4 const_reverse_iterator;
```

### <a name="remarks"></a>Açıklamalar

Bilinmeyen türde bir nesne tanımlayan bir tür `T4` denetlenen dizi için bir sabit ters yineleyici olarak verebilir.

### <a name="example"></a>Örnek

```cpp
// cliext_hash_map_const_reverse_iterator.cpp
// compile with: /clr
#include <cliext/hash_map>

typedef cliext::hash_map<wchar_t, int> Myhash_map;
int main()
    {
    Myhash_map c1;
    c1.insert(Myhash_map::make_value(L'a', 1));
    c1.insert(Myhash_map::make_value(L'b', 2));
    c1.insert(Myhash_map::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]" reversed
    Myhash_map::const_reverse_iterator crit = c1.rbegin();
    for (; crit != c1.rend(); ++crit)
        System::Console::Write("[{0} {1}] ", crit->first, crit->second);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
[c 3] [b 2] [a 1]
```

## <a name="count"></a> hash_map::Count (STL/CLR)

Belirtilen bir anahtar ile eşleşen öğe sayısını bulur.

### <a name="syntax"></a>Sözdizimi

```cpp
size_type count(key_type key);
```

#### <a name="parameters"></a>Parametreler

*Anahtarı*<br/>
Aranacak anahtar değeri.

### <a name="remarks"></a>Açıklamalar

Üye işlevi ile eşdeğer sıralamaya sahip denetlenen dizideki öğelerin sayısını döndürür. *anahtar*. Belirtilen bir anahtarla eşleşen şu anda denetlenen dizideki öğelerin sayısını belirlemek için kullanın.

### <a name="example"></a>Örnek

```cpp
// cliext_hash_map_count.cpp
// compile with: /clr
#include <cliext/hash_map>

typedef cliext::hash_map<wchar_t, int> Myhash_map;
int main()
    {
    Myhash_map c1;
    c1.insert(Myhash_map::make_value(L'a', 1));
    c1.insert(Myhash_map::make_value(L'b', 2));
    c1.insert(Myhash_map::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Myhash_map::value_type elem in c1)
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

## <a name="difference_type"></a> hash_map::difference_type (STL/CLR)

İki öğe arasındaki işaretli mesafenin türü.

### <a name="syntax"></a>Sözdizimi

```cpp
typedef int difference_type;
```

### <a name="remarks"></a>Açıklamalar

Büyük olasılıkla negatif öğe sayısını tanımlayan bir tür.

### <a name="example"></a>Örnek

```cpp
// cliext_hash_map_difference_type.cpp
// compile with: /clr
#include <cliext/hash_map>

typedef cliext::hash_map<wchar_t, int> Myhash_map;
int main()
    {
    Myhash_map c1;
    c1.insert(Myhash_map::make_value(L'a', 1));
    c1.insert(Myhash_map::make_value(L'b', 2));
    c1.insert(Myhash_map::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Myhash_map::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // compute positive difference
    Myhash_map::difference_type diff = 0;
    for (Myhash_map::iterator it = c1.begin(); it != c1.end(); ++it)
        ++diff;
    System::Console::WriteLine("end()-begin() = {0}", diff);

    // compute negative difference
    diff = 0;
    for (Myhash_map::iterator it = c1.end(); it != c1.begin(); --it)
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

## <a name="empty"></a> hash_map::Empty (STL/CLR)

Bir öğe olup olmadığını sınar.

### <a name="syntax"></a>Sözdizimi

```cpp
bool empty();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi boş bir denetlenmiş dizi için true değerini döndürür. Eşdeğerdir [hash_map::size (STL/CLR)](../dotnet/hash-map-size-stl-clr.md)`() == 0`. Hash_map boş olup olmadığını sınamak için kullanın.

### <a name="example"></a>Örnek

```cpp
// cliext_hash_map_empty.cpp
// compile with: /clr
#include <cliext/hash_map>

typedef cliext::hash_map<wchar_t, int> Myhash_map;
int main()
    {
    Myhash_map c1;
    c1.insert(Myhash_map::make_value(L'a', 1));
    c1.insert(Myhash_map::make_value(L'b', 2));
    c1.insert(Myhash_map::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Myhash_map::value_type elem in c1)
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

## <a name="end"></a> hash_map::End (STL/CLR)

Denetlenen dizinin bitişini belirtir.

### <a name="syntax"></a>Sözdizimi

```cpp
iterator end();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, denetlenen dizinin sonuna hemen ötesine işaret eden çift yönlü bir yineleyici döndürür. Denetlenen dizinin sonuna belirten bir yineleyici almak için kullanın. kendi durum eklenmemişse denetlenen dizinin uzunluğu değişirse değiştiremezsiniz.

### <a name="example"></a>Örnek

```cpp
// cliext_hash_map_end.cpp
// compile with: /clr
#include <cliext/hash_map>

typedef cliext::hash_map<wchar_t, int> Myhash_map;
int main()
    {
    Myhash_map c1;
    c1.insert(Myhash_map::make_value(L'a', 1));
    c1.insert(Myhash_map::make_value(L'b', 2));
    c1.insert(Myhash_map::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Myhash_map::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // inspect last two items
    Myhash_map::iterator it = c1.end();
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

```Output
[a 1] [b 2] [c 3]
*-- --end() = [b 2]
*--end() = [c 3]
```

## <a name="equal_range"></a> hash_map::equal_range (STL/CLR)

Belirtilen bir anahtarla eşleşen aralığı bulur.

### <a name="syntax"></a>Sözdizimi

```cpp
cliext::pair<iterator, iterator> equal_range(key_type key);
```

#### <a name="parameters"></a>Parametreler

*Anahtarı*<br/>
Aranacak anahtar değeri.

### <a name="remarks"></a>Açıklamalar

Üye işlevi Yineleyicilerin bir çiftini döndürür `cliext::pair<iterator, iterator>(lower_bound(key), upper_bound(key))`. Belirtilen bir anahtarla eşleşen öğeleri şu anda denetlenen dizideki aralığı belirlemek için kullanın.

### <a name="example"></a>Örnek

```cpp
// cliext_hash_map_equal_range.cpp
// compile with: /clr
#include <cliext/hash_map>

typedef cliext::hash_map<wchar_t, int> Myhash_map;
typedef Myhash_map::pair_iter_iter Pairii;
int main()
    {
    Myhash_map c1;
    c1.insert(Myhash_map::make_value(L'a', 1));
    c1.insert(Myhash_map::make_value(L'b', 2));
    c1.insert(Myhash_map::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Myhash_map::value_type elem in c1)
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

## <a name="erase"></a> hash_map::ERASE (STL/CLR)

Belirtilen konumlardaki öğeleri kaldırır.

### <a name="syntax"></a>Sözdizimi

```cpp
iterator erase(iterator where);
iterator erase(iterator first, iterator last);
bool erase(key_type key)
```

#### <a name="parameters"></a>Parametreler

*ilk*<br/>
Silme aralığını başlangıcı.

*Anahtarı*<br/>
Silinecek anahtar değer.

*Son*<br/>
Silinecek aralığı sonu.

*Burada*<br/>
Silinecek öğe.

### <a name="remarks"></a>Açıklamalar

İlk üye işlevi tarafından denetlenen dizinin öğeyi kaldırır *burada*ve kaldırıldı, öğenin dışında kalan ilk öğeyi belirleyen bir yineleyici döndürür veya [hash_map::end (STL / CLR)](../dotnet/hash-map-end-stl-clr.md) `()` böyle bir öğe varsa. Tek bir öğe kaldırmak için kullanın.

İkinci üye işlevi öğeleri denetlenen dizinin aralıktaki kaldırır. [`first`, `last`) ve kaldırılan tüm öğelerin ötesindeki ilk öğeyi belirleyen bir yineleyici döndürür veya `end()` böyle bir öğe varsa var... Sıfır veya daha fazla ardışık öğeleri kaldırmak için kullanın.

Üçüncü üye işlevi olan anahtara sahip eşdeğer sıralamaya denetlenen dizideki herhangi bir öğe kaldırır için *anahtarı*ve kaldırılan öğelerin sayısını döndürür. Kaldırın ve belirtilen bir anahtarla eşleşen tüm öğeleri saymak için kullanın.

Her öğe silinme için öğelerin sayısını logaritmasını orantılı zaman denetlenen dizide alır.

### <a name="example"></a>Örnek

```cpp
// cliext_hash_map_erase.cpp
// compile with: /clr
#include <cliext/hash_map>

typedef cliext::hash_map<wchar_t, int> Myhash_map;
int main()
    {
    cliext::hash_map<wchar_t, int> c1;
    c1.insert(cliext::hash_map<wchar_t, int>::make_value(L'a', 1));
    c1.insert(cliext::hash_map<wchar_t, int>::make_value(L'b', 2));
    c1.insert(cliext::hash_map<wchar_t, int>::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (cliext::hash_map<wchar_t, int>::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // erase an element and reinspect
    cliext::hash_map<wchar_t, int>::iterator it =
        c1.erase(c1.begin());
    System::Console::WriteLine("erase(begin()) = [{0} {1}]",
        it->first, it->second);

    // add elements and display " b c d e"
    c1.insert(cliext::hash_map<wchar_t, int>::make_value(L'd', 4));
    c1.insert(cliext::hash_map<wchar_t, int>::make_value(L'e', 5));
    for each (cliext::hash_map<wchar_t, int>::value_type elem in c1)
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

## <a name="find"></a> hash_map::Find (STL/CLR)

Belirtilen bir anahtarla eşleşen bir öğeyi bulur.

### <a name="syntax"></a>Sözdizimi

```cpp
iterator find(key_type key);
```

#### <a name="parameters"></a>Parametreler

*Anahtarı*<br/>
Aranacak anahtar değeri.

### <a name="remarks"></a>Açıklamalar

Denetlenen dizideki en az bir öğe ile eşdeğer sıralamaya sahipse *anahtarı*, üye işlevi biri bu öğeleri gösteren bir yineleyici döndürür; Aksi halde döndürür [hash_map::end (STL/CLR)](../dotnet/hash-map-end-stl-clr.md)`()`. Bir öğe şu anda belirtilen bir anahtarla eşleşen denetlenen dizide bulmak için kullanın.

### <a name="example"></a>Örnek

```cpp
// cliext_hash_map_find.cpp
// compile with: /clr
#include <cliext/hash_map>

typedef cliext::hash_map<wchar_t, int> Myhash_map;
int main()
    {
    Myhash_map c1;
    c1.insert(Myhash_map::make_value(L'a', 1));
    c1.insert(Myhash_map::make_value(L'b', 2));
    c1.insert(Myhash_map::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Myhash_map::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    System::Console::WriteLine("find {0} = {1}",
        L'A', c1.find(L'A') != c1.end());

    Myhash_map::iterator it = c1.find(L'b');
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

## <a name="generic_container"></a> hash_map::generic_container (STL/CLR)

Kapsayıcı için genel arabirim türü.

### <a name="syntax"></a>Sözdizimi

```cpp
typedef Microsoft::VisualC::StlClr::
    IHash<GKey, GValue>
    generic_container;
```

### <a name="remarks"></a>Açıklamalar

Bu şablon kapsayıcı sınıfı için genel arabirim tanımlayan bir tür.

### <a name="example"></a>Örnek

```cpp
// cliext_hash_map_generic_container.cpp
// compile with: /clr
#include <cliext/hash_map>

typedef cliext::hash_map<wchar_t, int> Myhash_map;
int main()
    {
    Myhash_map c1;
    c1.insert(Myhash_map::make_value(L'a', 1));
    c1.insert(Myhash_map::make_value(L'b', 2));
    c1.insert(Myhash_map::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Myhash_map::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // construct a generic container
    Myhash_map::generic_container^ gc1 = %c1;
    for each (Myhash_map::value_type elem in gc1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // modify generic and display original
    gc1->insert(Myhash_map::make_value(L'd', 4));
    for each (Myhash_map::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // modify original and display generic
    c1.insert(Myhash_map::make_value(L'e', 5));
    for each (Myhash_map::value_type elem in gc1)
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

## <a name="generic_iterator"></a> hash_map::generic_iterator (STL/CLR)

Kapsayıcı için genel arabirimi ile kullanmak için bir yineleyici türü.

### <a name="syntax"></a>Sözdizimi

```cpp
typedef Microsoft::VisualC::StlClr::Generic::
    ContainerBidirectionalIterator<generic_value>
    generic_iterator;
```

### <a name="remarks"></a>Açıklamalar

Genel arabirim ile bu şablon kapsayıcı sınıfı için kullanılabilecek genel bir yineleyici türü açıklar.

### <a name="example"></a>Örnek

```cpp
// cliext_hash_map_generic_iterator.cpp
// compile with: /clr
#include <cliext/hash_map>

typedef cliext::hash_map<wchar_t, int> Myhash_map;
int main()
    {
    Myhash_map c1;
    c1.insert(Myhash_map::make_value(L'a', 1));
    c1.insert(Myhash_map::make_value(L'b', 2));
    c1.insert(Myhash_map::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Myhash_map::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // construct a generic container
    Myhash_map::generic_container^ gc1 = %c1;
    for each (Myhash_map::value_type elem in gc1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // get an element and display it
    Myhash_map::generic_iterator gcit = gc1->begin();
    Myhash_map::generic_value gcval = *gcit;
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

## <a name="generic_reverse_iterator"></a> hash_map::generic_reverse_iterator (STL/CLR)

Kapsayıcı için genel arabirimi ile kullanmak için bir ters yineleyici türü.

### <a name="syntax"></a>Sözdizimi

```cpp
typedef Microsoft::VisualC::StlClr::Generic::
    ReverseRandomAccessIterator<generic_value>
    generic_reverse_iterator;
```

### <a name="remarks"></a>Açıklamalar

Genel arabirim ile bu şablon kapsayıcı sınıfı için kullanılabilecek genel bir ters yineleyici türü açıklar.

### <a name="example"></a>Örnek

```cpp
// cliext_hash_map_generic_reverse_iterator.cpp
// compile with: /clr
#include <cliext/hash_map>

typedef cliext::hash_map<wchar_t, int> Myhash_map;
int main()
    {
    Myhash_map c1;
    c1.insert(Myhash_map::make_value(L'a', 1));
    c1.insert(Myhash_map::make_value(L'b', 2));
    c1.insert(Myhash_map::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Myhash_map::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // construct a generic container
    Myhash_map::generic_container^ gc1 = %c1;
    for each (Myhash_map::value_type elem in gc1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // get an element and display it
    Myhash_map::generic_reverse_iterator gcit = gc1->rbegin();
    Myhash_map::generic_value gcval = *gcit;
    System::Console::WriteLine("[{0} {1}] ", gcval->first, gcval->second);
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
[a 1] [b 2] [c 3]
[c 3]
```

## <a name="generic_value"></a> hash_map::generic_value (STL/CLR)

Kapsayıcı için genel arabirimi ile kullanmak için bir öğe türü.

### <a name="syntax"></a>Sözdizimi

```cpp
typedef GValue generic_value;
```

### <a name="remarks"></a>Açıklamalar

Türünde bir nesneyi tanımlayan bir tür `GValue` açıklayan yönelik genel arabirimi için bu şablonu kapsayıcı sınıfı ile kullanmak için depolanan öğenin değeri.

### <a name="example"></a>Örnek

```cpp
// cliext_hash_map_generic_value.cpp
// compile with: /clr
#include <cliext/hash_map>

typedef cliext::hash_map<wchar_t, int> Myhash_map;
int main()
    {
    Myhash_map c1;
    c1.insert(Myhash_map::make_value(L'a', 1));
    c1.insert(Myhash_map::make_value(L'b', 2));
    c1.insert(Myhash_map::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Myhash_map::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // construct a generic container
    Myhash_map::generic_container^ gc1 = %c1;
    for each (Myhash_map::value_type elem in gc1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // get an element and display it
    Myhash_map::generic_iterator gcit = gc1->begin();
    Myhash_map::generic_value gcval = *gcit;
    System::Console::WriteLine("[{0} {1}] ", gcval->first, gcval->second);
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
[a 1] [b 2] [c 3]
[a 1]
```

## <a name="hash_delegate"></a> hash_map::hash_delegate (STL/CLR)

Belirtilen bir anahtarla eşleşen bir öğeyi bulur.

### <a name="syntax"></a>Sözdizimi

```cpp
hasher^ hash_delegate();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi bir anahtar değeri bir tamsayıya dönüştürmek için kullanılan temsilci döndürür. Bir anahtar karması için kullanın.

### <a name="example"></a>Örnek

```cpp
// cliext_hash_map_hash_delegate.cpp
// compile with: /clr
#include <cliext/hash_map>

typedef cliext::hash_map<wchar_t, int> Myhash_map;
int main()
    {
    Myhash_map c1;
    Myhash_map::hasher^ myhash = c1.hash_delegate();

    System::Console::WriteLine("hash(L'a') = {0}", myhash(L'a'));
    System::Console::WriteLine("hash(L'b') = {0}", myhash(L'b'));
    return (0);
    }
```

```Output
hash(L'a') = 1616896120
hash(L'b') = 570892832
```

## <a name="hash_map"></a> hash_map::hash_map (STL/CLR)

Bir kapsayıcı nesnesi oluşturur.

### <a name="syntax"></a>Sözdizimi

```cpp
hash_map();
explicit hash_map(key_compare^ pred);
hash_map(key_compare^ pred, hasher^ hashfn);
hash_map(hash_map<Key, Mapped>% right);
hash_map(hash_map<Key, Mapped>^ right);
template<typename InIter>
    hash_maphash_map(InIter first, InIter last);
template<typename InIter>
    hash_map(InIter first, InIter last,
        key_compare^ pred);
template<typename InIter>
    hash_map(InIter first, InIter last,
        key_compare^ pred, hasher^ hashfn);
hash_map(System::Collections::Generic::IEnumerable<GValue>^ right);
hash_map(System::Collections::Generic::IEnumerable<GValue>^ right,
    key_compare^ pred);
hash_map(System::Collections::Generic::IEnumerable<GValue>^ right,
    key_compare^ pred, hasher^ hashfn);
```

#### <a name="parameters"></a>Parametreler

*ilk*<br/>
Eklenecek Aralık başlangıcı.

*hashfn*<br/>
İşlev eşleme anahtarlarını demet için karma.

*Son*<br/>
Eklenecek aralık sonu.

*Pred*<br/>
Denetlenen dizi için koşul sıralaması.

*sağ*<br/>
Nesne veya eklenecek aralık.

### <a name="remarks"></a>Açıklamalar

Oluşturucu:

`hash_map();`

Varsayılan karşılaştırma sıralama ile denetlenen dizideki herhangi bir öğesi ile başlatır `key_compare()`ve varsayılan karma işlevi ile. Varsayılan sıralama koşulu ve karma işlevi ile bir boş ilk denetlenen sıra belirtmek için kullanın.

Oluşturucu:

`explicit hash_map(key_compare^ pred);`

Denetlenen dizi sıralama koşul ile hiçbir öğe ile başlatır *pred*ve varsayılan karma işlevi ile. Belirtilen sıralama önerme ve varsayılan karma işlevi ile bir boş ilk denetlenen sıra belirtmek için kullanın.

Oluşturucu:

`hash_map(key_compare^ pred, hasher^ hashfn);`

Denetlenen dizi sıralama koşul ile hiçbir öğe ile başlatır *pred*ve karma işlevi ile *hashfn*. Belirtilen sıralama koşulu ve karma işlevi ile bir boş ilk denetlenen sıra belirtmek için kullanın.

Oluşturucu:

`hash_map(hash_map<Key, Mapped>% right);`

Denetlenen dizi sırası başlatır [`right.begin()`, `right.end()`), koşul sıralama varsayılan ve varsayılan karma işlevi ile. Hash_map nesnesi tarafından denetlenen dizinin bir kopyasını olan ilk denetimli bir sıra belirtmek için kullandığınız *doğru*, karma işlevi ve varsayılan sıralama koşul.

Oluşturucu:

`hash_map(hash_map<Key, Mapped>^ right);`

Denetlenen dizi sırası başlatır [`right->begin()`, `right->end()`), koşul sıralama varsayılan ve varsayılan karma işlevi ile. Hash_map nesnesi tarafından denetlenen dizinin bir kopyasını olan ilk denetimli bir sıra belirtmek için kullandığınız *doğru*, karma işlevi ve varsayılan sıralama koşul.

Oluşturucu:

`template<typename InIter> hash_map(InIter first, InIter last);`

Denetlenen dizi sırası başlatır [`first`, `last`), koşul sıralama varsayılan ve varsayılan karma işlevi ile. Denetlenen dizi başka bir dizinin bir kopyasını varsayılan karşılaştırma ve karma işlevi sıralama yapmak için kullanın.

Oluşturucu:

`template<typename InIter> hash_map(InIter first, InIter last, key_compare^ pred);`

Denetlenen dizi sırası başlatır [`first`, `last`), sıralama koşul ile *pred*ve varsayılan karma işlevi ile. Denetlenen dizi belirtilen sıralama önerme ve varsayılan karma işlevi ile başka bir sıralı bir kopyasını kullanın.

Oluşturucu:

`template<typename InIter> hash_map(InIter first, InIter last, key_compare^ pred, hasher^ hashfn);`

Denetlenen dizi sırası başlatır [`first`, `last`), sıralama koşul ile *pred*ve karma işlevi ile *hashfn*. Denetlenen dizi belirtilen sıralama koşulu ve karma işlevi ile başka bir sıralı bir kopyasını kullanın.

Oluşturucu:

`hash_map(System::Collections::Generic::IEnumerable<Key>^ right);`

Denetlenen dizi numaralandırıcı tarafından belirtilen sıra başlatır *doğru*, koşul sıralama varsayılan ve varsayılan karma işlevi ile. Denetlenen dizi başka bir sıralı karşılaştırma ve karma işlevi sıralama varsayılan bir numaralandırıcı tarafından açıklanan bir kopyasını kullanın.

Oluşturucu:

`hash_map(System::Collections::Generic::IEnumerable<Key>^ right, key_compare^ pred);`

Denetlenen dizi numaralandırıcı tarafından belirtilen sıra başlatır *doğru*, sıralama koşul ile *pred*ve varsayılan karma işlevi ile. Denetlenen dizi, başka bir dizisi tarafından belirtilen sıralama koşulu ve varsayılan karma işlevi ile bir numaralandırıcı açıklanan kopyasını kullanın.

Oluşturucu:

`hash_map(System::Collections::Generic::IEnumerable<Key>^ right, key_compare^ pred, hasher^ hashfn);`

Denetlenen dizi numaralandırıcı tarafından belirtilen sıra başlatır *doğru*, sıralama koşul ile *pred*ve karma işlevi ile *hashfn*. Denetlenen dizi, başka bir dizisi tarafından belirtilen sıralama koşulu ve karma işlevi ile bir numaralandırıcı açıklanan kopyasını kullanın.

### <a name="example"></a>Örnek

```cpp
// cliext_hash_map_construct.cpp
// compile with: /clr
#include <cliext/hash_map>

int myfun(wchar_t key)
    { // hash a key
    return (key ^ 0xdeadbeef);
    }

typedef cliext::hash_map<wchar_t, int> Myhash_map;
int main()
    {
// construct an empty container
    Myhash_map c1;
    System::Console::WriteLine("size() = {0}", c1.size());

    c1.insert(Myhash_map::make_value(L'a', 1));
    c1.insert(Myhash_map::make_value(L'b', 2));
    c1.insert(Myhash_map::make_value(L'c', 3));
    for each (Myhash_map::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // construct with an ordering rule
    Myhash_map c2 = cliext::greater_equal<wchar_t>();
    System::Console::WriteLine("size() = {0}", c2.size());

    c2.insert(c1.begin(), c1.end());
    for each (Myhash_map::value_type elem in c2)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // construct with an ordering rule and hash function
    Myhash_map c2h(cliext::greater_equal<wchar_t>(),
        gcnew Myhash_map::hasher(&myfun));
    System::Console::WriteLine("size() = {0}", c2h.size());

    c2h.insert(c1.begin(), c1.end());
    for each (Myhash_map::value_type elem in c2h)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();
    System::Console::WriteLine();

    // construct with an iterator range
    Myhash_map c3(c1.begin(), c1.end());
    for each (Myhash_map::value_type elem in c3)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // construct with an iterator range and an ordering rule
    Myhash_map c4(c1.begin(), c1.end(),
        cliext::greater_equal<wchar_t>());
    for each (Myhash_map::value_type elem in c4)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // construct with an iterator range and an ordering rule and hash function
    Myhash_map c4h(c1.begin(), c1.end(),
        cliext::greater_equal<wchar_t>(),
        gcnew Myhash_map::hasher(&myfun));
    for each (Myhash_map::value_type elem in c4h)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();
    System::Console::WriteLine();

    // construct with an enumeration
    Myhash_map c5(   // NOTE: cast is not needed
        (System::Collections::Generic::IEnumerable<
            Myhash_map::value_type>^)%c3);
    for each (Myhash_map::value_type elem in c5)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // construct with an enumeration and an ordering rule
    Myhash_map c6(   // NOTE: cast is not needed
        (System::Collections::Generic::IEnumerable<
            Myhash_map::value_type>^)%c3,
                cliext::greater_equal<wchar_t>());
    for each (Myhash_map::value_type elem in c6)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // construct with an enumeration and an ordering rule and hash function
    Myhash_map c6h(   // NOTE: cast is not needed
        (System::Collections::Generic::IEnumerable<
            Myhash_map::value_type>^)%c3,
                cliext::greater_equal<wchar_t>(),
                gcnew Myhash_map::hasher(&myfun));
    for each (Myhash_map::value_type elem in c6h)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();
    System::Console::WriteLine();

    // construct by copying another container
    Myhash_map c7(c4);
    for each (Myhash_map::value_type elem in c7)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // construct by copying a container handle
    Myhash_map c8(%c3);
    for each (Myhash_map::value_type elem in c8)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
size() = 0
[a 1] [b 2] [c 3]
size() = 0
[a 1] [b 2] [c 3]
size() = 0
[c 3] [b 2] [a 1]

[a 1] [b 2] [c 3]
[a 1] [b 2] [c 3]
[c 3] [b 2] [a 1]

[a 1] [b 2] [c 3]
[a 1] [b 2] [c 3]
[c 3] [b 2] [a 1]

[a 1] [b 2] [c 3]
[a 1] [b 2] [c 3]
```

## <a name="hasher"></a> hash_map::hasher (STL/CLR)

Bir anahtarı karma temsilcisi.

### <a name="syntax"></a>Sözdizimi

```cpp
Microsoft::VisualC::StlClr::UnaryDelegate<GKey, int>
    hasher;
```

### <a name="remarks"></a>Açıklamalar

Bir anahtar değeri bir tamsayıya dönüştürür bir temsilci türü açıklar.

### <a name="example"></a>Örnek

```cpp
// cliext_hash_map_hasher.cpp
// compile with: /clr
#include <cliext/hash_map>

typedef cliext::hash_map<wchar_t, int> Myhash_map;
int main()
    {
    Myhash_map c1;
    Myhash_map::hasher^ myhash = c1.hash_delegate();

    System::Console::WriteLine("hash(L'a') = {0}", myhash(L'a'));
    System::Console::WriteLine("hash(L'b') = {0}", myhash(L'b'));
    return (0);
    }
```

```Output
hash(L'a') = 1616896120
hash(L'b') = 570892832
```

## <a name="insert"></a> hash_map::insert (STL/CLR)

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

*ilk*<br/>
Eklenecek Aralık başlangıcı.

*Son*<br/>
Eklenecek aralık sonu.

*sağ*<br/>
Eklemek için sabit listesi.

*VAL*<br/>
Eklenecek anahtar değeri.

*Burada*<br/>
WHERE (yalnızca ipucu) eklemek için kapsayıcı.

### <a name="remarks"></a>Açıklamalar

Üye işlevlerin her biri, diğer işlenen tarafından belirtilen bir dizisi ekler.

İlk üye işlevi endeavors değere sahip bir öğe eklemek `val`ve bir değer çiftini döndürür `X`. Varsa `X.second` true ise `X.first` yeni eklenen öğeyi belirler; Aksi takdirde `X.first` eşdeğer olan bir öğeyi belirleyen sıralama zaten var ve yeni bir öğe yok eklenir. Tek bir öğe eklemek için kullanın.

İkinci üye işlevi değere sahip bir öğe ekler *val*kullanarak *burada* (performansını artırmak için) bir ipucu olarak ve yeni eklenen öğeyi belirleyen bir yineleyici döndürür. Bildiğiniz bir öğeye bitişik olabilecek tek bir öğe eklemek için kullanın.

Üçüncü üye işlevi ekler dizisi [`first`, `last`). Başka bir diziden kopyalanan sıfır veya daha fazla öğe eklemek için kullanın.

Dördüncü üye işlevi tarafından belirlenen dizisi ekler *doğru*. Bir numaralandırıcı tarafından açıklanan bir dizi eklemek için kullanın.

Her öğe ekleme, denetlenen dizide öğe sayısı için logaritmasını orantılı zaman alır. Ekleme, ekleme noktasını bitişik bir öğeyi belirleyen bir ipucu verilen amorti edilmiş sabit sürede bir ancak ortaya çıkabilir.

### <a name="example"></a>Örnek

```cpp
// cliext_hash_map_insert.cpp
// compile with: /clr
#include <cliext/hash_map>

typedef cliext::hash_map<wchar_t, int> Myhash_map;
typedef Myhash_map::pair_iter_bool Pairib;
int main()
    {
    Myhash_map c1;
    c1.insert(Myhash_map::make_value(L'a', 1));
    c1.insert(Myhash_map::make_value(L'b', 2));
    c1.insert(Myhash_map::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Myhash_map::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // insert a single value, unique and duplicate
    Pairib pair1 =
        c1.insert(Myhash_map::make_value(L'x', 24));
    System::Console::WriteLine("insert([L'x' 24]) = [{0} {1}] {2}",
        pair1.first->first, pair1.first->second, pair1.second);

    pair1 = c1.insert(Myhash_map::make_value(L'b', 2));
    System::Console::WriteLine("insert([L'b' 2]) = [{0} {1}] {2}",
        pair1.first->first, pair1.first->second, pair1.second);

    for each (Myhash_map::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // insert a single value with hint
    Myhash_map::iterator it =
        c1.insert(c1.begin(), Myhash_map::make_value(L'y', 25));
    System::Console::WriteLine("insert(begin(), [L'y' 25]) = [{0} {1}]",
        it->first, it->second);
    for each (Myhash_map::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // insert an iterator range
    Myhash_map c2;
    it = c1.end();
    c2.insert(c1.begin(), --it);
    for each (Myhash_map::value_type elem in c2)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // insert an enumeration
    Myhash_map c3;
    c3.insert(   // NOTE: cast is not needed
        (System::Collections::Generic::
            IEnumerable<Myhash_map::value_type>^)%c1);
    for each (Myhash_map::value_type elem in c3)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
insert([L'x' 24]) = [x 24] True
insert([L'b' 2]) = [b 2] False
[a 1] [b 2] [c 3] [x 24]
insert(begin(), [L'y' 25]) = [y 25]
[a 1] [b 2] [c 3] [x 24] [y 25]
[a 1] [b 2] [c 3] [x 24]
[a 1] [b 2] [c 3] [x 24] [y 25]
```

## <a name="iterator"></a> hash_map::iterator (STL/CLR)

Denetlenen dizi için bir yineleyici türü.

### <a name="syntax"></a>Sözdizimi

```cpp
typedef T1 iterator;
```

### <a name="remarks"></a>Açıklamalar

Bilinmeyen türde bir nesne tanımlayan bir tür `T1` denetlenen dizi için çift yönlü bir yineleyici olarak verebilir.

### <a name="example"></a>Örnek

```cpp
// cliext_hash_map_iterator.cpp
// compile with: /clr
#include <cliext/hash_map>

typedef cliext::hash_map<wchar_t, int> Myhash_map;
int main()
    {
    Myhash_map c1;
    c1.insert(Myhash_map::make_value(L'a', 1));
    c1.insert(Myhash_map::make_value(L'b', 2));
    c1.insert(Myhash_map::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    Myhash_map::iterator it = c1.begin();
    for (; it != c1.end(); ++it)
        System::Console::Write("[{0} {1}] ", it->first, it->second);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
```

## <a name="key_comp"></a> hash_map::key_comp (STL/CLR)

İki anahtar sıralama temsilcisi kopyalar.

### <a name="syntax"></a>Sözdizimi

```cpp
key_compare^key_comp();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi denetlenen diziyi sıralamak için kullanılan sıralama temsilci döndürür. İki anahtar karşılaştırmak için kullanın.

### <a name="example"></a>Örnek

```cpp
// cliext_hash_map_key_comp.cpp
// compile with: /clr
#include <cliext/hash_map>

typedef cliext::hash_map<wchar_t, int> Myhash_map;
int main()
    {
    Myhash_map c1;
    Myhash_map::key_compare^ kcomp = c1.key_comp();

    System::Console::WriteLine("compare(L'a', L'a') = {0}",
        kcomp(L'a', L'a'));
    System::Console::WriteLine("compare(L'a', L'b') = {0}",
        kcomp(L'a', L'b'));
    System::Console::WriteLine("compare(L'b', L'a') = {0}",
        kcomp(L'b', L'a'));
    System::Console::WriteLine();

    // test a different ordering rule
    Myhash_map c2 = cliext::greater<wchar_t>();
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

## <a name="key_compare"></a> hash_map::key_compare (STL/CLR)

İki anahtar sıralama temsilcisi.

### <a name="syntax"></a>Sözdizimi

```cpp
Microsoft::VisualC::StlClr::BinaryDelegate<GKey, GKey, bool>
    key_compare;
```

### <a name="remarks"></a>Açıklamalar

Türü, sıralama anahtarı, bağımsız değişkenleri belirler temsilci eşanlamlıdır.

### <a name="example"></a>Örnek

```cpp
// cliext_hash_map_key_compare.cpp
// compile with: /clr
#include <cliext/hash_map>

typedef cliext::hash_map<wchar_t, int> Myhash_map;
int main()
    {
    Myhash_map c1;
    Myhash_map::key_compare^ kcomp = c1.key_comp();

    System::Console::WriteLine("compare(L'a', L'a') = {0}",
        kcomp(L'a', L'a'));
    System::Console::WriteLine("compare(L'a', L'b') = {0}",
        kcomp(L'a', L'b'));
    System::Console::WriteLine("compare(L'b', L'a') = {0}",
        kcomp(L'b', L'a'));
    System::Console::WriteLine();

    // test a different ordering rule
    Myhash_map c2 = cliext::greater<wchar_t>();
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

## <a name="key_type"></a> hash_map::key_type (STL/CLR)

Bir sıralama anahtarının türü.

### <a name="syntax"></a>Sözdizimi

```cpp
typedef Key key_type;
```

### <a name="remarks"></a>Açıklamalar

Şablon parametresi için bir eşanlamlı türüdür *anahtar*.

### <a name="example"></a>Örnek

```cpp
// cliext_hash_map_key_type.cpp
// compile with: /clr
#include <cliext/hash_map>

typedef cliext::hash_map<wchar_t, int> Myhash_map;
int main()
    {
    Myhash_map c1;
    c1.insert(Myhash_map::make_value(L'a', 1));
    c1.insert(Myhash_map::make_value(L'b', 2));
    c1.insert(Myhash_map::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]" using key_type
    for (Myhash_map::iterator it = c1.begin(); it != c1.end(); ++it)
        {   // store element in key_type object
        Myhash_map::key_type val = it->first;

        System::Console::Write("{0} ", val);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="load_factor"></a> hash_map::load_factor (STL/CLR)

Demet başına ortalama öğeyi sayar.

### <a name="syntax"></a>Sözdizimi

```cpp
float load_factor();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevinin döndürdüğü `(float)` [hash_map::size (STL/CLR)](../dotnet/hash-map-size-stl-clr.md) `() /` [hash_map::bucket_count (STL/CLR)](../dotnet/hash-map-bucket-count-stl-clr.md)`()`. Ortalama demet boyutunu belirlemek için kullanın.

### <a name="example"></a>Örnek

```cpp
// cliext_hash_map_load_factor.cpp
// compile with: /clr
#include <cliext/hash_map>

typedef cliext::hash_map<wchar_t, int> Myhash_map;
int main()
    {
    Myhash_map c1 = gcnew Myhash_map;
    c1.insert(Myhash_map::make_value(L'a', 1));
    c1.insert(Myhash_map::make_value(L'b', 2));
    c1.insert(Myhash_map::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Myhash_map::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
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
[a 1] [b 2] [c 3]
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

## <a name="lower_bound"></a> hash_map::lower_bound (STL/CLR)

Belirtilen bir anahtarla eşleşen aralığı başlangıcını bulur.

### <a name="syntax"></a>Sözdizimi

```cpp
iterator lower_bound(key_type key);
```

#### <a name="parameters"></a>Parametreler

*Anahtarı*<br/>
Aranacak anahtar değeri.

### <a name="remarks"></a>Açıklamalar

Üye işlevi ilk öğeyi belirleyen `X` aynı Demetin karıştırır denetlenen dizideki *anahtarı* ve için eşdeğer sıralamaya sahip *anahtar*. Böyle bir öğe var olup olmadığını döndürür [hash_map::end (STL/CLR)](../dotnet/hash-map-end-stl-clr.md)`()`; Aksi halde gösteren bir yineleyici döndürür `X`. Bir dizi öğe başına şu anda belirtilen bir anahtarla eşleşen denetlenen dizide bulmak için kullanın.

### <a name="example"></a>Örnek

```cpp
// cliext_hash_map_lower_bound.cpp
// compile with: /clr
#include <cliext/hash_map>

typedef cliext::hash_map<wchar_t, int> Myhash_map;
int main()
    {
    Myhash_map c1;
    c1.insert(Myhash_map::make_value(L'a', 1));
    c1.insert(Myhash_map::make_value(L'b', 2));
    c1.insert(Myhash_map::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Myhash_map::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    System::Console::WriteLine("lower_bound(L'x')==end() = {0}",
        c1.lower_bound(L'x') == c1.end());

    Myhash_map::iterator it = c1.lower_bound(L'a');
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

## <a name="make_value"></a> hash_map::make_value (STL/CLR)

Değer bir nesne oluşturur.

### <a name="syntax"></a>Sözdizimi

```cpp
static value_type make_value(key_type key, mapped_type mapped);
```

#### <a name="parameters"></a>Parametreler

*Anahtarı*<br/>
Kullanılacak anahtar değeri.

*Eşlenen*<br/>
Aranacak eşlenen değer.

### <a name="remarks"></a>Açıklamalar

Üye işlevi döndürür bir `value_type` nesne anahtarı *anahtarı* ve eşlenen değeri *eşlenen*. Çeşitli üye işlevleri ile kullanım için uygun bir nesne oluşturmak için kullanın.

### <a name="example"></a>Örnek

```cpp
// cliext_hash_map_make_value.cpp
// compile with: /clr
#include <cliext/hash_map>

typedef cliext::hash_map<wchar_t, int> Myhash_map;
int main()
    {
    Myhash_map c1;
    c1.insert(Myhash_map::make_value(L'a', 1));
    c1.insert(Myhash_map::make_value(L'b', 2));
    c1.insert(Myhash_map::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Myhash_map::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
```

## <a name="mapped_type"></a> hash_map::mapped_type (STL/CLR)

Her bir anahtar ile ilişkili bir eşlenen değer türü.

### <a name="syntax"></a>Sözdizimi

```cpp
typedef Mapped mapped_type;
```

### <a name="remarks"></a>Açıklamalar

Şablon parametresi için bir eşanlamlı türüdür `Mapped`.

### <a name="example"></a>Örnek

```cpp
// cliext_hash_map_mapped_type.cpp
// compile with: /clr
#include <cliext/hash_map>

typedef cliext::hash_map<wchar_t, int> Myhash_map;
int main()
    {
    Myhash_map c1;
    c1.insert(Myhash_map::make_value(L'a', 1));
    c1.insert(Myhash_map::make_value(L'b', 2));
    c1.insert(Myhash_map::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]" using mapped_type
    for (Myhash_map::iterator it = c1.begin(); it != c1.end(); ++it)
        {   // store element in mapped_type object
        Myhash_map::mapped_type val = it->second;

        System::Console::Write("{0} ", val);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
1 2 3
```

## <a name="max_load_factor"></a> hash_map::max_load_factor (STL/CLR)

Demet başına en yüksek öğe sayısını alır veya ayarlar.

### <a name="syntax"></a>Sözdizimi

```cpp
float max_load_factor();
void max_load_factor(float new_factor);
```

#### <a name="parameters"></a>Parametreler

*new_factor*<br/>
Yeni en büyük faktör depolamak için yükleyin.

### <a name="remarks"></a>Açıklamalar

İlk üye işlevi, geçerli depolanan en yüksek yük faktörünün döndürür. En yüksek ortalama demet boyutunu belirlemek için kullanın.

İkinci üye işlevi ile mağaza en yüksek yük faktörünün değiştirir *new_factor*. Hiçbir otomatik rehashing kadar bir sonraki INSERT gerçekleşir.

### <a name="example"></a>Örnek

```cpp
// cliext_hash_map_max_load_factor.cpp
// compile with: /clr
#include <cliext/hash_map>

typedef cliext::hash_map<wchar_t, int> Myhash_map;
int main()
    {
    Myhash_map c1 = gcnew Myhash_map;
    c1.insert(Myhash_map::make_value(L'a', 1));
    c1.insert(Myhash_map::make_value(L'b', 2));
    c1.insert(Myhash_map::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Myhash_map::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
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
[a 1] [b 2] [c 3]
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

## <a name="op_as"></a> hash_map::operator (STL/CLR) =

Denetlenen dizi değiştirir.

### <a name="syntax"></a>Sözdizimi

```cpp
hash_map<Key, Mapped>% operator=(hash_map<Key, Mapped>% right);
```

#### <a name="parameters"></a>Parametreler

*sağ*<br/>
Kopyalanacak kapsayıcı.

### <a name="remarks"></a>Açıklamalar

Üye işleci kopyaları *doğru* ardından nesneye döndürür `*this`. Denetlenen dizi denetlenen dizide bir kopyasını değiştirmek için kullandığınız *doğru*.

### <a name="example"></a>Örnek

```cpp
// cliext_hash_map_operator_as.cpp
// compile with: /clr
#include <cliext/hash_map>

typedef cliext::hash_map<wchar_t, int> Myhash_map;
int main()
    {
    Myhash_map c1;
    c1.insert(Myhash_map::make_value(L'a', 1));
    c1.insert(Myhash_map::make_value(L'b', 2));
    c1.insert(Myhash_map::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Myhash_map::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // assign to a new container
    Myhash_map c2;
    c2 = c1;
// display contents " [a 1] [b 2] [c 3]"
    for each (Myhash_map::value_type elem in c2)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
[a 1] [b 2] [c 3]
```

## <a name="op"></a> hash_map::operator(stl/CLR)

Bir anahtar için ilişkili eşlenen değeri eşler.

### <a name="syntax"></a>Sözdizimi

```cpp
mapped_type operator[](key_type key);
```

#### <a name="parameters"></a>Parametreler

*Anahtarı*<br/>
Aranacak anahtar değeri.

### <a name="remarks"></a>Açıklamalar

Çalışmaları için eşdeğer sıralamaya sahip öğeyi bulma için üye işlevlerini *anahtar*. Bu biri bulunursa, ilişkili bir eşlenen değer döndürür; Aksi takdirde ekler `value_type(key, mapped_type())` ve ilişkili döndürür (varsayılan) eşlenen değeri. Verilen anahtarıyla eşleşen bir değeri aramak için veya bulunamazsa anahtarı için bir giriş var. olmak için kullanın.

### <a name="example"></a>Örnek

```cpp
// cliext_hash_map_operator_sub.cpp
// compile with: /clr
#include <cliext/hash_map>

typedef cliext::hash_map<wchar_t, int> Myhash_map;
int main()
    {
    Myhash_map c1;
    c1.insert(Myhash_map::make_value(L'a', 1));
    c1.insert(Myhash_map::make_value(L'b', 2));
    c1.insert(Myhash_map::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Myhash_map::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    System::Console::WriteLine("c1[{0}] = {1}",
        L'A', c1[L'A']);
    System::Console::WriteLine("c1[{0}] = {1}",
        L'b', c1[L'b']);

    // redisplay altered contents
    for each (Myhash_map::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // alter mapped values and redisplay
    c1[L'A'] = 10;
    c1[L'c'] = 13;
    for each (Myhash_map::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
c1[A] = 0
c1[b] = 2
[a 1] [A 0] [b 2] [c 3]
[a 1] [A 10] [b 2] [c 13]
```

## <a name="rbegin"></a> hash_map::rbegin (STL/CLR)

Ters çevrilen denetlenen dizinin başlangıç belirler.

### <a name="syntax"></a>Sözdizimi

```cpp
reverse_iterator rbegin();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, denetlenen dizinin ya da boş bir dizi başlangıcı hemen ötesinde son öğeyi belirleyen bir ters yineleyici döndürür. Bu nedenle, atayan `beginning` ters dizisi. Gösteren bir yineleyici almak için kullandığınız `current` denetlenen dizinin uzunluğu değişirse başlangıcına ters sırada görülen denetlenen dizideki ancak durumunu değiştirebilirsiniz.

### <a name="example"></a>Örnek

```cpp
// cliext_hash_map_rbegin.cpp
// compile with: /clr
#include <cliext/hash_map>

typedef cliext::hash_map<wchar_t, int> Myhash_map;
int main()
    {
    Myhash_map c1;
    c1.insert(Myhash_map::make_value(L'a', 1));
    c1.insert(Myhash_map::make_value(L'b', 2));
    c1.insert(Myhash_map::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Myhash_map::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // inspect first two items in reversed sequence
    Myhash_map::reverse_iterator rit = c1.rbegin();
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

## <a name="reference"></a> hash_map::Reference (STL/CLR)

Bir öğe için bir başvuru türü.

### <a name="syntax"></a>Sözdizimi

```cpp
typedef value_type% reference;
```

### <a name="remarks"></a>Açıklamalar

Öğeye bir başvuru türü açıklar.

### <a name="example"></a>Örnek

```cpp
// cliext_hash_map_reference.cpp
// compile with: /clr
#include <cliext/hash_map>

typedef cliext::hash_map<wchar_t, int> Myhash_map;
int main()
    {
    Myhash_map c1;
    c1.insert(Myhash_map::make_value(L'a', 1));
    c1.insert(Myhash_map::make_value(L'b', 2));
    c1.insert(Myhash_map::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    Myhash_map::iterator it = c1.begin();
    for (; it != c1.end(); ++it)
        {   // get a reference to an element
        Myhash_map::reference ref = *it;
        System::Console::Write("[{0} {1}] ", ref->first, ref->second);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
```

## <a name="rehash"></a> hash_map::rehash (STL/CLR)

Karma tabloyu yeniden oluşturur.

### <a name="syntax"></a>Sözdizimi

```cpp
void rehash();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi sağlanarak, bir karma tabloyu yeniden oluşturur [hash_map::load_factor (STL/CLR)](../dotnet/hash-map-load-factor-stl-clr.md) `() <=` [hash_map::max_load_factor (STL/CLR)](../dotnet/hash-map-max-load-factor-stl-clr.md). Aksi takdirde, karma tablo yalnızca bir ekleme sonra gerektiği şekilde boyutu artar. (Hiçbir zaman otomatik olarak boyutundaki azalır.) Karma tablo boyutunu ayarlamak için kullanın.

### <a name="example"></a>Örnek

```cpp
// cliext_hash_map_rehash.cpp
// compile with: /clr
#include <cliext/hash_map>

typedef cliext::hash_map<wchar_t, int> Myhash_map;
int main()
    {
    Myhash_map c1 = gcnew Myhash_map;
    c1.insert(Myhash_map::make_value(L'a', 1));
    c1.insert(Myhash_map::make_value(L'b', 2));
    c1.insert(Myhash_map::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Myhash_map::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
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
[a 1] [b 2] [c 3]
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

## <a name="rend"></a> hash_map::rend (STL/CLR)

Ters çevrilen denetlenen dizinin sonuna belirler.

### <a name="syntax"></a>Sözdizimi

```cpp
reverse_iterator rend();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi hemen ötesine işaret eden bir başlangıç değerinin denetlenen dizideki ters yineleyici döndürür. Bu nedenle, atayan `end` ters dizisi. Gösteren bir yineleyici almak için kullandığınız `current` denetlenen dizinin uzunluğu değişirse sonuna ters sırada görülen denetlenen dizideki ancak durumunu değiştirebilirsiniz.

### <a name="example"></a>Örnek

```cpp
// cliext_hash_map_rend.cpp
// compile with: /clr
#include <cliext/hash_map>

typedef cliext::hash_map<wchar_t, int> Myhash_map;
int main()
    {
    Myhash_map c1;
    c1.insert(Myhash_map::make_value(L'a', 1));
    c1.insert(Myhash_map::make_value(L'b', 2));
    c1.insert(Myhash_map::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Myhash_map::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // inspect first two items in reversed sequence
    Myhash_map::reverse_iterator rit = c1.rend();
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

## <a name="reverse_iterator"></a> hash_map::reverse_iterator (STL/CLR)

Denetlenen dizi için bir ters yineleyici türü.

### <a name="syntax"></a>Sözdizimi

```cpp
typedef T3 reverse_iterator;
```

### <a name="remarks"></a>Açıklamalar

Bilinmeyen türde bir nesne tanımlayan bir tür `T3` denetlenen dizi için bir ters yineleyici olarak verebilir.

### <a name="example"></a>Örnek

```cpp
// cliext_hash_map_reverse_iterator.cpp
// compile with: /clr
#include <cliext/hash_map>

typedef cliext::hash_map<wchar_t, int> Myhash_map;
int main()
    {
    Myhash_map c1;
    c1.insert(Myhash_map::make_value(L'a', 1));
    c1.insert(Myhash_map::make_value(L'b', 2));
    c1.insert(Myhash_map::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]" reversed
    Myhash_map::reverse_iterator rit = c1.rbegin();
    for (; rit != c1.rend(); ++rit)
        System::Console::Write("[{0} {1}] ", rit->first, rit->second);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
[c 3] [b 2] [a 1]
```

## <a name="size"></a> hash_map::size (STL/CLR)

Öğe sayısını sayar.

### <a name="syntax"></a>Sözdizimi

```cpp
size_type size();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, denetlenen dizinin uzunluğunu döndürür. Şu anda denetlenen dizideki öğelerin sayısını belirlemek için kullanın. Tümü, önem verdiğiniz ise dizisi bakın, sıfır olmayan boyutu olup [hash_map::empty (STL/CLR)](../dotnet/hash-map-empty-stl-clr.md)`()`.

### <a name="example"></a>Örnek

```cpp
// cliext_hash_map_size.cpp
// compile with: /clr
#include <cliext/hash_map>

typedef cliext::hash_map<wchar_t, int> Myhash_map;
int main()
    {
    Myhash_map c1;
    c1.insert(Myhash_map::make_value(L'a', 1));
    c1.insert(Myhash_map::make_value(L'b', 2));
    c1.insert(Myhash_map::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Myhash_map::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // clear the container and reinspect
    c1.clear();
    System::Console::WriteLine("size() = {0} after clearing", c1.size());

    // add elements and clear again
    c1.insert(Myhash_map::make_value(L'd', 4));
    c1.insert(Myhash_map::make_value(L'e', 5));
    System::Console::WriteLine("size() = {0} after adding 2", c1.size());
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
size() = 0 after clearing
size() = 2 after adding 2
```

## <a name="size_type"></a> hash_map::size_type (STL/CLR)

İki öğe arasındaki işaretli mesafenin türü.

### <a name="syntax"></a>Sözdizimi

```cpp
typedef int size_type;
```

### <a name="remarks"></a>Açıklamalar

Bir negatif olmayan öğe sayısını tanımlayan bir tür.

### <a name="example"></a>Örnek

```cpp
// cliext_hash_map_size_type.cpp
// compile with: /clr
#include <cliext/hash_map>

typedef cliext::hash_map<wchar_t, int> Myhash_map;
int main()
    {
    Myhash_map c1;
    c1.insert(Myhash_map::make_value(L'a', 1));
    c1.insert(Myhash_map::make_value(L'b', 2));
    c1.insert(Myhash_map::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Myhash_map::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // compute positive difference
    Myhash_map::size_type diff = 0;
    for (Myhash_map::iterator it = c1.begin(); it != c1.end(); ++it)
        ++diff;
    System::Console::WriteLine("end()-begin() = {0}", diff);
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
end()-begin() = 3
```

## <a name="swap"></a> hash_map::Swap (STL/CLR)

İki kapsayıcının içeriğinin yerini değiştirir.

### <a name="syntax"></a>Sözdizimi

```cpp
void swap(hash_map<Key, Mapped>% right);
```

#### <a name="parameters"></a>Parametreler

*sağ*<br/>
Kapsayıcı içeriğini değiştirmek için.

### <a name="remarks"></a>Açıklamalar

Denetlenen diziyi üye işlevi değiştirir `this` ve *doğru*. Bunu Sabit sürede yapar ve hiçbir özel durum oluşturur. İki kapsayıcının içeriğinin değişimi için hızlı bir şekilde kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// cliext_hash_map_swap.cpp
// compile with: /clr
#include <cliext/hash_map>

typedef cliext::hash_map<wchar_t, int> Myhash_map;
int main()
    {
    Myhash_map c1;
    c1.insert(Myhash_map::make_value(L'a', 1));
    c1.insert(Myhash_map::make_value(L'b', 2));
    c1.insert(Myhash_map::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Myhash_map::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // construct another container with repetition of values
    Myhash_map c2;
    c2.insert(Myhash_map::make_value(L'd', 4));
    c2.insert(Myhash_map::make_value(L'e', 5));
    c2.insert(Myhash_map::make_value(L'f', 6));
    for each (Myhash_map::value_type elem in c2)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // swap and redisplay
    c1.swap(c2);
    for each (Myhash_map::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    for each (Myhash_map::value_type elem in c2)
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

## <a name="to_array"></a> hash_map::to_array (STL/CLR)

Denetlenen dizideki, yeni bir diziye kopyalar.

### <a name="syntax"></a>Sözdizimi

```cpp
cli::array<value_type>^ to_array();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, denetlenen bir dizi içeren bir dizi döndürür. Dizi formunda denetlenen dizinin bir kopyasını almak için kullanın.

### <a name="example"></a>Örnek

```cpp
// cliext_hash_map_to_array.cpp
// compile with: /clr
#include <cliext/hash_map>

typedef cliext::hash_map<wchar_t, int> Myhash_map;
int main()
    {
    Myhash_map c1;
    c1.insert(Myhash_map::make_value(L'a', 1));
    c1.insert(Myhash_map::make_value(L'b', 2));
    c1.insert(Myhash_map::make_value(L'c', 3));

    // copy the container and modify it
    cli::array<Myhash_map::value_type>^ a1 = c1.to_array();

    c1.insert(Myhash_map::make_value(L'd', 4));
    for each (Myhash_map::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // display the earlier array copy
    for each (Myhash_map::value_type elem in a1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3] [d 4]
[a 1] [b 2] [c 3]
```

## <a name="upper_bound"></a> hash_map::upper_bound (STL/CLR)

Belirtilen bir anahtarla eşleşen aralığı sonu bulur.

### <a name="syntax"></a>Sözdizimi

```cpp
iterator upper_bound(key_type key);
```

#### <a name="parameters"></a>Parametreler

*Anahtarı*<br/>
Aranacak anahtar değeri.

### <a name="remarks"></a>Açıklamalar

Üye işlevi son öğeyi belirler `X` aynı Demetin karıştırır denetlenen dizideki *anahtarı* ve için eşdeğer sıralamaya sahip *anahtar*. Böyle bir öğe varsa veya `X` denetlenen dizideki son öğeyi döndürür olan [hash_map::end (STL/CLR)](../dotnet/hash-map-end-stl-clr.md)`()`; Aksi halde ötesindekiilköğeyibelirleyenbiryineleyicidöndürür`X`. Bir dizi öğe sonuna şu anda belirtilen bir anahtarla eşleşen denetlenen dizide bulmak için kullanın.

### <a name="example"></a>Örnek

```cpp
// cliext_hash_map_upper_bound.cpp
// compile with: /clr
#include <cliext/hash_map>

typedef cliext::hash_map<wchar_t, int> Myhash_map;
int main()
    {
    Myhash_map c1;
    c1.insert(Myhash_map::make_value(L'a', 1));
    c1.insert(Myhash_map::make_value(L'b', 2));
    c1.insert(Myhash_map::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Myhash_map::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    System::Console::WriteLine("upper_bound(L'x')==end() = {0}",
        c1.upper_bound(L'x') == c1.end());

    Myhash_map::iterator it = c1.upper_bound(L'a');
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

## <a name="value_comp"></a> hash_map::value_comp (STL/CLR)

İki öğenin değerlerini sıralama temsilcisi kopyalar.

### <a name="syntax"></a>Sözdizimi

```cpp
value_compare^ value_comp();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi denetlenen diziyi sıralamak için kullanılan sıralama temsilci döndürür. İki öğenin değerlerini karşılaştırmak için kullanın.

### <a name="example"></a>Örnek

```cpp
// cliext_hash_map_value_comp.cpp
// compile with: /clr
#include <cliext/hash_map>

typedef cliext::hash_map<wchar_t, int> Myhash_map;
int main()
    {
    Myhash_map c1;
    Myhash_map::value_compare^ kcomp = c1.value_comp();

    System::Console::WriteLine("compare([L'a', 1], [L'a', 1]) = {0}",
        kcomp(Myhash_map::make_value(L'a', 1),
            Myhash_map::make_value(L'a', 1)));
    System::Console::WriteLine("compare([L'a', 1], [L'b', 2]) = {0}",
        kcomp(Myhash_map::make_value(L'a', 1),
            Myhash_map::make_value(L'b', 2)));
    System::Console::WriteLine("compare([L'b', 2], [L'a', 1]) = {0}",
        kcomp(Myhash_map::make_value(L'b', 2),
            Myhash_map::make_value(L'a', 1)));
    System::Console::WriteLine();
    return (0);
    }
```

```Output
compare([L'a', 1], [L'a', 1]) = True
compare([L'a', 1], [L'b', 2]) = True
compare([L'b', 2], [L'a', 1]) = False
```

## <a name="value_compare"></a> hash_map::value_compare (STL/CLR)

İki öğenin değerlerini sıralama temsilcisi.

### <a name="syntax"></a>Sözdizimi

```cpp
Microsoft::VisualC::StlClr::BinaryDelegate<generic_value, generic_value, bool>
    value_compare;
```

### <a name="remarks"></a>Açıklamalar

Türü, değer bağımsız değişkenleri sıralama belirleyen temsilci eşanlamlıdır.

### <a name="example"></a>Örnek

```cpp
// cliext_hash_map_value_compare.cpp
// compile with: /clr
#include <cliext/hash_map>

typedef cliext::hash_map<wchar_t, int> Myhash_map;
int main()
    {
    Myhash_map c1;
    Myhash_map::value_compare^ kcomp = c1.value_comp();

    System::Console::WriteLine("compare([L'a', 1], [L'a', 1]) = {0}",
        kcomp(Myhash_map::make_value(L'a', 1),
            Myhash_map::make_value(L'a', 1)));
    System::Console::WriteLine("compare([L'a', 1], [L'b', 2]) = {0}",
        kcomp(Myhash_map::make_value(L'a', 1),
            Myhash_map::make_value(L'b', 2)));
    System::Console::WriteLine("compare([L'b', 2], [L'a', 1]) = {0}",
        kcomp(Myhash_map::make_value(L'b', 2),
            Myhash_map::make_value(L'a', 1)));
    System::Console::WriteLine();
    return (0);
    }
```

```Output
compare([L'a', 1], [L'a', 1]) = True
compare([L'a', 1], [L'b', 2]) = True
compare([L'b', 2], [L'a', 1]) = False
```

## <a name="value_type"></a> hash_map::value_type (STL/CLR)

Öğenin türü.

### <a name="syntax"></a>Sözdizimi

```cpp
typedef generic_value value_type;
```

### <a name="remarks"></a>Açıklamalar

Türü eşanlamlıdır `generic_value`.

### <a name="example"></a>Örnek

```cpp
// cliext_hash_map_value_type.cpp
// compile with: /clr
#include <cliext/hash_map>

typedef cliext::hash_map<wchar_t, int> Myhash_map;
int main()
    {
    Myhash_map c1;
    c1.insert(Myhash_map::make_value(L'a', 1));
    c1.insert(Myhash_map::make_value(L'b', 2));
    c1.insert(Myhash_map::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]" using value_type
    for (Myhash_map::iterator it = c1.begin(); it != c1.end(); ++it)
        {   // store element in value_type object
        Myhash_map::value_type val = *it;
        System::Console::Write("[{0} {1}] ", val->first, val->second);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
```