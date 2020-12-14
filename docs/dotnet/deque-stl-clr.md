---
description: 'Daha fazla bilgi edinin: deque (STL/CLR)'
title: sıradan ayır (STL/CLR)
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- cliext::deque
- cliext::deque::assign
- cliext::deque::at
- cliext::deque::back
- cliext::deque::back_item
- cliext::deque::begin
- cliext::deque::clear
- cliext::deque::const_iterator
- cliext::deque::const_reference
- cliext::deque::const_reverse_iterator
- cliext::deque::deque
- cliext::deque::difference_type
- cliext::deque::empty
- cliext::deque::end
- cliext::deque::erase
- cliext::deque::front
- cliext::deque::front_item
- cliext::deque::generic_container
- cliext::deque::generic_iterator
- cliext::deque::generic_reverse_iterator
- cliext::deque::generic_value
- cliext::deque::insert
- cliext::deque::iterator
- cliext::deque::operator!=
- cliext::deque::operator[]
- cliext::deque::pop_back
- cliext::deque::pop_front
- cliext::deque::push_back
- cliext::deque::push_front
- cliext::deque::rbegin
- cliext::deque::reference
- cliext::deque::rend
- cliext::deque::resize
- cliext::deque::reverse_iterator
- cliext::deque::size
- cliext::deque::size_type
- cliext::deque::swap
- cliext::deque::to_array
- cliext::deque::value_type
- cliext::deque::operator<
- cliext::deque::operator<=
- cliext::deque::operator=
- cliext::deque::operator==
- cliext::deque::operator>
- cliext::deque::operator>=
helpviewer_keywords:
- deque class [STL/CLR]
- <deque> header [STL/CLR]
- <cliext/deque> header [STL/CLR]
- assign member [STL/CLR]
- assign member [STL/CLR]
- at member [STL/CLR]
- back member [STL/CLR]
- back_item member [STL/CLR]
- begin member [STL/CLR]
- clear member [STL/CLR]
- const_iterator member [STL/CLR]
- const_reference member [STL/CLR]
- const_reverse_iterator member [STL/CLR]
- deque member [STL/CLR]
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
- operator!= member [STL/CLR]
- operator member [] [STL/CLR]
- pop_back member [STL/CLR]
- pop_front member [STL/CLR]
- push_back member [STL/CLR]
- push_front member [STL/CLR]
- rbegin member [STL/CLR]
- reference member [STL/CLR]
- rend member [STL/CLR]
- resize member [STL/CLR]
- reverse_iterator member [STL/CLR]
- size member [STL/CLR]
- size_type member [STL/CLR]
- swap member [STL/CLR]
- to_array member [STL/CLR]
- value_type member [STL/CLR]
- operator< member [STL/CLR]
- operator<= member [STL/CLR]
- operator= member [STL/CLR]
- operator== member [STL/CLR]
- operator> member [STL/CLR]
- operator>= member [STL/CLR]
ms.assetid: dd669da3-3c0e-45e9-8596-f6b483720941
ms.openlocfilehash: 98ad68c3220424a30b6cc75363e5ff92fbc0f965
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97252213"
---
# <a name="deque-stlclr"></a>sıradan ayır (STL/CLR)

Şablon sınıfı, rasgele erişimi olan öğelerin değişen uzunluklu dizisini denetleyen bir nesneyi tanımlar. Kapsayıcıyı `deque` bitişik bir depolama bloğu gibi görünen bir dizi öğeyi yönetmek için kullanın, ancak kalan öğeleri kopyalamaya gerek kalmadan herhangi bir uçta büyümek veya küçülebilir. Bu nedenle, verimli bir şekilde uygulayabilir `double-ended queue` . (Bu nedenle ad.)

Aşağıdaki açıklamada, `GValue` `Value` İkincisi bir başvuru türü olmadığı ve bu durumda olduğu sürece aynıdır `Value^` .

## <a name="syntax"></a>Sözdizimi

```cpp
template<typename Value>
    ref class deque
        :   public
        System::ICloneable,
        System::Collections::IEnumerable,
        System::Collections::ICollection,
        System::Collections::Generic::IEnumerable<GValue>,
        System::Collections::Generic::ICollection<GValue>,
        System::Collections::Generic::IList<GValue>,
        Microsoft::VisualC::StlClr::IDeque<GValue>
    { ..... };
```

### <a name="parameters"></a>Parametreler

*GValue*<br/>
Denetlenen dizideki bir öğenin genel türü.

*Değer*<br/>
Denetlenen sıradaki öğenin türü.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<cliext/deque>

**Ad alanı:** cliext

## <a name="declarations"></a>Bildirimler

|Tür Tanımı|Açıklama|
|---------------------|-----------------|
|[deque::const_iterator (STL/CLR)](#const_iterator)|Denetlenen dizi için bir sabit yineleyici türü.|
|[deque::const_reference (STL/CLR)](#const_reference)|Bir öğe için sabit bir başvuru türü.|
|[deque::const_reverse_iterator (STL/CLR)](#const_reverse_iterator)|Denetlenen sıra için bir sabit ters yineleyicinin türü.|
|[deque::difference_type (STL/CLR)](#difference_type)|İki öğe arasındaki işaretli mesafenin türü.|
|[deque::generic_container (STL/CLR)](#generic_container)|Kapsayıcının genel arabiriminin türü.|
|[deque::generic_iterator (STL/CLR)](#generic_iterator)|Kapsayıcının genel arabirimi için bir yineleyici türü.|
|[deque::generic_reverse_iterator (STL/CLR)](#generic_reverse_iterator)|Kapsayıcının genel arabirimi için ters yineleyicinin türü.|
|[deque::generic_value (STL/CLR)](#generic_value)|Kapsayıcının genel arabirimi için bir öğenin türü.|
|[deque::iterator (STL/CLR)](#iterator)|Denetlenen dizi için bir yineleyici türü.|
|[deque::reference (STL/CLR)](#reference)|Bir öğe için bir başvuru türü.|
|[deque::reverse_iterator (STL/CLR)](#reverse_iterator)|Denetlenen sıra için ters yineleyicinin türü.|
|[deque::size_type (STL/CLR)](#size_type)|İki öğe arasındaki işaretli mesafenin türü.|
|[deque::value_type (STL/CLR)](#value_type)|Öğenin türü.|

|Üye İşlevi|Açıklama|
|---------------------|-----------------|
|[deque::assign (STL/CLR)](#assign)|Tüm öğeleri değiştirir.|
|[deque::at (STL/CLR)](#at)|Belirtilen konumdaki bir öğeye erişir.|
|[deque::back (STL/CLR)](#back)|Son öğeye erişir.|
|[deque::begin (STL/CLR)](#begin)|Denetlenen dizinin başlangıcını belirtir.|
|[deque::clear (STL/CLR)](#clear)|Tüm öğeleri kaldırır.|
|[deque::deque (STL/CLR)](#deque)|Bir kapsayıcı nesnesi oluşturur.|
|[deque::empty (STL/CLR)](#empty)|Bir öğe olup olmadığını sınar.|
|[deque::end (STL/CLR)](#end)|Denetlenen dizinin bitişini belirtir.|
|[deque::erase (STL/CLR)](#erase)|Belirtilen konumlardaki öğeleri kaldırır.|
|[deque::front (STL/CLR)](#front)|İlk öğeye erişir.|
|[deque::insert (STL/CLR)](#insert)|Belirtilen konumdaki öğeleri ekler.|
|[deque::pop_back (STL/CLR)](#pop_back)|Son öğeyi kaldırır.|
|[deque::pop_front (STL/CLR)](#pop_front)|İlk öğeyi kaldırır.|
|[deque::push_back (STL/CLR)](#push_back)|Yeni bir son öğe ekler.|
|[deque::push_front (STL/CLR)](#push_front)|Yeni bir ilk öğe ekler.|
|[deque::rbegin (STL/CLR)](#rbegin)|Ters denetlenen sıranın başlangıcını belirtir.|
|[deque::rend (STL/CLR)](#rend)|Ters denetlenen sıranın sonunu belirtir.|
|[deque::resize (STL/CLR)](#resize)|Öğe sayısını değiştirir.|
|[deque::size (STL/CLR)](#size)|Öğe sayısını sayar.|
|[deque::swap (STL/CLR)](#swap)|İki kapsayıcının içeriğinin yerini değiştirir.|
|[deque::to_array (STL/CLR)](#to_array)|Denetimli sırayı yeni bir diziye kopyalar.|

|Özellik|Açıklama|
|--------------|-----------------|
|[deque::back_item (STL/CLR)](#back_item)|Son öğeye erişir.|
|[deque::front_item (STL/CLR)](#front_item)|İlk öğeye erişir.|

|İşleç|Açıklama|
|--------------|-----------------|
|[deque::operator!= (STL/CLR)](#op_neq)|İki nesnenin eşit olup olmadığını belirler `deque` .|
|[deque::operator(STL/CLR)](#operator)|Belirtilen konumdaki bir öğeye erişir.|
|[operator< (deque) (STL/CLR)](#op_lt)|Bir `deque` nesnenin başka bir nesneden daha az olup olmadığını belirler `deque` .|
|[işleç<= (deque) (STL/CLR)](#op_lteq)|Bir `deque` nesnenin başka bir nesneden küçük veya ona eşit olup olmadığını belirler `deque` .|
|[operator = (deque) (STL/CLR)](#op_as)|Denetlenen sırayı değiştirir.|
|[operator = = (deque) (STL/CLR)](#op_eq)|Bir `deque` nesnenin başka bir nesneye eşit olup olmadığını belirler `deque` .|
|[işleç> (deque) (STL/CLR)](#op_gt)|Bir `deque` nesnenin başka bir nesneden daha büyük olup olmadığını belirler `deque` .|
|[işleç>= (deque) (STL/CLR)](#op_gteq)|Bir `deque` nesnenin başka bir nesneden büyük veya ona eşit olup olmadığını belirler `deque` .|

## <a name="interfaces"></a>Arabirimler

|Arabirim|Açıklama|
|---------------|-----------------|
|<xref:System.ICloneable>|Bir nesneyi çoğaltın.|
|<xref:System.Collections.IEnumerable>|Öğeler aracılığıyla sıralama.|
|<xref:System.Collections.ICollection>|Öğe grubunu saklayın.|
|<xref:System.Collections.Generic.IEnumerable%601>|Yazılı öğeler aracılığıyla sıralama.|
|<xref:System.Collections.Generic.ICollection%601>|Türü belirtilmiş öğelerin grubunu koruyun.|
|<xref:System.Collections.Generic.IList%601>|Yazılı öğelerin sıralı grubunu saklayın.|
|IDeque<değeri\>|Genel kapsayıcıyı koruyun.|

## <a name="remarks"></a>Açıklamalar

Nesnesi, öğe bloklarını belirten bir dizi tutamacı aracılığıyla denetlediği sıra için depolamayı ayırır ve boşaltır `Value` . Dizi isteğe bağlı olarak büyür. Büyüme, ön bekleyen ya da yeni bir öğe ekleme maliyetinin sabit zamanlı olduğu ve kalan öğelerin olumsuz olmadığı bir şekilde gerçekleşir. Ayrıca, sabit zamanlı olarak ve kalan öğeleri rahatsız etmeden bir öğeyi da kaldırabilirsiniz. Bu nedenle, bir deque şablon sınıfı [kuyruğu (STL/CLR)](../dotnet/queue-stl-clr.md) veya şablon sınıfı [yığını (STL/CLR)](../dotnet/stack-stl-clr.md)için temel alınan kapsayıcı için iyi bir adaydır.

Bir `deque` nesne Rastgele erişimli yineleyiciler destekler, bu da bir öğeye, ilk (ön) öğesi için sıfırdan saymaya, [](#size) `() - 1` en son (arka) öğe için sıfırdan (önde gelen) kadar olan bir öğeye başvuruda bulunmak üzere doğrudan bir öğe yazabilirsiniz. Ayrıca, bir deque 'ın, [priority_queue (STL/CLR)](../dotnet/priority-queue-stl-clr.md)şablon sınıfı için temel alınan kapsayıcı için iyi bir aday olduğu anlamına gelir.

Bir deque Yineleyici, kendi ilişkili deque nesnesine bir tutamacı depolar ve bu nesnenin, oluşturduğu öğe sapması ile birlikte depolar. Yineleyiciler yalnızca ilişkili kapsayıcı nesneleriyle birlikte kullanabilirsiniz. Bir deque öğesinin sapması, konumuyla aynı *değildir.* Eklenen ilk öğe sapma sıfıra sahip, Next eklenmiş öğenin sapma 1, ancak Next prepelement, sapma-1 ' i içerir.

Her iki uçta öğe eklemek veya silmek geçerli bir sapmaya depolanmış bir öğenin *değerini değiştirmez.* Ancak iç öğe ekleme veya silme, belirli bir sapmaya depolanan öğe *değerini değiştirebilir,* bu nedenle bir yineleyici tarafından belirlenen değer de değişebilir. (Bir INSERT 'tan önce bir delik oluşturmak veya bir silme işleminden sonra bir delik açmak için kapsayıcının öğeleri yukarı veya aşağı kopyalaması gerekebilir.) Bununla birlikte, bir deque Yineleyici geçerli kalır, çünkü sapması geçerli bir öğe belirler. Üstelik, geçerli bir yineleyici, bir üst kabloyla devam eder; bu işlemi, yaptığı öğe değerine erişmek veya değiştirmek için kullanabilirsiniz. bu nedenle, sapması tarafından döndürülen Yineleyici için sapma değerine eşit olmadığı sürece `end()` .

Bir öğeyi silme veya kaldırma, kendi saklı değeri için yıkıcıyı çağırır. Kapsayıcının yok edilmesi tüm öğeleri siler. Bu nedenle, öğe türü bir başvuru sınıfı olan bir kapsayıcı, kapsayıcının hiçbir öğenin etkin olmamasını sağlar. Ancak, bir işleç kapsayıcısının *öğelerini yok ettiğini* unutmayın.

## <a name="members"></a>Üyeler

## <a name="dequeassign-stlclr"></a><a name="assign"></a> deque:: Assign (STL/CLR)

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
// cliext_deque_assign.cpp
// compile with: /clr
#include <cliext/deque>

int main()
    {
    cliext::deque<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // assign a repetition of values
    cliext::deque<wchar_t> c2;
    c2.assign(6, L'x');
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // assign an iterator range
    c2.assign(c1.begin(), c1.end() - 1);
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

## <a name="dequeat-stlclr"></a><a name="at"></a> deque:: at (STL/CLR)

Belirtilen konumdaki bir öğeye erişir.

### <a name="syntax"></a>Sözdizimi

```cpp
reference at(size_type pos);
```

#### <a name="parameters"></a>Parametreler

*'un*<br/>
Erişim için öğenin konumu.

### <a name="remarks"></a>Açıklamalar

Üye işlevi, *POS* konumundaki denetimli sıranın öğesine bir başvuru döndürür. Konumunu bildiğiniz bir öğeyi okumak veya yazmak için bunu kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// cliext_deque_at.cpp
// compile with: /clr
#include <cliext/deque>

int main()
    {
    cliext::deque<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display contents " a b c" using at
    for (int i = 0; i < c1.size(); ++i)
        System::Console::Write("{0} ", c1.at(i));
    System::Console::WriteLine();

    // change an entry and redisplay
    c1.at(1) = L'x';
    for (int i = 0; i < c1.size(); ++i)
        System::Console::Write("{0} ", c1[i]);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
a x c
```

## <a name="dequeback-stlclr"></a><a name="back"></a> deque:: Back (STL/CLR)

Son öğeye erişir.

### <a name="syntax"></a>Syntax

```cpp
reference back();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, denetimli sıranın son öğesine bir başvuru döndürür ve bu değer boş olmamalıdır. Bunu, olduğunu bildiğiniz zaman son öğeye erişmek için kullanabilirsiniz.

### <a name="example"></a>Örnek

```cpp
// cliext_deque_back.cpp
// compile with: /clr
#include <cliext/deque>

int main()
    {
    cliext::deque<wchar_t> c1;
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

## <a name="dequeback_item-stlclr"></a><a name="back_item"></a> deque:: back_item (STL/CLR)

Son öğeye erişir.

### <a name="syntax"></a>Syntax

```cpp
property value_type back_item;
```

### <a name="remarks"></a>Açıklamalar

Özelliği, denetimli sıranın son öğesine erişir, bu da boş olmamalıdır. Bunu, olduğunu bildiğiniz zaman son öğeyi okumak veya yazmak için kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// cliext_deque_back_item.cpp
// compile with: /clr
#include <cliext/deque>

int main()
    {
    cliext::deque<wchar_t> c1;
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

## <a name="dequebegin-stlclr"></a><a name="begin"></a> deque:: Begin (STL/CLR)

Denetlenen dizinin başlangıcını belirtir.

### <a name="syntax"></a>Syntax

```cpp
iterator begin();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, denetlenen sıranın ilk öğesini veya boş bir dizinin sonunun ötesinde bir rastgele erişim yineleyici döndürür. Denetlenen dizinin başlangıcını atayan bir yineleyici elde etmek için bunu kullanırsınız `current` , ancak denetlenen sıranın uzunluğu değişirse durum değişebilir.

### <a name="example"></a>Örnek

```cpp
// cliext_deque_begin.cpp
// compile with: /clr
#include <cliext/deque>

int main()
    {
    cliext::deque<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // inspect first two items
    cliext::deque<wchar_t>::iterator it = c1.begin();
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

## <a name="dequeclear-stlclr"></a><a name="clear"></a> deque:: Clear (STL/CLR)

Tüm öğeleri kaldırır.

### <a name="syntax"></a>Syntax

```cpp
void clear();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, [deque:: Erase (STL/CLR)](#erase) `(` [deque:: BEGIN (STL/CLR)](#begin) `(),` [deque:: End (STL/CLR)](#end)öğesini etkin bir şekilde çağırır `())` . Denetlenen sıranın boş olduğundan emin olmak için bunu kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// cliext_deque_clear.cpp
// compile with: /clr
#include <cliext/deque>

int main()
    {
    cliext::deque<wchar_t> c1;
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

## <a name="dequeconst_iterator-stlclr"></a><a name="const_iterator"></a> deque:: const_iterator (STL/CLR)

Denetlenen dizi için bir sabit yineleyici türü.

### <a name="syntax"></a>Syntax

```cpp
typedef T2 const_iterator;
```

### <a name="remarks"></a>Açıklamalar

Türü, `T2` denetimli sıra için sabit bir rastgele erişim Yineleyici işlevi görebilecek belirtilmemiş türdeki bir nesneyi tanımlar.

### <a name="example"></a>Örnek

```cpp
// cliext_deque_const_iterator.cpp
// compile with: /clr
#include <cliext/deque>

int main()
    {
    cliext::deque<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display contents " a b c"
    cliext::deque<wchar_t>::const_iterator cit = c1.begin();
    for (; cit != c1.end(); ++cit)
        System::Console::Write("{0} ", *cit);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="dequeconst_reference-stlclr"></a><a name="const_reference"></a> deque:: const_reference (STL/CLR)

Bir öğe için sabit bir başvuru türü.

### <a name="syntax"></a>Syntax

```cpp
typedef value_type% const_reference;
```

### <a name="remarks"></a>Açıklamalar

Türü bir öğeye sabit bir başvuru tanımlar.

### <a name="example"></a>Örnek

```cpp
// cliext_deque_const_reference.cpp
// compile with: /clr
#include <cliext/deque>

int main()
    {
    cliext::deque<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display initial contents " a b c"
    cliext::deque<wchar_t>::const_iterator cit = c1.begin();
    for (; cit != c1.end(); ++cit)
        {   // get a const reference to an element
        cliext::deque<wchar_t>::const_reference cref = *cit;
        System::Console::Write("{0} ", cref);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="dequeconst_reverse_iterator-stlclr"></a><a name="const_reverse_iterator"></a> deque:: const_reverse_iterator (STL/CLR)

Denetlenen sıra için bir sabit ters yineleyicinin türü..

### <a name="syntax"></a>Syntax

```cpp
typedef T4 const_reverse_iterator;
```

### <a name="remarks"></a>Açıklamalar

Türü, `T4` denetimli sıra için sabit bir ters Yineleyici işlevi görebilecek belirtilmemiş türdeki bir nesneyi tanımlar.

### <a name="example"></a>Örnek

```cpp
// cliext_deque_const_reverse_iterator.cpp
// compile with: /clr
#include <cliext/deque>

int main()
    {
    cliext::deque<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display contents " a b c" reversed
    cliext::deque<wchar_t>::const_reverse_iterator crit = c1.rbegin();
    cliext::deque<wchar_t>::const_reverse_iterator crend = c1.rend();
    for (; crit != crend; ++crit)
        System::Console::Write("{0} ", *crit);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
c b a
```

## <a name="dequedeque-stlclr"></a><a name="deque"></a> deque::d eque (STL/CLR)

Bir kapsayıcı nesnesi oluşturur.

### <a name="syntax"></a>Sözdizimi

```cpp
deque();
deque(deque<Value>% right);
deque(deque<Value>^ right);
explicit deque(size_type count);
deque(size_type count, value_type val);
template<typename InIt>
    deque(InIt first, InIt last);
deque(System::Collections::Generic::IEnumerable<Value>^ right);
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

`deque();`

denetimli sırayı öğesi olmadan başlatır. Boş bir ilk denetimli sıra belirtmek için bunu kullanırsınız.

Oluşturucu:

`deque(deque<Value>% right);`

denetlenen sırayı [ `right.begin()` ,) sırasıyla başlatır `right.end()` . Bu işlemi, deque nesnesi *sağa* tarafından denetlenen sıranın bir kopyası olan ilk denetimli bir sıra belirtmek için kullanırsınız. Yineleyiciler hakkında daha fazla bilgi için bkz. [deque:: Begin (STL/CLR)](#begin) ve [deque:: End (STL/CLR)](#end).

Oluşturucu:

`deque(deque<Value>^ right);`

denetlenen sırayı [ `right->begin()` ,) sırasıyla başlatır `right->end()` . Tutamacı *doğru* olan deque nesnesi tarafından denetlenen sıranın bir kopyası olan ilk denetimli bir sıra belirtmek için bunu kullanırsınız.

Oluşturucu:

`explicit deque(size_type count);`

Her bir değer içeren *sayı* öğeleri olan denetimli sırayı başlatır `value_type()` . Kapsayıcıyı, varsayılan değere sahip olan öğelerle birlikte doldurmanız için kullanırsınız.

Oluşturucu:

`deque(size_type count, value_type val);`

her biri değer *Val* ile denetlenen diziyi *say* öğesi ile başlatır. Kapsayıcıyı aynı değere sahip olan öğelerle birlikte doldurmanız için kullanabilirsiniz.

Oluşturucu:

`template<typename InIt>`

`deque(InIt first, InIt last);`

denetlenen sırayı [ `first` ,) sırasıyla başlatır `last` . Bunu, denetimli diziyi başka bir dizinin bir kopyası yapmak için kullanırsınız.

Oluşturucu:

`deque(System::Collections::Generic::IEnumerable<Value>^ right);`

denetlenen sırayı Numaralandırıcı *hakkı* tarafından belirlenen sırayla başlatır. Denetlenen diziyi, Numaralandırıcı tarafından tanımlanan başka bir dizinin bir kopyası yapmak için kullanabilirsiniz.

### <a name="example"></a>Örnek

```cpp
// cliext_deque_construct.cpp
// compile with: /clr
#include <cliext/deque>

int main()
    {
// construct an empty container
    cliext::deque<wchar_t> c1;
    System::Console::WriteLine("size() = {0}", c1.size());

    // construct with a repetition of default values
    cliext::deque<wchar_t> c2(3);
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", (int)elem);
    System::Console::WriteLine();

    // construct with a repetition of values
    cliext::deque<wchar_t> c3(6, L'x');
    for each (wchar_t elem in c3)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct with an iterator range
    cliext::deque<wchar_t>::iterator it = c3.end();
    cliext::deque<wchar_t> c4(c3.begin(), --it);
    for each (wchar_t elem in c4)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct with an enumeration
    cliext::deque<wchar_t> c5(   // NOTE: cast is not needed
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c3);
    for each (wchar_t elem in c5)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct by copying another container
    cliext::deque<wchar_t> c7(c3);
    for each (wchar_t elem in c7)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct by copying a container handle
    cliext::deque<wchar_t> c8(%c3);
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

## <a name="dequedifference_type-stlclr"></a><a name="difference_type"></a> deque::d ifference_type (STL/CLR)

İki öğe arasındaki işaretli bir mesafe türü.

### <a name="syntax"></a>Syntax

```cpp
typedef int difference_type;
```

### <a name="remarks"></a>Açıklamalar

Türü, imzalı bir öğe sayısını tanımlar.

### <a name="example"></a>Örnek

```cpp
// cliext_deque_difference_type.cpp
// compile with: /clr
#include <cliext/deque>

int main()
    {
    cliext::deque<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // compute positive difference
    cliext::deque<wchar_t>::difference_type diff = 0;
    for (cliext::deque<wchar_t>::iterator it = c1.begin();
        it != c1.end(); ++it) ++diff;
    System::Console::WriteLine("end()-begin() = {0}", diff);

    // compute negative difference
    diff = 0;
    for (cliext::deque<wchar_t>::iterator it = c1.end();
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

## <a name="dequeempty-stlclr"></a><a name="empty"></a> deque:: Empty (STL/CLR)

Bir öğe olup olmadığını sınar.

### <a name="syntax"></a>Syntax

```cpp
bool empty();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi boş bir denetlenen dizi için true döndürür. [Deque:: size (STL/CLR)](#size)eşdeğerdir `() == 0` . Bu uygulamayı, deque 'in boş olup olmadığını test etmek için kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// cliext_deque_empty.cpp
// compile with: /clr
#include <cliext/deque>

int main()
    {
    cliext::deque<wchar_t> c1;
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

## <a name="dequeend-stlclr"></a><a name="end"></a> deque:: End (STL/CLR)

Denetlenen dizinin bitişini belirtir.

### <a name="syntax"></a>Syntax

```cpp
iterator end();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, denetimli dizinin sonunun hemen ötesinde işaret eden bir rastgele erişim yineleyici döndürür. Denetlenen dizinin sonunu atayan bir yineleyici elde etmek için bunu kullanırsınız `current` , ancak denetlenen sıranın uzunluğu değişirse durumu değişebilir.

### <a name="example"></a>Örnek

```cpp
// cliext_deque_end.cpp
// compile with: /clr
#include <cliext/deque>

int main()
    {
    cliext::deque<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // inspect last two items
    cliext::deque<wchar_t>::iterator it = c1.end();
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

## <a name="dequeerase-stlclr"></a><a name="erase"></a> deque:: Erase (STL/CLR)

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

Her iki üye işlevi de kaldırılan öğelerin dışında kalan ilk öğeyi atayan bir yineleyici döndürür veya böyle bir öğe yoksa [deque:: End (STL/CLR)](#end) `()` .

Öğeleri silerken, öğe kopyalarının sayısı doğrusal bir şekilde sıra sayısının bitişine ve sonuna kadar olan sayı arasındaki öğe sayısını gösterir. (Sıranın her iki ucunda bir veya daha fazla öğe silinirken, hiçbir öğe kopyası gerçekleşmez.)

### <a name="example"></a>Örnek

```cpp
// cliext_deque_erase.cpp
// compile with: /clr
#include <cliext/deque>

int main()
    {
    cliext::deque<wchar_t> c1;
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
    cliext::deque<wchar_t>::iterator it = c1.end();
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

## <a name="dequefront-stlclr"></a><a name="front"></a> deque:: Front (STL/CLR)

İlk öğeye erişir.

### <a name="syntax"></a>Syntax

```cpp
reference front();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, denetimli sıranın ilk öğesine bir başvuru döndürür ve bu değer boş olmamalıdır. Olduğunu bildiğiniz zaman ilk öğeyi okumak veya yazmak için bunu kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// cliext_deque_front.cpp
// compile with: /clr
#include <cliext/deque>

int main()
    {
    cliext::deque<wchar_t> c1;
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

## <a name="dequefront_item-stlclr"></a><a name="front_item"></a> deque:: front_item (STL/CLR)

İlk öğeye erişir.

### <a name="syntax"></a>Syntax

```cpp
property value_type front_item;
```

### <a name="remarks"></a>Açıklamalar

Özelliği, denetimli sıranın ilk öğesine erişir, bu da boş olmamalıdır. Olduğunu bildiğiniz zaman ilk öğeyi okumak veya yazmak için bunu kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// cliext_deque_front_item.cpp
// compile with: /clr
#include <cliext/deque>

int main()
    {
    cliext::deque<wchar_t> c1;
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

## <a name="dequegeneric_container-stlclr"></a><a name="generic_container"></a> deque:: generic_container (STL/CLR)

Kapsayıcının genel arabiriminin türü.

### <a name="syntax"></a>Syntax

```cpp
typedef Microsoft::VisualC::StlClr::
    IDeque<generic_value>
    generic_container;
```

### <a name="remarks"></a>Açıklamalar

Tür, bu şablon kapsayıcı sınıfı için genel arabirimi tanımlar.

### <a name="example"></a>Örnek

```cpp
// cliext_deque_generic_container.cpp
// compile with: /clr
#include <cliext/deque>

int main()
    {
    cliext::deque<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct a generic container
    cliext::deque<wchar_t>::generic_container^ gc1 = %c1;
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

## <a name="dequegeneric_iterator-stlclr"></a><a name="generic_iterator"></a> deque:: generic_iterator (STL/CLR)

Kapsayıcı için genel arabirimle birlikte kullanılacak bir yineleyici türü.

### <a name="syntax"></a>Syntax

```cpp
typedef Microsoft::VisualC::StlClr::Generic::
    ContainerRandomAccessIterator<generic_value> generic_iterator;
```

### <a name="remarks"></a>Açıklamalar

Tür, bu şablon kapsayıcı sınıfı için genel arabirim ile kullanılabilen genel bir yineleyiciyi açıklar.

### <a name="example"></a>Örnek

```cpp
// cliext_deque_generic_iterator.cpp
// compile with: /clr
#include <cliext/deque>

int main()
    {
    cliext::deque<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct a generic container
    cliext::deque<wchar_t>::generic_container^ gc1 = %c1;
    for each (wchar_t elem in gc1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // modify generic and display original
    cliext::deque<wchar_t>::generic_iterator gcit = gc1->begin();
    cliext::deque<wchar_t>::generic_value gcval = *gcit;
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

## <a name="dequegeneric_reverse_iterator-stlclr"></a><a name="generic_reverse_iterator"></a> deque:: generic_reverse_iterator (STL/CLR)

Kapsayıcı için genel arabirimle birlikte kullanılacak ters yineleyicinin türü.

### <a name="syntax"></a>Syntax

```cpp
typedef Microsoft::VisualC::StlClr::Generic::
    ReverseRandomAccessIterator<generic_value> generic_reverse_iterator;
```

### <a name="remarks"></a>Açıklamalar

Tür, bu şablon kapsayıcı sınıfı için genel arabirimle birlikte kullanılabilecek bir genel ters yineleyici tanımlar.

### <a name="example"></a>Örnek

```cpp
// cliext_deque_generic_reverse_iterator.cpp
// compile with: /clr
#include <cliext/deque>

int main()
    {
    cliext::deque<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct a generic container
    cliext::deque<wchar_t>::generic_container^ gc1 = %c1;
    for each (wchar_t elem in gc1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // modify generic and display original
    cliext::deque<wchar_t>::generic_reverse_iterator gcit = gc1->rbegin();
    cliext::deque<wchar_t>::generic_value gcval = *gcit;
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

## <a name="dequegeneric_value-stlclr"></a><a name="generic_value"></a> deque:: generic_value (STL/CLR)

Kapsayıcının genel arabirimiyle kullanılacak öğe türü.

### <a name="syntax"></a>Syntax

```cpp
typedef GValue generic_value;
```

### <a name="remarks"></a>Açıklamalar

Tür, `GValue` Bu şablon kapsayıcı sınıfı için genel arabirimle birlikte kullanılacak saklı öğe değerini açıklayan türünde bir nesne tanımlar.

### <a name="example"></a>Örnek

```cpp
// cliext_deque_generic_value.cpp
// compile with: /clr
#include <cliext/deque>

int main()
    {
    cliext::deque<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct a generic container
    cliext::deque<wchar_t>::generic_container^ gc1 = %c1;
    for each (wchar_t elem in gc1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // modify generic and display original
    cliext::deque<wchar_t>::generic_iterator gcit = gc1->begin();
    cliext::deque<wchar_t>::generic_value gcval = *gcit;
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

## <a name="dequeinsert-stlclr"></a><a name="insert"></a> deque:: insert (STL/CLR)

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
// cliext_deque_insert.cpp
// compile with: /clr
#include <cliext/deque>

int main()
    {
    cliext::deque<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // insert a single value using iterator
    cliext::deque<wchar_t>::iterator it = c1.begin();
    System::Console::WriteLine("insert(begin()+1, L'x') = {0}",
        *c1.insert(++it, L'x'));
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // insert a repetition of values
    cliext::deque<wchar_t> c2;
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

## <a name="dequeiterator-stlclr"></a><a name="iterator"></a> deque:: yineleyici (STL/CLR)

Denetlenen dizi için bir yineleyici türü.

### <a name="syntax"></a>Syntax

```cpp
typedef T1 iterator;
```

### <a name="remarks"></a>Açıklamalar

Türü, `T1` denetimli sıra için rastgele erişim Yineleyici işlevi görebilecek belirtilmemiş türdeki bir nesneyi tanımlar.

### <a name="example"></a>Örnek

```cpp
// cliext_deque_iterator.cpp
// compile with: /clr
#include <cliext/deque>

int main()
    {
    cliext::deque<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display contents " a b c"
    cliext::deque<wchar_t>::iterator it = c1.begin();
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

## <a name="dequeoperator-stlclr"></a><a name="op_neq"></a> deque:: operator! = (STL/CLR)

Deque eşit değildir.

### <a name="syntax"></a>Sözdizimi

```cpp
template<typename Value>
    bool operator!=(deque<Value>% left,
        deque<Value>% right);
```

#### <a name="parameters"></a>Parametreler

*tarafta*<br/>
Karşılaştırılacak sol kapsayıcı.

*Right*<br/>
Karşılaştırılacak doğru kapsayıcı.

### <a name="remarks"></a>Açıklamalar

İşleç işlevi döndürülür `!(left == right)` . İki deques öğe öğesine göre karşılaştırıldığı zaman *sola* doğru sıralanmadığını test  etmek için bunu kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// cliext_deque_operator_ne.cpp
// compile with: /clr
#include <cliext/deque>

int main()
    {
    cliext::deque<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // assign to a new container
    cliext::deque<wchar_t> c2;
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

## <a name="dequeoperatorstlclr"></a><a name="operator"></a> deque:: operator (STL/CLR)

Belirtilen konumdaki bir öğeye erişir.

### <a name="syntax"></a>Sözdizimi

```cpp
reference operator[](size_type pos);
```

#### <a name="parameters"></a>Parametreler

*'un*<br/>
Erişim için öğenin konumu.

### <a name="remarks"></a>Açıklamalar

Member işleci, *POS* konumundaki öğesine bir referene döndürür. Bu, konumunu bildiğiniz bir öğeye erişmek için kullanılır.

### <a name="example"></a>Örnek

```cpp
// cliext_deque_operator_sub.cpp
// compile with: /clr
#include <cliext/deque>

int main()
    {
    cliext::deque<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display contents " a b c" using subscripting
    for (int i = 0; i < c1.size(); ++i)
        System::Console::Write("{0} ", c1[i]);
    System::Console::WriteLine();

    // change an entry and redisplay
    c1[1] = L'x';
    for (int i = 0; i < c1.size(); ++i)
        System::Console::Write("{0} ", c1[i]);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
a x c
```

## <a name="dequepop_back-stlclr"></a><a name="pop_back"></a> deque::p op_back (STL/CLR)

Son öğeyi kaldırır.

### <a name="syntax"></a>Syntax

```cpp
void pop_back();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, denetimli sıranın son öğesini kaldırır ve bu boş olmamalıdır. Bunu, arka arkaya bir öğe ile kısaltmak için kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// cliext_deque_pop_back.cpp
// compile with: /clr
#include <cliext/deque>

int main()
    {
    cliext::deque<wchar_t> c1;
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

## <a name="dequepop_front-stlclr"></a><a name="pop_front"></a> deque::p op_front (STL/CLR)

İlk öğeyi kaldırır.

### <a name="syntax"></a>Syntax

```cpp
void pop_front();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, denetimli dizinin ilk öğesini kaldırır ve boş olmamalıdır. Önünde bir öğe ile en baştan ayırmayı kısaltmak için bunu kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// cliext_deque_pop_front.cpp
// compile with: /clr
#include <cliext/deque>

int main()
    {
    cliext::deque<wchar_t> c1;
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

## <a name="dequepush_back-stlclr"></a><a name="push_back"></a> deque::p ush_back (STL/CLR)

Yeni bir son öğe ekler.

### <a name="syntax"></a>Syntax

```cpp
void push_back(value_type val);
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi denetlenen sıranın sonunda değeri olan bir öğe ekler `val` . Bu öğeyi başka bir öğe eklemek için kullanabilirsiniz.

### <a name="example"></a>Örnek

```cpp
// cliext_deque_push_back.cpp
// compile with: /clr
#include <cliext/deque>

int main()
    {
    cliext::deque<wchar_t> c1;
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

## <a name="dequepush_front-stlclr"></a><a name="push_front"></a> deque::p ush_front (STL/CLR)

Yeni bir ilk öğe ekler.

### <a name="syntax"></a>Syntax

```cpp
void push_front(value_type val);
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi denetlenen sıranın başlangıcında değeri olan bir öğe ekler `val` . Başka bir öğeyi daha sonuna eklemek için bunu kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// cliext_deque_push_front.cpp
// compile with: /clr
#include <cliext/deque>

int main()
    {
    cliext::deque<wchar_t> c1;
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

## <a name="dequerbegin-stlclr"></a><a name="rbegin"></a> deque:: rbegin (STL/CLR)

Ters denetlenen sıranın başlangıcını belirtir.

### <a name="syntax"></a>Syntax

```cpp
reverse_iterator rbegin();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, denetimli sıranın son öğesini veya boş bir dizinin başlangıcının ötesinde bir ters yineleyici döndürür. Bu nedenle, `beginning` ters sıranın öğesini belirler. Doğru sırada görülen denetimli sıranın başlangıcını atayan bir yineleyici elde etmek için bunu kullanırsınız `current` , ancak denetlenen sıranın uzunluğu değişirse durum değişebilir.

### <a name="example"></a>Örnek

```cpp
// cliext_deque_rbegin.cpp
// compile with: /clr
#include <cliext/deque>

int main()
    {
    cliext::deque<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // inspect first two items in reversed sequence
    cliext::deque<wchar_t>::reverse_iterator rit = c1.rbegin();
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

## <a name="dequereference-stlclr"></a><a name="reference"></a> deque:: Reference (STL/CLR)

Bir öğe için bir başvuru türü.

### <a name="syntax"></a>Syntax

```cpp
typedef value_type% reference;
```

### <a name="remarks"></a>Açıklamalar

Türü bir öğesi başvurusunu tanımlar.

### <a name="example"></a>Örnek

```cpp
// cliext_deque_reference.cpp
// compile with: /clr
#include <cliext/deque>

int main()
    {
    cliext::deque<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display initial contents " a b c"
    cliext::deque<wchar_t>::iterator it = c1.begin();
    for (; it != c1.end(); ++it)
        {   // get a reference to an element
        cliext::deque<wchar_t>::reference ref = *it;
        System::Console::Write("{0} ", ref);
        }
    System::Console::WriteLine();

    // modify contents " a b c"
    for (it = c1.begin(); it != c1.end(); ++it)
        {   // get a reference to an element
        cliext::deque<wchar_t>::reference ref = *it;

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

## <a name="dequerend-stlclr"></a><a name="rend"></a> deque:: rend (STL/CLR)

Ters denetlenen sıranın sonunu belirtir.

### <a name="syntax"></a>Syntax

```cpp
reverse_iterator rend();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, denetimli sıranın başlangıcının hemen ötesinde bir ters yineleyici döndürür. Bu nedenle, `end` ters sıranın öğesini belirler. Bu uygulamayı, `current` geriye doğru sırada görülen denetlenen sıranın sonunu atayan bir yineleyici elde etmek için kullanırsınız, ancak denetlenen sıranın uzunluğu değişirse durum değişebilir.

### <a name="example"></a>Örnek

```cpp
// cliext_deque_rend.cpp
// compile with: /clr
#include <cliext/deque>

int main()
    {
    cliext::deque<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // inspect first two items
    cliext::deque<wchar_t>::reverse_iterator rit = c1.rend();
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

## <a name="dequeresize-stlclr"></a><a name="resize"></a> deque:: Resize (STL/CLR)

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

Üye işlevleri, [deque:: size (STL/CLR)](#size) `()` henceileri 'nin *new_size* döndürdüğünden emin olun. Denetlenen diziyi daha uzun hale getirmek gerekiyorsa, ilk üye işlevi değeri olan öğeleri ekler `value_type()` ; İkinci üye işlevi ise değer *Val* ile öğeleri ekler. Denetimli diziyi daha kısa hale getirmek için, her iki üye işlevi son öğe [deque:: size (STL/CLR)](#size) zamanlarını etkin bir şekilde siler `() -` `new_size` . Kontrol edilen sıranın boyut *new_size* sahip olduğundan emin olmak için, geçerli denetimli diziyi kırparak veya doldurmaya göre kullanabilirsiniz.

### <a name="example"></a>Örnek

```cpp
// cliext_deque_resize.cpp
// compile with: /clr
#include <cliext/deque>

int main()
    {
// construct an empty container and pad with default values
    cliext::deque<wchar_t> c1;
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

## <a name="dequereverse_iterator-stlclr"></a><a name="reverse_iterator"></a> deque:: reverse_iterator (STL/CLR)

Denetlenen sıra için ters yineleyicinin türü.

### <a name="syntax"></a>Syntax

```cpp
typedef T3 reverse_iterator;
```

### <a name="remarks"></a>Açıklamalar

Tür, `T3` denetlenen sıra için ters Yineleyici olarak işlev görebilecek belirtilmemiş türdeki bir nesneyi tanımlar.

### <a name="example"></a>Örnek

```cpp
// cliext_deque_reverse_iterator.cpp
// compile with: /clr
#include <cliext/deque>

int main()
    {
    cliext::deque<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display contents " a b c" reversed
    cliext::deque<wchar_t>::reverse_iterator rit = c1.rbegin();
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

## <a name="dequesize-stlclr"></a><a name="size"></a> deque:: size (STL/CLR)

Öğe sayısını sayar.

### <a name="syntax"></a>Syntax

```cpp
size_type size();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi denetlenen sıranın uzunluğunu döndürür. Bu, şu anda denetlenen dizideki öğelerin sayısını tespit etmek için kullanılır. Her şey için, sıranın sıfır dışında bir boyuta sahip olup olmadığı, bkz. [deque:: Empty (STL/CLR)](#empty) `()` .

### <a name="example"></a>Örnek

```cpp
// cliext_deque_size.cpp
// compile with: /clr
#include <cliext/deque>

int main()
    {
    cliext::deque<wchar_t> c1;
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

## <a name="dequesize_type-stlclr"></a><a name="size_type"></a> deque:: size_type (STL/CLR)

İki öğe arasındaki işaretli bir mesafe türü.

### <a name="syntax"></a>Syntax

```cpp
typedef int size_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, negatif olmayan bir öğe sayısını tanımlar.

### <a name="example"></a>Örnek

```cpp
// cliext_deque_size_type.cpp
// compile with: /clr
#include <cliext/deque>

int main()
    {
    cliext::deque<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // compute positive difference
    cliext::deque<wchar_t>::size_type diff = c1.end() - c1.begin();
    System::Console::WriteLine("end()-begin() = {0}", diff);
    return (0);
    }
```

```Output
a b c
end()-begin() = 3
```

## <a name="dequeswap-stlclr"></a><a name="swap"></a> deque:: swap (STL/CLR)

İki kapsayıcının içeriğinin yerini değiştirir.

### <a name="syntax"></a>Sözdizimi

```cpp
void swap(deque<Value>% right);
```

#### <a name="parameters"></a>Parametreler

*Right*<br/>
İçeriği takas eden kapsayıcı.

### <a name="remarks"></a>Açıklamalar

Üye işlevi, ve sağ arasındaki denetlenen dizileri **`*this`** değiştirir . Bu, sabit zamanlı olarak yapar ve özel durum oluşturmaz. Bunu iki kapsayıcının içeriğini değiş tokuş etmek için hızlı bir yol olarak kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// cliext_deque_swap.cpp
// compile with: /clr
#include <cliext/deque>

int main()
    {
    cliext::deque<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct another container with repetition of values
    cliext::deque<wchar_t> c2(5, L'x');
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

## <a name="dequeto_array-stlclr"></a><a name="to_array"></a> deque:: to_array (STL/CLR)

Denetimli sırayı yeni bir diziye kopyalar.

### <a name="syntax"></a>Syntax

```cpp
cli::array<Value>^ to_array();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi denetlenen sırayı içeren bir dizi döndürür. Dizi biçiminde denetlenen sıranın bir kopyasını almak için bunu kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// cliext_deque_to_array.cpp
// compile with: /clr
#include <cliext/deque>

int main()
    {
    cliext::deque<wchar_t> c1;
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

## <a name="dequevalue_type-stlclr"></a><a name="value_type"></a> deque:: value_type (STL/CLR)

Öğenin türü.

### <a name="syntax"></a>Syntax

```cpp
typedef Value value_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, şablon parametre *değeri* için bir eş anlamlı.

### <a name="example"></a>Örnek

```cpp
// cliext_deque_value_type.cpp
// compile with: /clr
#include <cliext/deque>

int main()
    {
    cliext::deque<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display contents " a b c" using value_type
    for (cliext::deque<wchar_t>::iterator it = c1.begin();
        it != c1.end(); ++it)
        {   // store element in value_type object
        cliext::deque<wchar_t>::value_type val = *it;

        System::Console::Write("{0} ", val);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="operatorlt-deque-stlclr"></a><a name="op_lt"></a> işleç &lt; (deque) (STL/CLR)

Karşılaştırmadan daha az.

### <a name="syntax"></a>Sözdizimi

```cpp
template<typename Value>
    bool operator<(deque<Value>% left,
        deque<Value>% right);
```

#### <a name="parameters"></a>Parametreler

*tarafta*<br/>
Karşılaştırılacak sol kapsayıcı.

*Right*<br/>
Karşılaştırılacak doğru kapsayıcı.

### <a name="remarks"></a>Açıklamalar

İşleç işlevi, `i` `!(right[i] < left[i])` bunun da doğru olduğu en düşük konum için true değerini döndürür `left[i] < right[i]` . Aksi takdirde, `left->size() < right->size()` iki deques öğe öğesine göre karşılaştırıldığı zaman, *sol taraftaki sola* *doğru* sıralı olup olmadığını test etmek için bunu kullanır.

### <a name="example"></a>Örnek

```cpp
// cliext_deque_operator_lt.cpp
// compile with: /clr
#include <cliext/deque>

int main()
    {
    cliext::deque<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // assign to a new container
    cliext::deque<wchar_t> c2;
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

## <a name="operatorlt-deque-stlclr"></a><a name="op_lteq"></a> operator &lt; = (deque) (STL/CLR)

Deque küçüktür veya eşittir karşılaştırması.

### <a name="syntax"></a>Sözdizimi

```cpp
template<typename Value>
    bool operator<=(deque<Value>% left,
        deque<Value>% right);
```

#### <a name="parameters"></a>Parametreler

*tarafta*<br/>
Karşılaştırılacak sol kapsayıcı.

*Right*<br/>
Karşılaştırılacak doğru kapsayıcı.

### <a name="remarks"></a>Açıklamalar

İşleç işlevi döndürülür `!(right < left)` . İki deques öğe öğesine göre karşılaştırıldığı zaman *sağdan* *sola* doğru sıralanmadığını test etmek için bunu kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// cliext_deque_operator_le.cpp
// compile with: /clr
#include <cliext/deque>

int main()
    {
    cliext::deque<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // assign to a new container
    cliext::deque<wchar_t> c2;
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

## <a name="operator-deque-stlclr"></a><a name="op_as"></a> operator = (deque) (STL/CLR)

Denetlenen sırayı değiştirir.

### <a name="syntax"></a>Sözdizimi

```cpp
deque<Value>% operator=(deque<Value>% right);
```

#### <a name="parameters"></a>Parametreler

*Right*<br/>
Kopyalanacak kapsayıcı.

### <a name="remarks"></a>Açıklamalar

Üye işleci nesnesine *sağ* kopyalar ve ardından döndürür **`*this`** . Denetlenen diziyi, denetimli sıranın bir kopyasıyla değiştirmek için bunu *kullanırsınız.*

### <a name="example"></a>Örnek

```cpp
// cliext_deque_operator_as.cpp
// compile with: /clr
#include <cliext/deque>

int main()
    {
    cliext::deque<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // assign to a new container
    cliext::deque<wchar_t> c2;
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

## <a name="operator-deque-stlclr"></a><a name="op_eq"></a> operator = = (deque) (STL/CLR)

Deque eşittir karşılaştırması.

### <a name="syntax"></a>Sözdizimi

```cpp
template<typename Value>
    bool operator==(deque<Value>% left,
        deque<Value>% right);
```

#### <a name="parameters"></a>Parametreler

*tarafta*<br/>
Karşılaştırılacak sol kapsayıcı.

*Right*<br/>
Karşılaştırılacak doğru kapsayıcı.

### <a name="remarks"></a>Açıklamalar

İşleç işlevi yalnızca *sol* ve *sağ* tarafından denetlenen diziler aynı uzunlukta ve her bir konum için aynı uzunluğa sahip olursa true değerini döndürür `i` `left[i] ==` `right[i]` . İki deques öğe öğesine göre karşılaştırıldığı zaman *solinin* *doğru* olup olmadığını test etmek için bunu kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// cliext_deque_operator_eq.cpp
// compile with: /clr
#include <cliext/deque>

int main()
    {
    cliext::deque<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // assign to a new container
    cliext::deque<wchar_t> c2;
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

## <a name="operatorgt-deque-stlclr"></a><a name="op_gt"></a> işleç &gt; (deque) (STL/CLR)

Karşılaştırmadan daha büyük.

### <a name="syntax"></a>Sözdizimi

```cpp
template<typename Value>
    bool operator>(deque<Value>% left,
        deque<Value>% right);
```

#### <a name="parameters"></a>Parametreler

*tarafta*<br/>
Karşılaştırılacak sol kapsayıcı.

*Right*<br/>
Karşılaştırılacak doğru kapsayıcı.

### <a name="remarks"></a>Açıklamalar

İşleç işlevi döndürülür `right` `<` `left` . İki deques öğe öğesine göre karşılaştırıldığı zaman, *sol* *taraftaki bir* değer olup olmadığını test etmek için bunu kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// cliext_deque_operator_gt.cpp
// compile with: /clr
#include <cliext/deque>

int main()
    {
    cliext::deque<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // assign to a new container
    cliext::deque<wchar_t> c2;
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

## <a name="operatorgt-deque-stlclr"></a><a name="op_gteq"></a> operator &gt; = (deque) (STL/CLR)

Deque veya eşittir karşılaştırması.

### <a name="syntax"></a>Sözdizimi

```cpp
template<typename Value>
    bool operator>=(deque<Value>% left,
        deque<Value>% right);
```

#### <a name="parameters"></a>Parametreler

*tarafta*<br/>
Karşılaştırılacak sol kapsayıcı.

*Right*<br/>
Karşılaştırılacak doğru kapsayıcı.

### <a name="remarks"></a>Açıklamalar

İşleç işlevi döndürülür `!(left` `<` `right)` . İki deques öğe öğesine göre karşılaştırıldığı zaman *sağdan* *sola* doğru sıralanmadığını test etmek için bunu kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// cliext_deque_operator_ge.cpp
// compile with: /clr
#include <cliext/deque>

int main()
    {
    cliext::deque<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // assign to a new container
    cliext::deque<wchar_t> c2;
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
