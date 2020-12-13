---
description: 'Şu konuda daha fazla bilgi edinin: liste (STL/CLR)'
title: liste (STL/CLR)
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- cliext::list
- cliext::list::assign
- cliext::list::back
- cliext::list::back_item
- cliext::list::begin
- cliext::list::clear
- cliext::list::const_iterator
- cliext::list::const_reference
- cliext::list::const_reverse_iterator
- cliext::list::difference_type
- cliext::list::empty
- cliext::list::end
- cliext::list::erase
- cliext::list::front
- cliext::list::front_item
- cliext::list::generic_container
- cliext::list::generic_iterator
- cliext::list::generic_reverse_iterator
- cliext::list::generic_value
- cliext::list::insert
- cliext::list::iterator
- cliext::list::list
- cliext::list::merge
- cliext::list::operator=
- cliext::list::pop_back
- cliext::list::pop_front
- cliext::list::push_back
- cliext::list::push_front
- cliext::list::rbegin
- cliext::list::reference
- cliext::list::remove
- cliext::list::remove_if
- cliext::list::rend
- cliext::list::resize
- cliext::list::reverse
- cliext::list::reverse_iterator
- cliext::list::size
- cliext::list::size_type
- cliext::list::sort
- cliext::list::splice
- cliext::list::swap
- cliext::list::to_array
- cliext::list::unique
- cliext::list::value_type
- cliext::operator!=(list)
- cliext::operator<(list)
- cliext::operator<=(list)
- cliext::operator==(list)
- cliext::operator>(list)
- cliext::operator>=(list)
helpviewer_keywords:
- <cliext/list> header [STL/CLR]
- list class [STL/CLR]
- <list> header [STL/CLR]
- assign member [STL/CLR]
- assign member [STL/CLR]
- back member [STL/CLR]
- back_item member [STL/CLR]
- begin member [STL/CLR]
- clear member [STL/CLR]
- const_iterator member [STL/CLR]
- const_reference member [STL/CLR]
- const_reverse_iterator member [STL/CLR]
- difference_type member [STL/CLR]
- empty member [STL/CLR]
- end member [STL/CLR]
- erase member [STL/CLR]
- front member [STL/CLR]
- front_item member [STL/CLR]
- generic_container member [STL/CLR]
- generic_iterator member [STL/CLR]
- generic_reverse_iterator member [STL/CLR]
- generic_value member [STL/CLR]
- insert member [STL/CLR]
- iterator member [STL/CLR]
- list member [STL/CLR]
- merge member [STL/CLR]
- operator= member [STL/CLR]
- pop_back member [STL/CLR]
- pop_front member [STL/CLR]
- push_back member [STL/CLR]
- push_front member [STL/CLR]
- rbegin member [STL/CLR]
- reference member [STL/CLR]
- remove member [STL/CLR]
- remove_if member [STL/CLR]
- rend member [STL/CLR]
- resize member [STL/CLR]
- reverse member [STL/CLR]
- reverse_iterator member [STL/CLR]
- size member [STL/CLR]
- size_type member [STL/CLR]
- sort member [STL/CLR]
- splice member [STL/CLR]
- swap member [STL/CLR]
- to_array member [STL/CLR]
- unique member [STL/CLR]
- value_type member [STL/CLR]
- operator!=(list) member [STL/CLR]
- operator<(list) member [STL/CLR]
- operator<=(list) member [STL/CLR]
- operator==(list) member [STL/CLR]
- operator>(list) member [STL/CLR]
- operator>=(list) member [STL/CLR]
ms.assetid: a70c45c8-a257-4f6b-8434-b27ff6685bac
ms.openlocfilehash: b23bc3f53cc13338e09ee8a6171d3da3b0b75d67
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97344516"
---
# <a name="list-stlclr"></a>liste (STL/CLR)

Şablon sınıfı, çift yönlü erişime sahip olan öğelerin değişen uzunluklu bir dizisini denetleyen bir nesneyi tanımlar. `list`Her biri bir öğe depolayan çift yönlü bağlantılı düğümlerin bir listesi olarak öğe dizisini yönetmek için kapsayıcısını kullanırsınız.

Aşağıdaki açıklamada, `GValue` Ikinci *değeri* bir başvuru türü olmadığı sürece, bu örnekte olduğu gibi olur `Value^` .

## <a name="syntax"></a>Sözdizimi

```cpp
template<typename Value>
    ref class list
        :   public
        System::ICloneable,
        System::Collections::IEnumerable,
        System::Collections::ICollection,
        System::Collections::Generic::IEnumerable<GValue>,
        System::Collections::Generic::ICollection<GValue>,
        Microsoft::VisualC::StlClr::IList<GValue>
    { ..... };
```

### <a name="parameters"></a>Parametreler

*Değer*<br/>
Denetlenen sıradaki öğenin türü.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<cliext/list>

**Ad alanı:** cliext

## <a name="declarations"></a>Bildirimler

|Tür Tanımı|Açıklama|
|---------------------|-----------------|
|[list::const_iterator (STL/CLR)](#const_iterator)|Denetlenen dizi için bir sabit yineleyici türü.|
|[list::const_reference (STL/CLR)](#const_reference)|Bir öğe için sabit bir başvuru türü.|
|[list::const_reverse_iterator (STL/CLR)](#const_reverse_iterator)|Denetlenen sıra için bir sabit ters yineleyicinin türü.|
|[list::difference_type (STL/CLR)](#difference_type)|İki öğe arasındaki işaretli mesafenin türü.|
|[list::generic_container (STL/CLR)](#generic_container)|Kapsayıcının genel arabiriminin türü.|
|[list::generic_iterator (STL/CLR)](#generic_iterator)|Kapsayıcının genel arabirimi için bir yineleyici türü.|
|[list::generic_reverse_iterator (STL/CLR)](#generic_reverse_iterator)|Kapsayıcının genel arabirimi için ters yineleyicinin türü.|
|[list::generic_value (STL/CLR)](#generic_value)|Kapsayıcının genel arabirimi için bir öğenin türü.|
|[list::iterator (STL/CLR)](#iterator)|Denetlenen dizi için bir yineleyici türü.|
|[list::reference (STL/CLR)](#reference)|Bir öğe için bir başvuru türü.|
|[list::reverse_iterator (STL/CLR)](#reverse_iterator)|Denetlenen sıra için ters yineleyicinin türü.|
|[list::size_type (STL/CLR)](#size_type)|İki öğe arasındaki işaretli mesafenin türü.|
|[list::value_type (STL/CLR)](#value_type)|Öğenin türü.|

|Üye İşlevi|Açıklama|
|---------------------|-----------------|
|[list::assign (STL/CLR)](#assign)|Tüm öğeleri değiştirir.|
|[list::back (STL/CLR)](#back)|Son öğeye erişir.|
|[list::begin (STL/CLR)](#begin)|Denetlenen dizinin başlangıcını belirtir.|
|[list::clear (STL/CLR)](#clear)|Tüm öğeleri kaldırır.|
|[list::empty (STL/CLR)](#empty)|Bir öğe olup olmadığını sınar.|
|[list::end (STL/CLR)](#end)|Denetlenen dizinin bitişini belirtir.|
|[list::erase (STL/CLR)](#erase)|Belirtilen konumlardaki öğeleri kaldırır.|
|[list::front (STL/CLR)](#front)|İlk öğeye erişir.|
|[list::insert (STL/CLR)](#insert)|Belirtilen konumdaki öğeleri ekler.|
|[list::list (STL/CLR)](#list)|Bir kapsayıcı nesnesi oluşturur.|
|[list::merge (STL/CLR)](#merge)|Sıralı iki kontrollü diziyi birleştirir.|
|[list::pop_back (STL/CLR)](#pop_back)|Son öğeyi kaldırır.|
|[list::pop_front (STL/CLR)](#pop_front)|İlk öğeyi kaldırır.|
|[list::push_back (STL/CLR)](#push_back)|Yeni bir son öğe ekler.|
|[list::push_front (STL/CLR)](#push_front)|Yeni bir ilk öğe ekler.|
|[list::rbegin (STL/CLR)](#rbegin)|Ters denetlenen sıranın başlangıcını belirtir.|
|[list::remove (STL/CLR)](#remove)|Belirtilen değere sahip bir öğeyi kaldırır.|
|[list::remove_if (STL/CLR)](#remove_if)|Belirtilen testi geçiren öğeleri kaldırır.|
|[list::rend (STL/CLR)](#rend)|Ters denetlenen sıranın sonunu belirtir.|
|[list::resize (STL/CLR)](#resize)|Öğe sayısını değiştirir.|
|[list::reverse (STL/CLR)](#reverse)|Denetlenen sırayı tersine çevirir.|
|[list::size (STL/CLR)](#size)|Öğe sayısını sayar.|
|[list::sort (STL/CLR)](#sort)|Denetlenen sırayı sıralar.|
|[list::splice (STL/CLR)](#splice)|Düğümler arasındaki bağlantıları yeniden bağlar.|
|[list::swap (STL/CLR)](#swap)|İki kapsayıcının içeriğinin yerini değiştirir.|
|[list::to_array (STL/CLR)](#to_array)|Denetimli sırayı yeni bir diziye kopyalar.|
|[list::unique (STL/CLR)](#unique)|Belirtilen testi geçiren bitişik öğeleri kaldırır.|

|Özellik|Açıklama|
|--------------|-----------------|
|[list::back_item (STL/CLR)](#back_item)|Son öğeye erişir.|
|[list::front_item (STL/CLR)](#front_item)|İlk öğeye erişir.|

|İşleç|Açıklama|
|--------------|-----------------|
|[list::operator= (STL/CLR)](#op_as)|Denetlenen sırayı değiştirir.|
|[işleç! = (liste) (STL/CLR)](#op_neq)|Bir `list` nesnenin başka bir nesneye eşit olup olmadığını belirler `list` .|
|[işleç< (liste) (STL/CLR)](#op_lt)|Bir `list` nesnenin başka bir nesneden daha az olup olmadığını belirler `list` .|
|[işleç<= (liste) (STL/CLR)](#op_lteq)|Bir `list` nesnenin başka bir nesneden küçük veya ona eşit olup olmadığını belirler `list` .|
|[işleç = = (liste) (STL/CLR)](#op_eq)|Bir `list` nesnenin başka bir nesneye eşit olup olmadığını belirler `list` .|
|[işleç> (liste) (STL/CLR)](#op_gt)|Bir `list` nesnenin başka bir nesneden daha büyük olup olmadığını belirler `list` .|
|[operator>= (list) (STL/CLR)](#op_gteq)|Bir `list` nesnenin başka bir nesneden büyük veya ona eşit olup olmadığını belirler `list` .|

## <a name="interfaces"></a>Arabirimler

|Arabirim|Açıklama|
|---------------|-----------------|
|<xref:System.ICloneable>|Bir nesneyi çoğaltın.|
|<xref:System.Collections.IEnumerable>|Öğeler aracılığıyla sıralama.|
|<xref:System.Collections.ICollection>|Öğe grubunu saklayın.|
|<xref:System.Collections.Generic.IEnumerable%601>|Yazılı öğeler aracılığıyla sıralama.|
|<xref:System.Collections.Generic.ICollection%601>|Türü belirtilmiş öğelerin grubunu koruyun.|
|IList\<Value>|Genel kapsayıcıyı koruyun.|

## <a name="remarks"></a>Açıklamalar

Nesnesi, çift yönlü bağlantı listesinde tek düğüm olarak denetlediği sıra için depolamayı ayırır ve boşaltır. Bir düğümün içeriğini diğerine kopyalayarak, düğümler arasındaki bağlantıları değiştirerek öğeleri yeniden düzenler. Diğer bir deyişle, daha fazla Bing, kalan öğeleri etkilemeden öğeleri ekleyebileceğiniz ve kaldırabileceğiniz anlamına gelir. Bu nedenle, liste şablon sınıfı [kuyruğu (STL/CLR)](../dotnet/queue-stl-clr.md) veya şablon sınıfı [yığını (STL/CLR)](../dotnet/stack-stl-clr.md)için temel alınan kapsayıcı için iyi bir adaydır.

Bir `list` nesne çift yönlü yineleyiciler destekler, bu, denetlenen dizide bir öğe atayan bir yineleyici verilen bitişik öğelere adım adım yol açabilir. Özel bir baş düğüm [list:: End (STL/CLR)](#end)tarafından döndürülen Yineleyici öğesine karşılık gelir `()` . Varsa, denetlenen sıradaki son öğeye ulaşmak için bu yineleyiciyi azaltamazsınız. Baş düğüme ulaşmak için bir liste yineleyicisini arttırıp daha sonra eşit olarak karşılaştırılacağını sağlayabilirsiniz `end()` . Ancak tarafından döndürülen Yineleyici için başvuru oluşturamazsınız `end()` .

Bir liste öğesine doğrudan sayısal konumu verildiğinde (rastgele erişim Yineleyici gerektiren) başvurmayacağınızı unutmayın. Bu nedenle, liste şablon sınıfı [priority_queue (STL/CLR)](../dotnet/priority-queue-stl-clr.md)için temel alınan kapsayıcı *olarak kullanılamaz.*

Liste Yineleyici, ilişkili kapsayıcısına bir tutamacı depolayan bir tutamacı ilişkili liste düğümüne depolar. Yineleyiciler yalnızca ilişkili kapsayıcı nesneleriyle birlikte kullanabilirsiniz. İlişkili liste düğümü bazı listeyle ilişkili olduğu sürece liste Yineleyici geçerli kalır. Üstelik, geçerli bir yineleyici bir şekilde gönderilir--bunu, oluşturduğu öğe değerine erişmek veya değiştirmek için kullanabilirsiniz. buna eşit olmadığı sürece `end()` .

Bir öğeyi silme veya kaldırma, kendi saklı değeri için yıkıcıyı çağırır. Kapsayıcının yok edilmesi tüm öğeleri siler. Bu nedenle, öğe türü bir başvuru sınıfı olan bir kapsayıcı, kapsayıcının hiçbir öğenin etkin olmamasını sağlar. Ancak, bir işleç kapsayıcısının *öğelerini yok ettiğini* unutmayın.

## <a name="members"></a>Üyeler

## <a name="listassign-stlclr"></a><a name="assign"></a> List:: Assign (STL/CLR)

Tüm öğeleri değiştirir.

### <a name="syntax"></a>Sözdizimi

```cpp
void assign(size_type count, value_type val);
template<typename InIt>
    void assign(InIt first, InIt last);
void assign(System::Collections::Generic::IEnumerable<Value>^ right);
```

#### <a name="parameters"></a>Parametreler

*biriktirme*<br/>
Eklenecek öğe sayısı.

*adı*<br/>
Eklenecek aralığın başlangıcı.

*soyadına*<br/>
Eklenecek aralığın sonu.

*Right*<br/>
Eklenecek sabit listesi.

*Acil*<br/>
Eklenecek öğenin değeri.

### <a name="remarks"></a>Açıklamalar

İlk üye işlevi denetlenen diziyi değer *değer değeri olan* *Count* öğelerinin yinelemesi ile değiştirir. Kapsayıcıyı aynı değere sahip olan öğelerle birlikte doldurmanız için kullanabilirsiniz.

`InIt`Bir tamsayı türünde ise ikinci üye işlevi ile aynı şekilde davranır `assign((size_type)first, (value_type)last)` . Aksi takdirde, denetlenen diziyi [ `first` ,) sırasıyla değiştirir `last` . Bunu, denetimli diziyi başka bir sıra kopyalamak için kullanırsınız.

Üçüncü üye işlevi, denetlenen diziyi Numaralandırıcı *sağ* tarafından belirlenen sırayla değiştirir. Denetim, bir Numaralandırıcı tarafından tanımlanan bir dizinin bir kopyasını denetimli sıra haline getirmek için kullanılır.

### <a name="example"></a>Örnek

```cpp
// cliext_list_assign.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // assign a repetition of values
    cliext::list<wchar_t> c2;
    c2.assign(6, L'x');
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // assign an iterator range
    cliext::list<wchar_t>::iterator it = c1.end();
    c2.assign(c1.begin(), --it);
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // assign an enumeration
    c2.assign(   // NOTE: cast is not needed
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c1);
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
x x x x x x
a b
a b c
```

## <a name="listback-stlclr"></a><a name="back"></a> List:: Back (STL/CLR)

Son öğeye erişir.

### <a name="syntax"></a>Syntax

```cpp
reference back();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, denetimli sıranın son öğesine bir başvuru döndürür ve bu değer boş olmamalıdır. Bunu, olduğunu bildiğiniz zaman son öğeye erişmek için kullanabilirsiniz.

### <a name="example"></a>Örnek

```cpp
// cliext_list_back.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // inspect last item
    System::Console::WriteLine("back() = {0}", c1.back());

    // alter last item and reinspect
    c1.back() = L'x';
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
back() = c
a b x
```

## <a name="listback_item-stlclr"></a><a name="back_item"></a> List:: back_item (STL/CLR)

Son öğeye erişir.

### <a name="syntax"></a>Syntax

```cpp
property value_type back_item;
```

### <a name="remarks"></a>Açıklamalar

Özelliği, denetimli sıranın son öğesine erişir, bu da boş olmamalıdır. Bunu, olduğunu bildiğiniz zaman son öğeyi okumak veya yazmak için kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// cliext_list_back_item.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // inspect last item
    System::Console::WriteLine("back_item = {0}", c1.back_item);

    // alter last item and reinspect
    c1.back_item = L'x';
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
back_item = c
a b x
```

## <a name="listbegin-stlclr"></a><a name="begin"></a> List:: Begin (STL/CLR)

Denetlenen dizinin başlangıcını belirtir.

### <a name="syntax"></a>Syntax

```cpp
iterator begin();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, denetlenen sıranın ilk öğesini veya boş bir dizinin sonunun ötesinde bir rastgele erişim yineleyici döndürür. Denetlenen dizinin başlangıcını atayan bir yineleyici elde etmek için bunu kullanırsınız `current` , ancak denetlenen sıranın uzunluğu değişirse durum değişebilir.

### <a name="example"></a>Örnek

```cpp
// cliext_list_begin.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // inspect first two items
    cliext::list<wchar_t>::iterator it = c1.begin();
    System::Console::WriteLine("*begin() = {0}", *it);
    System::Console::WriteLine("*++begin() = {0}", *++it);

    // alter first two items and reinspect
    *--it = L'x';
    *++it = L'y';
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
*begin() = a
*++begin() = b
x y c
```

## <a name="listclear-stlclr"></a><a name="clear"></a> List:: Clear (STL/CLR)

Tüm öğeleri kaldırır.

### <a name="syntax"></a>Syntax

```cpp
void clear();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, [list:: Erase (STL/CLR)](#erase) List: `(` [: BEGIN (STL/CLR)](#begin) `(),` [list:: End (STL/CLR](#end)) listesini etkin bir şekilde çağırır `())` . Denetlenen sıranın boş olduğundan emin olmak için bunu kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// cliext_list_clear.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // clear the container and reinspect
    c1.clear();
    System::Console::WriteLine("size() = {0}", c1.size());

    // add elements and clear again
    c1.push_back(L'a');
    c1.push_back(L'b');

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

## <a name="listconst_iterator-stlclr"></a><a name="const_iterator"></a> List:: const_iterator (STL/CLR)

Denetlenen dizi için bir sabit yineleyici türü.

### <a name="syntax"></a>Syntax

```cpp
typedef T2 const_iterator;
```

### <a name="remarks"></a>Açıklamalar

Türü, `T2` denetimli sıra için sabit bir rastgele erişim Yineleyici işlevi görebilecek belirtilmemiş türdeki bir nesneyi tanımlar.

### <a name="example"></a>Örnek

```cpp
// cliext_list_const_iterator.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display contents " a b c"
    cliext::list<wchar_t>::const_iterator cit = c1.begin();
    for (; cit != c1.end(); ++cit)
        System::Console::Write("{0} ", *cit);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="listconst_reference-stlclr"></a><a name="const_reference"></a> List:: const_reference (STL/CLR)

Bir öğe için sabit bir başvuru türü.

### <a name="syntax"></a>Syntax

```cpp
typedef value_type% const_reference;
```

### <a name="remarks"></a>Açıklamalar

Türü bir öğeye sabit bir başvuru tanımlar.

### <a name="example"></a>Örnek

```cpp
// cliext_list_const_reference.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display initial contents " a b c"
    cliext::list<wchar_t>::const_iterator cit = c1.begin();
    for (; cit != c1.end(); ++cit)
        {   // get a const reference to an element
        cliext::list<wchar_t>::const_reference cref = *cit;
        System::Console::Write("{0} ", cref);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="listconst_reverse_iterator-stlclr"></a><a name="const_reverse_iterator"></a> List:: const_reverse_iterator (STL/CLR)

Denetlenen sıra için bir sabit ters yineleyicinin türü..

### <a name="syntax"></a>Syntax

```cpp
typedef T4 const_reverse_iterator;
```

### <a name="remarks"></a>Açıklamalar

Türü, `T4` denetimli sıra için sabit bir ters Yineleyici işlevi görebilecek belirtilmemiş türdeki bir nesneyi tanımlar.

### <a name="example"></a>Örnek

```cpp
// cliext_list_const_reverse_iterator.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display contents " a b c" reversed
    cliext::list<wchar_t>::const_reverse_iterator crit = c1.rbegin();
    cliext::list<wchar_t>::const_reverse_iterator crend = c1.rend();
    for (; crit != crend; ++crit)
        System::Console::Write("{0} ", *crit);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
c b a
```

## <a name="listdifference_type-stlclr"></a><a name="difference_type"></a> liste::d ifference_type (STL/CLR)

İki öğe arasındaki işaretli bir mesafe türü.

### <a name="syntax"></a>Syntax

```cpp
typedef int difference_type;
```

### <a name="remarks"></a>Açıklamalar

Türü, imzalı bir öğe sayısını tanımlar.

### <a name="example"></a>Örnek

```cpp
// cliext_list_difference_type.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // compute positive difference
    cliext::list<wchar_t>::difference_type diff = 0;
    for (cliext::list<wchar_t>::iterator it = c1.begin();
        it != c1.end(); ++it) ++diff;
    System::Console::WriteLine("end()-begin() = {0}", diff);

    // compute negative difference
    diff = 0;
    for (cliext::list<wchar_t>::iterator it = c1.end();
        it != c1.begin(); --it) --diff;
    System::Console::WriteLine("begin()-end() = {0}", diff);
    return (0);
    }
```

```Output
a b c
end()-begin() = 3
begin()-end() = -3
```

## <a name="listempty-stlclr"></a><a name="empty"></a> List:: Empty (STL/CLR)

Bir öğe olup olmadığını sınar.

### <a name="syntax"></a>Syntax

```cpp
bool empty();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi boş bir denetlenen dizi için true döndürür. [LIST:: size (STL/CLR)](#size) `() == 0` . Listenin boş olup olmadığını test etmek için bunu kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// cliext_list_empty.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

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

## <a name="listend-stlclr"></a><a name="end"></a> List:: End (STL/CLR)

Denetlenen dizinin bitişini belirtir.

### <a name="syntax"></a>Syntax

```cpp
iterator end();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, denetimli dizinin sonunun hemen ötesinde işaret eden bir rastgele erişim yineleyici döndürür. Denetlenen dizinin sonunu atayan bir yineleyici elde etmek için bunu kullanırsınız; denetlenen sıranın uzunluğu değişirse, durumu değişmez.

### <a name="example"></a>Örnek

```cpp
// cliext_list_end.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // inspect last two items
    cliext::list<wchar_t>::iterator it = c1.end();
    --it;
    System::Console::WriteLine("*-- --end() = {0}", *--it);
    System::Console::WriteLine("*--end() = {0}", *++it);

    // alter first two items and reinspect
    *--it = L'x';
    *++it = L'y';
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
*-- --end() = b
*--end() = c
a x y
```

## <a name="listerase-stlclr"></a><a name="erase"></a> List:: Erase (STL/CLR)

Belirtilen konumlardaki öğeleri kaldırır.

### <a name="syntax"></a>Sözdizimi

```cpp
iterator erase(iterator where);
iterator erase(iterator first, iterator last);
```

#### <a name="parameters"></a>Parametreler

*adı*<br/>
Silinecek aralığın başlangıcı.

*soyadına*<br/>
Silinecek aralığın sonu.

*olmadığı*<br/>
Silinecek öğe.

### <a name="remarks"></a>Açıklamalar

İlk üye işlevi, tarafından işaret edilen kontrollü sıranın öğesini *olduğu* gibi kaldırır. Tek bir öğeyi kaldırmak için bunu kullanırsınız.

İkinci üye işlevi, [,) aralığındaki denetlenen sıranın öğelerini kaldırır `first` `last` . Sıfır veya daha fazla bitişik öğeyi kaldırmak için bunu kullanırsınız.

Her iki üye işlevi de kaldırılan öğelerin ötesinde kalan ilk öğeyi atayan bir yineleyici döndürür veya böyle bir öğe yoksa [list:: End (STL/CLR)](#end) `()` .

Öğeleri silerken, öğe kopyalarının sayısı doğrusal bir şekilde sıra sayısının bitişine ve sonuna kadar olan sayı arasındaki öğe sayısını gösterir. (Sıranın her iki ucunda bir veya daha fazla öğe silinirken, hiçbir öğe kopyası gerçekleşmez.)

### <a name="example"></a>Örnek

```cpp
// cliext_list_erase.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // erase an element and reinspect
    System::Console::WriteLine("erase(begin()) = {0}",
        *c1.erase(c1.begin()));

    // add elements and display " b c d e"
    c1.push_back(L'd');
    c1.push_back(L'e');
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // erase all but end
    cliext::list<wchar_t>::iterator it = c1.end();
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

## <a name="listfront-stlclr"></a><a name="front"></a> List:: Front (STL/CLR)

İlk öğeye erişir.

### <a name="syntax"></a>Syntax

```cpp
reference front();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, denetimli sıranın ilk öğesine bir başvuru döndürür ve bu değer boş olmamalıdır. Olduğunu bildiğiniz zaman ilk öğeyi okumak veya yazmak için bunu kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// cliext_list_front.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // inspect first item
    System::Console::WriteLine("front() = {0}", c1.front());

    // alter first item and reinspect
    c1.front() = L'x';
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
front() = a
x b c
```

## <a name="listfront_item-stlclr"></a><a name="front_item"></a> List:: front_item (STL/CLR)

İlk öğeye erişir.

### <a name="syntax"></a>Syntax

```cpp
property value_type front_item;
```

### <a name="remarks"></a>Açıklamalar

Özelliği, denetimli sıranın ilk öğesine erişir, bu da boş olmamalıdır. Olduğunu bildiğiniz zaman ilk öğeyi okumak veya yazmak için bunu kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// cliext_list_front_item.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // inspect first item
    System::Console::WriteLine("front_item = {0}", c1.front_item);

    // alter first item and reinspect
    c1.front_item = L'x';
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
front_item = a
x b c
```

## <a name="listgeneric_container-stlclr"></a><a name="generic_container"></a> List:: generic_container (STL/CLR)

Kapsayıcının genel arabiriminin türü.

### <a name="syntax"></a>Syntax

```cpp
typedef Microsoft::VisualC::StlClr::
    IList<generic_value>
    generic_container;
```

### <a name="remarks"></a>Açıklamalar

Tür, bu şablon kapsayıcı sınıfı için genel arabirimi tanımlar.

### <a name="example"></a>Örnek

```cpp
// cliext_list_generic_container.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct a generic container
    cliext::list<wchar_t>::generic_container^ gc1 = %c1;
    for each (wchar_t elem in gc1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // modify generic and display original
    gc1->insert(gc1->end(), L'd');
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // modify original and display generic
    c1.push_back(L'e');

    System::Collections::IEnumerator^ enum1 =
        gc1->GetEnumerator();
    while (enum1->MoveNext())
        System::Console::Write("{0} ", enum1->Current);
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

## <a name="listgeneric_iterator-stlclr"></a><a name="generic_iterator"></a> List:: generic_iterator (STL/CLR)

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
// cliext_list_generic_iterator.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct a generic container
    cliext::list<wchar_t>::generic_container^ gc1 = %c1;
    for each (wchar_t elem in gc1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // modify generic and display original
    cliext::list<wchar_t>::generic_iterator gcit = gc1->begin();
    cliext::list<wchar_t>::generic_value gcval = *gcit;
    *++gcit = gcval;
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
a b c
a a c
```

## <a name="listgeneric_reverse_iterator-stlclr"></a><a name="generic_reverse_iterator"></a> List:: generic_reverse_iterator (STL/CLR)

Kapsayıcı için genel arabirimle birlikte kullanılacak ters yineleyicinin türü.

### <a name="syntax"></a>Syntax

```cpp
typedef Microsoft::VisualC::StlClr::Generic::
    ReverseBidirectionalIterator<generic_value> generic_reverse_iterator;
```

### <a name="remarks"></a>Açıklamalar

Tür, bu şablon kapsayıcı sınıfı için genel arabirimle birlikte kullanılabilecek bir genel ters yineleyici tanımlar.

### <a name="example"></a>Örnek

```cpp
// cliext_list_generic_reverse_iterator.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct a generic container
    cliext::list<wchar_t>::generic_container^ gc1 = %c1;
    for each (wchar_t elem in gc1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // modify generic and display original
    cliext::list<wchar_t>::generic_reverse_iterator gcit = gc1->rbegin();
    cliext::list<wchar_t>::generic_value gcval = *gcit;
    *++gcit = gcval;
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
a b c
a c c
```

## <a name="listgeneric_value-stlclr"></a><a name="generic_value"></a> List:: generic_value (STL/CLR)

Kapsayıcının genel arabirimiyle kullanılacak öğe türü.

### <a name="syntax"></a>Syntax

```cpp
typedef GValue generic_value;
```

### <a name="remarks"></a>Açıklamalar

Tür, `GValue` Bu şablon kapsayıcı sınıfı için genel arabirimle birlikte kullanılacak saklı öğe değerini açıklayan türünde bir nesne tanımlar.

### <a name="example"></a>Örnek

```cpp
// cliext_list_generic_value.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct a generic container
    cliext::list<wchar_t>::generic_container^ gc1 = %c1;
    for each (wchar_t elem in gc1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // modify generic and display original
    cliext::list<wchar_t>::generic_iterator gcit = gc1->begin();
    cliext::list<wchar_t>::generic_value gcval = *gcit;
    *++gcit = gcval;
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
a b c
a a c
```

## <a name="listinsert-stlclr"></a><a name="insert"></a> List:: insert (STL/CLR)

Belirtilen konumdaki öğeleri ekler.

### <a name="syntax"></a>Sözdizimi

```cpp
iterator insert(iterator where, value_type val);
void insert(iterator where, size_type count, value_type val);
template<typename InIt>
    void insert(iterator where, InIt first, InIt last);
void insert(iterator where,
    System::Collections::Generic::IEnumerable<Value>^ right);
```

#### <a name="parameters"></a>Parametreler

*biriktirme*<br/>
Eklenecek öğe sayısı.

*adı*<br/>
Eklenecek aralığın başlangıcı.

*soyadına*<br/>
Eklenecek aralığın sonu.

*Right*<br/>
Eklenecek sabit listesi.

*Acil*<br/>
Eklenecek öğenin değeri.

*olmadığı*<br/>
Kapsayıcının ekleneceği yer.

### <a name="remarks"></a>Açıklamalar

Üye işlevlerinin her biri, öğe denetimli sırada, kalan işlenenler tarafından belirtilen bir *sıra olarak işaret eden öğesinden* önce eklenir.

İlk üye *işlevi value değeri* olan bir öğe ekler ve yeni eklenen öğeyi atayan bir yineleyici döndürür. Yineleyiciyi, bir yineleyici tarafından belirlenmiş bir konumdan önce tek bir öğe eklemek için kullanırsınız.

İkinci üye işlevi, değer *Val*'in *Count* öğelerinin tekrarından birini ekler. Aynı değerin tüm kopyaları olan sıfır veya daha fazla bitişik öğe eklemek için bunu kullanırsınız.

`InIt`Bir tamsayı türü ise, üçüncü üye işlevi ile aynı şekilde davranır `insert(where, (size_type)first, (value_type)last)` . Aksi takdirde, [ `first` ,) dizisini ekler `last` . Başka bir dizide kopyalanmış sıfır veya daha fazla bitişik öğe eklemek için bunu kullanırsınız.

Dördüncü üye işlevi, *sağ* tarafından belirlenen diziyi ekler. Bir Numaralandırıcı tarafından tanımlanan bir sıra eklemek için bunu kullanırsınız.

Tek bir öğe eklenirken, öğe kopyalarının sayısı, ekleme noktası ve sıranın bir kapanış ucu arasındaki öğe sayısında doğrusal olur. (Sıranın her iki ucunda bir veya daha fazla öğe eklenirken, hiçbir öğe kopyası gerçekleşmez.) `InIt` Bir giriş yineleyicidir, üçüncü üye işlevi dizideki her öğe için etkin bir şekilde tek bir ekleme gerçekleştirir. Aksi halde, öğe eklerken `N` , öğe kopyalarının sayısı doğrusal `N` ve ekleme noktası ile sıranın bir kapanış ucu arasındaki öğe sayısına eklenir.

### <a name="example"></a>Örnek

```cpp
// cliext_list_insert.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // insert a single value using iterator
    cliext::list<wchar_t>::iterator it = c1.begin();
    System::Console::WriteLine("insert(begin()+1, L'x') = {0}",
        *c1.insert(++it, L'x'));
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // insert a repetition of values
    cliext::list<wchar_t> c2;
    c2.insert(c2.begin(), 2, L'y');
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // insert an iterator range
    it = c1.end();
    c2.insert(c2.end(), c1.begin(), --it);
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // insert an enumeration
    c2.insert(c2.begin(),   // NOTE: cast is not needed
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c1);
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // insert a single value using index
    it = c2.begin();
    ++it, ++it, ++it;
    c2.insert(it, L'z');
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    return (0);
    }
```

```Output
a b c
insert(begin()+1, L'x') = x
a x b c
y y
y y a x b
a x b c y y a x b
```

## <a name="listiterator-stlclr"></a><a name="iterator"></a> List:: yineleyici (STL/CLR)

Denetlenen dizi için bir yineleyici türü.

### <a name="syntax"></a>Syntax

```cpp
typedef T1 iterator;
```

### <a name="remarks"></a>Açıklamalar

Türü, `T1` denetimli sıra için rastgele erişim Yineleyici işlevi görebilecek belirtilmemiş türdeki bir nesneyi tanımlar.

### <a name="example"></a>Örnek

```cpp
// cliext_list_iterator.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display contents " a b c"
    cliext::list<wchar_t>::iterator it = c1.begin();
    for (; it != c1.end(); ++it)
        System::Console::Write("{0} ", *it);
    System::Console::WriteLine();

    // alter first element and redisplay
    it = c1.begin();
    *it = L'x';
    for (; it != c1.end(); ++it)
        System::Console::Write("{0} ", *it);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
x b c
```

## <a name="listlist-stlclr"></a><a name="list"></a> List:: List (STL/CLR)

Bir kapsayıcı nesnesi oluşturur.

### <a name="syntax"></a>Sözdizimi

```cpp
list();
list(list<Value>% right);
list(list<Value>^ right);
explicit list(size_type count);
list(size_type count, value_type val);
template<typename InIt>
    list(InIt first, InIt last);
list(System::Collections::Generic::IEnumerable<Value>^ right);
```

#### <a name="parameters"></a>Parametreler

*biriktirme*<br/>
Eklenecek öğe sayısı.

*adı*<br/>
Eklenecek aralığın başlangıcı.

*soyadına*<br/>
Eklenecek aralığın sonu.

*Right*<br/>
Eklenecek nesne veya Aralık.

*Acil*<br/>
Eklenecek öğenin değeri.

### <a name="remarks"></a>Açıklamalar

Oluşturucu:

`list();`

denetimli sırayı öğesi olmadan başlatır. Boş bir ilk denetimli sıra belirtmek için bunu kullanırsınız.

Oluşturucu:

`list(list<Value>% right);`

denetlenen sırayı [ `right.begin()` ,) sırasıyla başlatır `right.end()` . Liste nesnesi *sağa* tarafından denetlenen sıranın bir kopyası olan ilk denetimli bir sıra belirtmek için bunu kullanırsınız.

Oluşturucu:

`list(list<Value>^ right);`

denetlenen sırayı [ `right->begin()` ,) sırasıyla başlatır `right->end()` . Tutamacı *doğru* olan List nesnesi tarafından denetlenen sıranın bir kopyası olan bir ilk denetimli sıra belirtmek için bunu kullanırsınız.

Oluşturucu:

`explicit list(size_type count);`

Her bir değer içeren *sayı* öğeleri olan denetimli sırayı başlatır `value_type()` . Kapsayıcıyı, varsayılan değere sahip olan öğelerle birlikte doldurmanız için kullanırsınız.

Oluşturucu:

`list(size_type count, value_type val);`

her biri değer *Val* ile denetlenen diziyi *say* öğesi ile başlatır. Kapsayıcıyı aynı değere sahip olan öğelerle birlikte doldurmanız için kullanabilirsiniz.

Oluşturucu:

`template<typename InIt>`

`list(InIt first, InIt last);`

denetlenen sırayı [ `first` ,) sırasıyla başlatır `last` . Bunu, denetimli diziyi başka bir dizinin bir kopyası yapmak için kullanırsınız.

Oluşturucu:

`list(System::Collections::Generic::IEnumerable<Value>^ right);`

denetlenen sırayı Numaralandırıcı *hakkı* tarafından belirlenen sırayla başlatır. Denetlenen diziyi, Numaralandırıcı tarafından tanımlanan başka bir dizinin bir kopyası yapmak için kullanabilirsiniz.

### <a name="example"></a>Örnek

```cpp
// cliext_list_construct.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
// construct an empty container
    cliext::list<wchar_t> c1;
    System::Console::WriteLine("size() = {0}", c1.size());

    // construct with a repetition of default values
    cliext::list<wchar_t> c2(3);
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", (int)elem);
    System::Console::WriteLine();

    // construct with a repetition of values
    cliext::list<wchar_t> c3(6, L'x');
    for each (wchar_t elem in c3)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct with an iterator range
    cliext::list<wchar_t>::iterator it = c3.end();
    cliext::list<wchar_t> c4(c3.begin(), --it);
    for each (wchar_t elem in c4)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct with an enumeration
    cliext::list<wchar_t> c5(   // NOTE: cast is not needed
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c3);
    for each (wchar_t elem in c5)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct by copying another container
    cliext::list<wchar_t> c7(c3);
    for each (wchar_t elem in c7)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct by copying a container handle
    cliext::list<wchar_t> c8(%c3);
    for each (wchar_t elem in c8)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    return (0);
    }
```

```Output
size() = 0
0 0 0
x x x x x x
x x x x x
x x x x x x
x x x x x x
x x x x x x
```

## <a name="listmerge-stlclr"></a><a name="merge"></a> List:: Merge (STL/CLR)

Sıralı iki kontrollü diziyi birleştirir.

### <a name="syntax"></a>Sözdizimi

```cpp
void merge(list<Value>% right);
template<typename Pred2>
    void merge(list<Value>% right, Pred2 pred);
```

#### <a name="parameters"></a>Parametreler

*pred*<br/>
Öğe çiftleri için karşılaştırıcı.

*Right*<br/>
Birleştirilecek kapsayıcı.

### <a name="remarks"></a>Açıklamalar

İlk üye işlevi, tüm öğeleri denetimli sırayla *kaldırır ve denetimli* diziye ekler. Her iki dizi de daha önce sıralanmış olmalıdır `operator<` --öğeler, her iki sırada da ilerleyerek değeri azaltmamalıdır. Elde edilen sıra, tarafından da sıralanır `operator<` . Değerde arttığı iki diziyi, değerde de artan bir diziye birleştirmek için bu üye işlevini kullanın.

İkinci üye işlevi, sıralamadaki `pred`  --  `pred(X, Y)` öğeyi takip eden herhangi bir öğe için, diziler `X` sıralama ölçütü dışında, ilk ile aynı şekilde davranır `Y` . Belirlediğiniz bir koşul işlevi veya temsilci tarafından sıralanan iki diziyi birleştirmek için kullanın.

Her iki işlev de kararlı bir birleştirme gerçekleştirir--orijinal denetimli dizilerden birinde hiçbir öğe çifti elde edilen kontrollü sırada tersine çevrilir. Ayrıca, bir öğe çifti `X` ve `Y` elde edilen denetimli dizide eşdeğer sıralama varsa-- `!(X < Y) && !(X < Y)` --orijinal denetimli dizideki bir öğe, *sağa* denetlenen dizideki bir öğeden önce görünür.

### <a name="example"></a>Örnek

```cpp
// cliext_list_merge.cpp
// compile with: /clr
#include <cliext/list>

typedef cliext::list<wchar_t> Mylist;
int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'c');
    c1.push_back(L'e');

    // display initial contents " a c e"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    cliext::list<wchar_t> c2;
    c2.push_back(L'b');
    c2.push_back(L'd');
    c2.push_back(L'f');

    // display initial contents " b d f"
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // merge and display
    cliext::list<wchar_t> c3(c1);
    c3.merge(c2);
    for each (wchar_t elem in c3)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    System::Console::WriteLine("c2.size() = {0}", c2.size());

    // sort descending, merge descending, and redisplay
    c1.sort(cliext::greater<wchar_t>());
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    c3.sort(cliext::greater<wchar_t>());
    for each (wchar_t elem in c3)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    c3.merge(c1, cliext::greater<wchar_t>());
    for each (wchar_t elem in c3)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    System::Console::WriteLine("c1.size() = {0}", c1.size());
    return (0);
    }
```

```Output
a c e
b d f
a b c d e f
c2.size() = 0
e c a
f e d c b a
f e e d c c b a a
c1.size() = 0
```

## <a name="listoperator-stlclr"></a><a name="op_as"></a> List:: operator = (STL/CLR)

Denetlenen sırayı değiştirir.

### <a name="syntax"></a>Sözdizimi

```
list<Value>% operator=(list<Value>% right);
```

#### <a name="parameters"></a>Parametreler

*Right*<br/>
Kopyalanacak kapsayıcı.

### <a name="remarks"></a>Açıklamalar

Üye işleci nesnesine *sağ* kopyalar ve ardından döndürür **`*this`** . Denetlenen diziyi, denetimli sıranın bir kopyasıyla değiştirmek için bunu *kullanırsınız.*

### <a name="example"></a>Örnek

```cpp
// cliext_list_operator_as.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // assign to a new container
    cliext::list<wchar_t> c2;
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

## <a name="listpop_back-stlclr"></a><a name="pop_back"></a> liste::p op_back (STL/CLR)

Son öğeyi kaldırır.

### <a name="syntax"></a>Syntax

```cpp
void pop_back();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, denetimli sıranın son öğesini kaldırır ve bu boş olmamalıdır. Listeyi geri doğru bir öğe ile kısaltmak için kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// cliext_list_pop_back.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // pop an element and redisplay
    c1.pop_back();
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
a b
```

## <a name="listpop_front-stlclr"></a><a name="pop_front"></a> liste::p op_front (STL/CLR)

İlk öğeyi kaldırır.

### <a name="syntax"></a>Syntax

```cpp
void pop_front();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, denetimli dizinin ilk öğesini kaldırır ve boş olmamalıdır. Listeyi önünde bir öğe ile kısaltmak için kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// cliext_list_pop_front.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // pop an element and redisplay
    c1.pop_front();
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
b c
```

## <a name="listpush_back-stlclr"></a><a name="push_back"></a> liste::p ush_back (STL/CLR)

Yeni bir son öğe ekler.

### <a name="syntax"></a>Syntax

```cpp
void push_back(value_type val);
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi denetlenen sıranın sonunda değeri olan bir öğe ekler `val` . Listeye başka bir öğe eklemek için bunu kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// cliext_list_push_back.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="listpush_front-stlclr"></a><a name="push_front"></a> liste::p ush_front (STL/CLR)

Yeni bir ilk öğe ekler.

### <a name="syntax"></a>Syntax

```cpp
void push_front(value_type val);
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi denetlenen sıranın başlangıcında değeri olan bir öğe ekler `val` . Başka bir öğeyi listeye eklemek için bunu kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// cliext_list_push_front.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_front(L'a');
    c1.push_front(L'b');
    c1.push_front(L'c');

    // display contents " c b a"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
c b a
```

## <a name="listrbegin-stlclr"></a><a name="rbegin"></a> List:: rbegin (STL/CLR)

Ters denetlenen sıranın başlangıcını belirtir.

### <a name="syntax"></a>Syntax

```cpp
reverse_iterator rbegin();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, denetimli sıranın son öğesini veya boş bir dizinin başlangıcının ötesinde bir ters yineleyici döndürür. Bu nedenle, `beginning` ters sıranın öğesini belirler. Doğru sırada görülen denetimli sıranın başlangıcını atayan bir yineleyici elde etmek için bunu kullanırsınız `current` , ancak denetlenen sıranın uzunluğu değişirse durum değişebilir.

### <a name="example"></a>Örnek

```cpp
// cliext_list_rbegin.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // inspect first two items in reversed sequence
    cliext::list<wchar_t>::reverse_iterator rit = c1.rbegin();
    System::Console::WriteLine("*rbegin() = {0}", *rit);
    System::Console::WriteLine("*++rbegin() = {0}", *++rit);

    // alter first two items and reinspect
    *--rit = L'x';
    *++rit = L'y';
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
*rbegin() = c
*++rbegin() = b
a y x
```

## <a name="listreference-stlclr"></a><a name="reference"></a> List:: Reference (STL/CLR)

Bir öğe için bir başvuru türü.

### <a name="syntax"></a>Syntax

```cpp
typedef value_type% reference;
```

### <a name="remarks"></a>Açıklamalar

Türü bir öğesi başvurusunu tanımlar.

### <a name="example"></a>Örnek

```cpp
// cliext_list_reference.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display initial contents " a b c"
    cliext::list<wchar_t>::iterator it = c1.begin();
    for (; it != c1.end(); ++it)
        {   // get a reference to an element
        cliext::list<wchar_t>::reference ref = *it;
        System::Console::Write("{0} ", ref);
        }
    System::Console::WriteLine();

    // modify contents " a b c"
    for (it = c1.begin(); it != c1.end(); ++it)
        {   // get a reference to an element
        cliext::list<wchar_t>::reference ref = *it;

        ref += (wchar_t)(L'A' - L'a');
        System::Console::Write("{0} ", ref);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
A B C
```

## <a name="listremove-stlclr"></a><a name="remove"></a> List:: Remove (STL/CLR)

Belirtilen değere sahip bir öğeyi kaldırır.

### <a name="syntax"></a>Sözdizimi

```cpp
void remove(value_type val);
```

#### <a name="parameters"></a>Parametreler

*Acil*<br/>
Kaldırılacak öğenin değeri.

### <a name="remarks"></a>Açıklamalar

Üye işlevi, denetimli dizideki bir öğeyi `((System::Object^)val)->Equals((System::Object^)x)` (varsa) kaldırır. Belirtilen değere sahip rastgele bir öğeyi silmek için bunu kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// cliext_list_remove.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // fail to remove and redisplay
    c1.remove(L'A');
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // remove and redisplay
    c1.remove(L'b');
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
a b c
a c
```

## <a name="listremove_if-stlclr"></a><a name="remove_if"></a> List:: remove_if (STL/CLR)

Belirtilen testi geçiren öğeleri kaldırır.

### <a name="syntax"></a>Sözdizimi

```cpp
template<typename Pred1>
    void remove_if(Pred1 pred);
```

#### <a name="parameters"></a>Parametreler

*pred*<br/>
Kaldırılacak öğeler için test.

### <a name="remarks"></a>Açıklamalar

Üye işlevi, doğru olan her öğe için denetimli sıra (siler) öğesini kaldırır `X` `pred(X)` . Bir işlev veya temsilci olarak belirttiğiniz bir koşulu karşılayan tüm öğeleri kaldırmak için bunu kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// cliext_list_remove_if.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'b');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display initial contents " a b b b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // fail to remove and redisplay
    c1.remove_if(cliext::binder2nd<cliext::equal_to<wchar_t> >(
        cliext::equal_to<wchar_t>(), L'd'));
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // remove and redisplay
    c1.remove_if(cliext::binder2nd<cliext::not_equal_to<wchar_t> >(
        cliext::not_equal_to<wchar_t>(), L'b'));
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b b b c
a b b b c
b b b
```

## <a name="listrend-stlclr"></a><a name="rend"></a> List:: rend (STL/CLR)

Ters denetlenen sıranın sonunu belirtir.

### <a name="syntax"></a>Syntax

```cpp
reverse_iterator rend();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, denetimli sıranın başlangıcının hemen ötesinde bir ters yineleyici döndürür. Bu nedenle, `end` ters sıranın öğesini belirler. Bu uygulamayı, `current` geriye doğru sırada görülen denetlenen sıranın sonunu atayan bir yineleyici elde etmek için kullanırsınız, ancak denetlenen sıranın uzunluğu değişirse durum değişebilir.

### <a name="example"></a>Örnek

```cpp
// cliext_list_rend.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // inspect first two items
    cliext::list<wchar_t>::reverse_iterator rit = c1.rend();
    --rit;
    System::Console::WriteLine("*-- --rend() = {0}", *--rit);
    System::Console::WriteLine("*--rend() = {0}", *++rit);

    // alter first two items and reinspect
    *--rit = L'x';
    *++rit = L'y';
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
*-- --rend() = b
*--rend() = a
y x c
```

## <a name="listresize-stlclr"></a><a name="resize"></a> List:: Resize (STL/CLR)

Öğe sayısını değiştirir.

### <a name="syntax"></a>Sözdizimi

```cpp
void resize(size_type new_size);
void resize(size_type new_size, value_type val);
```

#### <a name="parameters"></a>Parametreler

*new_size*<br/>
Denetlenen sıranın yeni boyutu.

*Acil*<br/>
Padding öğesinin değeri.

### <a name="remarks"></a>Açıklamalar

Üye işlevleri hem [list:: size (STL/CLR)](#size) `()` henceileri ' nin *new_size* döndürdüğünden emin olun. Denetlenen diziyi daha uzun hale getirmek gerekiyorsa, ilk üye işlevi değeri olan öğeleri ekler `value_type()` ; İkinci üye işlevi ise değer *Val* ile öğeleri ekler. Denetimli diziyi daha kısa hale getirmek için, her iki üye işlevi son öğe [listesi:: size (STL/CLR)](#size) zamanlarını etkin bir şekilde siler `() -` `new_size` . Kontrol edilen sıranın boyut *new_size* sahip olduğundan emin olmak için, geçerli denetimli diziyi kırparak veya doldurmaya göre kullanabilirsiniz.

### <a name="example"></a>Örnek

```cpp
// cliext_list_resize.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
// construct an empty container and pad with default values
    cliext::list<wchar_t> c1;
    System::Console::WriteLine("size() = {0}", c1.size());
    c1.resize(4);
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", (int)elem);
    System::Console::WriteLine();

    // resize to empty
    c1.resize(0);
    System::Console::WriteLine("size() = {0}", c1.size());

    // resize and pad
    c1.resize(5, L'x');
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
size() = 0
0 0 0 0
size() = 0
x x x x x
```

## <a name="listreverse-stlclr"></a><a name="reverse"></a> List:: Reverse (STL/CLR)

Denetlenen sırayı tersine çevirir.

### <a name="syntax"></a>Syntax

```cpp
void reverse();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi denetlenen dizideki tüm öğelerin sırasını tersine çevirir. Bu öğeyi bir öğe listesini yansıtacak şekilde kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// cliext_list_reverse.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // reverse and redisplay
    c1.reverse();
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
c b a
```

## <a name="listreverse_iterator-stlclr"></a><a name="reverse_iterator"></a> List:: reverse_iterator (STL/CLR)

Denetlenen sıra için ters yineleyicinin türü.

### <a name="syntax"></a>Syntax

```cpp
typedef T3 reverse_iterator;
```

### <a name="remarks"></a>Açıklamalar

Tür, `T3` denetlenen sıra için ters Yineleyici olarak işlev görebilecek belirtilmemiş türdeki bir nesneyi tanımlar.

### <a name="example"></a>Örnek

```cpp
// cliext_list_reverse_iterator.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display contents " a b c" reversed
    cliext::list<wchar_t>::reverse_iterator rit = c1.rbegin();
    for (; rit != c1.rend(); ++rit)
        System::Console::Write("{0} ", *rit);
    System::Console::WriteLine();

    // alter first element and redisplay
    rit = c1.rbegin();
    *rit = L'x';
    for (; rit != c1.rend(); ++rit)
        System::Console::Write("{0} ", *rit);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
c b a
x b a
```

## <a name="listsize-stlclr"></a><a name="size"></a> List:: size (STL/CLR)

Öğe sayısını sayar.

### <a name="syntax"></a>Syntax

```cpp
size_type size();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi denetlenen sıranın uzunluğunu döndürür. Bu, şu anda denetlenen dizideki öğelerin sayısını tespit etmek için kullanılır. Her şey, sıranın sıfır dışında bir boyuta sahip olup olmadığı konusunda bilgi için bkz. [list:: Empty (STL/CLR)](#empty) `()` .

### <a name="example"></a>Örnek

```cpp
// cliext_list_size.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    System::Console::WriteLine("size() = {0} starting with 3", c1.size());

    // clear the container and reinspect
    c1.clear();
    System::Console::WriteLine("size() = {0} after clearing", c1.size());

    // add elements and clear again
    c1.push_back(L'a');
    c1.push_back(L'b');
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

## <a name="listsize_type-stlclr"></a><a name="size_type"></a> List:: size_type (STL/CLR)

İki öğe arasındaki işaretli bir mesafe türü.

### <a name="syntax"></a>Syntax

```cpp
typedef int size_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, negatif olmayan bir öğe sayısını tanımlar.

### <a name="example"></a>Örnek

```cpp
// cliext_list_size_type.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // compute positive difference
    cliext::list<wchar_t>::size_type diff = 0;
    for (cliext::list<wchar_t>::iterator it = c1.begin();
        it != c1.end(); ++it)
        ++diff;
    System::Console::WriteLine("end()-begin() = {0}", diff);
    return (0);
    }
```

```Output
a b c
end()-begin() = 3
```

## <a name="listsort-stlclr"></a><a name="sort"></a> List:: Sort (STL/CLR)

Denetlenen sırayı sıralar.

### <a name="syntax"></a>Sözdizimi

```cpp
void sort();
template<typename Pred2>
    void sort(Pred2 pred);
```

#### <a name="parameters"></a>Parametreler

*pred*<br/>
Öğe çiftleri için karşılaştırıcı.

### <a name="remarks"></a>Açıklamalar

İlk üye işlevi denetlenen dizideki öğeleri yeniden düzenler, böylece `operator<` sıralama sırasında ilerleyerek öğelerin değeri azalmaz. Diziyi artan sırada sıralamak için bu üye işlevini kullanın.

İkinci üye işlevi ilki ile aynı şekilde davranır, ancak sıranın sıralama ölçütü `pred`  --  `pred(X, Y)` `X` sonuç dizisindeki öğesi takip eden herhangi bir öğe için false şeklindedir `Y` . Bu işlemi, bir koşul işlevi veya temsilci ile belirttiğiniz sırada sıralamayı sıralamak için kullanırsınız.

Her iki işlev de kararlı bir sıralama gerçekleştirir--orijinal denetimli dizide hiçbir öğe çifti, sonuçta elde edilen kontrollü sırada ters çevrilir.

### <a name="example"></a>Örnek

```cpp
// cliext_list_sort.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // sort descending and redisplay
    c1.sort(cliext::greater<wchar_t>());
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // sort ascending and redisplay
    c1.sort();
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
c b a
a b c
```

## <a name="listsplice-stlclr"></a><a name="splice"></a> List:: splice (STL/CLR)

Düğümler arasındaki bağlantıları restitch.

### <a name="syntax"></a>Sözdizimi

```cpp
void splice(iterator where, list<Value>% right);
void splice(iterator where, list<Value>% right,
    iterator first);
void splice(iterator where, list<Value>% right,
    iterator first, iterator last);
```

#### <a name="parameters"></a>Parametreler

*adı*<br/>
Splice için aralığın başlangıcı.

*soyadına*<br/>
Splice için aralığın sonu.

*Right*<br/>
' Dan splice ' öğesine kapsayıcı.

*olmadığı*<br/>
Daha önce nereye splice olarak kapsayıcı.

### <a name="remarks"></a>Açıklamalar

İlk üye işlevi, denetimli dizideki öğeden önce tarafından denetlenen sırayı, *WHERE* tarafından *işaret ederek ekler* . Ayrıca tüm öğeleri *sağdan* kaldırır. ( `%right` eşit olmamalı **`this`** .) Tek bir listenin tümünü başka bir listeye eklemek için kullanabilirsiniz.

İkinci üye işlevi, tarafından işaret edilen öğeyi *ilk* olarak denetim sırasına göre *kaldırır ve denetimli* dizideki öğeden önce *WHERE* tarafından işaret ederek ekler. `where`( `==` `first` `||` `where` `== ++first`, hiçbir değişiklik gerçekleşmez.) Bir listenin tek bir öğesini diğerine eklemek için bunu kullanırsınız.

Üçüncü üye işlevi, `first` `last` denetlenen dizideki öğeden önce *tarafından* denetlenen sıra [,) tarafından belirlenen alt aralığı, *WHERE* tarafından işaret edilen öğesinden ekler. Ayrıca, özgün alt aralığı *sağ* tarafından denetlenen sırayla kaldırır. ( `right == this` [,) Aralığı, `first` `last` *WHERE* tarafından işaret edilen öğe içermemelidir.) Sıfır veya daha fazla öğenin bir alt dizisini başka bir listeden diğerine eklemek için bunu kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// cliext_list_splice.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // splice to a new list
    cliext::list<wchar_t> c2;
    c2.splice(c2.begin(), c1);
    System::Console::WriteLine("c1.size() = {0}", c1.size());
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // return one element
    c1.splice(c1.end(), c2, c2.begin());
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // return remaining elements
    c1.splice(c1.begin(), c2, c2.begin(), c2.end());
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    System::Console::WriteLine("c2.size() = {0}", c2.size());
    return (0);
    }
```

```Output
a b c
c1.size() = 0
a b c
a
b c
b c a
c2.size() = 0
```

## <a name="listswap-stlclr"></a><a name="swap"></a> List:: swap (STL/CLR)

İki kapsayıcının içeriğinin yerini değiştirir.

### <a name="syntax"></a>Sözdizimi

```cpp
void swap(list<Value>% right);
```

#### <a name="parameters"></a>Parametreler

*Right*<br/>
İçeriği takas eden kapsayıcı.

### <a name="remarks"></a>Açıklamalar

Üye işlevi, ve sağ arasındaki denetlenen dizileri **`*this`** değiştirir . Bu, sabit zamanlı olarak yapar ve özel durum oluşturmaz. Bunu iki kapsayıcının içeriğini değiş tokuş etmek için hızlı bir yol olarak kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// cliext_list_swap.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct another container with repetition of values
    cliext::list<wchar_t> c2(5, L'x');
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

## <a name="listto_array-stlclr"></a><a name="to_array"></a> List:: to_array (STL/CLR)

Denetimli sırayı yeni bir diziye kopyalar.

### <a name="syntax"></a>Syntax

```cpp
cli::array<Value>^ to_array();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi denetlenen sırayı içeren bir dizi döndürür. Dizi biçiminde denetlenen sıranın bir kopyasını almak için bunu kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// cliext_list_to_array.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // copy the container and modify it
    cli::array<wchar_t>^ a1 = c1.to_array();

    c1.push_back(L'd');
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

## <a name="listunique-stlclr"></a><a name="unique"></a> List:: Unique (STL/CLR)

Belirtilen testi geçiren bitişik öğeleri kaldırır.

### <a name="syntax"></a>Sözdizimi

```cpp
void unique();
template<typename Pred2>
    void unique(Pred2 pred);
```

#### <a name="parameters"></a>Parametreler

*pred*<br/>
Öğe çiftleri için karşılaştırıcı.

### <a name="remarks"></a>Açıklamalar

İlk üye işlevi, bir önceki öğesiyle eşit olarak karşılaştırdığı her öğe denetimli sırayla (siler) kaldırılır--Eğer öğesi `X` öğeden önce `Y` ve `X == Y` üye işlevi kaldırılır `Y` . Eşit olarak karşılaştırıldığı bitişik öğelerin her alt dizisinin bir kopyasını kaldırmak için bunu kullanırsınız. Denetlenen sıra sıralı ise (örneğin, [list:: Sort (STL/CLR)](#sort) `()` , üye işlevinin yalnızca benzersiz değerlere sahip öğelerin ayrıldığına unutmayın. (Bu nedenle ad).

İkinci üye işlevi ilki ile aynı şekilde davranır, ancak `Y` bir öğeden sonraki her öğeyi kaldırır `X` `pred(X, Y)` . Belirlediğiniz bir koşul işlevini veya temsilciyi karşılayan bitişik öğelerin her alt dizisinin bir kopyasını kaldırmak için bunu kullanırsınız. Denetlenen dizi sıralı ise, `sort(pred)` üye işlevi yalnızca diğer öğelerle eşdeğer sıralama bulunmayan öğelerin ayrıldığına unutmayın.

### <a name="example"></a>Örnek

```cpp
// cliext_list_unique.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display initial contents " a a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // display contents after unique
    cliext::list<wchar_t> c2(c1);
    c2.unique();
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // display contents after unique(not_equal_to)
    c2 = c1;
    c2.unique(cliext::not_equal_to<wchar_t>());
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a a b c
a b c
a a
```

## <a name="listvalue_type-stlclr"></a><a name="value_type"></a> List:: value_type (STL/CLR)

Öğenin türü.

### <a name="syntax"></a>Syntax

```cpp
typedef Value value_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, şablon parametre *değeri* için bir eş anlamlı.

### <a name="example"></a>Örnek

```cpp
// cliext_list_value_type.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display contents " a b c" using value_type
    for (cliext::list<wchar_t>::iterator it = c1.begin();
        it != c1.end(); ++it)
        {   // store element in value_type object
        cliext::list<wchar_t>::value_type val = *it;

        System::Console::Write("{0} ", val);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="operator-list-stlclr"></a><a name="op_neq"></a> işleç! = (liste) (STL/CLR)

Liste eşit değildir karşılaştırması.

### <a name="syntax"></a>Sözdizimi

```cpp
template<typename Value>
    bool operator!=(list<Value>% left,
        list<Value>% right);
```

#### <a name="parameters"></a>Parametreler

*tarafta*<br/>
Karşılaştırılacak sol kapsayıcı.

*Right*<br/>
Karşılaştırılacak doğru kapsayıcı.

### <a name="remarks"></a>Açıklamalar

İşleç işlevi döndürülür `!(left == right)` . İki liste öğe öğesine göre karşılaştırıldığı zaman, *sol* öğenin *doğru* şekilde sıralı olup olmadığını test etmek için kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// cliext_list_operator_ne.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // assign to a new container
    cliext::list<wchar_t> c2;
    c2.push_back(L'a');
    c2.push_back(L'b');
    c2.push_back(L'd');

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

## <a name="operatorlt-list-stlclr"></a><a name="op_lt"></a> işleç &lt; (liste) (STL/CLR)

Liste karşılaştırmadan daha az.

### <a name="syntax"></a>Sözdizimi

```cpp
template<typename Value>
    bool operator<(list<Value>% left,
        list<Value>% right);
```

#### <a name="parameters"></a>Parametreler

*tarafta*<br/>
Karşılaştırılacak sol kapsayıcı.

*Right*<br/>
Karşılaştırılacak doğru kapsayıcı.

### <a name="remarks"></a>Açıklamalar

İşleç işlevi, `i` `!(right[i] < left[i])` bunun da doğru olduğu en düşük konum için true değerini döndürür `left[i] < right[i]` . Aksi takdirde, `left->size() < right->size()` iki liste öğe öğesine göre karşılaştırıldığı zaman, *sol taraftaki* bir süre önce sola *doğru* sıralı olup olmadığını test etmek için bunu kullanır.

### <a name="example"></a>Örnek

```cpp
// cliext_list_operator_lt.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // assign to a new container
    cliext::list<wchar_t> c2;
    c2.push_back(L'a');
    c2.push_back(L'b');
    c2.push_back(L'd');

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

## <a name="operatorlt-list-stlclr"></a><a name="op_lteq"></a> operator &lt; = (liste) (STL/CLR)

Küçüktür veya eşit karşılaştırma listesi.

### <a name="syntax"></a>Sözdizimi

```cpp
template<typename Value>
    bool operator<=(list<Value>% left,
        list<Value>% right);
```

#### <a name="parameters"></a>Parametreler

*tarafta*<br/>
Karşılaştırılacak sol kapsayıcı.

*Right*<br/>
Karşılaştırılacak doğru kapsayıcı.

### <a name="remarks"></a>Açıklamalar

İşleç işlevi döndürülür `!(right < left)` . İki liste öğe öğesine göre karşılaştırıldığı zaman *farenin sağ* *tarafında* sıralı olup olmadığını test etmek için bunu kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// cliext_list_operator_le.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // assign to a new container
    cliext::list<wchar_t> c2;
    c2.push_back(L'a');
    c2.push_back(L'b');
    c2.push_back(L'd');

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

## <a name="operator-list-stlclr"></a><a name="op_eq"></a> işleç = = (liste) (STL/CLR)

Liste eşit karşılaştırması.

### <a name="syntax"></a>Sözdizimi

```cpp
template<typename Value>
    bool operator==(list<Value>% left,
        list<Value>% right);
```

#### <a name="parameters"></a>Parametreler

*tarafta*<br/>
Karşılaştırılacak sol kapsayıcı.

*Right*<br/>
Karşılaştırılacak doğru kapsayıcı.

### <a name="remarks"></a>Açıklamalar

İşleç işlevi yalnızca *sol* ve *sağ* tarafından denetlenen diziler aynı uzunlukta ve her bir konum için aynı uzunluğa sahip olursa true değerini döndürür `i` `left[i] ==` `right[i]` . Bu, iki liste öğe öğesine göre karşılaştırıldığı zaman *solinin* *doğru* olup olmadığını test etmek için kullanılır.

### <a name="example"></a>Örnek

```cpp
// cliext_list_operator_eq.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // assign to a new container
    cliext::list<wchar_t> c2;
    c2.push_back(L'a');
    c2.push_back(L'b');
    c2.push_back(L'd');

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

## <a name="operatorgt-list-stlclr"></a><a name="op_gt"></a> işleç &gt; (liste) (STL/CLR)

Karşılaştırmadan daha büyük bir liste.

### <a name="syntax"></a>Sözdizimi

```cpp
template<typename Value>
    bool operator>(list<Value>% left,
        list<Value>% right);
```

#### <a name="parameters"></a>Parametreler

*tarafta*<br/>
Karşılaştırılacak sol kapsayıcı.

*Right*<br/>
Karşılaştırılacak doğru kapsayıcı.

### <a name="remarks"></a>Açıklamalar

İşleç işlevi döndürülür `right` `<` `left` . Bu, iki liste öğe öğesine göre karşılaştırıldığı zaman, *sol* *taraftaki doğru olup* olmadığını test etmek için kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// cliext_list_operator_gt.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // assign to a new container
    cliext::list<wchar_t> c2;
    c2.push_back(L'a');
    c2.push_back(L'b');
    c2.push_back(L'd');

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

## <a name="operatorgt-list-stlclr"></a><a name="op_gteq"></a> operator &gt; = (liste) (STL/CLR)

Büyük veya eşit karşılaştırmayı listele.

### <a name="syntax"></a>Sözdizimi

```cpp
template<typename Value>
    bool operator>=(list<Value>% left,
        list<Value>% right);
```

#### <a name="parameters"></a>Parametreler

*tarafta*<br/>
Karşılaştırılacak sol kapsayıcı.

*Right*<br/>
Karşılaştırılacak doğru kapsayıcı.

### <a name="remarks"></a>Açıklamalar

İşleç işlevi döndürülür `!(left` `<` `right)` . İki liste öğe öğesine göre karşılaştırıldığı zaman *sağdan* *sola* doğru sıralanmadığını test etmek için bunu kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// cliext_list_operator_ge.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // assign to a new container
    cliext::list<wchar_t> c2;
    c2.push_back(L'a');
    c2.push_back(L'b');
    c2.push_back(L'd');

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
