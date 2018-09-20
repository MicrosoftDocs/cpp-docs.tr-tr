---
title: multimap (STL/CLR) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::multimap
- cliext::multimap::begin
- cliext::multimap::clear
- cliext::multimap::const_iterator
- cliext::multimap::const_reference
- cliext::multimap::const_reverse_iterator
- cliext::multimap::count
- cliext::multimap::difference_type
- cliext::multimap::empty
- cliext::multimap::end
- cliext::multimap::equal_range
- cliext::multimap::erase
- cliext::multimap::find
- cliext::multimap::generic_container
- cliext::multimap::generic_iterator
- cliext::multimap::generic_reverse_iterator
- cliext::multimap::generic_value
- cliext::multimap::insert
- cliext::multimap::iterator
- cliext::multimap::key_comp
- cliext::multimap::key_compare
- cliext::multimap::key_type
- cliext::multimap::lower_bound
- cliext::multimap::make_value
- cliext::multimap::mapped_type
- cliext::multimap::multimap
- cliext::multimap::operator=
- cliext::multimap::rbegin
- cliext::multimap::reference
- cliext::multimap::rend
- cliext::multimap::reverse_iterator
- cliext::multimap::size
- cliext::multimap::size_type
- cliext::multimap::swap
- cliext::multimap::to_array
- cliext::multimap::upper_bound
- cliext::multimap::value_comp
- cliext::multimap::value_compare
- cliext::multimap::value_type
- cliext::mutlimap::operator!=
- cliext::mutlimap::operator<
- cliext::mutlimap::operator<=
- cliext::mutlimap::operator==
- cliext::mutlimap::operator>
- cliext::mutlimap::operator>=
dev_langs:
- C++
helpviewer_keywords:
- <map> header [STL/CLR]
- <cliext/map> header [STL/CLR]
- multimap class [STL/CLR]
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
- mapped_type member [STL/CLR]
- multimap member [STL/CLR]
- operator= member [STL/CLR]
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
ms.assetid: 3dfe329d-a078-462a-b050-7999ce6110ad
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: a2bff83bd59cf4a0346c4d1b2bb6f5e39a1f47e0
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46419678"
---
# <a name="multimap-stlclr"></a>çoklu eşleme (STL/CLR)

Şablon sınıfı, iki yönlü erişime sahip öğelerin değişen uzunluktaki dizisini denetleyen bir nesneyi tanımlar. Kapsayıcı kullandığınız `multimap` her bir öğe depolama bir dizi öğe (yaklaşık) dengeli sıralı ağacı düğümleri olarak yönetilecek. Bir öğe dizisi ve için kılma gider bir eşlenen değer sıralama için bir anahtar oluşur.

Aşağıdaki açıklamada `GValue` aynıdır:

`Microsoft::VisualC::StlClr::GenericPair<GKey, GMapped>`

burada:

`GKey` aynı *anahtar* ikinci bir başvuru türü olmadığı sürece olduğu durumda `Key^`

`GMapped` aynı *eşlenen* ikinci bir başvuru türü olmadığı sürece olduğu durumda `Mapped^`

## <a name="syntax"></a>Sözdizimi

```cpp
template<typename Key,
    typename Mapped>
    ref class multimap
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
Denetlenen sıradaki öğenin anahtar bileşen türü.

*Eşlenen*<br/>
Ek bileşen denetlenen sıradaki öğenin türü.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<cliext/map >

**Namespace:** cliext

## <a name="declarations"></a>Bildirimler

|Tür Tanımlaması|Açıklama|
|---------------------|-----------------|
|[multimap::const_iterator (STL/CLR)](#const_iterator)|Denetlenen dizi için bir sabit yineleyici türü.|
|[multimap::const_reference (STL/CLR)](#const_reference)|Bir öğe için sabit bir başvuru türü.|
|[multimap::const_reverse_iterator (STL/CLR)](#const_reverse_iterator)|Denetlenen dizi için bir sabit ters yineleyici türü.|
|[multimap::difference_type (STL/CLR)](#difference_type)|İki öğe arasındaki (büyük olasılıkla işaretli) mesafenin türü.|
|[multimap::generic_container (STL/CLR)](#generic_container)|Kapsayıcı için genel arabirim türü.|
|[multimap::generic_iterator (STL/CLR)](#generic_iterator)|Kapsayıcı için genel arabirimi için bir yineleyici türü.|
|[multimap::generic_reverse_iterator (STL/CLR)](#generic_reverse_iterator)|Kapsayıcı için genel arabirimi için ters yineleyici türü.|
|[multimap::generic_value (STL/CLR)](#generic_value)|Kapsayıcı için genel arabirimi için bir öğe türü.|
|[multimap::iterator (STL/CLR)](#iterator)|Denetlenen dizi için bir yineleyici türü.|
|[multimap::key_compare (STL/CLR)](#key_compare)|İki anahtar sıralama temsilcisi.|
|[multimap::key_type (STL/CLR)](#key_type)|Bir sıralama anahtarının türü.|
|[multimap::mapped_type (STL/CLR)](#mapped_type)|Her bir anahtar ile ilişkili bir eşlenen değer türü.|
|[multimap::reference (STL/CLR)](#reference)|Bir öğe için bir başvuru türü.|
|[multimap::reverse_iterator (STL/CLR)](#reverse_iterator)|Denetlenen dizi için bir ters yineleyici türü.|
|[multimap::size_type (STL/CLR)](#size_type)|İki öğe arasındaki bir (negatif) mesafenin türü.|
|[multimap::value_compare (STL/CLR)](#value_compare)|İki öğenin değerlerini sıralama temsilcisi.|
|[multimap::value_type (STL/CLR)](#value_type)|Öğenin türü.|

|Üye İşlevi|Açıklama|
|---------------------|-----------------|
|[multimap::begin (STL/CLR)](#begin)|Denetlenen dizinin başlangıcını belirtir.|
|[multimap::clear (STL/CLR)](#clear)|Tüm öğeleri kaldırır.|
|[multimap::count (STL/CLR)](#count)|Belirtilen bir anahtarla eşleşen öğeleri sayar.|
|[multimap::empty (STL/CLR)](#empty)|Bir öğe olup olmadığını sınar.|
|[multimap::end (STL/CLR)](#end)|Denetlenen dizinin bitişini belirtir.|
|[multimap::equal_range (STL/CLR)](#equal_range)|Belirtilen bir anahtarla eşleşen aralığı bulur.|
|[multimap::erase (STL/CLR)](#erase)|Belirtilen konumlardaki öğeleri kaldırır.|
|[multimap::find (STL/CLR)](#find)|Belirtilen bir anahtarla eşleşen bir öğeyi bulur.|
|[multimap::insert (STL/CLR)](#insert)|Öğeleri ekler.|
|[multimap::key_comp (STL/CLR)](#key_comp)|İki anahtar sıralama temsilcisi kopyalar.|
|[multimap::lower_bound (STL/CLR)](#lower_bound)|Belirtilen bir anahtarla eşleşen aralığı başlangıcını bulur.|
|[multimap::make_value (STL/CLR)](#make_value)|Değer bir nesne oluşturur.|
|[multimap::multimap (STL/CLR)](#multimap)|Bir kapsayıcı nesnesi oluşturur.|
|[multimap::rbegin (STL/CLR)](#rbegin)|Ters çevrilen denetlenen dizinin başlangıç belirler.|
|[multimap::rend (STL/CLR)](#rend)|Ters çevrilen denetlenen dizinin sonuna belirler.|
|[multimap::size (STL/CLR)](#size)|Öğe sayısını sayar.|
|[multimap::swap (STL/CLR)](#swap)|İki kapsayıcının içeriğinin yerini değiştirir.|
|[multimap::to_array (STL/CLR)](#to_array)|Denetlenen dizideki, yeni bir diziye kopyalar.|
|[multimap::upper_bound (STL/CLR)](#upper_bound)|Belirtilen bir anahtarla eşleşen aralığı sonu bulur.|
|[multimap::value_comp (STL/CLR)](#value_comp)|İki öğenin değerlerini sıralama temsilcisi kopyalar.|

|İşleç|Açıklama|
|--------------|-----------------|
|[multimap::operator= (STL/CLR)](#op_as)|Denetlenen dizi değiştirir.|
|[operator!= (multimap) (STL/CLR)](#op_neq)|Belirler bir `multimap` nesnesi, diğerine eşit değil `multimap` nesne.|
|[operator< (multimap) (STL/CLR)](#op_lt)|Belirler bir `multimap` nesnedir daha az `multimap` nesne.|
|[operator<= (multimap) (STL/CLR)](#op_lteq)|Belirler bir `multimap` nesnedir küçüktür veya eşittir diğerine `multimap` nesne.|
|[operator== (multimap) (STL/CLR)](#op_eq)|Belirler bir `multimap` nesnedir diğerine eşit `multimap` nesne.|
|[operator> (multimap) (STL/CLR)](#op_gt)|Belirler bir `multimap` nesnedir diğerinden daha büyük `multimap` nesne.|
|[operator>= (multimap) (STL/CLR)](#op_gteq)|Belirler bir `multimap` nesnedir büyüktür veya eşittir diğerine `multimap` nesne.|

## <a name="interfaces"></a>Arabirimler

|Arabirim|Açıklama|
|---------------|-----------------|
|<xref:System.ICloneable>|Bir nesne çoğaltın.|
|<xref:System.Collections.IEnumerable>|Öğeleri dizisi.|
|<xref:System.Collections.ICollection>|Öğe grubunu koruyun.|
|<xref:System.Collections.Generic.IEnumerable%601>|Türü belirtilmiş öğelerini dizisi.|
|<xref:System.Collections.Generic.ICollection%601>|Türü belirtilmiş bir öğe grubunu koruyun.|
|ITree\<anahtar, değer >|Genel kapsayıcı korur.|

## <a name="remarks"></a>Açıklamalar

Nesne ayırır ve tek tek düğüm olarak denetlediği dizi için depolama serbest bırakır. Bir düğüm içeriğini diğerine kopyalama tarafından hiçbir zaman düğümleri arasındaki bağlantıları değiştirerek düzenli tutar (yaklaşık) dengeli bir ağaç öğeleri ekler. Bu, ekleyin ve özgürce rahatsız edici kalan öğeleri olmadan öğeleri kaldırın anlamına gelir.

Nesne türünde bir saklı temsilci nesnesi çağırarak denetlediği diziyi sıralar [multimap::key_compare (STL/CLR)](../dotnet/multimap-key-compare-stl-clr.md). Multimap oluştururken saklı temsilci nesnesi belirtebilirsiniz; hiçbir temsilci nesnesi belirtirseniz, karşılaştırma varsayılandır `operator<(key_type, key_type)`. Üye işlevini çağırarak depolanan bu nesne erişim [multimap::key_comp (STL/CLR)](../dotnet/multimap-key-comp-stl-clr.md)`()`.

Bu tür bir temsilci nesnesinin katı bir zayıf anahtarları türünde sıralama dayatır gerekir [multimap::key_type (STL/CLR)](../dotnet/multimap-key-type-stl-clr.md). Anlamına gelir, için iki anahtar `X` ve `Y`:

`key_comp()(X, Y)` Her çağrıda aynı Boolean sonucu döndürür.

Varsa `key_comp()(X, Y)` true ise `key_comp()(Y, X)` false olmalıdır.

Varsa `key_comp()(X, Y)` true ise `X` önce sıralanmalıdır söylenir `Y`.

Varsa `!key_comp()(X, Y) && !key_comp()(Y, X)` true ise `X` ve `Y` eşdeğer sıralamaya olduğu söylenir.

Herhangi bir öğe için `X` metninden önce `Y` denetlenen dizideki `key_comp()(Y, X)` false'tur. (Varsayılan temsilci nesne için anahtarları asla değerini azaltın.) Şablon sınıfının aksine [(STL/CLR) map](../dotnet/map-stl-clr.md), şablon sınıfın bir nesnesi `multimap` tüm öğeler için anahtarlarının benzersiz olduğundan emin olması gerekmez. (İki veya daha fazla anahtarı eşdeğer sıralamaya sahip olabilir.)

Her öğe ayrı bir anahtar ve eşleşen bir değer içerir. Sıra, arama, ekleme ve kaldırma işlemleri için öğelerin sayısını logaritmasını orantılı sayısıyla rastgele bir öğenin (Logaritmik süre) sırada izin veren bir şekilde temsil edilir. Ayrıca, bir öğe eklenmesi hiçbir yineleyiciyi geçersiz kılmaz; bir öğenin kaldırılması yalnızca bu kaldırılan öğeyi gösteren yineleyicileri geçersiz kılar.

Çoklu eşlem çift yönlü yineleyiciler bitişik öğelere denetlenen dizideki bir öğeyi belirleyen bir yineleyici verilen adım yani destekler. Özel bir baş düğüm tarafından döndürülen yineleyici karşılık gelen [multimap::end (STL/CLR)](../dotnet/multimap-end-stl-clr.md)`()`. Denetlenen dizi içindeki son öğeden ulaşmak için bu yineleyici varsa azaltma. Baş düğüm ulaşmaya multimap bir yineleyici artırabilirsiniz ve bu sonra eşittir karşılaştıracağız `end()`. Ancak tarafından döndürülen yineleyici başvurulamıyor `end()`.

Doğrudan bir rastgele erişim yineleyici gerektiren sayısal konumunu--verilen multimap bir öğeye başvuramaz unutmayın.

Sırayla ilişkilendirilmiş kapsayıcısı için bir tanıtıcı depolayan görevin ilişkili multimap düğümü için bir tanıtıcı multimap yineleyici depolar. Yineleyiciler yalnızca ilişkili kapsayıcı nesneleri ile kullanabilirsiniz. Multimap Yineleyici, multimap görevin ilişkili düğümü bazı multimap ile ilişkili olduğu sürece geçerli kalır. Ayrıca, geçerli bir yineleyici yineleyicisine--erişmek veya eşit değildir sürece bu atayan--öğe değeri değiştirmek için kullanabilirsiniz `end()`.

Silme veya bir öğenin kaldırılması için depolanan değerine yıkıcı çağırır. Kapsayıcı yok etme tüm öğelerini siler. Bu nedenle, hiçbir öğe'nin kapsayıcı daha uzun sürmesi başvuru sınıfı, öğe türü olan bir kapsayıcı sağlar. Ancak, bir kapsayıcı tutamaçlarından yaptığı unutmayın *değil* öğelerini yok edin.

## <a name="members"></a>Üyeler

## <a name="begin"></a> multimap::Begin (STL/CLR)

Denetlenen dizinin başlangıcını belirtir.

### <a name="syntax"></a>Sözdizimi

```cpp
iterator begin();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, denetlenen dizinin ya da boş bir dizi bitiminin ötesinde yalnızca ilk öğeyi belirleyen çift yönlü bir yineleyici döndürür. Gösteren bir yineleyici almak için kullandığınız `current` denetlenen dizideki ancak durumu başına denetlenen dizinin uzunluğu değişirse değiştirebilirsiniz.

### <a name="example"></a>Örnek

```cpp
// cliext_multimap_begin.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::multimap<wchar_t, int> Mymultimap;
int main()
    {
    Mymultimap c1;
    c1.insert(Mymultimap::make_value(L'a', 1));
    c1.insert(Mymultimap::make_value(L'b', 2));
    c1.insert(Mymultimap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Mymultimap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // inspect first two items
    Mymultimap::iterator it = c1.begin();
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

## <a name="clear"></a> multimap::Clear (STL/CLR)

Tüm öğeleri kaldırır.

### <a name="syntax"></a>Sözdizimi

```cpp
void clear();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi etkili bir şekilde çağıran [multimap::erase (STL/CLR)](../dotnet/multimap-erase-stl-clr.md) `(` [multimap::begin (STL/CLR)](../dotnet/multimap-begin-stl-clr.md) `(),` [multimap::end (STL/CLR)](../dotnet/multimap-end-stl-clr.md) `())`. Denetlenen dizi boş olduğundan emin olmak için kullanın.

### <a name="example"></a>Örnek

```cpp
// cliext_multimap_clear.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::multimap<wchar_t, int> Mymultimap;
int main()
    {
    Mymultimap c1;
    c1.insert(Mymultimap::make_value(L'a', 1));
    c1.insert(Mymultimap::make_value(L'b', 2));
    c1.insert(Mymultimap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Mymultimap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // clear the container and reinspect
    c1.clear();
    System::Console::WriteLine("size() = {0}", c1.size());

    c1.insert(Mymultimap::make_value(L'a', 1));
    c1.insert(Mymultimap::make_value(L'b', 2));

    // display contents " [a 1] [b 2]"
    for each (Mymultimap::value_type elem in c1)
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

## <a name="const_iterator"></a> multimap::const_iterator (STL/CLR)

Denetlenen dizi için bir sabit yineleyici türü.

### <a name="syntax"></a>Sözdizimi

```cpp
typedef T2 const_iterator;
```

### <a name="remarks"></a>Açıklamalar

Bilinmeyen türde bir nesne tanımlayan bir tür `T2` denetlenen dizi için sabit bir çift yönlü bir yineleyici olarak verebilir.

### <a name="example"></a>Örnek

```cpp
// cliext_multimap_const_iterator.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::multimap<wchar_t, int> Mymultimap;
int main()
    {
    Mymultimap c1;
    c1.insert(Mymultimap::make_value(L'a', 1));
    c1.insert(Mymultimap::make_value(L'b', 2));
    c1.insert(Mymultimap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    Mymultimap::const_iterator cit = c1.begin();
    for (; cit != c1.end(); ++cit)
        System::Console::Write("[{0} {1}] ", cit->first, cit->second);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
```

## <a name="const_reference"></a> multimap::const_reference (STL/CLR)

Bir öğe için sabit bir başvuru türü.

### <a name="syntax"></a>Sözdizimi

```cpp
typedef value_type% const_reference;
```

### <a name="remarks"></a>Açıklamalar

Bir öğe için sabit bir başvuru türü açıklar.

### <a name="example"></a>Örnek

```cpp
// cliext_multimap_const_reference.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::multimap<wchar_t, int> Mymultimap;
int main()
    {
    Mymultimap c1;
    c1.insert(Mymultimap::make_value(L'a', 1));
    c1.insert(Mymultimap::make_value(L'b', 2));
    c1.insert(Mymultimap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    Mymultimap::const_iterator cit = c1.begin();
    for (; cit != c1.end(); ++cit)
        {   // get a const reference to an element
        Mymultimap::const_reference cref = *cit;
        System::Console::Write("[{0} {1}] ", cref->first, cref->second);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
```

## <a name="const_reverse_iterator"></a> multimap::const_reverse_iterator (STL/CLR)

Denetlenen dizi için bir sabit ters yineleyici türü.

### <a name="syntax"></a>Sözdizimi

```cpp
typedef T4 const_reverse_iterator;
```

### <a name="remarks"></a>Açıklamalar

Bilinmeyen türde bir nesne tanımlayan bir tür `T4` denetlenen dizi için bir sabit ters yineleyici olarak verebilir.

### <a name="example"></a>Örnek

```cpp
// cliext_multimap_const_reverse_iterator.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::multimap<wchar_t, int> Mymultimap;
int main()
    {
    Mymultimap c1;
    c1.insert(Mymultimap::make_value(L'a', 1));
    c1.insert(Mymultimap::make_value(L'b', 2));
    c1.insert(Mymultimap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]" reversed
    Mymultimap::const_reverse_iterator crit = c1.rbegin();
    for (; crit != c1.rend(); ++crit)
        System::Console::Write("[{0} {1}] ", crit->first, crit->second);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
[c 3] [b 2] [a 1]
```

## <a name="count"></a> multimap::Count (STL/CLR)

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
// cliext_multimap_count.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::multimap<wchar_t, int> Mymultimap;
int main()
    {
    Mymultimap c1;
    c1.insert(Mymultimap::make_value(L'a', 1));
    c1.insert(Mymultimap::make_value(L'b', 2));
    c1.insert(Mymultimap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Mymultimap::value_type elem in c1)
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

## <a name="difference_type"></a> multimap::difference_type (STL/CLR)

İki öğe arasındaki işaretli mesafenin türü.

### <a name="syntax"></a>Sözdizimi

```cpp
typedef int difference_type;
```

### <a name="remarks"></a>Açıklamalar

Büyük olasılıkla negatif öğe sayısını tanımlayan bir tür.

### <a name="example"></a>Örnek

```cpp
// cliext_multimap_difference_type.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::multimap<wchar_t, int> Mymultimap;
int main()
    {
    Mymultimap c1;
    c1.insert(Mymultimap::make_value(L'a', 1));
    c1.insert(Mymultimap::make_value(L'b', 2));
    c1.insert(Mymultimap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Mymultimap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // compute positive difference
    Mymultimap::difference_type diff = 0;
    for (Mymultimap::iterator it = c1.begin(); it != c1.end(); ++it)
        ++diff;
    System::Console::WriteLine("end()-begin() = {0}", diff);

    // compute negative difference
    diff = 0;
    for (Mymultimap::iterator it = c1.end(); it != c1.begin(); --it)
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

## <a name="empty"></a> multimap::Empty (STL/CLR)

Bir öğe olup olmadığını sınar.

### <a name="syntax"></a>Sözdizimi

```cpp
bool empty();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi boş bir denetlenmiş dizi için true değerini döndürür. Eşdeğerdir [multimap::size (STL/CLR)](../dotnet/multimap-size-stl-clr.md)`() == 0`. Multimap boş olup olmadığını sınamak için kullanın.

### <a name="example"></a>Örnek

```cpp
// cliext_multimap_empty.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::multimap<wchar_t, int> Mymultimap;
int main()
    {
    Mymultimap c1;
    c1.insert(Mymultimap::make_value(L'a', 1));
    c1.insert(Mymultimap::make_value(L'b', 2));
    c1.insert(Mymultimap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Mymultimap::value_type elem in c1)
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

## <a name="end"></a> multimap::End (STL/CLR)

Denetlenen dizinin bitişini belirtir.

### <a name="syntax"></a>Sözdizimi

```cpp
iterator end();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, denetlenen dizinin sonuna hemen ötesine işaret eden çift yönlü bir yineleyici döndürür. Denetlenen dizinin sonuna belirten bir yineleyici almak için kullanın. kendi durum eklenmemişse denetlenen dizinin uzunluğu değişirse değiştiremezsiniz.

### <a name="example"></a>Örnek

```cpp
// cliext_multimap_end.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::multimap<wchar_t, int> Mymultimap;
int main()
    {
    Mymultimap c1;
    c1.insert(Mymultimap::make_value(L'a', 1));
    c1.insert(Mymultimap::make_value(L'b', 2));
    c1.insert(Mymultimap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Mymultimap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // inspect last two items
    Mymultimap::iterator it = c1.end();
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

## <a name="equal_range"></a> multimap::equal_range (STL/CLR)

Belirtilen bir anahtarla eşleşen aralığı bulur.

### <a name="syntax"></a>Sözdizimi

```cpp
pair_iter_iter equal_range(key_type _Keyval);
```

#### <a name="parameters"></a>Parametreler

*_Keyval*<br/>
Aranacak anahtar değeri.

### <a name="remarks"></a>Açıklamalar

Yöntem Yineleyicilerin bir çiftini döndürür `-` [multimap::lower_bound (STL/CLR)](../dotnet/multimap-lower-bound-stl-clr.md) `(_Keyval),` [multimap::upper_bound (STL/CLR)](../dotnet/multimap-upper-bound-stl-clr.md)`(_Keyval)`. Belirtilen bir anahtarla eşleşen öğeleri şu anda denetlenen dizideki aralığı belirlemek için kullanın.

### <a name="example"></a>Örnek

```cpp
// cliext_multimap_equal_range.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::multimap<wchar_t, int> Mymultimap;
typedef Mymultimap::pair_iter_iter Pairii;
int main()
    {
    Mymultimap c1;
    c1.insert(Mymultimap::make_value(L'a', 1));
    c1.insert(Mymultimap::make_value(L'b', 2));
    c1.insert(Mymultimap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Mymultimap::value_type elem in c1)
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

## <a name="erase"></a> multimap::ERASE (STL/CLR)

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

İlk üye işlevi tarafından denetlenen dizinin öğeyi kaldırır *burada*ve kaldırıldı, öğenin dışında kalan ilk öğeyi belirleyen bir yineleyici döndürür veya [multimap::end (STL / CLR)](../dotnet/multimap-end-stl-clr.md) `()` böyle bir öğe varsa. Tek bir öğe kaldırmak için kullanın.

İkinci üye işlevi öğeleri denetlenen dizinin aralıktaki kaldırır. [`first`, `last`) ve kaldırılan tüm öğelerin ötesindeki ilk öğeyi belirleyen bir yineleyici döndürür veya `end()` böyle bir öğe varsa var... Sıfır veya daha fazla ardışık öğeleri kaldırmak için kullanın.

Üçüncü üye işlevi olan anahtara sahip eşdeğer sıralamaya denetlenen dizideki herhangi bir öğe kaldırır için *anahtarı*ve kaldırılan öğelerin sayısını döndürür. Kaldırın ve belirtilen bir anahtarla eşleşen tüm öğeleri saymak için kullanın.

Her öğe silinme için öğelerin sayısını logaritmasını orantılı zaman denetlenen dizide alır.

### <a name="example"></a>Örnek

```cpp
// cliext_multimap_erase.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::multimap<wchar_t, int> Mymultimap;
int main()
    {
    cliext::multimap<wchar_t, int> c1;
    c1.insert(cliext::multimap<wchar_t, int>::make_value(L'a', 1));
    c1.insert(cliext::multimap<wchar_t, int>::make_value(L'b', 2));
    c1.insert(cliext::multimap<wchar_t, int>::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (cliext::multimap<wchar_t, int>::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // erase an element and reinspect
    cliext::multimap<wchar_t, int>::iterator it =
        c1.erase(c1.begin());
    System::Console::WriteLine("erase(begin()) = [{0} {1}]",
        it->first, it->second);

    // add elements and display " b c d e"
    c1.insert(cliext::multimap<wchar_t, int>::make_value(L'd', 4));
    c1.insert(cliext::multimap<wchar_t, int>::make_value(L'e', 5));
    for each (cliext::multimap<wchar_t, int>::value_type elem in c1)
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

## <a name="find"></a> multimap::Find (STL/CLR)

Belirtilen bir anahtarla eşleşen bir öğeyi bulur.

### <a name="syntax"></a>Sözdizimi

```cpp
iterator find(key_type key);
```

#### <a name="parameters"></a>Parametreler

*Anahtarı*<br/>
Aranacak anahtar değeri.

### <a name="remarks"></a>Açıklamalar

Denetlenen dizideki en az bir öğe ile eşdeğer sıralamaya sahipse *anahtarı*, üye işlevi biri bu öğeleri gösteren bir yineleyici döndürür; Aksi halde döndürür [multimap::end (STL/CLR)](../dotnet/multimap-end-stl-clr.md) `()`. Bir öğe şu anda belirtilen bir anahtarla eşleşen denetlenen dizide bulmak için kullanın.

### <a name="example"></a>Örnek

```cpp
// cliext_multimap_find.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::multimap<wchar_t, int> Mymultimap;
int main()
    {
    Mymultimap c1;
    c1.insert(Mymultimap::make_value(L'a', 1));
    c1.insert(Mymultimap::make_value(L'b', 2));
    c1.insert(Mymultimap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Mymultimap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    System::Console::WriteLine("find {0} = {1}",
        L'A', c1.find(L'A') != c1.end());

    Mymultimap::iterator it = c1.find(L'b');
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

## <a name="generic_container"></a> multimap::generic_container (STL/CLR)

Kapsayıcı için genel arabirim türü.

### <a name="syntax"></a>Sözdizimi

```cpp
typedef Microsoft::VisualC::StlClr::
    ITree<GKey, GValue>
    generic_container;
```

### <a name="remarks"></a>Açıklamalar

Bu şablon kapsayıcı sınıfı için genel arabirim tanımlayan bir tür.

### <a name="example"></a>Örnek

```cpp
// cliext_multimap_generic_container.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::multimap<wchar_t, int> Mymultimap;
int main()
    {
    Mymultimap c1;
    c1.insert(Mymultimap::make_value(L'a', 1));
    c1.insert(Mymultimap::make_value(L'b', 2));
    c1.insert(Mymultimap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Mymultimap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // construct a generic container
    Mymultimap::generic_container^ gc1 = %c1;
    for each (Mymultimap::value_type elem in gc1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // modify generic and display original
    gc1->insert(Mymultimap::make_value(L'd', 4));
    for each (Mymultimap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // modify original and display generic
    c1.insert(Mymultimap::make_value(L'e', 5));
    for each (Mymultimap::value_type elem in gc1)
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

## <a name="generic_iterator"></a> multimap::generic_iterator (STL/CLR)

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
// cliext_multimap_generic_iterator.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::multimap<wchar_t, int> Mymultimap;
int main()
    {
    Mymultimap c1;
    c1.insert(Mymultimap::make_value(L'a', 1));
    c1.insert(Mymultimap::make_value(L'b', 2));
    c1.insert(Mymultimap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Mymultimap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // construct a generic container
    Mymultimap::generic_container^ gc1 = %c1;
    for each (Mymultimap::value_type elem in gc1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // get an element and display it
    Mymultimap::generic_iterator gcit = gc1->begin();
    Mymultimap::generic_value gcval = *gcit;
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

## <a name="generic_reverse_iterator"></a> multimap::generic_reverse_iterator (STL/CLR)

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
// cliext_multimap_generic_reverse_iterator.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::multimap<wchar_t, int> Mymultimap;
int main()
    {
    Mymultimap c1;
    c1.insert(Mymultimap::make_value(L'a', 1));
    c1.insert(Mymultimap::make_value(L'b', 2));
    c1.insert(Mymultimap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Mymultimap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // construct a generic container
    Mymultimap::generic_container^ gc1 = %c1;
    for each (Mymultimap::value_type elem in gc1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // get an element and display it
    Mymultimap::generic_reverse_iterator gcit = gc1->rbegin();
    Mymultimap::generic_value gcval = *gcit;
    System::Console::WriteLine("[{0} {1}] ", gcval->first, gcval->second);
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
[a 1] [b 2] [c 3]
[c 3]
```

## <a name="generic_value"></a> multimap::generic_value (STL/CLR)

Kapsayıcı için genel arabirimi ile kullanmak için bir öğe türü.

### <a name="syntax"></a>Sözdizimi

```cpp
typedef GValue generic_value;
```

### <a name="remarks"></a>Açıklamalar

Türünde bir nesneyi tanımlayan bir tür `GValue` açıklayan yönelik genel arabirimi için bu şablonu kapsayıcı sınıfı ile kullanmak için depolanan öğenin değeri.

### <a name="example"></a>Örnek

```cpp
// cliext_multimap_generic_value.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::multimap<wchar_t, int> Mymultimap;
int main()
    {
    Mymultimap c1;
    c1.insert(Mymultimap::make_value(L'a', 1));
    c1.insert(Mymultimap::make_value(L'b', 2));
    c1.insert(Mymultimap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Mymultimap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // construct a generic container
    Mymultimap::generic_container^ gc1 = %c1;
    for each (Mymultimap::value_type elem in gc1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // get an element and display it
    Mymultimap::generic_iterator gcit = gc1->begin();
    Mymultimap::generic_value gcval = *gcit;
    System::Console::WriteLine("[{0} {1}] ", gcval->first, gcval->second);
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
[a 1] [b 2] [c 3]
[a 1]
```

## <a name="insert"></a> multimap::insert (STL/CLR)

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

İlk üye işlevi değere sahip bir öğe ekler *val*ve yeni eklenen öğeyi belirleyen bir yineleyici döndürür. Tek bir öğe eklemek için kullanın.

İkinci üye işlevi değere sahip bir öğe ekler *val*kullanarak *burada* (performansını artırmak için) bir ipucu olarak ve yeni eklenen öğeyi belirleyen bir yineleyici döndürür. Bildiğiniz bir öğeye bitişik olabilecek tek bir öğe eklemek için kullanın.

Üçüncü üye işlevi ekler dizisi [`first`, `last`). Başka bir diziden kopyalanan sıfır veya daha fazla öğe eklemek için kullanın.

Dördüncü üye işlevi tarafından belirlenen dizisi ekler *doğru*. Bir numaralandırıcı tarafından açıklanan bir dizi eklemek için kullanın.

Her öğe ekleme, denetlenen dizide öğe sayısı için logaritmasını orantılı zaman alır. Ekleme, ekleme noktasını bitişik bir öğeyi belirleyen bir ipucu verilen amorti edilmiş sabit sürede bir ancak ortaya çıkabilir.

### <a name="example"></a>Örnek

```cpp
// cliext_multimap_insert.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::multimap<wchar_t, int> Mymultimap;
int main()
    {
    Mymultimap c1;
    c1.insert(Mymultimap::make_value(L'a', 1));
    c1.insert(Mymultimap::make_value(L'b', 2));
    c1.insert(Mymultimap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Mymultimap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // insert a single value, unique and duplicate
    Mymultimap::iterator it =
        c1.insert(Mymultimap::make_value(L'x', 24));
    System::Console::WriteLine("insert([L'x' 24]) = [{0} {1}]",
        it->first, it->second);

    it = c1.insert(Mymultimap::make_value(L'b', 2));
    System::Console::WriteLine("insert([L'b' 2]) = [{0} {1}]",
        it->first, it->second);

    for each (Mymultimap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // insert a single value with hint
    it = c1.insert(c1.begin(), Mymultimap::make_value(L'y', 25));
    System::Console::WriteLine("insert(begin(), [L'y' 25]) = [{0} {1}]",
        it->first, it->second);
    for each (Mymultimap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // insert an iterator range
    Mymultimap c2;
    it = c1.end();
    c2.insert(c1.begin(), --it);
    for each (Mymultimap::value_type elem in c2)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // insert an enumeration
    Mymultimap c3;
    c3.insert(   // NOTE: cast is not needed
        (System::Collections::Generic::
            IEnumerable<Mymultimap::value_type>^)%c1);
    for each (Mymultimap::value_type elem in c3)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
insert([L'x' 24]) = [x 24]
insert([L'b' 2]) = [b 2]
[a 1] [b 2] [b 2] [c 3] [x 24]
insert(begin(), [L'y' 25]) = [y 25]
[a 1] [b 2] [b 2] [c 3] [x 24] [y 25]
[a 1] [b 2] [b 2] [c 3] [x 24]
[a 1] [b 2] [b 2] [c 3] [x 24] [y 25]
```

## <a name="iterator"></a> multimap::iterator (STL/CLR)

Denetlenen dizi için bir yineleyici türü.

### <a name="syntax"></a>Sözdizimi

```cpp
typedef T1 iterator;
```

### <a name="remarks"></a>Açıklamalar

Bilinmeyen türde bir nesne tanımlayan bir tür `T1` denetlenen dizi için çift yönlü bir yineleyici olarak verebilir.

### <a name="example"></a>Örnek

```cpp
// cliext_multimap_iterator.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::multimap<wchar_t, int> Mymultimap;
int main()
    {
    Mymultimap c1;
    c1.insert(Mymultimap::make_value(L'a', 1));
    c1.insert(Mymultimap::make_value(L'b', 2));
    c1.insert(Mymultimap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    Mymultimap::iterator it = c1.begin();
    for (; it != c1.end(); ++it)
        System::Console::Write("[{0} {1}] ", it->first, it->second);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
```

## <a name="key_comp"></a> multimap::key_comp (STL/CLR)

İki anahtar sıralama temsilcisi kopyalar.

### <a name="syntax"></a>Sözdizimi

```cpp
key_compare^key_comp();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi denetlenen diziyi sıralamak için kullanılan sıralama temsilci döndürür. İki anahtar karşılaştırmak için kullanın.

### <a name="example"></a>Örnek

```cpp
// cliext_multimap_key_comp.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::multimap<wchar_t, int> Mymultimap;
int main()
    {
    Mymultimap c1;
    Mymultimap::key_compare^ kcomp = c1.key_comp();

    System::Console::WriteLine("compare(L'a', L'a') = {0}",
        kcomp(L'a', L'a'));
    System::Console::WriteLine("compare(L'a', L'b') = {0}",
        kcomp(L'a', L'b'));
    System::Console::WriteLine("compare(L'b', L'a') = {0}",
        kcomp(L'b', L'a'));
    System::Console::WriteLine();

    // test a different ordering rule
    Mymultimap c2 = cliext::greater<wchar_t>();
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

## <a name="key_compare"></a> multimap::key_compare (STL/CLR)

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
// cliext_multimap_key_compare.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::multimap<wchar_t, int> Mymultimap;
int main()
    {
    Mymultimap c1;
    Mymultimap::key_compare^ kcomp = c1.key_comp();

    System::Console::WriteLine("compare(L'a', L'a') = {0}",
        kcomp(L'a', L'a'));
    System::Console::WriteLine("compare(L'a', L'b') = {0}",
        kcomp(L'a', L'b'));
    System::Console::WriteLine("compare(L'b', L'a') = {0}",
        kcomp(L'b', L'a'));
    System::Console::WriteLine();

    // test a different ordering rule
    Mymultimap c2 = cliext::greater<wchar_t>();
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

## <a name="key_type"></a> multimap::key_type (STL/CLR)

Bir sıralama anahtarının türü.

### <a name="syntax"></a>Sözdizimi

```cpp
typedef Key key_type;
```

### <a name="remarks"></a>Açıklamalar

Şablon parametresi için bir eşanlamlı türüdür *anahtar*.

### <a name="example"></a>Örnek

```cpp
// cliext_multimap_key_type.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::multimap<wchar_t, int> Mymultimap;
int main()
    {
    Mymultimap c1;
    c1.insert(Mymultimap::make_value(L'a', 1));
    c1.insert(Mymultimap::make_value(L'b', 2));
    c1.insert(Mymultimap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]" using key_type
    for (Mymultimap::iterator it = c1.begin(); it != c1.end(); ++it)
        {   // store element in key_type object
        Mymultimap::key_type val = it->first;

        System::Console::Write("{0} ", val);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="lower_bound"></a> multimap::lower_bound (STL/CLR)

Belirtilen bir anahtarla eşleşen aralığı başlangıcını bulur.

### <a name="syntax"></a>Sözdizimi

```cpp
iterator lower_bound(key_type key);
```

#### <a name="parameters"></a>Parametreler

*Anahtarı*<br/>
Aranacak anahtar değeri.

### <a name="remarks"></a>Açıklamalar

Üye işlevi ilk öğeyi belirleyen `X` için eşdeğer sıralamaya sahip denetlenen dizideki *anahtar*. Böyle bir öğe var olup olmadığını döndürür [multimap::end (STL/CLR)](../dotnet/multimap-end-stl-clr.md)`()`; Aksi halde gösteren bir yineleyici döndürür `X`. Bir dizi öğe başına şu anda belirtilen bir anahtarla eşleşen denetlenen dizide bulmak için kullanın.

### <a name="example"></a>Örnek

```cpp
// cliext_multimap_lower_bound.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::multimap<wchar_t, int> Mymultimap;
int main()
    {
    Mymultimap c1;
    c1.insert(Mymultimap::make_value(L'a', 1));
    c1.insert(Mymultimap::make_value(L'b', 2));
    c1.insert(Mymultimap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Mymultimap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    System::Console::WriteLine("lower_bound(L'x')==end() = {0}",
        c1.lower_bound(L'x') == c1.end());

    Mymultimap::iterator it = c1.lower_bound(L'a');
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

## <a name="make_value"></a> multimap::make_value (STL/CLR)

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
// cliext_multimap_make_value.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::multimap<wchar_t, int> Mymultimap;
int main()
    {
    Mymultimap c1;
    c1.insert(Mymultimap::make_value(L'a', 1));
    c1.insert(Mymultimap::make_value(L'b', 2));
    c1.insert(Mymultimap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Mymultimap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
```

## <a name="mapped_type"></a> multimap::mapped_type (STL/CLR)

Her bir anahtar ile ilişkili bir eşlenen değer türü.

### <a name="syntax"></a>Sözdizimi

```cpp
typedef Mapped mapped_type;
```

### <a name="remarks"></a>Açıklamalar

Şablon parametresi için bir eşanlamlı türüdür *eşlenen*.

### <a name="example"></a>Örnek

```cpp
// cliext_multimap_mapped_type.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::multimap<wchar_t, int> Mymultimap;
int main()
    {
    Mymultimap c1;
    c1.insert(Mymultimap::make_value(L'a', 1));
    c1.insert(Mymultimap::make_value(L'b', 2));
    c1.insert(Mymultimap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]" using mapped_type
    for (Mymultimap::iterator it = c1.begin(); it != c1.end(); ++it)
        {   // store element in mapped_type object
        Mymultimap::mapped_type val = it->second;

        System::Console::Write("{0} ", val);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
1 2 3
```

## <a name="multimap"></a> multimap::multimap (STL/CLR)

Bir kapsayıcı nesnesi oluşturur.

### <a name="syntax"></a>Sözdizimi

```cpp
multimap();
explicit multimap(key_compare^ pred);
multimap(multimap<Key, Mapped>% right);
multimap(multimap<Key, Mapped>^ right);
template<typename InIter>
    multimapmultimap(InIter first, InIter last);
template<typename InIter>
    multimap(InIter first, InIter last,
        key_compare^ pred);
multimap(System::Collections::Generic::IEnumerable<GValue>^ right);
multimap(System::Collections::Generic::IEnumerable<GValue>^ right,
    key_compare^ pred);
```

#### <a name="parameters"></a>Parametreler

*ilk*<br/>
Eklenecek Aralık başlangıcı.

*Son*<br/>
Eklenecek aralık sonu.

*Pred*<br/>
Denetlenen dizi için koşul sıralaması.

*sağ*<br/>
Nesne veya eklenecek aralık.

### <a name="remarks"></a>Açıklamalar

Oluşturucu:

`multimap();`

Varsayılan karşılaştırma sıralama ile denetlenen dizideki herhangi bir öğesi ile başlatır `key_compare()`. Koşul sıralama varsayılan bir boş ilk denetlenen sıra belirtmek için kullanın.

Oluşturucu:

`explicit multimap(key_compare^ pred);`

Denetlenen dizi sıralama koşul ile hiçbir öğe ile başlatır *pred*. Bir boş ilk denetlenen sıra ile belirtilen sıralama koşulu belirtmek için kullanın.

Oluşturucu:

`multimap(multimap<Key, Mapped>% right);`

Denetlenen dizi sırası başlatır [`right.begin()`, `right.end()`), koşul sıralama varsayılan. Multimap nesnesi tarafından denetlenen dizinin bir kopyasını olan ilk denetimli bir sıra belirtmek için kullandığınız *doğru*, koşul sıralama varsayılan.

Oluşturucu:

`multimap(multimap<Key, Mapped>^ right);`

Denetlenen dizi sırası başlatır [`right->begin()`, `right->end()`), koşul sıralama varsayılan. Multimap nesnesi tarafından denetlenen dizinin bir kopyasını olan ilk denetimli bir sıra belirtmek için kullandığınız *doğru*, koşul sıralama varsayılan.

Oluşturucu:

`template<typename InIter> multimap(InIter first, InIter last);`

Denetlenen dizi sırası başlatır [`first`, `last`), koşul sıralama varsayılan. Denetlenen dizi başka bir dizinin bir kopyasını varsayılan karşılaştırma sıralama yapmak için kullanın.

Oluşturucu:

`template<typename InIter> multimap(InIter first, InIter last, key_compare^ pred);`

Denetlenen dizi sırası başlatır [`first`, `last`), sıralama koşul ile *pred*. Denetlenen dizi belirtilen sıralama koşul ile başka bir sıralı bir kopyasını kullanın.

Oluşturucu:

`multimap(System::Collections::Generic::IEnumerable<Key>^ right);`

Denetlenen dizi numaralandırıcı tarafından belirtilen sıra başlatır *doğru*, koşul sıralama varsayılan. Denetlenen dizi başka bir sıralı karşılaştırma sıralama varsayılan bir numaralandırıcı tarafından açıklanan bir kopyasını kullanın.

Oluşturucu:

`multimap(System::Collections::Generic::IEnumerable<Key>^ right, key_compare^ pred);`

Denetlenen dizi numaralandırıcı tarafından belirtilen sıra başlatır *doğru*, sıralama koşul ile *pred*. Denetlenen dizi, başka bir dizisi tarafından belirtilen sıralama koşul ile bir numaralandırıcı açıklanan kopyasını kullanın.

### <a name="example"></a>Örnek

```cpp
// cliext_multimap_construct.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::multimap<wchar_t, int> Mymultimap;
int main()
    {
// construct an empty container
    Mymultimap c1;
    System::Console::WriteLine("size() = {0}", c1.size());

    c1.insert(Mymultimap::make_value(L'a', 1));
    c1.insert(Mymultimap::make_value(L'b', 2));
    c1.insert(Mymultimap::make_value(L'c', 3));
    for each (Mymultimap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // construct with an ordering rule
    Mymultimap c2 = cliext::greater_equal<wchar_t>();
    System::Console::WriteLine("size() = {0}", c2.size());

    c2.insert(c1.begin(), c1.end());
    for each (Mymultimap::value_type elem in c2)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // construct with an iterator range
    Mymultimap c3(c1.begin(), c1.end());
    for each (Mymultimap::value_type elem in c3)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // construct with an iterator range and an ordering rule
    Mymultimap c4(c1.begin(), c1.end(),
        cliext::greater_equal<wchar_t>());
    for each (Mymultimap::value_type elem in c4)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // construct with an enumeration
    Mymultimap c5(   // NOTE: cast is not needed
        (System::Collections::Generic::IEnumerable<
            Mymultimap::value_type>^)%c3);
    for each (Mymultimap::value_type elem in c5)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // construct with an enumeration and an ordering rule
    Mymultimap c6(   // NOTE: cast is not needed
        (System::Collections::Generic::IEnumerable<
            Mymultimap::value_type>^)%c3,
                cliext::greater_equal<wchar_t>());
    for each (Mymultimap::value_type elem in c6)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // construct by copying another container
    Mymultimap c7(c4);
    for each (Mymultimap::value_type elem in c7)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // construct by copying a container handle
    Mymultimap c8(%c3);
    for each (Mymultimap::value_type elem in c8)
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

## <a name="op_as"></a> multimap::operator (STL/CLR) =

Denetlenen dizi değiştirir.

### <a name="syntax"></a>Sözdizimi

```cpp
multimap<Key, Mapped>% operator=(multimap<Key, Mapped>% right);
```

#### <a name="parameters"></a>Parametreler

*sağ*<br/>
Kopyalanacak kapsayıcı.

### <a name="remarks"></a>Açıklamalar

Üye işleci kopyaları *doğru* ardından nesneye döndürür `*this`. Denetlenen dizi denetlenen dizide bir kopyasını değiştirmek için kullandığınız *doğru*.

### <a name="example"></a>Örnek

```cpp
// cliext_multimap_operator_as.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::multimap<wchar_t, int> Mymultimap;
int main()
    {
    Mymultimap c1;
    c1.insert(Mymultimap::make_value(L'a', 1));
    c1.insert(Mymultimap::make_value(L'b', 2));
    c1.insert(Mymultimap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Mymultimap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // assign to a new container
    Mymultimap c2;
    c2 = c1;
// display contents " [a 1] [b 2] [c 3]"
    for each (Mymultimap::value_type elem in c2)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
[a 1] [b 2] [c 3]
```

## <a name="rbegin"></a> multimap::rbegin (STL/CLR)

Ters çevrilen denetlenen dizinin başlangıç belirler.

### <a name="syntax"></a>Sözdizimi

```cpp
reverse_iterator rbegin();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, denetlenen dizinin ya da boş bir dizi başlangıcı hemen ötesinde son öğeyi belirleyen bir ters yineleyici döndürür. Bu nedenle, atayan `beginning` ters dizisi. Gösteren bir yineleyici almak için kullandığınız `current` denetlenen dizinin uzunluğu değişirse başlangıcına ters sırada görülen denetlenen dizideki ancak durumunu değiştirebilirsiniz.

### <a name="example"></a>Örnek

```cpp
// cliext_multimap_rbegin.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::multimap<wchar_t, int> Mymultimap;
int main()
    {
    Mymultimap c1;
    c1.insert(Mymultimap::make_value(L'a', 1));
    c1.insert(Mymultimap::make_value(L'b', 2));
    c1.insert(Mymultimap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Mymultimap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // inspect first two items in reversed sequence
    Mymultimap::reverse_iterator rit = c1.rbegin();
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

## <a name="reference"></a> multimap::Reference (STL/CLR)

Bir öğe için bir başvuru türü.

### <a name="syntax"></a>Sözdizimi

```cpp
typedef value_type% reference;
```

### <a name="remarks"></a>Açıklamalar

Öğeye bir başvuru türü açıklar.

### <a name="example"></a>Örnek

```cpp
// cliext_multimap_reference.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::multimap<wchar_t, int> Mymultimap;
int main()
    {
    Mymultimap c1;
    c1.insert(Mymultimap::make_value(L'a', 1));
    c1.insert(Mymultimap::make_value(L'b', 2));
    c1.insert(Mymultimap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    Mymultimap::iterator it = c1.begin();
    for (; it != c1.end(); ++it)
        {   // get a reference to an element
        Mymultimap::reference ref = *it;
        System::Console::Write("[{0} {1}] ", ref->first, ref->second);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
```

## <a name="rend"></a> multimap::rend (STL/CLR)

Ters çevrilen denetlenen dizinin sonuna belirler.

### <a name="syntax"></a>Sözdizimi

```cpp
reverse_iterator rend();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi hemen ötesine işaret eden bir başlangıç değerinin denetlenen dizideki ters yineleyici döndürür. Bu nedenle, atayan `end` ters dizisi. Gösteren bir yineleyici almak için kullandığınız `current` denetlenen dizinin uzunluğu değişirse sonuna ters sırada görülen denetlenen dizideki ancak durumunu değiştirebilirsiniz.

### <a name="example"></a>Örnek

```cpp
// cliext_multimap_rend.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::multimap<wchar_t, int> Mymultimap;
int main()
    {
    Mymultimap c1;
    c1.insert(Mymultimap::make_value(L'a', 1));
    c1.insert(Mymultimap::make_value(L'b', 2));
    c1.insert(Mymultimap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Mymultimap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // inspect first two items in reversed sequence
    Mymultimap::reverse_iterator rit = c1.rend();
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

## <a name="reverse_iterator"></a> multimap::reverse_iterator (STL/CLR)

Denetlenen dizi için bir ters yineleyici türü.

### <a name="syntax"></a>Sözdizimi

```cpp
typedef T3 reverse_iterator;
```

### <a name="remarks"></a>Açıklamalar

Bilinmeyen türde bir nesne tanımlayan bir tür `T3` denetlenen dizi için bir ters yineleyici olarak verebilir.

### <a name="example"></a>Örnek

```cpp
// cliext_multimap_reverse_iterator.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::multimap<wchar_t, int> Mymultimap;
int main()
    {
    Mymultimap c1;
    c1.insert(Mymultimap::make_value(L'a', 1));
    c1.insert(Mymultimap::make_value(L'b', 2));
    c1.insert(Mymultimap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]" reversed
    Mymultimap::reverse_iterator rit = c1.rbegin();
    for (; rit != c1.rend(); ++rit)
        System::Console::Write("[{0} {1}] ", rit->first, rit->second);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
[c 3] [b 2] [a 1]
```

## <a name="size"></a> multimap::size (STL/CLR)

Öğe sayısını sayar.

### <a name="syntax"></a>Sözdizimi

```cpp
size_type size();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, denetlenen dizinin uzunluğunu döndürür. Şu anda denetlenen dizideki öğelerin sayısını belirlemek için kullanın. Tümü, önem verdiğiniz ise dizisi bakın, sıfır olmayan boyutu olup [multimap::empty (STL/CLR)](../dotnet/multimap-empty-stl-clr.md)`()`.

### <a name="example"></a>Örnek

```cpp
// cliext_multimap_size.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::multimap<wchar_t, int> Mymultimap;
int main()
    {
    Mymultimap c1;
    c1.insert(Mymultimap::make_value(L'a', 1));
    c1.insert(Mymultimap::make_value(L'b', 2));
    c1.insert(Mymultimap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Mymultimap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // clear the container and reinspect
    c1.clear();
    System::Console::WriteLine("size() = {0} after clearing", c1.size());

    // add elements and clear again
    c1.insert(Mymultimap::make_value(L'd', 4));
    c1.insert(Mymultimap::make_value(L'e', 5));
    System::Console::WriteLine("size() = {0} after adding 2", c1.size());
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
size() = 0 after clearing
size() = 2 after adding 2
```

## <a name="size_type"></a> multimap::size_type (STL/CLR)

İki öğe arasındaki işaretli mesafenin türü.

### <a name="syntax"></a>Sözdizimi

```cpp
typedef int size_type;
```

### <a name="remarks"></a>Açıklamalar

Bir negatif olmayan öğe sayısını tanımlayan bir tür.

### <a name="example"></a>Örnek

```cpp
// cliext_multimap_size_type.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::multimap<wchar_t, int> Mymultimap;
int main()
    {
    Mymultimap c1;
    c1.insert(Mymultimap::make_value(L'a', 1));
    c1.insert(Mymultimap::make_value(L'b', 2));
    c1.insert(Mymultimap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Mymultimap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // compute positive difference
    Mymultimap::size_type diff = 0;
    for (Mymultimap::iterator it = c1.begin(); it != c1.end(); ++it)
        ++diff;
    System::Console::WriteLine("end()-begin() = {0}", diff);
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
end()-begin() = 3
```

## <a name="swap"></a> multimap::Swap (STL/CLR)

İki kapsayıcının içeriğinin yerini değiştirir.

### <a name="syntax"></a>Sözdizimi

```cpp
void swap(multimap<Key, Mapped>% right);
```

#### <a name="parameters"></a>Parametreler

*sağ*<br/>
Kapsayıcı içeriğini değiştirmek için.

### <a name="remarks"></a>Açıklamalar

Denetlenen diziyi üye işlevi değiştirir `this` ve *doğru*. Bunu Sabit sürede yapar ve hiçbir özel durum oluşturur. İki kapsayıcının içeriğinin değişimi için hızlı bir şekilde kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// cliext_multimap_swap.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::multimap<wchar_t, int> Mymultimap;
int main()
    {
    Mymultimap c1;
    c1.insert(Mymultimap::make_value(L'a', 1));
    c1.insert(Mymultimap::make_value(L'b', 2));
    c1.insert(Mymultimap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Mymultimap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // construct another container with repetition of values
    Mymultimap c2;
    c2.insert(Mymultimap::make_value(L'd', 4));
    c2.insert(Mymultimap::make_value(L'e', 5));
    c2.insert(Mymultimap::make_value(L'f', 6));
    for each (Mymultimap::value_type elem in c2)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // swap and redisplay
    c1.swap(c2);
    for each (Mymultimap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    for each (Mymultimap::value_type elem in c2)
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

## <a name="to_array"></a> multimap::to_array (STL/CLR)

Denetlenen dizideki, yeni bir diziye kopyalar.

### <a name="syntax"></a>Sözdizimi

```cpp
cli::array<value_type>^ to_array();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, denetlenen bir dizi içeren bir dizi döndürür. Dizi formunda denetlenen dizinin bir kopyasını almak için kullanın.

### <a name="example"></a>Örnek

```cpp
// cliext_multimap_to_array.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::multimap<wchar_t, int> Mymultimap;
int main()
    {
    Mymultimap c1;
    c1.insert(Mymultimap::make_value(L'a', 1));
    c1.insert(Mymultimap::make_value(L'b', 2));
    c1.insert(Mymultimap::make_value(L'c', 3));

    // copy the container and modify it
    cli::array<Mymultimap::value_type>^ a1 = c1.to_array();

    c1.insert(Mymultimap::make_value(L'd', 4));
    for each (Mymultimap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // display the earlier array copy
    for each (Mymultimap::value_type elem in a1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3] [d 4]
[a 1] [b 2] [c 3]
```

## <a name="upper_bound"></a> multimap::upper_bound (STL/CLR)

Belirtilen bir anahtarla eşleşen aralığı sonu bulur.

### <a name="syntax"></a>Sözdizimi

```cpp
iterator upper_bound(key_type key);
```

#### <a name="parameters"></a>Parametreler

*Anahtarı*<br/>
Aranacak anahtar değeri.

### <a name="remarks"></a>Açıklamalar

Üye işlevi son öğeyi belirler `X` için eşdeğer sıralamaya sahip denetlenen dizideki *anahtar*. Böyle bir öğe varsa veya `X` denetlenen dizideki son öğeyi döndürür olan [multimap::end (STL/CLR)](../dotnet/multimap-end-stl-clr.md)`()`; Aksi halde ötesindekiilköğeyibelirleyenbiryineleyicidöndürür `X`. Bir dizi öğe sonuna şu anda belirtilen bir anahtarla eşleşen denetlenen dizide bulmak için kullanın.

### <a name="example"></a>Örnek

```cpp
// cliext_multimap_upper_bound.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::multimap<wchar_t, int> Mymultimap;
int main()
    {
    Mymultimap c1;
    c1.insert(Mymultimap::make_value(L'a', 1));
    c1.insert(Mymultimap::make_value(L'b', 2));
    c1.insert(Mymultimap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Mymultimap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    System::Console::WriteLine("upper_bound(L'x')==end() = {0}",
        c1.upper_bound(L'x') == c1.end());

    Mymultimap::iterator it = c1.upper_bound(L'a');
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

## <a name="value_comp"></a> multimap::value_comp (STL/CLR)

İki öğenin değerlerini sıralama temsilcisi kopyalar.

### <a name="syntax"></a>Sözdizimi

```cpp
value_compare^ value_comp();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi denetlenen diziyi sıralamak için kullanılan sıralama temsilci döndürür. İki öğenin değerlerini karşılaştırmak için kullanın.

### <a name="example"></a>Örnek

```cpp
// cliext_multimap_value_comp.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymultimap;
int main()
    {
    Mymultimap c1;
    Mymultimap::value_compare^ kcomp = c1.value_comp();

    System::Console::WriteLine("compare([L'a', 1], [L'a', 1]) = {0}",
        kcomp(Mymultimap::make_value(L'a', 1),
            Mymultimap::make_value(L'a', 1)));
    System::Console::WriteLine("compare([L'a', 1], [L'b', 2]) = {0}",
        kcomp(Mymultimap::make_value(L'a', 1),
            Mymultimap::make_value(L'b', 2)));
    System::Console::WriteLine("compare([L'b', 2], [L'a', 1]) = {0}",
        kcomp(Mymultimap::make_value(L'b', 2),
            Mymultimap::make_value(L'a', 1)));
    System::Console::WriteLine();
    return (0);
    }
```

```Output
compare([L'a', 1], [L'a', 1]) = False
compare([L'a', 1], [L'b', 2]) = True
compare([L'b', 2], [L'a', 1]) = False
```

## <a name="value_compare"></a> multimap::value_compare (STL/CLR)

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
// cliext_multimap_value_compare.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymultimap;
int main()
    {
    Mymultimap c1;
    Mymultimap::value_compare^ kcomp = c1.value_comp();

    System::Console::WriteLine("compare([L'a', 1], [L'a', 1]) = {0}",
        kcomp(Mymultimap::make_value(L'a', 1),
            Mymultimap::make_value(L'a', 1)));
    System::Console::WriteLine("compare([L'a', 1], [L'b', 2]) = {0}",
        kcomp(Mymultimap::make_value(L'a', 1),
            Mymultimap::make_value(L'b', 2)));
    System::Console::WriteLine("compare([L'b', 2], [L'a', 1]) = {0}",
        kcomp(Mymultimap::make_value(L'b', 2),
            Mymultimap::make_value(L'a', 1)));
    System::Console::WriteLine();
    return (0);
    }
```

```Output
compare([L'a', 1], [L'a', 1]) = False
compare([L'a', 1], [L'b', 2]) = True
compare([L'b', 2], [L'a', 1]) = False
```

## <a name="value_type"></a> multimap::value_type (STL/CLR)

Öğenin türü.

### <a name="syntax"></a>Sözdizimi

```cpp
typedef generic_value value_type;
```

### <a name="remarks"></a>Açıklamalar

Türü eşanlamlıdır `generic_value`.

### <a name="example"></a>Örnek

```cpp
// cliext_multimap_value_type.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::multimap<wchar_t, int> Mymultimap;
int main()
    {
    Mymultimap c1;
    c1.insert(Mymultimap::make_value(L'a', 1));
    c1.insert(Mymultimap::make_value(L'b', 2));
    c1.insert(Mymultimap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]" using value_type
    for (Mymultimap::iterator it = c1.begin(); it != c1.end(); ++it)
        {   // store element in value_type object
        Mymultimap::value_type val = *it;
        System::Console::Write("[{0} {1}] ", val->first, val->second);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
```

## <a name="op_neq"></a> işleç! = (multimap) (STL/CLR)

Eşit değildir karşılaştırma listeleyin.

### <a name="syntax"></a>Sözdizimi

```cpp
template<typename Key,
    typename Mapped>
    bool operator!=(multimap<Key, Mapped>% left,
        multimap<Key, Mapped>% right);
```

#### <a name="parameters"></a>Parametreler

*Sol*<br/>
Karşılaştırılacak sol kapsayıcısı.

*sağ*<br/>
Karşılaştırılacak doğru kapsayıcısı.

### <a name="remarks"></a>Açıklamalar

İşleç işlevini döndürür `!(left == right)`. Test etmek için kullandığınız olmadığını *sol* aynı sıralı değil *doğru* iki multimaps karşılaştırılan öğe öğe olduğunda.

### <a name="example"></a>Örnek

```cpp
// cliext_multimap_operator_ne.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::multimap<wchar_t, int> Mymultimap;
int main()
    {
    Mymultimap c1;
    c1.insert(Mymultimap::make_value(L'a', 1));
    c1.insert(Mymultimap::make_value(L'b', 2));
    c1.insert(Mymultimap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Mymultimap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // assign to a new container
    Mymultimap c2;
    c2.insert(Mymultimap::make_value(L'a', 1));
    c2.insert(Mymultimap::make_value(L'b', 2));
    c2.insert(Mymultimap::make_value(L'd', 4));

    // display contents " [a 1] [b 2] [d 4]"
    for each (Mymultimap::value_type elem in c2)
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

## <a name="op_lt"></a> İşleç&lt; (multimap) (STL/CLR)

Liste değerinden karşılaştırma.

### <a name="syntax"></a>Sözdizimi

```cpp
template<typename Key,
    typename Mapped>
    bool operator<(multimap<Key, Mapped>% left,
        multimap<Key, Mapped>% right);
```

#### <a name="parameters"></a>Parametreler

*Sol*<br/>
Karşılaştırılacak sol kapsayıcısı.

*sağ*<br/>
Karşılaştırılacak doğru kapsayıcısı.

### <a name="remarks"></a>Açıklamalar

İşleç işlevi döndürür true ise, en düşük konumu için `i` hangi `!(right[i] < left[i])` de true olduğu `left[i] < right[i]`. Aksi halde `left->size() < right->size()` test etmek için kullandığınız olmadığını *sol* önceyse *doğru* iki multimaps karşılaştırılan öğe öğe olduğunda.

### <a name="example"></a>Örnek

```cpp
// cliext_multimap_operator_lt.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::multimap<wchar_t, int> Mymultimap;
int main()
    {
    Mymultimap c1;
    c1.insert(Mymultimap::make_value(L'a', 1));
    c1.insert(Mymultimap::make_value(L'b', 2));
    c1.insert(Mymultimap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Mymultimap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // assign to a new container
    Mymultimap c2;
    c2.insert(Mymultimap::make_value(L'a', 1));
    c2.insert(Mymultimap::make_value(L'b', 2));
    c2.insert(Mymultimap::make_value(L'd', 4));

    // display contents " [a 1] [b 2] [d 4]"
    for each (Mymultimap::value_type elem in c2)
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

## <a name="op_lteq"></a> İşleç&lt;= (multimap) (STL/CLR)

Küçüktür veya eşittir listesinde karşılaştırma.

### <a name="syntax"></a>Sözdizimi

```cpp
template<typename Key,
    typename Mapped>
    bool operator<=(multimap<Key, Mapped>% left,
        multimap<Key, Mapped>% right);
```

#### <a name="parameters"></a>Parametreler

*Sol*<br/>
Karşılaştırılacak sol kapsayıcısı.

*sağ*<br/>
Karşılaştırılacak doğru kapsayıcısı.

### <a name="remarks"></a>Açıklamalar

İşleç işlevini döndürür `!(right < left)`. Test etmek için kullandığınız olmadığını *sol* sonra sıralı değil *doğru* iki multimaps karşılaştırılan öğe öğe olduğunda.

### <a name="example"></a>Örnek

```cpp
// cliext_multimap_operator_le.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::multimap<wchar_t, int> Mymultimap;
int main()
    {
    Mymultimap c1;
    c1.insert(Mymultimap::make_value(L'a', 1));
    c1.insert(Mymultimap::make_value(L'b', 2));
    c1.insert(Mymultimap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Mymultimap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // assign to a new container
    Mymultimap c2;
    c2.insert(Mymultimap::make_value(L'a', 1));
    c2.insert(Mymultimap::make_value(L'b', 2));
    c2.insert(Mymultimap::make_value(L'd', 4));

    // display contents " [a 1] [b 2] [d 4]"
    for each (Mymultimap::value_type elem in c2)
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

## <a name="op_eq"></a> işleç == (multimap) (STL/CLR)

Eşit karşılaştırma listeleyin.

### <a name="syntax"></a>Sözdizimi

```cpp
template<typename Key,
    typename Mapped>
    bool operator==(multimap<Key, Mapped>% left,
        multimap<Key, Mapped>% right);
```

#### <a name="parameters"></a>Parametreler

*Sol*<br/>
Karşılaştırılacak sol kapsayıcısı.

*sağ*<br/>
Karşılaştırılacak doğru kapsayıcısı.

### <a name="remarks"></a>Açıklamalar

İşleç işlevini dizileri denetlediği yalnızca, true değerini döndürür *sol* ve *doğru* aynı uzunluğa sahip ve her konum için `i`, `left[i] ==` `right[i]`. Test etmek için kullandığınız olmadığını *sol* aynı sıralı *doğru* iki multimaps karşılaştırılan öğe öğe olduğunda.

### <a name="example"></a>Örnek

```cpp
// cliext_multimap_operator_eq.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::multimap<wchar_t, int> Mymultimap;
int main()
    {
    Mymultimap c1;
    c1.insert(Mymultimap::make_value(L'a', 1));
    c1.insert(Mymultimap::make_value(L'b', 2));
    c1.insert(Mymultimap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Mymultimap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // assign to a new container
    Mymultimap c2;
    c2.insert(Mymultimap::make_value(L'a', 1));
    c2.insert(Mymultimap::make_value(L'b', 2));
    c2.insert(Mymultimap::make_value(L'd', 4));

    // display contents " [a 1] [b 2] [d 4]"
    for each (Mymultimap::value_type elem in c2)
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

## <a name="op_gt"></a> İşleç&gt; (multimap) (STL/CLR)

Karşılaştırma büyük listeler.

### <a name="syntax"></a>Sözdizimi

```cpp
template<typename Key,
    typename Mapped>
    bool operator>(multimap<Key, Mapped>% left,
        multimap<Key, Mapped>% right);
```

#### <a name="parameters"></a>Parametreler

*Sol*<br/>
Karşılaştırılacak sol kapsayıcısı.

*sağ*<br/>
Karşılaştırılacak doğru kapsayıcısı.

### <a name="remarks"></a>Açıklamalar

İşleç işlevini döndürür `right` `<` `left`. Test etmek için kullandığınız olmadığını *sol* sonra sıralı *doğru* iki multimaps karşılaştırılan öğe öğe olduğunda.

### <a name="example"></a>Örnek

```cpp
// cliext_multimap_operator_gt.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::multimap<wchar_t, int> Mymultimap;
int main()
    {
    Mymultimap c1;
    c1.insert(Mymultimap::make_value(L'a', 1));
    c1.insert(Mymultimap::make_value(L'b', 2));
    c1.insert(Mymultimap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Mymultimap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // assign to a new container
    Mymultimap c2;
    c2.insert(Mymultimap::make_value(L'a', 1));
    c2.insert(Mymultimap::make_value(L'b', 2));
    c2.insert(Mymultimap::make_value(L'd', 4));

    // display contents " [a 1] [b 2] [d 4]"
    for each (Mymultimap::value_type elem in c2)
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

## <a name="op_gteq"></a> İşleç&gt;= (multimap) (STL/CLR)

Liste büyüktür veya eşittir karşılaştırma.

### <a name="syntax"></a>Sözdizimi

```cpp
template<typename Key,
    typename Mapped>
    bool operator>=(multimap<Key, Mapped>% left,
        multimap<Key, Mapped>% right);
```

#### <a name="parameters"></a>Parametreler

*Sol*<br/>
Karşılaştırılacak sol kapsayıcısı.

*sağ*<br/>
Karşılaştırılacak doğru kapsayıcısı.

### <a name="remarks"></a>Açıklamalar

İşleç işlevini döndürür `!(left` `<` `right)`. Test etmek için kullandığınız olmadığını *sol* önce sıralı değil *doğru* iki multimaps karşılaştırılan öğe öğe olduğunda.

### <a name="example"></a>Örnek

```cpp
// cliext_multimap_operator_ge.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::multimap<wchar_t, int> Mymultimap;
int main()
    {
    Mymultimap c1;
    c1.insert(Mymultimap::make_value(L'a', 1));
    c1.insert(Mymultimap::make_value(L'b', 2));
    c1.insert(Mymultimap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Mymultimap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // assign to a new container
    Mymultimap c2;
    c2.insert(Mymultimap::make_value(L'a', 1));
    c2.insert(Mymultimap::make_value(L'b', 2));
    c2.insert(Mymultimap::make_value(L'd', 4));

    // display contents " [a 1] [b 2] [d 4]"
    for each (Mymultimap::value_type elem in c2)
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