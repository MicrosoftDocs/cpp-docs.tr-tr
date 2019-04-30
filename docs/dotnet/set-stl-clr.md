---
title: set (STL/CLR)
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- cliext::set
- cliext::operator!=
- cliext::operator<
- cliext::operator<=
- cliext::operator==
- cliext::operator>
- cliext::operator>=
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
ms.openlocfilehash: 612c0772504043a99f3a2ae9fa7da9c791076d6a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62384653"
---
# <a name="set-stlclr"></a>set (STL/CLR)

Şablon sınıfı, iki yönlü erişime sahip öğelerin değişen uzunluktaki dizisini denetleyen bir nesneyi tanımlar. Kapsayıcı kullandığınız `set` her bir öğe depolama bir dizi öğe (yaklaşık) dengeli sıralı ağacı düğümleri olarak yönetilecek.

Aşağıdaki açıklamada `GValue` aynı `GKey`, sırayla olduğu aynı *anahtarı* ikinci bir başvuru türü olmadığı sürece olduğu durumda `Key^`.

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
Denetlenen sıradaki öğenin anahtar bileşen türü.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<cliext/kümesi >

**Namespace:** cliext

## <a name="declarations"></a>Bildirimler

|Tür Tanımlaması|Açıklama|
|---------------------|-----------------|
|[set::const_iterator (STL/CLR)](#const_iterator)|Denetlenen dizi için bir sabit yineleyici türü.|
|[set::const_reference (STL/CLR)](#const_reference)|Bir öğe için sabit bir başvuru türü.|
|[set::const_reverse_iterator (STL/CLR)](#const_reverse_iterator)|Denetlenen dizi için bir sabit ters yineleyici türü.|
|[set::difference_type (STL/CLR)](#difference_type)|İki öğe arasındaki (büyük olasılıkla işaretli) mesafenin türü.|
|[set::generic_container (STL/CLR)](#generic_container)|Kapsayıcı için genel arabirim türü.|
|[set::generic_iterator (STL/CLR)](#generic_iterator)|Kapsayıcı için genel arabirimi için bir yineleyici türü.|
|[set::generic_reverse_iterator (STL/CLR)](#generic_reverse_iterator)|Kapsayıcı için genel arabirimi için ters yineleyici türü.|
|[set::generic_value (STL/CLR)](#generic_value)|Kapsayıcı için genel arabirimi için bir öğe türü.|
|[set::iterator (STL/CLR)](#iterator)|Denetlenen dizi için bir yineleyici türü.|
|[set::key_compare (STL/CLR)](#key_compare)|İki anahtar sıralama temsilcisi.|
|[set::key_type (STL/CLR)](#key_type)|Bir sıralama anahtarının türü.|
|[set::reference (STL/CLR)](#reference)|Bir öğe için bir başvuru türü.|
|[set::reverse_iterator (STL/CLR)](#reverse_iterator)|Denetlenen dizi için bir ters yineleyici türü.|
|[set::size_type (STL/CLR)](#size_type)|İki öğe arasındaki bir (negatif) mesafenin türü.|
|[set::value_compare (STL/CLR)](#value_compare)|İki öğenin değerlerini sıralama temsilcisi.|
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
|[set::key_comp (STL/CLR)](#key_comp)|İki anahtar sıralama temsilcisi kopyalar.|
|[set::lower_bound (STL/CLR)](#lower_bound)|Belirtilen bir anahtarla eşleşen aralığı başlangıcını bulur.|
|[set::make_value (STL/CLR)](#make_value)|Değer bir nesne oluşturur.|
|[set::rbegin (STL/CLR)](#rbegin)|Ters çevrilen denetlenen dizinin başlangıç belirler.|
|[set::rend (STL/CLR)](#rend)|Ters çevrilen denetlenen dizinin sonuna belirler.|
|[set::set (STL/CLR)](#set)|Bir kapsayıcı nesnesi oluşturur.|
|[set::size (STL/CLR)](#size)|Öğe sayısını sayar.|
|[set::swap (STL/CLR)](#swap)|İki kapsayıcının içeriğinin yerini değiştirir.|
|[set::to_array (STL/CLR)](#to_array)|Denetlenen dizideki, yeni bir diziye kopyalar.|
|[set::upper_bound (STL/CLR)](#upper_bound)|Belirtilen bir anahtarla eşleşen aralığı sonu bulur.|
|[set::value_comp (STL/CLR)](#value_comp)|İki öğenin değerlerini sıralama temsilcisi kopyalar.|

|İşleç|Açıklama|
|--------------|-----------------|
|[set::operator= (STL/CLR)](#op_as)|Denetlenen dizi değiştirir.|
|[operator!= (set) (STL/CLR)](#op_neq)|Belirler bir `set` nesnesi, diğerine eşit değil `set` nesne.|
|[operator< (set) (STL/CLR)](#op_lt)|Belirler bir `set` nesnedir daha az `set` nesne.|
|[operator<= (set) (STL/CLR)](#op_lteq)|Belirler bir `set` nesnedir küçüktür veya eşittir diğerine `set` nesne.|
|[operator== (set) (STL/CLR)](#op_eq)|Belirler bir `set` nesnedir diğerine eşit `set` nesne.|
|[operator> (set) (STL/CLR)](#op_gt)|Belirler bir `set` nesnedir diğerinden daha büyük `set` nesne.|
|[operator>= (set) (STL/CLR)](#op_gteq)|Belirler bir `set` nesnedir büyüktür veya eşittir diğerine `set` nesne.|

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

Nesne türünde bir saklı temsilci nesnesi çağırarak denetlediği diziyi sıralar [set::key_compare (STL/CLR)](../dotnet/set-key-compare-stl-clr.md). Kümeyi oluştururken saklı temsilci nesnesi belirtebilirsiniz; hiçbir temsilci nesnesi belirtirseniz, karşılaştırma varsayılandır `operator<(key_type, key_type)`. Üye işlevini çağırarak depolanan bu nesne erişim [set::key_comp (STL/CLR)](../dotnet/set-key-comp-stl-clr.md)`()`.

Bu tür bir temsilci nesnesinin katı bir zayıf anahtarları türünde sıralama dayatır gerekir [set::key_type (STL/CLR)](../dotnet/set-key-type-stl-clr.md). Anlamına gelir, için iki anahtar `X` ve `Y`:

`key_comp()(X, Y)` Her çağrıda aynı Boolean sonucu döndürür.

Varsa `key_comp()(X, Y)` true ise `key_comp()(Y, X)` false olmalıdır.

Varsa `key_comp()(X, Y)` true ise `X` önce sıralanmalıdır söylenir `Y`.

Varsa `!key_comp()(X, Y) && !key_comp()(Y, X)` true ise `X` ve `Y` eşdeğer sıralamaya olduğu söylenir.

Herhangi bir öğe için `X` metninden önce `Y` denetlenen dizideki `key_comp()(Y, X)` false'tur. (Varsayılan temsilci nesne için anahtarları asla değerini azaltın.) Şablon sınıfının aksine [ayarlamak](../dotnet/set-stl-clr.md), şablon sınıfın bir nesnesi `set` tüm öğeler için anahtarlarının benzersiz olduğundan emin olması gerekmez. (İki veya daha fazla anahtarı eşdeğer sıralamaya sahip olabilir.)

Her öğe bir tuş hem de bir değer olarak görev yapar. Sıra, arama, ekleme ve kaldırma işlemleri için öğelerin sayısını logaritmasını orantılı sayısıyla rastgele bir öğenin (Logaritmik süre) sırada izin veren bir şekilde temsil edilir. Ayrıca, bir öğe eklenmesi hiçbir yineleyiciyi geçersiz kılmaz; bir öğenin kaldırılması yalnızca bu kaldırılan öğeyi gösteren yineleyicileri geçersiz kılar.

Denetlenen dizideki bir öğeyi belirleyen bir yineleyici verilen bitişik öğelere adım anlamına gelir kümesi, çift yönlü yineleyiciler destekler. Özel bir baş düğüm tarafından döndürülen yineleyici karşılık gelen [set::end (STL/CLR)](../dotnet/set-end-stl-clr.md)`()`. Denetlenen dizi içindeki son öğeden ulaşmak için bu yineleyici varsa azaltma. Baş düğüm erişmek için bir set yineleyici artırabilirsiniz ve bu sonra eşittir karşılaştıracağız `end()`. Ancak tarafından döndürülen yineleyici başvurulamıyor `end()`.

Doğrudan bir rastgele erişim yineleyici gerektiren sayısal konumunu--verilen kümesi öğesine başvuramaz unutmayın.

Sırayla ilişkilendirilmiş kapsayıcısı için bir tanıtıcı depolar, ilişkili küme düğümü için bir tanıtıcı kümesi yineleyici depolar. Yineleyiciler yalnızca ilişkili kapsayıcı nesneleri ile kullanabilirsiniz. Kümesi Yineleyici, onun ilişkili küme düğümü bazı kümesiyle ilişkili olduğu sürece geçerli kalır. Ayrıca, geçerli bir yineleyici yineleyicisine--erişmek veya eşit değildir sürece bu atayan--öğe değeri değiştirmek için kullanabilirsiniz `end()`.

Silme veya bir öğenin kaldırılması için depolanan değerine yıkıcı çağırır. Kapsayıcı yok etme tüm öğelerini siler. Bu nedenle, hiçbir öğe'nin kapsayıcı daha uzun sürmesi başvuru sınıfı, öğe türü olan bir kapsayıcı sağlar. Ancak, bir kapsayıcı tutamaçlarından yaptığı unutmayın *değil* öğelerini yok edin.

## <a name="members"></a>Üyeler

## <a name="begin"></a>set::begin (STL/CLR)

Denetlenen dizinin başlangıcını belirtir.

### <a name="syntax"></a>Sözdizimi

```cpp
iterator begin();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, denetlenen dizinin ya da boş bir dizi bitiminin ötesinde yalnızca ilk öğeyi belirleyen çift yönlü bir yineleyici döndürür. Gösteren bir yineleyici almak için kullandığınız `current` denetlenen dizideki ancak durumu başına denetlenen dizinin uzunluğu değişirse değiştirebilirsiniz.

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

## <a name="clear"></a>set::Clear (STL/CLR)

Tüm öğeleri kaldırır.

### <a name="syntax"></a>Sözdizimi

```cpp
void clear();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi etkili bir şekilde çağıran [set::erase (STL/CLR)](../dotnet/set-erase-stl-clr.md) `(` [set::begin (STL/CLR)](../dotnet/set-begin-stl-clr.md) `(),` [set::end (STL/CLR)](../dotnet/set-end-stl-clr.md) `())`. Denetlenen dizi boş olduğundan emin olmak için kullanın.

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

## <a name="const_iterator"></a>set::const_iterator (STL/CLR)

Denetlenen dizi için bir sabit yineleyici türü.

### <a name="syntax"></a>Sözdizimi

```cpp
typedef T2 const_iterator;
```

### <a name="remarks"></a>Açıklamalar

Bilinmeyen türde bir nesne tanımlayan bir tür `T2` denetlenen dizi için sabit bir çift yönlü bir yineleyici olarak verebilir.

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

## <a name="const_reference"></a>set::const_reference (STL/CLR)

Bir öğe için sabit bir başvuru türü.

### <a name="syntax"></a>Sözdizimi

```cpp
typedef value_type% const_reference;
```

### <a name="remarks"></a>Açıklamalar

Bir öğe için sabit bir başvuru türü açıklar.

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

## <a name="const_reverse_iterator"></a>set::const_reverse_iterator (STL/CLR)

Denetlenen dizi için bir sabit ters yineleyici türü...

### <a name="syntax"></a>Sözdizimi

```cpp
typedef T4 const_reverse_iterator;
```

### <a name="remarks"></a>Açıklamalar

Bilinmeyen türde bir nesne tanımlayan bir tür `T4` denetlenen dizi için bir sabit ters yineleyici olarak verebilir.

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

## <a name="count"></a>set::Count (STL/CLR)

Belirtilen bir anahtar ile eşleşen öğe sayısını bulur.

### <a name="syntax"></a>Sözdizimi

```cpp
size_type count(key_type key);
```

#### <a name="parameters"></a>Parametreler

*anahtar*<br/>
Aranacak anahtar değeri.

### <a name="remarks"></a>Açıklamalar

Üye işlevi ile eşdeğer sıralamaya sahip denetlenen dizideki öğelerin sayısını döndürür. *anahtar*. Belirtilen bir anahtarla eşleşen şu anda denetlenen dizideki öğelerin sayısını belirlemek için kullanın.

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

## <a name="difference_type"></a>set::difference_type (STL/CLR)

İki öğe arasındaki işaretli mesafenin türü.

### <a name="syntax"></a>Sözdizimi

```cpp
typedef int difference_type;
```

### <a name="remarks"></a>Açıklamalar

Büyük olasılıkla negatif öğe sayısını tanımlayan bir tür.

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

## <a name="empty"></a>set::Empty (STL/CLR)

Bir öğe olup olmadığını sınar.

### <a name="syntax"></a>Sözdizimi

```cpp
bool empty();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi boş bir denetlenmiş dizi için true değerini döndürür. Eşdeğerdir [set::size (STL/CLR)](../dotnet/set-size-stl-clr.md)`() == 0`. Kümenin boş olup olmadığını test etmek için kullanın.

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

## <a name="end"></a>set::End (STL/CLR)

Denetlenen dizinin bitişini belirtir.

### <a name="syntax"></a>Sözdizimi

```cpp
iterator end();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, denetlenen dizinin sonuna hemen ötesine işaret eden çift yönlü bir yineleyici döndürür. Denetlenen dizinin sonuna belirten bir yineleyici almak için kullanın. kendi durum eklenmemişse denetlenen dizinin uzunluğu değişirse değiştiremezsiniz.

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

## <a name="equal_range"></a>set::equal_range (STL/CLR)

Belirtilen bir anahtarla eşleşen aralığı bulur.

### <a name="syntax"></a>Sözdizimi

```cpp
cliext::pair<iterator, iterator> equal_range(key_type key);
```

#### <a name="parameters"></a>Parametreler

*anahtar*<br/>
Aranacak anahtar değeri.

### <a name="remarks"></a>Açıklamalar

Üye işlevi Yineleyicilerin bir çiftini döndürür `cliext::pair<iterator, iterator>(` [set::lower_bound (STL/CLR)](../dotnet/set-lower-bound-stl-clr.md) `(key),` [set::upper_bound (STL/CLR)](../dotnet/set-upper-bound-stl-clr.md)`(key))`. Belirtilen bir anahtarla eşleşen öğeleri şu anda denetlenen dizideki aralığı belirlemek için kullanın.

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

## <a name="erase"></a>set::ERASE (STL/CLR)

Belirtilen konumlardaki öğeleri kaldırır.

### <a name="syntax"></a>Sözdizimi

```cpp
iterator erase(iterator where);
iterator erase(iterator first, iterator last);
size_type erase(key_type key)
```

#### <a name="parameters"></a>Parametreler

*ilk*<br/>
Silme aralığını başlangıcı.

*anahtar*<br/>
Silinecek anahtar değer.

*Son*<br/>
Silinecek aralığı sonu.

*Burada*<br/>
Silinecek öğe.

### <a name="remarks"></a>Açıklamalar

İlk üye işlevi tarafından denetlenen dizinin öğeyi kaldırır *burada*ve kaldırıldı, öğenin dışında kalan ilk öğeyi belirleyen bir yineleyici döndürür veya [set::end (STL/CLR) ](../dotnet/set-end-stl-clr.md) `()` böyle bir öğe varsa. Tek bir öğe kaldırmak için kullanın.

İkinci üye işlevi öğeleri denetlenen dizinin aralıktaki kaldırır. [`first`, `last`) ve kaldırılan tüm öğelerin ötesindeki ilk öğeyi belirleyen bir yineleyici döndürür veya `end()` böyle bir öğe varsa var... Sıfır veya daha fazla ardışık öğeleri kaldırmak için kullanın.

Üçüncü üye işlevi olan anahtara sahip eşdeğer sıralamaya denetlenen dizideki herhangi bir öğe kaldırır için *anahtarı*ve kaldırılan öğelerin sayısını döndürür. Kaldırın ve belirtilen bir anahtarla eşleşen tüm öğeleri saymak için kullanın.

Her öğe silinme için öğelerin sayısını logaritmasını orantılı zaman denetlenen dizide alır.

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

## <a name="find"></a>set::find (STL/CLR)

Belirtilen bir anahtarla eşleşen bir öğeyi bulur.

### <a name="syntax"></a>Sözdizimi

```cpp
iterator find(key_type key);
```

#### <a name="parameters"></a>Parametreler

*anahtar*<br/>
Aranacak anahtar değeri.

### <a name="remarks"></a>Açıklamalar

Denetlenen dizideki en az bir öğe ile eşdeğer sıralamaya sahipse *anahtarı*, üye işlevi biri bu öğeleri gösteren bir yineleyici döndürür; Aksi halde döndürür [set::end (STL/CLR)](../dotnet/set-end-stl-clr.md)`()`. Bir öğe şu anda belirtilen bir anahtarla eşleşen denetlenen dizide bulmak için kullanın.

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

## <a name="generic_container"></a>set::generic_container (STL/CLR)

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

## <a name="generic_iterator"></a> set::generic_iterator (STL/CLR)

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

## <a name="generic_reverse_iterator"></a> set::generic_reverse_iterator (STL/CLR)

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

## <a name="generic_value"></a> set::generic_value (STL/CLR)

Kapsayıcı için genel arabirimi ile kullanmak için bir öğe türü.

### <a name="syntax"></a>Sözdizimi

```cpp
typedef GValue generic_value;
```

### <a name="remarks"></a>Açıklamalar

Türünde bir nesneyi tanımlayan bir tür `GValue` açıklayan yönelik genel arabirimi için bu şablonu kapsayıcı sınıfı ile kullanmak için depolanan öğenin değeri.

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

## <a name="insert"></a> set::insert (STL/CLR)

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

İlk üye işlevi endeavors değere sahip bir öğe eklemek *val*ve bir değer çiftini döndürür `X`. Varsa `X.second` true ise `X.first` yeni eklenen öğeyi belirler; Aksi takdirde `X.first` eşdeğer olan bir öğeyi belirleyen sıralama zaten var ve yeni bir öğe yok eklenir. Tek bir öğe eklemek için kullanın.

İkinci üye işlevi değere sahip bir öğe ekler *val*kullanarak *burada* (performansını artırmak için) bir ipucu olarak ve yeni eklenen öğeyi belirleyen bir yineleyici döndürür. Bildiğiniz bir öğeye bitişik olabilecek tek bir öğe eklemek için kullanın.

Üçüncü üye işlevi ekler dizisi [`first`, `last`). Başka bir diziden kopyalanan sıfır veya daha fazla öğe eklemek için kullanın.

Dördüncü üye işlevi tarafından belirlenen dizisi ekler *doğru*. Bir numaralandırıcı tarafından açıklanan bir dizi eklemek için kullanın.

Her öğe ekleme, denetlenen dizide öğe sayısı için logaritmasını orantılı zaman alır. Ekleme, ekleme noktasını bitişik bir öğeyi belirleyen bir ipucu verilen amorti edilmiş sabit sürede bir ancak ortaya çıkabilir.

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

## <a name="iterator"></a> set::iterator (STL/CLR)

Denetlenen dizi için bir yineleyici türü.

### <a name="syntax"></a>Sözdizimi

```cpp
typedef T1 iterator;
```

### <a name="remarks"></a>Açıklamalar

Bilinmeyen türde bir nesne tanımlayan bir tür `T1` denetlenen dizi için çift yönlü bir yineleyici olarak verebilir.

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

## <a name="key_comp"></a> set::key_comp (STL/CLR)

İki anahtar sıralama temsilcisi kopyalar.

### <a name="syntax"></a>Sözdizimi

```cpp
key_compare^key_comp();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi denetlenen diziyi sıralamak için kullanılan sıralama temsilci döndürür. İki anahtar karşılaştırmak için kullanın.

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

## <a name="key_compare"></a> set::key_compare (STL/CLR)

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

## <a name="key_type"></a> set::key_type (STL/CLR)

Bir sıralama anahtarının türü.

### <a name="syntax"></a>Sözdizimi

```cpp
typedef Key key_type;
```

### <a name="remarks"></a>Açıklamalar

Şablon parametresi için bir eşanlamlı türüdür *anahtar*.

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

## <a name="lower_bound"></a> set::lower_bound (STL/CLR)

Belirtilen bir anahtarla eşleşen aralığı başlangıcını bulur.

### <a name="syntax"></a>Sözdizimi

```cpp
iterator lower_bound(key_type key);
```

#### <a name="parameters"></a>Parametreler

*anahtar*<br/>
Aranacak anahtar değeri.

### <a name="remarks"></a>Açıklamalar

Üye işlevi ilk öğeyi belirleyen `X` için eşdeğer sıralamaya sahip denetlenen dizideki *anahtar*. Böyle bir öğe var olup olmadığını döndürür [set::end (STL/CLR)](../dotnet/set-end-stl-clr.md)`()`; Aksi halde gösteren bir yineleyici döndürür `X`. Bir dizi öğe başına şu anda belirtilen bir anahtarla eşleşen denetlenen dizide bulmak için kullanın.

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

## <a name="make_value"></a> set::make_value (STL/CLR)

Değer bir nesne oluşturur.

### <a name="syntax"></a>Sözdizimi

```cpp
static value_type make_value(key_type key);
```

#### <a name="parameters"></a>Parametreler

*anahtar*<br/>
Kullanılacak anahtar değeri.

### <a name="remarks"></a>Açıklamalar

Üye işlevi döndürür bir `value_type` nesne anahtarı *anahtar*. Çeşitli üye işlevleri ile kullanım için uygun bir nesne oluşturmak için kullanın.

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

## <a name="op_as"></a> set::operator (STL/CLR) =

Denetlenen dizi değiştirir.

### <a name="syntax"></a>Sözdizimi

```cpp
set<Key>% operator=(set<Key>% right);
```

#### <a name="parameters"></a>Parametreler

*sağ*<br/>
Kopyalanacak kapsayıcı.

### <a name="remarks"></a>Açıklamalar

Üye işleci kopyaları *doğru* ardından nesneye döndürür `*this`. Denetlenen dizi denetlenen dizide bir kopyasını değiştirmek için kullandığınız *doğru*.

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

## <a name="rbegin"></a> set::rbegin (STL/CLR)

Ters çevrilen denetlenen dizinin başlangıç belirler.

### <a name="syntax"></a>Sözdizimi

```cpp
reverse_iterator rbegin();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, denetlenen dizinin ya da boş bir dizi başlangıcı hemen ötesinde son öğeyi belirleyen bir ters yineleyici döndürür. Bu nedenle, atayan `beginning` ters dizisi. Gösteren bir yineleyici almak için kullandığınız `current` denetlenen dizinin uzunluğu değişirse başlangıcına ters sırada görülen denetlenen dizideki ancak durumunu değiştirebilirsiniz.

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

## <a name="reference"></a> set::Reference (STL/CLR)

Bir öğe için bir başvuru türü.

### <a name="syntax"></a>Sözdizimi

```cpp
typedef value_type% reference;
```

### <a name="remarks"></a>Açıklamalar

Öğeye bir başvuru türü açıklar.

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

## <a name="rend"></a> set::rend (STL/CLR)

Ters çevrilen denetlenen dizinin sonuna belirler.

### <a name="syntax"></a>Sözdizimi

```cpp
reverse_iterator rend();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi hemen ötesine işaret eden bir başlangıç değerinin denetlenen dizideki ters yineleyici döndürür. Bu nedenle, atayan `end` ters dizisi. Gösteren bir yineleyici almak için kullandığınız `current` denetlenen dizinin uzunluğu değişirse sonuna ters sırada görülen denetlenen dizideki ancak durumunu değiştirebilirsiniz.

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

## <a name="reverse_iterator"></a> set::reverse_iterator (STL/CLR)

Denetlenen dizi için bir ters yineleyici türü.

### <a name="syntax"></a>Sözdizimi

```cpp
typedef T3 reverse_iterator;
```

### <a name="remarks"></a>Açıklamalar

Bilinmeyen türde bir nesne tanımlayan bir tür `T3` denetlenen dizi için bir ters yineleyici olarak verebilir.

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

## <a name="set"></a> set::set (STL/CLR)

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

`set();`

Varsayılan karşılaştırma sıralama ile denetlenen dizideki herhangi bir öğesi ile başlatır `key_compare()`. Koşul sıralama varsayılan bir boş ilk denetlenen sıra belirtmek için kullanın.

Oluşturucu:

`explicit set(key_compare^ pred);`

Denetlenen dizi sıralama koşul ile hiçbir öğe ile başlatır *pred*. Bir boş ilk denetlenen sıra ile belirtilen sıralama koşulu belirtmek için kullanın.

Oluşturucu:

`set(set<Key>% right);`

Denetlenen dizi sırası başlatır [`right.begin()`, `right.end()`), koşul sıralama varsayılan. Küme nesnesi tarafından denetlenen dizinin bir kopyasını olan ilk denetimli bir sıra belirtmek için kullandığınız *doğru*, koşul sıralama varsayılan.

Oluşturucu:

`set(set<Key>^ right);`

Denetlenen dizi sırası başlatır [`right->begin()`, `right->end()`), koşul sıralama varsayılan. Küme nesnesi tarafından denetlenen dizinin bir kopyasını olan ilk denetimli bir sıra belirtmek için kullandığınız *doğru*, koşul sıralama varsayılan.

Oluşturucu:

`template<typename InIter> set(InIter first, InIter last);`

Denetlenen dizi sırası başlatır [`first`, `last`), koşul sıralama varsayılan. Denetlenen dizi başka bir dizinin bir kopyasını varsayılan karşılaştırma sıralama yapmak için kullanın.

Oluşturucu:

`template<typename InIter> set(InIter first, InIter last, key_compare^ pred);`

Denetlenen dizi sırası başlatır [`first`, `last`), sıralama koşul ile *pred*. Denetlenen dizi belirtilen sıralama koşul ile başka bir sıralı bir kopyasını kullanın.

Oluşturucu:

`set(System::Collections::Generic::IEnumerable<Key>^ right);`

Denetlenen dizi numaralandırıcı tarafından belirtilen sıra başlatır *doğru*, koşul sıralama varsayılan. Denetlenen dizi başka bir sıralı karşılaştırma sıralama varsayılan bir numaralandırıcı tarafından açıklanan bir kopyasını kullanın.

Oluşturucu:

`set(System::Collections::Generic::IEnumerable<Key>^ right, key_compare^ pred);`

Denetlenen dizi numaralandırıcı tarafından belirtilen sıra başlatır *doğru*, sıralama koşul ile *pred*. Denetlenen dizi, başka bir dizisi tarafından belirtilen sıralama koşul ile bir numaralandırıcı açıklanan kopyasını kullanın.

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

## <a name="size"></a> set::size (STL/CLR)

Öğe sayısını sayar.

### <a name="syntax"></a>Sözdizimi

```cpp
size_type size();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, denetlenen dizinin uzunluğunu döndürür. Şu anda denetlenen dizideki öğelerin sayısını belirlemek için kullanın. Tümü, önem verdiğiniz ise dizisi bakın, sıfır olmayan boyutu olup [set::empty (STL/CLR)](../dotnet/set-empty-stl-clr.md)`()`.

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

## <a name="size_type"></a> set::size_type (STL/CLR)

İki öğe arasındaki işaretli mesafenin türü.

### <a name="syntax"></a>Sözdizimi

```cpp
typedef int size_type;
```

### <a name="remarks"></a>Açıklamalar

Bir negatif olmayan öğe sayısını tanımlayan bir tür.

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

## <a name="swap"></a> set::Swap (STL/CLR)

İki kapsayıcının içeriğinin yerini değiştirir.

### <a name="syntax"></a>Sözdizimi

```cpp
void swap(set<Key>% right);
```

#### <a name="parameters"></a>Parametreler

*sağ*<br/>
Kapsayıcı içeriğini değiştirmek için.

### <a name="remarks"></a>Açıklamalar

Denetlenen diziyi üye işlevi değiştirir `this` ve *doğru*. Bunu Sabit sürede yapar ve hiçbir özel durum oluşturur. İki kapsayıcının içeriğinin değişimi için hızlı bir şekilde kullanırsınız.

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

## <a name="to_array"></a> set::to_array (STL/CLR)

Denetlenen dizideki, yeni bir diziye kopyalar.

### <a name="syntax"></a>Sözdizimi

```cpp
cli::array<value_type>^ to_array();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, denetlenen bir dizi içeren bir dizi döndürür. Dizi formunda denetlenen dizinin bir kopyasını almak için kullanın.

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

## <a name="upper_bound"></a> set::upper_bound (STL/CLR)

Belirtilen bir anahtarla eşleşen aralığı sonu bulur.

### <a name="syntax"></a>Sözdizimi

```cpp
iterator upper_bound(key_type key);
```

#### <a name="parameters"></a>Parametreler

*anahtar*<br/>
Aranacak anahtar değeri.

### <a name="remarks"></a>Açıklamalar

Üye işlevi son öğeyi belirler `X` için eşdeğer sıralamaya sahip denetlenen dizideki *anahtar*. Böyle bir öğe varsa veya `X` denetlenen dizideki son öğeyi döndürür olan [set::end (STL/CLR)](../dotnet/set-end-stl-clr.md)`()`; Aksi halde ötesindekiilköğeyibelirleyenbiryineleyicidöndürür`X`. Bir dizi öğe sonuna şu anda belirtilen bir anahtarla eşleşen denetlenen dizide bulmak için kullanın.

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

## <a name="value_comp"></a> set::value_comp (STL/CLR)

İki öğenin değerlerini sıralama temsilcisi kopyalar.

### <a name="syntax"></a>Sözdizimi

```cpp
value_compare^ value_comp();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi denetlenen diziyi sıralamak için kullanılan sıralama temsilci döndürür. İki öğenin değerlerini karşılaştırmak için kullanın.

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

## <a name="value_compare"></a> set::value_compare (STL/CLR)

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

## <a name="value_type"></a> set::value_type (STL/CLR)

Öğenin türü.

### <a name="syntax"></a>Sözdizimi

```cpp
typedef generic_value value_type;
```

### <a name="remarks"></a>Açıklamalar

Türü eşanlamlıdır `generic_value`.

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

## <a name="op_neq"></a> işleç! = (set) (STL/CLR)

Eşit değildir karşılaştırma listeleyin.

### <a name="syntax"></a>Sözdizimi

```cpp
template<typename Key>
    bool operator!=(set<Key>% left,
        set<Key>% right);
```

#### <a name="parameters"></a>Parametreler

*Sol*<br/>
Karşılaştırılacak sol kapsayıcısı.

*sağ*<br/>
Karşılaştırılacak doğru kapsayıcısı.

### <a name="remarks"></a>Açıklamalar

İşleç işlevini döndürür `!(left == right)`. Test etmek için kullandığınız olmadığını *sol* aynı sıralı değil *doğru* iki öğe tarafından karşılaştırılan öğe olduğunda.

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

## <a name="op_lt"></a> İşleç&lt; (set) (STL/CLR)

Liste değerinden karşılaştırma.

### <a name="syntax"></a>Sözdizimi

```cpp
template<typename Key>
    bool operator<(set<Key>% left,
        set<Key>% right);
```

#### <a name="parameters"></a>Parametreler

*Sol*<br/>
Karşılaştırılacak sol kapsayıcısı.

*sağ*<br/>
Karşılaştırılacak doğru kapsayıcısı.

### <a name="remarks"></a>Açıklamalar

İşleç işlevi döndürür true ise, en düşük konumu için `i` hangi `!(right[i] < left[i])` de true olduğu `left[i] < right[i]`. Aksi halde `left->size() < right->size()` test etmek için kullandığınız olmadığını *sol* önceyse *doğru* iki öğe tarafından karşılaştırılan öğe olduğunda.

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

## <a name="op_lteq"></a> İşleç&lt;= (set) (STL/CLR)

Küçüktür veya eşittir listesinde karşılaştırma.

### <a name="syntax"></a>Sözdizimi

```cpp
template<typename Key>
    bool operator<=(set<Key>% left,
        set<Key>% right);
```

#### <a name="parameters"></a>Parametreler

*Sol*<br/>
Karşılaştırılacak sol kapsayıcısı.

*sağ*<br/>
Karşılaştırılacak doğru kapsayıcısı.

### <a name="remarks"></a>Açıklamalar

İşleç işlevini döndürür `!(right < left)`. Test etmek için kullandığınız olmadığını *sol* sonra sıralı değil *doğru* iki öğe tarafından karşılaştırılan öğe olduğunda.

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

## <a name="op_eq"></a> işleç == (set) (STL/CLR)

Eşit karşılaştırma listeleyin.

### <a name="syntax"></a>Sözdizimi

```cpp
template<typename Key>
    bool operator==(set<Key>% left,
        set<Key>% right);
```

#### <a name="parameters"></a>Parametreler

*Sol*<br/>
Karşılaştırılacak sol kapsayıcısı.

*sağ*<br/>
Karşılaştırılacak doğru kapsayıcısı.

### <a name="remarks"></a>Açıklamalar

İşleç işlevini dizileri denetlediği yalnızca, true değerini döndürür *sol* ve *doğru* aynı uzunluğa sahip ve her konum için `i`, `left[i] ==` `right[i]`. Test etmek için kullandığınız olmadığını *sol* aynı sıralı *doğru* iki öğe tarafından karşılaştırılan öğe olduğunda.

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

## <a name="op_gt"></a> İşleç&gt; (set) (STL/CLR)

Karşılaştırma büyük listeler.

### <a name="syntax"></a>Sözdizimi

```cpp
template<typename Key>
    bool operator>(set<Key>% left,
        set<Key>% right);
```

#### <a name="parameters"></a>Parametreler

*Sol*<br/>
Karşılaştırılacak sol kapsayıcısı.

*sağ*<br/>
Karşılaştırılacak doğru kapsayıcısı.

### <a name="remarks"></a>Açıklamalar

İşleç işlevini döndürür `right` `<` `left`. Test etmek için kullandığınız olmadığını *sol* sonra sıralı *doğru* iki öğe tarafından karşılaştırılan öğe olduğunda.

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

## <a name="op_gteq"></a> İşleç&gt;= (set) (STL/CLR)

Liste büyüktür veya eşittir karşılaştırma.

### <a name="syntax"></a>Sözdizimi

```cpp
template<typename Key>
    bool operator>=(set<Key>% left,
        set<Key>% right);
```

#### <a name="parameters"></a>Parametreler

*Sol*<br/>
Karşılaştırılacak sol kapsayıcısı.

*sağ*<br/>
Karşılaştırılacak doğru kapsayıcısı.

### <a name="remarks"></a>Açıklamalar

İşleç işlevini döndürür `!(left < right)`. Test etmek için kullandığınız olmadığını *sol* önce sıralı değil *doğru* iki öğe tarafından karşılaştırılan öğe olduğunda.

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