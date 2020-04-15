---
title: vektör (STL/CLR)
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- cliext::vector
- cliext::vector::assign
- cliext::vector::at
- cliext::vector::back
- cliext::vector::back_item
- cliext::vector::begin
- cliext::vector::capacity
- cliext::vector::clear
- cliext::vector::const_iterator
- cliext::vector::const_reference
- cliext::vector::const_reverse_iterator
- cliext::vector::difference_type
- cliext::vector::empty
- cliext::vector::end
- cliext::vector::erase
- cliext::vector::front
- cliext::vector::front_item
- cliext::vector::generic_container
- cliext::vector::generic_iterator
- cliext::vector::generic_reverse_iterator
- cliext::vector::generic_value
- cliext::vector::insert
- cliext::vector::iterator
- cliext::vector::operator=
- cliext::vector::operator
- cliext::vector::pop_back
- cliext::vector::push_back
- cliext::vector::rbegin
- cliext::vector::reference
- cliext::vector::rend
- cliext::vector::reserve
- cliext::vector::resize
- cliext::vector::reverse_iterator
- cliext::vector::size
- cliext::vector::size_type
- cliext::vector::swap
- cliext::vector::to_array
- cliext::vector::value_type
- cliext::vector::vector
helpviewer_keywords:
- vector class [STL/CLR]
- <cliext/vector> header [STL/CLR]
- <vector> header [STL/CLR]
- operator!= member [STL/CLR]
- operator< member [STL/CLR]
- operator<= member [STL/CLR]
- operator== member [STL/CLR]
- operator> (vector) member [STL/CLR]
- operator>= member [STL/CLR]
- assign member [STL/CLR]
- at member [STL/CLR]
- back member [STL/CLR]
- back_item member [STL/CLR]
- begin member [STL/CLR]
- capacity member [STL/CLR]
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
- operator= member [STL/CLR]
- operator member [STL/CLR]
- pop_back member [STL/CLR]
- push_back member [STL/CLR]
- rbegin member [STL/CLR]
- reference member [STL/CLR]
- rend member [STL/CLR]
- reserve member [STL/CLR]
- resize member [STL/CLR]
- reverse_iterator member [STL/CLR]
- size member [STL/CLR]
- size_type member [STL/CLR]
- swap member [STL/CLR]
- to_array member [STL/CLR]
- value_type member [STL/CLR]
- vector member [STL/CLR]
ms.assetid: f90060d5-097a-4e9d-9a26-a634b5b9c6c2
ms.openlocfilehash: c6a001797e90bd7381358abb16612926442e8d9f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371829"
---
# <a name="vector-stlclr"></a>vektör (STL/CLR)

Şablon sınıfı, rasgele erişimi olan öğelerin değişen uzunluktaki dizisini kontrol eden bir nesneyi açıklar. Kapsayıcıyı, `vector` bitişik bir depolama bloğu olarak bir öğe dizisini yönetmek için kullanırsınız. Blok, isteğe bağlı olarak büyüyen bir dizi olarak uygulanır.

Aşağıdaki açıklamada, `GValue` ikincisi bir ref türü olmadığı sürece *Değer* ile aynıdır, `Value^`bu durumda .

## <a name="syntax"></a>Sözdizimi

```cpp
template<typename Value>
    ref class vector
        :   public
        System::ICloneable,
        System::Collections::IEnumerable,
        System::Collections::ICollection,
        System::Collections::Generic::IEnumerable<GValue>,
        System::Collections::Generic::ICollection<GValue>,
        System::Collections::Generic::IList<GValue>,
        Microsoft::VisualC::StlClr::IVector<GValue>
    { ..... };
```

### <a name="parameters"></a>Parametreler

*Değer*<br/>
Denetlenen sıradaki öğenin türü.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** \<cliext/vektör>

**Ad alanı:** cliext

## <a name="declarations"></a>Bildirimler

|Tür Tanımlaması|Açıklama|
|---------------------|-----------------|
|[vector::const_iterator (STL/CLR)](#const_iterator)|Denetlenen dizi için bir sabit yineleyici türü.|
|[vector::const_reference (STL/CLR)](#const_reference)|Bir öğe için sabit bir başvuru türü.|
|[vector::const_reverse_iterator (STL/CLR)](#const_reverse_iterator)|Denetlenmeyen dizi için sabit bir ters yineleyici türü.|
|[vector::difference_type (STL/CLR)](#difference_type)|İki öğe arasındaki işaretli mesafenin türü.|
|[vector::generic_container (STL/CLR)](#generic_container)|Kapsayıcı için genel arabirimin türü.|
|[vector::generic_iterator (STL/CLR)](#generic_iterator)|Kapsayıcının genel arabirimi için bir yineleyici türü.|
|[vector::generic_reverse_iterator (STL/CLR)](#generic_reverse_iterator)|Kapsayıcının genel arabirimi için ters yineleyici türü.|
|[vector::generic_value (STL/CLR)](#generic_value)|Kapsayıcı için genel arabirim için bir öğetürü.|
|[vector::iterator (STL/CLR)](#iterator)|Denetlenen dizi için bir yineleyici türü.|
|[vector::reference (STL/CLR)](#reference)|Bir öğe için bir başvuru türü.|
|[vector::reverse_iterator (STL/CLR)](#reverse_iterator)|Denetlenen dizi için ters yineleyici türü.|
|[vector::size_type (STL/CLR)](#size_type)|İki öğe arasındaki işaretli mesafenin türü.|
|[vector::value_type (STL/CLR)](#value_type)|Öğenin türü.|

|Üye İşlevi|Açıklama|
|---------------------|-----------------|
|[vector::assign (STL/CLR)](#assign)|Tüm öğeleri değiştirir.|
|[vector::at (STL/CLR)](#at)|Belirli bir konumda bir öğeye erişir.|
|[vector::back (STL/CLR)](#back)|Son öğeye erişir.|
|[vector::begin (STL/CLR)](#begin)|Denetlenen dizinin başlangıcını belirtir.|
|[vector::capacity (STL/CLR)](#capacity)|Kapsayıcı için ayrılan depolama alanının boyutunu raporlar.|
|[vector::clear (STL/CLR)](#clear)|Tüm öğeleri kaldırır.|
|[vector::empty (STL/CLR)](#empty)|Bir öğe olup olmadığını sınar.|
|[vector::end (STL/CLR)](#end)|Denetlenen dizinin bitişini belirtir.|
|[vector::erase (STL/CLR)](#erase)|Belirtilen konumlardaki öğeleri kaldırır.|
|[vector::front (STL/CLR)](#front)|İlk öğeye erişir.|
|[vector::insert (STL/CLR)](#insert)|Belirli bir konumda öğeleri ekler.|
|[vector::pop_back (STL/CLR)](#pop_back)|Son öğeyi kaldırır.|
|[vector::push_back (STL/CLR)](#push_back)|Yeni bir son öğe ekler.|
|[vector::rbegin (STL/CLR)](#rbegin)|Ters denetimli dizinin başlangıcını belirler.|
|[vector::rend (STL/CLR)](#rend)|Ters denetimli dizinin sonunu belirler.|
|[vector::reserve (STL/CLR)](#reserve)|Konteyner için minimum büyüme kapasitesi sağlar.|
|[vector::resize (STL/CLR)](#resize)|Öğelerin sayısını değiştirir.|
|[vector::size (STL/CLR)](#size)|Öğe sayısını sayar.|
|[vector::swap (STL/CLR)](#swap)|İki kapsayıcının içeriğinin yerini değiştirir.|
|[vector::to_array (STL/CLR)](#to_array)|Denetedilen sırayı yeni bir diziye kopyalar.|
|[vector::vector (STL/CLR)](#vector)|Bir kapsayıcı nesnesi oluşturur.|

|Özellik|Açıklama|
|--------------|-----------------|
|[vector::back_item (STL/CLR)](#back_item)|Son öğeye erişir.|
|[vector::front_item (STL/CLR)](#front_item)|İlk öğeye erişir.|

|İşleç|Açıklama|
|--------------|-----------------|
|[vector::operator= (STL/CLR)](#op_as)|Denetedilen sırayı değiştirir.|
|[vector::operator(STL/CLR)](#op)|Belirli bir konumda bir öğeye erişir.|
|[işleç!= (vektör) (STL/CLR)](#op_neq)|Bir nesnenin `vector` başka `vector` bir nesneye eşit olup olmadığını belirler.|
|[operatör< (vektör) (STL/CLR)](#op_lt)|Bir nesnenin `vector` başka `vector` bir nesneden küçük olup olmadığını belirler.|
|[işleç<= (vektör) (STL/CLR)](#op_lteq)|Bir nesnenin `vector` başka `vector` bir nesneden küçük veya eşit olup olmadığını belirler.|
|[işleç== (vektör) (STL/CLR)](#op_eq)|Bir nesnenin `vector` başka `vector` bir nesneye eşit olup olmadığını belirler.|
|[operator> (vector) (STL/CLR)](#op_gt)|Bir nesnenin `vector` başka `vector` bir nesneden büyük olup olmadığını belirler.|
|[işleç>= (vektör) (STL/CLR)](#op_gteq)|Bir nesnenin `vector` başka `vector` bir nesneden büyük mü yoksa eşit mi olduğunu belirler.|

## <a name="interfaces"></a>Arabirimler

|Arabirim|Açıklama|
|---------------|-----------------|
|<xref:System.ICloneable>|Bir nesneyi çoğaltma.|
|<xref:System.Collections.IEnumerable>|Elementler arasında sırala.|
|<xref:System.Collections.ICollection>|Elementler grubunu koruyun.|
|<xref:System.Collections.Generic.IEnumerable%601>|Yazılan öğeler arasında sıralanır.|
|<xref:System.Collections.Generic.ICollection%601>|Yazılan öğelergrubunu koruyun.|
|<xref:System.Collections.Generic.IList%601>|Sıralı daktilan öğeler grubunu koruyun.|
|IVector<Değeri\>|Genel kapsayıcıyı koruyun.|

## <a name="remarks"></a>Açıklamalar

Nesne, talep üzerine büyüyen depolanmış değer *öğeleri* dizisi aracılığıyla denetlediği dizi için depolama yı ayırır ve boşaltır. Büyüme, yeni bir öğeyi ekleyen maliyetin amortismana tabi sabit zaman olduğu şekilde gerçekleşir. Başka bir deyişle, denetlenen dizinin uzunluğu büyüdükçe, sonunda öğeleri ekleme maliyeti ortalama olarak artmaz. Böylece, bir vektör şablon sınıf [yığını (STL/CLR)](../dotnet/stack-stl-clr.md)için temel kapsayıcı için iyi bir adaydır.

Rasgele `vector` erişim yineleyicilerini destekler, bu da ilk (ön) öğe için sıfırdan son (arka) öğeye doğru sayan sayısal konumunu doğrudan veren bir öğeye `size() - 1` başvurabileceğiniz anlamına gelir. Ayrıca, bir vektörşablon sınıfı [priority_queue (STL/CLR)](../dotnet/priority-queue-stl-clr.md)için altta yatan kapsayıcı için iyi bir aday olduğu anlamına gelir.

Vektör yineleyici, bir sapı, belirlediği öğenin yanlılığıyla birlikte ilişkili vektör nesnesine depolar. Yineleyicileri yalnızca ilişkili kapsayıcı nesneleri ile kullanabilirsiniz. Bir vektör elemanının yanlılığı konumuyla aynıdır.

Öğeleri ekleme veya silerek belirli bir konumda depolanan öğe değerini değiştirebilir, böylece bir yineleyici tarafından belirlenen değer de değişebilir. (Kapsayıcı, eklemeden önce bir delik oluşturmak veya bir silmeden sonra bir deliği doldurmak için öğeleri yukarı veya aşağı kopyalamak zorunda kalabilir.) Yine de, bir vektör yineleyici, önyargı aralığında `[0, size()]`olduğu sürece geçerli kalır. Dahası, geçerli bir yineleyici dereferencable kalır - erişmek veya belirlediği öğe değerini değiştirmek için `size()`kullanabilirsiniz - sürece onun önyargı eşit değildir .

Bir öğeyi silme veya kaldırma, depolanan değeri için yıkıcı çağırır. Kapsayıcıyı yok etmek tüm öğeleri siler. Böylece, eleman türü ref sınıfı olan bir kapsayıcı, hiçbir öğenin kapsayıcıdan daha uzun yaşamamasını sağlar. Ancak, bir tutamaçların kapsayıcısının öğelerini yok etmediğini unutmayın.

## <a name="members"></a>Üyeler

## <a name="vectorassign-stlclr"></a><a name="assign"></a>vektör::atama (STL/CLR)

Tüm öğeleri değiştirir.

### <a name="syntax"></a>Sözdizimi

```cpp
void assign(size_type count, value_type val);
template<typename InIt>
    void assign(InIt first, InIt last);
void assign(System::Collections::Generic::IEnumerable<Value>^ right);
```

#### <a name="parameters"></a>Parametreler

*Sayısı*<br/>
Eklenecek öğe sayısı.

*Ilk*<br/>
Eklemek için aralığın başlangıcı.

*Son*<br/>
Eklenecek aralık sonu.

*Doğru*<br/>
Ekleme için numaralandırma.

*Val*<br/>
Eklenecek öğenin değeri.

### <a name="remarks"></a>Açıklamalar

İlk üye işlev, denetlenen sırayı değer *val'in* *sayı* elemanlarının tekrarı ile değiştirir. Kapsayıcıyı aynı değere sahip öğelerle doldurmak için kullanırsınız.

Tamsayı `InIt` türü ise, ikinci üye işlev `assign((size_type)first, (value_type)last)`. Aksi takdirde, kontrollü sırayı diziile`first` `last`değiştirir [ , ). Bunu, denetitilen sırayı başka bir diziyi kopyalamak için kullanırsınız.

Üçüncü üye işlev, kontrol edilen sıranın yerine, enumeratör *ünsağında*atanan diziyi alır. Bunu, denetite edilen sırayı bir sayıcı tarafından açıklanan bir dizinin kopyası yapmak için kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// cliext_vector_assign.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// assign a repetition of values
    cliext::vector<wchar_t> c2;
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

## <a name="vectorat-stlclr"></a><a name="at"></a>vektör::at (STL/CLR)

Belirli bir konumda bir öğeye erişir.

### <a name="syntax"></a>Sözdizimi

```cpp
reference at(size_type pos);
```

#### <a name="parameters"></a>Parametreler

*Pos*<br/>
Öğenin erişim konumu.

### <a name="remarks"></a>Açıklamalar

Üye *işlev,* konum pos'undaki kontrollü dizinin öğesine bir başvuru döndürür. Konumunu bildiğiniz bir öğeyi okumak veya yazmak için kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// cliext_vector_at.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
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

## <a name="vectorback-stlclr"></a><a name="back"></a>vektör::geri (STL/CLR)

Son öğeye erişir.

### <a name="syntax"></a>Sözdizimi

```cpp
reference back();
```

### <a name="remarks"></a>Açıklamalar

Üye işlev, boş olmayan kontrollü dizinin son öğesine bir başvuru döndürür. Var olduğunu bildiğinizde, son öğeye erişmek için kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// cliext_vector_back.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
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

## <a name="vectorback_item-stlclr"></a><a name="back_item"></a>vektör::back_item (STL/CLR)

Son öğeye erişir.

### <a name="syntax"></a>Sözdizimi

```cpp
property value_type back_item;
```

### <a name="remarks"></a>Açıklamalar

Özellik, boş olmayan olması gereken denetimli dizinin son öğesine erişer. Var olduğunu bildiğinizde, son öğeyi okumak veya yazmak için kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// cliext_vector_back_item.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
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

## <a name="vectorbegin-stlclr"></a><a name="begin"></a>vektör::begin (STL/CLR)

Denetlenen dizinin başlangıcını belirtir.

### <a name="syntax"></a>Sözdizimi

```cpp
iterator begin();
```

### <a name="remarks"></a>Açıklamalar

Üye işlev, denetlenen dizinin ilk öğesini veya boş bir dizinin sonunun hemen ötesini belirleyen rasgele erişim yinelemesini döndürür. Bunu, denetlenen dizinin başlangıcını `current` belirleyen bir yineleyici elde etmek için kullanırsınız, ancak denetlenen dizinin uzunluğu değişirse durumu değişebilir.

### <a name="example"></a>Örnek

```cpp
// cliext_vector_begin.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// inspect first two items
    cliext::vector<wchar_t>::iterator it = c1.begin();
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

## <a name="vectorcapacity-stlclr"></a><a name="capacity"></a>vektör::kapasite (STL/CLR)

Kapsayıcı için ayrılan depolama alanının boyutunu raporlar.

### <a name="syntax"></a>Sözdizimi

```cpp
size_type capacity();
```

### <a name="remarks"></a>Açıklamalar

Üye işlev, en az [vektör::boyut (STL/CLR)](../dotnet/vector-size-stl-clr.md)`()`kadar büyük bir değer olan, şu anda denetlenen sırayı tutmak için ayrılan depolamayı döndürür. Denetimli sıra için depolama alanı yeniden tahsis etmek gerekir önce kapsayıcı büyüyebilir ne kadar belirlemek için kullanabilirsiniz.

### <a name="example"></a>Örnek

```cpp
// cliext_vector_capacity.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display initial contents " a b c"
    for (int i = 0; i < c1.size(); ++i)
        System::Console::Write("{0} ", c1.at(i));
    System::Console::WriteLine();

// increase capacity
    cliext::vector<wchar_t>::size_type cap = c1.capacity();
    System::Console::WriteLine("capacity() = {0}, ok = {1}",
        cap, c1.size() <= cap);
    c1.reserve(cap + 5);
    System::Console::WriteLine("capacity() = {0}, ok = {1}",
        c1.capacity(), cap + 5 <= c1.capacity());
    return (0);
    }
```

```Output
a b c
capacity() = 4, ok = True
capacity() = 9, ok = True
```

## <a name="vectorclear-stlclr"></a><a name="clear"></a>vektör::net (STL/CLR)

Tüm öğeleri kaldırır.

### <a name="syntax"></a>Sözdizimi

```cpp
void clear();
```

### <a name="remarks"></a>Açıklamalar

Üye işlev etkili bir şekilde [vektör çağırır::sil (STL/CLR)](../dotnet/vector-erase-stl-clr.md) `(` [vektör::begin (STL/CLR)](../dotnet/vector-begin-stl-clr.md) `(),` [vektör::end (STL/CLR)](../dotnet/vector-end-stl-clr.md)`())`. Denetlenen dizinin boş olduğundan emin olmak için kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// cliext_vector_clear.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
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

## <a name="vectorconst_iterator-stlclr"></a><a name="const_iterator"></a>vektör::const_iterator (STL/CLR)

Denetlenen dizi için bir sabit yineleyici türü.

### <a name="syntax"></a>Sözdizimi

```cpp
typedef T2 const_iterator;
```

### <a name="remarks"></a>Açıklamalar

Tür, denetlenen dizi `T2` için sabit bir rasgele erişim yineleyici olarak hizmet verebilir belirtilmemiş türünde bir nesne açıklar.

### <a name="example"></a>Örnek

```cpp
// cliext_vector_const_iterator.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display contents " a b c"
    cliext::vector<wchar_t>::const_iterator cit = c1.begin();
    for (; cit != c1.end(); ++cit)
        System::Console::Write("{0} ", *cit);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="vectorconst_reference-stlclr"></a><a name="const_reference"></a>vektör::const_reference (STL/CLR)

Bir öğe için sabit bir başvuru türü.

### <a name="syntax"></a>Sözdizimi

```cpp
typedef value_type% const_reference;
```

### <a name="remarks"></a>Açıklamalar

Tür, bir öğeye sabit bir başvuru açıklar.

### <a name="example"></a>Örnek

```cpp
// cliext_vector_const_reference.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display initial contents " a b c"
    cliext::vector<wchar_t>::const_iterator cit = c1.begin();
    for (; cit != c1.end(); ++cit)
        {   // get a const reference to an element
        cliext::vector<wchar_t>::const_reference cref = *cit;
        System::Console::Write("{0} ", cref);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="vectorconst_reverse_iterator-stlclr"></a><a name="const_reverse_iterator"></a>vektör::const_reverse_iterator (STL/CLR)

Denetlenmeyen dizi için sabit bir ters yineleyici türü...

### <a name="syntax"></a>Sözdizimi

```cpp
typedef T4 const_reverse_iterator;
```

### <a name="remarks"></a>Açıklamalar

Tür, denetlenen dizi `T4` için sabit bir ters yineleyici olarak hizmet verebilen belirtilmemiş türde bir nesneyi açıklar.

### <a name="example"></a>Örnek

```cpp
// cliext_vector_const_reverse_iterator.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display contents " a b c" reversed
    cliext::vector<wchar_t>::const_reverse_iterator crit = c1.rbegin();
    cliext::vector<wchar_t>::const_reverse_iterator crend = c1.rend();
    for (; crit != crend; ++crit)
        System::Console::Write("{0} ", *crit);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
c b a
```

## <a name="vectordifference_type-stlclr"></a><a name="difference_type"></a>vektör::difference_type (STL/CLR)

İki öğe arasındaki imzalı uzaklık türleri.

### <a name="syntax"></a>Sözdizimi

```cpp
typedef int difference_type;
```

### <a name="remarks"></a>Açıklamalar

Türü, imzalı öğe sayısını açıklar.

### <a name="example"></a>Örnek

```cpp
// cliext_vector_difference_type.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// compute positive difference
    cliext::vector<wchar_t>::difference_type diff = 0;
    for (cliext::vector<wchar_t>::iterator it = c1.begin();
        it != c1.end(); ++it) ++diff;
    System::Console::WriteLine("end()-begin() = {0}", diff);

// compute negative difference
    diff = 0;
    for (cliext::vector<wchar_t>::iterator it = c1.end();
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

## <a name="vectorempty-stlclr"></a><a name="empty"></a>vektör::boş (STL/CLR)

Bir öğe olup olmadığını sınar.

### <a name="syntax"></a>Sözdizimi

```cpp
bool empty();
```

### <a name="remarks"></a>Açıklamalar

Üye işlev boş bir kontrollü dizi için doğru döndürür. [Vektör::boyut (STL/CLR)](../dotnet/vector-size-stl-clr.md)`() == 0`eşdeğerdir. Vektörün boş olup olmadığını test etmek için kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// cliext_vector_empty.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
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

## <a name="vectorend-stlclr"></a><a name="end"></a>vektör::end (STL/CLR)

Denetlenen dizinin bitişini belirtir.

### <a name="syntax"></a>Sözdizimi

```cpp
iterator end();
```

### <a name="remarks"></a>Açıklamalar

Üye işlev, denetlenen dizinin sonundan hemen ötesine işaret eden rasgele erişim yineleyicisi döndürür. Bunu, denetlenme sırasının `current` sonunu belirleyen bir yineleyici elde etmek için kullanırsınız, ancak denetlenen dizinin uzunluğu değişirse durumu değişebilir.

### <a name="example"></a>Örnek

```cpp
// cliext_vector_end.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// inspect last two items
    cliext::vector<wchar_t>::iterator it = c1.end();
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

## <a name="vectorerase-stlclr"></a><a name="erase"></a>vektör::silme (STL/CLR)

Belirtilen konumlardaki öğeleri kaldırır.

### <a name="syntax"></a>Sözdizimi

```cpp
iterator erase(iterator where);
iterator erase(iterator first, iterator last);
```

#### <a name="parameters"></a>Parametreler

*Ilk*<br/>
Silmek için aralığın başlangıcı.

*Son*<br/>
Silmek için aralığın sonu.

*Nerede*<br/>
Silecek öğe.

### <a name="remarks"></a>Açıklamalar

İlk üye işlev, kontrol edilen dizinin öğesini *nereye*işaret etti? Tek bir öğeyi kaldırmak için kullanırsınız.

İkinci üye işlev, kontrollü dizinin öğelerini aralıktaki`first` `last`öğeleri kaldırır [ , ). Sıfır veya daha fazla bitişik öğeyi kaldırmak için kullanabilirsiniz.

Her iki üye işlev de kaldırılan ilk öğenin ötesinde kalan ilk öğeyi belirleyen bir yineleyici döndürür veya böyle bir öğe yoksa [vektör::end (STL/CLR).](../dotnet/vector-end-stl-clr.md) `()`

Öğeleri silerken, öğe kopyalarının sayısı silme sonu ile dizinin yakın sonu arasındaki öğe sayısında doğrusaldır. (Dizinin her iki ucundaki bir veya daha fazla öğeyi silerken, öğe kopyaları oluşmaz.)

### <a name="example"></a>Örnek

```cpp
// cliext_vector_erase.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
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
    cliext::vector<wchar_t>::iterator it = c1.end();
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

## <a name="vectorfront-stlclr"></a><a name="front"></a>vektör::ön (STL/CLR)

İlk öğeye erişir.

### <a name="syntax"></a>Sözdizimi

```cpp
reference front();
```

### <a name="remarks"></a>Açıklamalar

Üye işlev, boş olmayan kontrollü dizinin ilk öğesine bir başvuru döndürür. Var olduğunu bildiğinizde, ilk öğeyi okumak veya yazmak için kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// cliext_vector_front.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
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

## <a name="vectorfront_item-stlclr"></a><a name="front_item"></a>vektör::front_item (STL/CLR)

İlk öğeye erişir.

### <a name="syntax"></a>Sözdizimi

```cpp
property value_type front_item;
```

### <a name="remarks"></a>Açıklamalar

Özellik, boş olmayan olması gereken denetlenme sırasının ilk öğesine erişer. Var olduğunu bildiğinizde, ilk öğeyi okumak veya yazmak için kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// cliext_vector_front_item.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
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

## <a name="vectorgeneric_container-stlclr"></a><a name="generic_container"></a>vektör::generic_container (STL/CLR)

Kapsayıcı için genel arabirimin türü.

### <a name="syntax"></a>Sözdizimi

```cpp
typedef Microsoft::VisualC::StlClr::
    IVector<generic_value>
    generic_container;
```

### <a name="remarks"></a>Açıklamalar

Tür, bu şablon kapsayıcı sınıfının genel arabirimini açıklar.

### <a name="example"></a>Örnek

```cpp
// cliext_vector_generic_container.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// construct a generic container
    cliext::vector<wchar_t>::generic_container^ gc1 = %c1;
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

## <a name="vectorgeneric_iterator-stlclr"></a><a name="generic_iterator"></a>vektör::generic_iterator (STL/CLR)

Kapsayıcının genel arabirimiyle kullanılmak üzere bir yineleyici türü.

### <a name="syntax"></a>Sözdizimi

```cpp
typedef Microsoft::VisualC::StlClr::Generic::
    ContainerRandomAccessIterator<generic_value>
    generic_iterator;
```

### <a name="remarks"></a>Açıklamalar

Tür, bu şablon kapsayıcı sınıfı nın genel arabirimiyle kullanılabilecek genel bir yineleyiciyi açıklar.

### <a name="example"></a>Örnek

```cpp
// cliext_vector_generic_iterator.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// construct a generic container
    cliext::vector<wchar_t>::generic_container^ gc1 = %c1;
    for each (wchar_t elem in gc1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// modify generic and display original
    cliext::vector<wchar_t>::generic_iterator gcit = gc1->begin();
    cliext::vector<wchar_t>::generic_value gcval = *gcit;
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

## <a name="vectorgeneric_reverse_iterator-stlclr"></a><a name="generic_reverse_iterator"></a>vektör::generic_reverse_iterator (STL/CLR)

Kapsayıcının genel arabirimiyle kullanılmak üzere ters yineleyici türü.

### <a name="syntax"></a>Sözdizimi

```cpp
typedef Microsoft::VisualC::StlClr::Generic::
    ReverseRandomAccessIterator<generic_value> generic_reverse_iterator;
```

### <a name="remarks"></a>Açıklamalar

Tür, bu şablon kapsayıcı sınıfının genel arabirimiyle kullanılabilecek genel bir ters yineleyiciyi açıklar.

### <a name="example"></a>Örnek

```cpp
// cliext_vector_generic_reverse_iterator.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// construct a generic container
    cliext::vector<wchar_t>::generic_container^ gc1 = %c1;
    for each (wchar_t elem in gc1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// modify generic and display original
    cliext::vector<wchar_t>::generic_reverse_iterator gcit = gc1->rbegin();
    cliext::vector<wchar_t>::generic_value gcval = *gcit;
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

## <a name="vectorgeneric_value-stlclr"></a><a name="generic_value"></a>vektör::generic_value (STL/CLR)

Kapsayıcının genel arabirimiyle kullanılmak üzere bir öğenin türü.

### <a name="syntax"></a>Sözdizimi

```cpp
typedef GValue generic_value;
```

### <a name="remarks"></a>Açıklamalar

Tür, bu şablon `GValue` kapsayıcı sınıfının genel arabirimiyle kullanılmak üzere depolanan öğe değerini açıklayan bir tür nesnesini açıklar.

### <a name="example"></a>Örnek

```cpp
// cliext_vector_generic_value.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// construct a generic container
    cliext::vector<wchar_t>::generic_container^ gc1 = %c1;
    for each (wchar_t elem in gc1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// modify generic and display original
    cliext::vector<wchar_t>::generic_iterator gcit = gc1->begin();
    cliext::vector<wchar_t>::generic_value gcval = *gcit;
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

## <a name="vectorinsert-stlclr"></a><a name="insert"></a>vektör::insert (STL/CLR)

Belirli bir konumda öğeleri ekler.

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

*Sayısı*<br/>
Eklenecek öğe sayısı.

*Ilk*<br/>
Eklemek için aralığın başlangıcı.

*Son*<br/>
Eklenecek aralık sonu.

*Doğru*<br/>
Ekleme için numaralandırma.

*Val*<br/>
Eklenecek öğenin değeri.

*Nerede*<br/>
Daha önce eklemek için konteyner nerede.

### <a name="remarks"></a>Açıklamalar

Üye işlevlerin her biri, eleman tarafından işaret önce ekler *nerede* kontrollü sırada, kalan operands tarafından belirtilen bir dizi.

İlk üye işlev değer *val'li* bir öğe ekler ve yeni eklenen öğeyi belirleyen bir yineleyici döndürür. Bir yineleyici tarafından belirlenen bir yerden önce tek bir öğe eklemek için kullanabilirsiniz.

İkinci üye işlev, değer *val'in* *in sayım* elemanlarının tekrarını ekler. Tümü aynı değerin kopyaları olan sıfır veya daha fazla bitişik öğe eklemek için kullanırsınız.

Tamsayı `InIt` türü ise, üçüncü üye işlev `insert(where, (size_type)first, (value_type)last)`. Aksi takdirde, sırayı ekler`first` `last`[ , ). Başka bir diziden kopyalanan sıfır veya daha fazla bitişik öğe eklemek için kullanırsınız.

Dördüncü üye *işlev, sağ*tarafından belirlenen sırayı ekler. Bir sayıcı tarafından açıklanan bir sıra eklemek için kullanabilirsiniz.

Tek bir öğe eklerken, öğe kopyalarının sayısı ekleme noktası ile dizinin yakın sonu arasındaki eleman sayısında doğrusaldır. (Dizinin her iki ucuna bir veya daha fazla öğe eklenirken, öğe kopyaları oluşmaz.) Bir `InIt` giriş yineleyiciise, üçüncü üye işlev dizideki her öğe için etkili bir şekilde tek bir ekleme gerçekleştirir. Aksi takdirde, `N` öğeleri eklerken, öğe kopyalarının sayısı `N` doğrusal artı ekleme noktası ile dizinin yakın sonu arasındaki öğelerin sayısıdır.

### <a name="example"></a>Örnek

```cpp
// cliext_vector_insert.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// insert a single value using iterator
    cliext::vector<wchar_t>::iterator it = c1.begin();
    System::Console::WriteLine("insert(begin()+1, L'x') = {0}",
        *c1.insert(++it, L'x'));
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// insert a repetition of values
    cliext::vector<wchar_t> c2;
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

## <a name="vectoriterator-stlclr"></a><a name="iterator"></a>vektör::iterator (STL/CLR)

Denetlenen dizi için bir yineleyici türü.

### <a name="syntax"></a>Sözdizimi

```cpp
typedef T1 iterator;
```

### <a name="remarks"></a>Açıklamalar

Tür, denetlenen dizi `T1` için rasgele erişim yineleyici olarak hizmet verebilir belirtilmemiş türünde bir nesne açıklar.

### <a name="example"></a>Örnek

```cpp
// cliext_vector_iterator.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display contents " a b c"
    cliext::vector<wchar_t>::iterator it = c1.begin();
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

## <a name="vectoroperator-stlclr"></a><a name="op_as"></a>vektör::operator= (STL/CLR)

Denetedilen sırayı değiştirir.

### <a name="syntax"></a>Sözdizimi

```cpp
vector<Value>% operator=(vector<Value>% right);
```

#### <a name="parameters"></a>Parametreler

*Doğru*<br/>
Kopyalanması gereken konteyner.

### <a name="remarks"></a>Açıklamalar

Üye işleç *nesneye doğru* kopyalar, sonra döndürür. `*this` Bunu, denetlenir sırayı *sağdaki*kontrollü dizinin bir kopyasıyla değiştirmek için kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// cliext_vector_operator_as.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// assign to a new container
    cliext::vector<wchar_t> c2;
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

## <a name="vectoroperatorstlclr"></a><a name="op"></a>vektör::operatör(STL/CLR)

Belirli bir konumda bir öğeye erişir.

### <a name="syntax"></a>Sözdizimi

```cpp
reference operator[](size_type pos);
```

#### <a name="parameters"></a>Parametreler

*Pos*<br/>
Öğenin erişim konumu.

### <a name="remarks"></a>Açıklamalar

Üye operatör *pozisyon konumundaki*elemana bir hakem döndürür. Konumunu bildiğin bir elemana erişmek için kullanırsın.

### <a name="example"></a>Örnek

```cpp
// cliext_vector_operator_sub.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
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

## <a name="vectorpop_back-stlclr"></a><a name="pop_back"></a>vektör::pop_back (STL/CLR)

Son öğeyi kaldırır.

### <a name="syntax"></a>Sözdizimi

```cpp
void pop_back();
```

### <a name="remarks"></a>Açıklamalar

Üye işlev, boş olmayan kontrollü dizinin son öğesini kaldırır. Vektörü arkadaki bir elemanla kısaltmak için kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// cliext_vector_pop_back.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
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

## <a name="vectorpush_back-stlclr"></a><a name="push_back"></a>vektör::push_back (STL/CLR)

Yeni bir son öğe ekler.

### <a name="syntax"></a>Sözdizimi

```cpp
void push_back(value_type val);
```

### <a name="remarks"></a>Açıklamalar

Üye işlev, denetlenen dizinin `val` sonunda değeri olan bir öğe ekler. Vektöre başka bir öğe yi eklemek için kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// cliext_vector_push_back.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
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

## <a name="vectorrbegin-stlclr"></a><a name="rbegin"></a>vektör::rbegin (STL/CLR)

Ters denetimli dizinin başlangıcını belirler.

### <a name="syntax"></a>Sözdizimi

```cpp
reverse_iterator rbegin();
```

### <a name="remarks"></a>Açıklamalar

Üye işlev, denetlenen dizinin son öğesini veya boş bir dizinin başlangıcının hemen ötesini belirleyen bir ters yineleyici döndürür. Bu nedenle, ters `beginning` sırayı belirler. Ters sırada görülen denetlenen dizinin `current` başlangıcını belirleyen bir yineleyici elde etmek için kullanabilirsiniz, ancak denetlenen dizinin uzunluğu değişirse durumu değişebilir.

### <a name="example"></a>Örnek

```cpp
// cliext_vector_rbegin.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// inspect first two items in reversed sequence
    cliext::vector<wchar_t>::reverse_iterator rit = c1.rbegin();
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

## <a name="vectorreference-stlclr"></a><a name="reference"></a>vektör::referans (STL/CLR)

Bir öğe için bir başvuru türü.

### <a name="syntax"></a>Sözdizimi

```cpp
typedef value_type% reference;
```

### <a name="remarks"></a>Açıklamalar

Tür, bir öğeye başvuru açıklar.

### <a name="example"></a>Örnek

```cpp
// cliext_vector_reference.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display initial contents " a b c"
    cliext::vector<wchar_t>::iterator it = c1.begin();
    for (; it != c1.end(); ++it)
        {   // get a reference to an element
        cliext::vector<wchar_t>::reference ref = *it;
        System::Console::Write("{0} ", ref);
        }
    System::Console::WriteLine();

// modify contents " a b c"
    for (it = c1.begin(); it != c1.end(); ++it)
        {   // get a reference to an element
        cliext::vector<wchar_t>::reference ref = *it;

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

## <a name="vectorrend-stlclr"></a><a name="rend"></a>vektör::rend (STL/CLR)

Ters denetimli dizinin sonunu belirler.

### <a name="syntax"></a>Sözdizimi

```cpp
reverse_iterator rend();
```

### <a name="remarks"></a>Açıklamalar

Üye işlev, denetitilen dizinin başlangıcının hemen ötesine işaret eden bir ters yineleyici döndürür. Bu nedenle, ters `end` sırayı belirler. Ters sırada görülen denetlenen dizinin `current` sonunu belirleyen bir yineleyici elde etmek için kullanabilirsiniz, ancak denetlenen dizinin uzunluğu değişirse durumu değişebilir.

### <a name="example"></a>Örnek

```cpp
// cliext_vector_rend.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// inspect first two items
    cliext::vector<wchar_t>::reverse_iterator rit = c1.rend();
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

## <a name="vectorreserve-stlclr"></a><a name="reserve"></a>vektör::rezerv (STL/CLR)

Konteyner için minimum büyüme kapasitesi sağlar.

### <a name="syntax"></a>Sözdizimi

```cpp
void reserve(size_type count);
```

#### <a name="parameters"></a>Parametreler

*Sayısı*<br/>
Kapsayıcının yeni minimum kapasitesi.

### <a name="remarks"></a>Açıklamalar

Üye işlev `capacity()` bundan sonra en az *sayma*döndürür sağlar. Kapsayıcının, belirtilen boyuta gelene kadar denetitilmiş sıra için depolama alanı tahsis etmesi gerekmediğinden emin olmak için kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// cliext_vector_reserve.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display initial contents " a b c"
    for (int i = 0; i < c1.size(); ++i)
        System::Console::Write("{0} ", c1.at(i));
    System::Console::WriteLine();

// increase capacity
    cliext::vector<wchar_t>::size_type cap = c1.capacity();
    System::Console::WriteLine("capacity() = {0}, ok = {1}",
        cap, c1.size() <= cap);
    c1.reserve(cap + 5);
    System::Console::WriteLine("capacity() = {0}, ok = {1}",
        c1.capacity(), cap + 5 <= c1.capacity());
    return (0);
    }
```

```Output
a b c
capacity() = 4, ok = True
capacity() = 9, ok = True
```

## <a name="vectorresize-stlclr"></a><a name="resize"></a>vektör::yeniden boyutlandırma (STL/CLR)

Öğelerin sayısını değiştirir.

### <a name="syntax"></a>Sözdizimi

```cpp
void resize(size_type new_size);
void resize(size_type new_size, value_type val);
```

#### <a name="parameters"></a>Parametreler

*new_size*<br/>
Kontrollü dizinin yeni boyutu.

*Val*<br/>
Dolgu elemanının değeri.

### <a name="remarks"></a>Açıklamalar

Üye işlevleri n için [vektör::size (STL/CLR)](../dotnet/vector-size-stl-clr.md) `()` bundan sonra *new_size*döndürür sağlamak. Kontrollü sırayı daha uzun yapması gerekiyorsa, ilk üye `value_type()`işlev değeri olan öğeleri ekler, ikinci üye işlev ise değer *val'i*olan öğeleri ekler. Denetedilen sırayı kısaltmak için, her iki üye işlev de son öğe [vektörü:boyut (STL/CLR)](../dotnet/vector-size-stl-clr.md) `() -` `new_size` kez etkin bir şekilde silinir. Denetlenebilen dizinin, geçerli kontrol edilen sırayı kırparak veya dolgu yaparak *boyut new_size*olduğundan emin olmak için kullanabilirsiniz.

### <a name="example"></a>Örnek

```cpp
// cliext_vector_resize.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
// construct an empty container and pad with default values
    cliext::vector<wchar_t> c1;
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

## <a name="vectorreverse_iterator-stlclr"></a><a name="reverse_iterator"></a>vektör::reverse_iterator (STL/CLR)

Denetlenen dizi için ters yineleyici türü.

### <a name="syntax"></a>Sözdizimi

```cpp
typedef T3 reverse_iterator;
```

### <a name="remarks"></a>Açıklamalar

Tür, denetlenen dizi `T3` için ters yineleyici olarak hizmet verebilen belirtilmemiş türde bir nesneyi açıklar.

### <a name="example"></a>Örnek

```cpp
// cliext_vector_reverse_iterator.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display contents " a b c" reversed
    cliext::vector<wchar_t>::reverse_iterator rit = c1.rbegin();
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

## <a name="vectorsize-stlclr"></a><a name="size"></a>vektör::boyut (STL/CLR)

Öğe sayısını sayar.

### <a name="syntax"></a>Sözdizimi

```cpp
size_type size();
```

### <a name="remarks"></a>Açıklamalar

Üye işlev, denetitilen dizinin uzunluğunu döndürür. Şu anda denetlenmeyen sırada bulunan öğe sayısını belirlemek için kullanırsınız. Tek umursadığınız dizinin sıfır olmayan boyutu olup olmadığıysa, [bkz.](../dotnet/vector-empty-stl-clr.md)`()`

### <a name="example"></a>Örnek

```cpp
// cliext_vector_size.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
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

## <a name="vectorsize_type-stlclr"></a><a name="size_type"></a>vektör::size_type (STL/CLR)

İki öğe arasındaki işaretli mesafenin türü.

### <a name="syntax"></a>Sözdizimi

```cpp
typedef int size_type;
```

### <a name="remarks"></a>Açıklamalar

Tür negatif olmayan öğe sayısını açıklar.

### <a name="example"></a>Örnek

```cpp
// cliext_vector_size_type.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// compute positive difference
    cliext::vector<wchar_t>::size_type diff = c1.end() - c1.begin();
    System::Console::WriteLine("end()-begin() = {0}", diff);
    return (0);
    }
```

```Output
a b c
end()-begin() = 3
```

## <a name="vectorswap-stlclr"></a><a name="swap"></a>vektör::takas (STL/CLR)

İki kapsayıcının içeriğinin yerini değiştirir.

### <a name="syntax"></a>Sözdizimi

```cpp
void swap(vector<Value>% right);
```

#### <a name="parameters"></a>Parametreler

*Doğru*<br/>
İçeriği takas etmek için konteyner.

### <a name="remarks"></a>Açıklamalar

Üye işlev, kontrollü dizileri `*this` sağ ve *arasındaki*sıraları değiştirir. Bunu sürekli zaman içinde yapar ve hiçbir istisna atar. İki kapsayıcının içeriğini değiştirmek için hızlı bir yol olarak kullanabilirsiniz.

### <a name="example"></a>Örnek

```cpp
// cliext_vector_swap.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// construct another container with repetition of values
    cliext::vector<wchar_t> c2(5, L'x');
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

## <a name="vectorto_array-stlclr"></a><a name="to_array"></a>vektör::to_array (STL/CLR)

Denetedilen sırayı yeni bir diziye kopyalar.

### <a name="syntax"></a>Sözdizimi

```cpp
cli::array<Value>^ to_array();
```

### <a name="remarks"></a>Açıklamalar

Üye işlev, denetitilmiş sırayı içeren bir dizi döndürür. Bunu, denetitilmiş dizinin dizi biçiminde bir kopyasını elde etmek için kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// cliext_vector_to_array.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
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

## <a name="vectorvalue_type-stlclr"></a><a name="value_type"></a>vektör::value_type (STL/CLR)

Öğenin türü.

### <a name="syntax"></a>Sözdizimi

```cpp
typedef Value value_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, şablon parametresi *Değeri*ile eş anlamlıdır.

### <a name="example"></a>Örnek

```cpp
// cliext_vector_value_type.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display contents " a b c" using value_type
    for (cliext::vector<wchar_t>::iterator it = c1.begin();
        it != c1.end(); ++it)
        {   // store element in value_type object
        cliext::vector<wchar_t>::value_type val = *it;

        System::Console::Write("{0} ", val);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="vectorvector-stlclr"></a><a name="vector"></a>vektör::vektör (STL/CLR)

Bir kapsayıcı nesnesi oluşturur.

### <a name="syntax"></a>Sözdizimi

```cpp
vector();
vector(vector<Value>% right);
vector(vector<Value>^ right);
explicit vector(size_type count);
vector(size_type count, value_type val);
template<typename InIt>
    vector(InIt first, InIt last);
vector(System::Collections::Generic::IEnumerable<Value>^ right);
```

#### <a name="parameters"></a>Parametreler

*Sayısı*<br/>
Eklenecek öğe sayısı.

*Ilk*<br/>
Eklemek için aralığın başlangıcı.

*Son*<br/>
Eklenecek aralık sonu.

*Doğru*<br/>
Eklemek için nesne veya aralık.

*Val*<br/>
Eklenecek öğenin değeri.

### <a name="remarks"></a>Açıklamalar

Yapıcı:

`vector();`

hiçbir öğe ile kontrol edilen sırayı başlatir. Boş bir ilk kontrollü sıra belirtmek için kullanabilirsiniz.

Yapıcı:

`vector(vector<Value>% right);`

[`right.begin()`, `right.end()`) ile kontrollü sırayı başlatir. Vektör nesnesi *sağ*tarafından kontrol edilen dizinin bir kopyası olan bir ilk kontrollü dizi belirtmek için kullanabilirsiniz.

Yapıcı:

`vector(vector<Value>^ right);`

[`right->begin()`, `right->end()`) ile kontrollü sırayı başlatir. Tutamacı *doğru*olan vektör nesnesi tarafından denetlenen dizinin bir kopyası olan ilk denetimli sırayı belirtmek için kullanırsınız.

Yapıcı:

`explicit vector(size_type count);`

her biri değeri `value_type()`olan *sayım* elemanları ile kontrol edilen sırayı başlatir. Kapsayıcıyı varsayılan değere sahip öğelerle doldurmak için kullanırsınız.

Yapıcı:

`vector(size_type count, value_type val);`

her biri değer *val'i*ile *sayım* elemanları ile kontrollü sırayı başlatir. Kapsayıcıyı aynı değere sahip öğelerle doldurmak için kullanırsınız.

Yapıcı:

`template<typename InIt>`

`vector(InIt first, InIt last);`

[`first`, `last`) ile kontrollü sırayı başlatir. Bunu, denetitilen sırayı başka bir dizinin kopyası yapmak için kullanırsınız.

Yapıcı:

`vector(System::Collections::Generic::IEnumerable<Value>^ right);`

enumerator *sağ*tarafından belirlenen sıra ile kontrollü sırayı başlatir. Bunu, denetite edilen sırayı bir yerumerator tarafından açıklanan başka bir dizinin kopyası yapmak için kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// cliext_vector_construct.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
// construct an empty container
    cliext::vector<wchar_t> c1;
    System::Console::WriteLine("size() = {0}", c1.size());

// construct with a repetition of default values
    cliext::vector<wchar_t> c2(3);
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", (int)elem);
    System::Console::WriteLine();

// construct with a repetition of values
    cliext::vector<wchar_t> c3(6, L'x');
    for each (wchar_t elem in c3)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// construct with an iterator range
    cliext::vector<wchar_t>::iterator it = c3.end();
    cliext::vector<wchar_t> c4(c3.begin(), --it);
    for each (wchar_t elem in c4)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// construct with an enumeration
    cliext::vector<wchar_t> c5(   // NOTE: cast is not needed
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c3);
    for each (wchar_t elem in c5)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// construct by copying another container
    cliext::vector<wchar_t> c7(c3);
    for each (wchar_t elem in c7)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// construct by copying a container handle
    cliext::vector<wchar_t> c8(%c3);
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

## <a name="operator-vector-stlclr"></a><a name="op_neq"></a>işleç!= (vektör) (STL/CLR)

Vektör eşit karşılaştırma değil.

### <a name="syntax"></a>Sözdizimi

```cpp
template<typename Value>
    bool operator!=(vector<Value>% left,
        vector<Value>% right);
```

#### <a name="parameters"></a>Parametreler

*Sol*<br/>
Karşılaştırmak için sol konteyner.

*Doğru*<br/>
Karşılaştırmak için doğru konteyner.

### <a name="remarks"></a>Açıklamalar

Operatör işlevi `!(left == right)`döndürür. İki vektör öğeyle karşılaştırıldığında *sol* adada *right* aynı sıralı olup olmadığını test etmek için kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// cliext_vector_operator_ne.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// assign to a new container
    cliext::vector<wchar_t> c2;
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

## <a name="operatorlt-vector-stlclr"></a><a name="op_lt"></a>işleç&lt; (vektör) (STL/CLR)

Vektör karşılaştırma daha az.

### <a name="syntax"></a>Sözdizimi

```cpp
template<typename Value>
    bool operator<(vector<Value>% left,
        vector<Value>% right);
```

#### <a name="parameters"></a>Parametreler

*Sol*<br/>
Karşılaştırmak için sol konteyner.

*Doğru*<br/>
Karşılaştırmak için doğru konteyner.

### <a name="remarks"></a>Açıklamalar

Operatör işlevi, en düşük pozisyon `i` için `!(right[i] < left[i])` de doğru ysa `left[i] < right[i]`doğru döndürür. Aksi takdirde, `left->size() < right->size()` iki vektör öğe ile karşılaştırıldığında *sağ* önce *sol* sıralanır olup olmadığını test etmek için kullanabilirsiniz döndürür.

### <a name="example"></a>Örnek

```cpp
// cliext_vector_operator_lt.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// assign to a new container
    cliext::vector<wchar_t> c2;
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

## <a name="operatorlt-vector-stlclr"></a><a name="op_lteq"></a>işleç&lt;= (vektör) (STL/CLR)

Vektör daha az veya eşit karşılaştırma.

### <a name="syntax"></a>Sözdizimi

```cpp
template<typename Value>
    bool operator<=(vector<Value>% left,
        vector<Value>% right);
```

#### <a name="parameters"></a>Parametreler

*Sol*<br/>
Karşılaştırmak için sol konteyner.

*Doğru*<br/>
Karşılaştırmak için doğru konteyner.

### <a name="remarks"></a>Açıklamalar

Operatör işlevi `!(right < left)`döndürür. İki vektör öğeyle elemanla *karşılaştırıldığında, sağdan* sonra *sola* sıralanıp sıralanmadığını test etmek için kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// cliext_vector_operator_le.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// assign to a new container
    cliext::vector<wchar_t> c2;
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

## <a name="operator-vector-stlclr"></a><a name="op_eq"></a>işleç== (vektör) (STL/CLR)

Vektör eşit karşılaştırma.

### <a name="syntax"></a>Sözdizimi

```cpp
template<typename Value>
    bool operator==(vector<Value>% left,
        vector<Value>% right);
```

#### <a name="parameters"></a>Parametreler

*Sol*<br/>
Karşılaştırmak için sol konteyner.

*Doğru*<br/>
Karşılaştırmak için doğru konteyner.

### <a name="remarks"></a>Açıklamalar

İşleç işlevi yalnızca *sol* ve *sağ* tarafından denetlenen diziler `i`aynı `left[i] ==` `right[i]`uzunluğa sahipse ve her pozisyon için doğru döndürür. İki vektör öğeyle karşılaştırıldığında *sola* *right* aynı sıraolup olmadığını test etmek için kullanabilirsiniz.

### <a name="example"></a>Örnek

```cpp
// cliext_vector_operator_eq.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// assign to a new container
    cliext::vector<wchar_t> c2;
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

## <a name="operatorgt-vector-stlclr"></a><a name="op_gt"></a>işleç&gt; (vektör) (STL/CLR)

Vektör karşılaştırmadan daha büyüktür.

### <a name="syntax"></a>Sözdizimi

```cpp
template<typename Value>
    bool operator>(vector<Value>% left,
        vector<Value>% right);
```

#### <a name="parameters"></a>Parametreler

*Sol*<br/>
Karşılaştırmak için sol konteyner.

*Doğru*<br/>
Karşılaştırmak için doğru konteyner.

### <a name="remarks"></a>Açıklamalar

Operatör işlevi `right` `<` `left`döndürür. İki vektör öğeyle elemanla karşılaştırıldığında *solun* *sağdan* sonra sıralanıp sıralanmadığını test etmek için kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// cliext_vector_operator_gt.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// assign to a new container
    cliext::vector<wchar_t> c2;
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

## <a name="operatorgt-vector-stlclr"></a><a name="op_gteq"></a>işleç&gt;= (vektör) (STL/CLR)

Vektör daha büyük veya eşit karşılaştırma.

### <a name="syntax"></a>Sözdizimi

```cpp
template<typename Value>
    bool operator>=(vector<Value>% left,
        vector<Value>% right);
```

#### <a name="parameters"></a>Parametreler

*Sol*<br/>
Karşılaştırmak için sol konteyner.

*Doğru*<br/>
Karşılaştırmak için doğru konteyner.

### <a name="remarks"></a>Açıklamalar

Operatör işlevi `!(left < right)`döndürür. İki vektör öğeyle *karşılaştırıldığında, sağdan* önce *sola* sıralanıp sıralanmadığını test etmek için kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// cliext_vector_operator_ge.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// assign to a new container
    cliext::vector<wchar_t> c2;
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
