---
title: priority_queue (STL/CLR)
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- cliext::priority_queue
- cliext::priority_queue::assign
- cliext::priority_queue::const_reference
- cliext::priority_queue::container_type
- cliext::priority_queue::difference_type
- cliext::priority_queue::empty
- cliext::priority_queue::generic_container
- cliext::priority_queue::generic_value
- cliext::priority_queue::get_container
- cliext::priority_queue::operator=
- cliext::priority_queue::pop
- cliext::priority_queue::priority_queue
- cliext::priority_queue::push
- cliext::priority_queue::reference
- cliext::priority_queue::size
- cliext::priority_queue::size_type
- cliext::priority_queue::to_array
- cliext::priority_queue::top
- cliext::priority_queue::top_item
- cliext::priority_queue::value_comp
- cliext::priority_queue::value_compare
- cliext::priority_queue::value_type
helpviewer_keywords:
- priority_queue class [STL/CLR]
- <queue> header [STL/CLR]
- <cliext/queue> header [STL/CLR]
- assign member [STL/CLR]
- const_reference member [STL/CLR]
- container_type member [STL/CLR]
- difference_type member [STL/CLR]
- empty member [STL/CLR]
- generic_container member [STL/CLR]
- generic_value member [STL/CLR]
- get_container member [STL/CLR]
- operator= member [STL/CLR]
- pop member [STL/CLR]
- priority_queue member [STL/CLR]
- push member [STL/CLR]
- reference member [STL/CLR]
- size member [STL/CLR]
- size_type member [STL/CLR]
- to_array member [STL/CLR]
- top member [STL/CLR]
- top_item member [STL/CLR]
- value_comp member [STL/CLR]
- value_compare member [STL/CLR]
- value_type member [STL/CLR]
ms.assetid: 4d0000d3-68ff-4c4b-8157-7060540136f5
ms.openlocfilehash: 6c5a37cc76f6ac3a3f92cf54b440960d7476daa9
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87211052"
---
# <a name="priority_queue-stlclr"></a>priority_queue (STL/CLR)

Şablon sınıfı, sınırlı erişimi olan öğelerin değişen uzunluklu sıralı dizisini denetleyen bir nesneyi tanımlar. Kapsayıcı bağdaştırıcısını, temel bir `priority_queue` kapsayıcıyı öncelik kuyruğu olarak yönetmek için kullanırsınız.

Aşağıdaki açıklamada, `GValue` Ikinci *değeri* bir başvuru türü olmadığı sürece, bu örnekte olduğu gibi olur `Value^` . Benzer şekilde, `GContainer` ikincinin bir başvuru türü olmadığı ve bu durumda olduğu sürece *kapsayıcı* ile aynıdır `Container^` .

## <a name="syntax"></a>Söz dizimi

```cpp
template<typename Value,
    typename Container>
    ref class priority_queue
        System::ICloneable,
        Microsoft::VisualC::StlClr::IPriorityQueue<GValue, GContainer>
    { ..... };
```

### <a name="parameters"></a>Parametreler

*Değer*<br/>
Denetlenen sıradaki öğenin türü.

*Kapsayıcı*<br/>
Temel alınan kapsayıcının türü.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<cliext/queue>

**Ad alanı:** cliext

## <a name="declarations"></a>Bildirimler

|Tür Tanımı|Açıklama|
|---------------------|-----------------|
|[priority_queue::const_reference (STL/CLR)](#const_reference)|Bir öğe için sabit bir başvuru türü.|
|[priority_queue::container_type (STL/CLR)](#container_type)|Temel alınan kapsayıcının türü.|
|[priority_queue::difference_type (STL/CLR)](#difference_type)|İki öğe arasındaki işaretli mesafenin türü.|
|[priority_queue::generic_container (STL/CLR)](#generic_container)|Kapsayıcı bağdaştırıcısının genel arabiriminin türü.|
|[priority_queue::generic_value (STL/CLR)](#generic_value)|Kapsayıcı bağdaştırıcısının genel arabirimi için bir öğe türü.|
|[priority_queue::reference (STL/CLR)](#reference)|Bir öğe için bir başvuru türü.|
|[priority_queue::size_type (STL/CLR)](#size_type)|İki öğe arasındaki işaretli mesafenin türü.|
|[priority_queue::value_compare (STL/CLR)](#value_compare)|İki öğe için sıralama temsilcisi.|
|[priority_queue::value_type (STL/CLR)](#value_type)|Öğenin türü.|

|Üye İşlevi|Açıklama|
|---------------------|-----------------|
|[priority_queue::assign (STL/CLR)](#assign)|Tüm öğeleri değiştirir.|
|[priority_queue::empty (STL/CLR)](#empty)|Bir öğe olup olmadığını sınar.|
|[priority_queue::get_container (STL/CLR)](#get_container)|Temel alınan kapsayıcıya erişir.|
|[priority_queue::pop (STL/CLR)](#pop)|Hghest-Priority öğesini kaldırır.|
|[priority_queue::priority_queue (STL/CLR)](#priority_queue)|Bir kapsayıcı nesnesi oluşturur.|
|[priority_queue::push (STL/CLR)](#push)|Yeni bir öğesi ekler.|
|[priority_queue::size (STL/CLR)](#size)|Öğe sayısını sayar.|
|[priority_queue::top (STL/CLR)](#top)|En yüksek önceliğe sahip öğeye erişir.|
|[priority_queue::to_array (STL/CLR)](#to_array)|Denetimli sırayı yeni bir diziye kopyalar.|
|[priority_queue::value_comp (STL/CLR)](#value_comp)|Sıralama temsilcisini iki öğe için kopyalar.|

|Özellik|Açıklama|
|--------------|-----------------|
|[priority_queue::top_item (STL/CLR)](#top_item)|En yüksek önceliğe sahip öğeye erişir.|

|İşleç|Açıklama|
|--------------|-----------------|
|[priority_queue::operator= (STL/CLR)](#op_as)|Denetlenen sırayı değiştirir.|

## <a name="interfaces"></a>Arabirimler

|Arabirim|Açıklama|
|---------------|-----------------|
|<xref:System.ICloneable>|Bir nesneyi çoğaltın.|
|IPriorityQueue\<Value, Container>|Genel kapsayıcı bağdaştırıcısını koruyun.|

## <a name="remarks"></a>Açıklamalar

Nesnesi, `Container` öğeleri depolayan ve isteğe bağlı olarak büyüyen türündeki temeldeki bir kapsayıcı aracılığıyla denetlediği sıra için depolamayı ayırır ve boşaltır `Value` . En yüksek öncelikli öğe (üst öğe) ile erişilebilir ve kaldırılabilir şekilde, diziyi bir yığın olarak sıralanmış tutar. Nesnesi, erişimi, yeni öğeleri göndermeye ve yalnızca en yüksek öncelikli öğenin bir öncelik sırası uygulayarak bir üst düzey öğenin altına alma işlemini kısıtlar.

Nesne, [priority_queue:: value_compare (STL/CLR)](../dotnet/priority-queue-value-compare-stl-clr.md)türünde depolanan bir temsilci nesnesi çağırarak denetlediği diziyi sıralar. Priority_queue oluşturduğunuzda saklı temsilci nesnesini belirtebilirsiniz; temsilci nesnesi belirtmezseniz, varsayılan değer karşılaştırmayla belirlenir `operator<(value_type, value_type)` . Bu saklı nesneye [priority_queue:: value_comp (STL/CLR)](../dotnet/priority-queue-value-comp-stl-clr.md)üye işlevini çağırarak erişirsiniz `()` .

Bu tür bir temsilci nesnesi, [priority_queue:: value_type (STL/CLR)](../dotnet/priority-queue-value-type-stl-clr.md)türündeki değerlere katı bir zayıf sıralama getirmelidir. Yani, her iki anahtar için `X` ve `Y` :

`value_comp()(X, Y)`her çağrıda aynı Boole sonucunu döndürür.

`value_comp()(X, Y)`True ise, false olmalıdır `value_comp()(Y, X)` .

`value_comp()(X, Y)`True ise, daha `X` önce sipariş olarak kabul edilir `Y` .

`!value_comp()(X, Y) && !value_comp()(Y, X)`True ise, `X` ve `Y` eşdeğer sıralamaya sahip olarak kabul edilir.

`X`Denetlenen dizide önündeki tüm öğeler için `Y` `key_comp()(Y, X)` false olur. (Varsayılan temsilci nesnesi için, anahtarlar hiçbir şekilde değerde azalmayın.)

Bu nedenle, en yüksek öncelik öğesi, başka bir öğeden önce Sıralanmayan öğelerinden biridir.

Temeldeki kapsayıcı öğeleri bir yığın olarak sıralanmış olarak tutduğundan:

Kapsayıcının Rastgele erişimli yineleyiciler desteklemesi gerekir.

Denk sıralamaya sahip öğeler, itilinden farklı bir sırada kesilebilir. (Sıralama kararlı değildir.)

Bu nedenle, temel alınan kapsayıcının adayları, [deque (STL/CLR)](../dotnet/deque-stl-clr.md) ve [Vector (STL/CLR)](../dotnet/vector-stl-clr.md)içerir.

## <a name="members"></a>Üyeler

## <a name="priority_queueassign-stlclr"></a><a name="assign"></a>priority_queue:: Assign (STL/CLR)

Tüm öğeleri değiştirir.

### <a name="syntax"></a>Söz dizimi

```cpp
void assign(priority_queue<Value, Container>% right);
```

#### <a name="parameters"></a>Parametreler

*Right*<br/>
Eklenecek kapsayıcı bağdaştırıcısı.

### <a name="remarks"></a>Açıklamalar

Üye işlevi, `right.get_container()` temel alınan kapsayıcıya atar. Bu, sıranın tüm içeriğini değiştirmek için kullanılır.

### <a name="example"></a>Örnek

```cpp
// cliext_priority_queue_assign.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::priority_queue<wchar_t> Mypriority_queue;
int main()
    {
    Mypriority_queue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // assign a repetition of values
    Mypriority_queue c2;
    c2.assign(c1);
    for each (wchar_t elem in c2.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
c a b
c a b
```

## <a name="priority_queueconst_reference-stlclr"></a><a name="const_reference"></a>priority_queue:: const_reference (STL/CLR)

Bir öğe için sabit bir başvuru türü.

### <a name="syntax"></a>Sözdizimi

```cpp
typedef value_type% const_reference;
```

### <a name="remarks"></a>Açıklamalar

Türü bir öğeye sabit bir başvuru tanımlar.

### <a name="example"></a>Örnek

```cpp
// cliext_priority_queue_const_reference.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::priority_queue<wchar_t> Mypriority_queue;
int main()
    {
    Mypriority_queue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

    // display reversed contents " c b a"
    for (; !c1.empty(); c1.pop())
        {   // get a const reference to an element
        Mypriority_queue::const_reference cref = c1.top();
        System::Console::Write("{0} ", cref);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
c b a
```

## <a name="priority_queuecontainer_type-stlclr"></a><a name="container_type"></a>priority_queue:: container_type (STL/CLR)

Temel alınan kapsayıcının türü.

### <a name="syntax"></a>Sözdizimi

```cpp
typedef Container value_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, şablon parametresi için bir eş anlamlı `Container` .

### <a name="example"></a>Örnek

```cpp
// cliext_priority_queue_container_type.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::priority_queue<wchar_t> Mypriority_queue;
int main()
    {
    Mypriority_queue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

    // display contents " a b c" using container_type
    Mypriority_queue::container_type wc1 = c1.get_container();
    for each (wchar_t elem in wc1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
c a b
```

## <a name="priority_queuedifference_type-stlclr"></a><a name="difference_type"></a>priority_queue::d ifference_type (STL/CLR)

İki öğe arasındaki işaretli bir mesafe türü.

### <a name="syntax"></a>Sözdizimi

```cpp
typedef int difference_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, büyük olasılıkla negatif bir öğe sayısını tanımlar.

### <a name="example"></a>Örnek

```cpp
// cliext_priority_queue_difference_type.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::priority_queue<wchar_t> Mypriority_queue;
int main()
    {
    Mypriority_queue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // compute negative difference
    Mypriority_queue::difference_type diff = c1.size();
    c1.push(L'd');
    c1.push(L'e');
    diff -= c1.size();
    System::Console::WriteLine("pushing 2 = {0}", diff);

    // compute positive difference
    diff = c1.size();
    c1.pop();
    c1.pop();
    c1.pop();
    diff -= c1.size();
    System::Console::WriteLine("popping 3 = {0}", diff);
    return (0);
    }
```

```Output
c a b
pushing 2 = -2
popping 3 = 3
```

## <a name="priority_queueempty-stlclr"></a><a name="empty"></a>priority_queue:: Empty (STL/CLR)

Bir öğe olup olmadığını sınar.

### <a name="syntax"></a>Sözdizimi

```cpp
bool empty();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi boş bir denetlenen dizi için true döndürür. [Priority_queue:: size (STL/CLR)](../dotnet/priority-queue-size-stl-clr.md)eşdeğerdir `() == 0` . Priority_queue boş olup olmadığını test etmek için kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// cliext_priority_queue_empty.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::priority_queue<wchar_t> Mypriority_queue;
int main()
    {
    Mypriority_queue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    System::Console::WriteLine("size() = {0}", c1.size());
    System::Console::WriteLine("empty() = {0}", c1.empty());

    // clear the container and reinspect
    c1.pop();
    c1.pop();
    c1.pop();
    System::Console::WriteLine("size() = {0}", c1.size());
    System::Console::WriteLine("empty() = {0}", c1.empty());
    return (0);
    }
```

```Output
c a b
size() = 3
empty() = False
size() = 0
empty() = True
```

## <a name="priority_queuegeneric_container-stlclr"></a><a name="generic_container"></a>priority_queue:: generic_container (STL/CLR)

Kapsayıcının genel arabiriminin türü.

### <a name="syntax"></a>Sözdizimi

```cpp
typedef Microsoft::VisualC::StlClr::IPriorityQueue<Value>
    generic_container;
```

### <a name="remarks"></a>Açıklamalar

Tür, bu şablon kapsayıcı bağdaştırıcısı sınıfı için genel arabirimi tanımlar.

### <a name="example"></a>Örnek

```cpp
// cliext_priority_queue_generic_container.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::priority_queue<wchar_t> Mypriority_queue;
int main()
    {
    Mypriority_queue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

    // display contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct a generic container
    Mypriority_queue::generic_container^ gc1 = %c1;
    for each (wchar_t elem in gc1->get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // modify generic and display original
    gc1->push(L'd');
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // modify original and display generic
    c1.push(L'e');
    for each (wchar_t elem in gc1->get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
c a b
c a b
d c b a
e d b a c
```

## <a name="priority_queuegeneric_value-stlclr"></a><a name="generic_value"></a>priority_queue:: generic_value (STL/CLR)

Kapsayıcının genel arabirimiyle kullanılacak öğe türü.

### <a name="syntax"></a>Sözdizimi

```cpp
typedef GValue generic_value;
```

### <a name="remarks"></a>Açıklamalar

Tür, `GValue` Bu şablon kapsayıcı sınıfı için genel arabirimle birlikte kullanılacak saklı öğe değerini açıklayan türünde bir nesne tanımlar. ( `GValue` ya da `value_type` `value_type^` `value_type` bir başvuru türüdür.)

### <a name="example"></a>Örnek

```cpp
// cliext_priority_queue_generic_value.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::priority_queue<wchar_t> Mypriority_queue;
int main()
    {
    Mypriority_queue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

    // display contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // get interface to container
    Mypriority_queue::generic_container^ gc1 = %c1;
    for each (wchar_t elem in gc1->get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // display in priority order using generic_value
    for (; !gc1->empty(); gc1->pop())
        {
        Mypriority_queue::generic_value elem = gc1->top();

        System::Console::Write("{0} ", elem);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
c a b
c a b
c b a
```

## <a name="priority_queueget_container-stlclr"></a><a name="get_container"></a>priority_queue:: get_container (STL/CLR)

Temel alınan kapsayıcıya erişir.

### <a name="syntax"></a>Sözdizimi

```cpp
container_type get_container();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, temeldeki kapsayıcıyı döndürür. Kapsayıcı sarmalayıcı tarafından uygulanan kısıtlamaları atlamak için bunu kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// cliext_priority_queue_get_container.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::priority_queue<wchar_t> Mypriority_queue;
int main()
    {
    Mypriority_queue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
c a b
```

## <a name="priority_queueoperator-stlclr"></a><a name="op_as"></a>priority_queue:: operator = (STL/CLR)

Denetlenen sırayı değiştirir.

### <a name="syntax"></a>Söz dizimi

```cpp
priority_queue <Value, Container>% operator=(priority_queue <Value, Container>% right);
```

#### <a name="parameters"></a>Parametreler

*Right*<br/>
Kopyalanacak kapsayıcı bağdaştırıcısı.

### <a name="remarks"></a>Açıklamalar

Üye işleci nesnesine *sağ* kopyalar ve ardından döndürür **`*this`** . Denetlenen diziyi, denetimli sıranın bir kopyasıyla değiştirmek için bunu *kullanırsınız.*

### <a name="example"></a>Örnek

```cpp
// cliext_priority_queue_operator_as.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::priority_queue<wchar_t> Mypriority_queue;
int main()
    {
    Mypriority_queue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

    // display contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // assign to a new container
    Mypriority_queue c2;
    c2 = c1;
    for each (wchar_t elem in c2.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
c a b
c a b
```

## <a name="priority_queuepop-stlclr"></a><a name="pop"></a>priority_queue::p op (STL/CLR)

En yüksek proırity öğesini kaldırır.

### <a name="syntax"></a>Sözdizimi

```cpp
void pop();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, denetimli sıranın en yüksek öncelikli öğesini kaldırır, bu da boş olmamalıdır. Kuyruğu, arka arkaya bir öğe ile kısaltmak için kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// cliext_priority_queue_pop.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::priority_queue<wchar_t> Mypriority_queue;
int main()
    {
    Mypriority_queue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

    // display contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // pop an element and redisplay
    c1.pop();
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
c a b
b a
```

## <a name="priority_queuepriority_queue-stlclr"></a><a name="priority_queue"></a>priority_queue::p riority_queue (STL/CLR)

Kapsayıcı bağdaştırıcı nesnesi oluşturur.

### <a name="syntax"></a>Söz dizimi

```cpp
priority_queue();
priority_queue(priority_queue<Value, Container> right);
priority_queue(priority_queue<Value, Container> right);
explicit priority_queue(value_compare^ pred);
priority_queue(value_compare^ pred, container_type% cont);
template<typename InIt>
    priority_queue(InIt first, InIt last);
template<typename InIt>
    priority_queue(InIt first, InIt last,
        value_compare^ pred);
template<typename InIt>
    priority_queue(InIt first, InIt last,
        value_compare^ pred, container_type% cont);
```

#### <a name="parameters"></a>Parametreler

*bildirisini*<br/>
Kopyalanacak kapsayıcı.

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

`priority_queue();`

Varsayılan sıralama koşulu ile boş bir sarmalanmış kapsayıcı oluşturur. Varsayılan sıralama koşulu ile boş bir ilk denetimli sıra belirtmek için bunu kullanırsınız.

Oluşturucu:

`priority_queue(priority_queue<Value, Container>% right);`

sıralama koşulu ile, kopyası olan sarmalanmış bir kapsayıcı oluşturur `right.get_container()` `right.value_comp()` . Aynı sıralama koşulu ile, *kuyruk nesnesi tarafından*denetlenen sıranın bir kopyası olan ilk denetimli bir sıra belirtmek için bunu kullanırsınız.

Oluşturucu:

`priority_queue(priority_queue<Value, Container>^ right);`

sıralama koşulu ile, kopyası olan sarmalanmış bir kapsayıcı oluşturur `right->get_container()` `right->value_comp()` . Sıra nesnesi tarafından denetlenen sıranın bir kopyası olan, aynı sıralama koşuluna sahip bir ilk denetimli sıra belirtmek için bunu kullanırsınız `*right` .

Oluşturucu:

`explicit priority_queue(value_compare^ pred);`

sıralama koşulu *Pred*içeren boş bir sarmalanmış kapsayıcı oluşturur. Belirtilen sıralama koşulu ile boş bir ilk denetimli sıra belirtmek için bunu kullanırsınız.

Oluşturucu:

`priority_queue(value_compare^ pred, container_type cont);`

sıralama koşulu *Pred*olan boş bir sarmalanmış kapsayıcı oluşturur, ardından tüm *devam* eden öğeleri, mevcut bir kapsayıcıdan, belirtilen sıralama koşuluna sahip bir ilk denetimli sıra belirtmek için kullanır.

Oluşturucu:

`template<typename InIt> priority_queue(InIt first, InIt last);`

Varsayılan sıralama koşulu ile boş bir sarmalanmış kapsayıcı oluşturur, sonra [,) dizisini gönderir `first` `last` . Belirtilen sıralama koşulu ile, belirtilen bir eqeuence 'tan ilk denetimli bir sıra belirtmek için bunu kullanırsınız.

Oluşturucu:

`template<typename InIt> priority_queue(InIt first, InIt last, value_compare^ pred);`

sıralama koşulu *Pred*olan boş bir sarmalanmış kapsayıcı oluşturur, sonra [,) dizisini gönderir `first` `last` . Belirtilen sıralama koşulu ile, belirtilen bir seq'tan bir başlangıç denetimli sıra belirtmek için bunu kullanırsınız.

Oluşturucu:

`template<typename InIt> priority_queue(InIt first, InIt last, value_compare^ pred, container_type% cont);`

sıralı koşul *Pred*ile boş bir sarmalanmış kapsayıcı oluşturur, ardından *devam* eden tüm öğeleri ve [ `first` ,) dizisini iter `last` . Mevcut bir kapsayıcıdan ve belirtilen bir seqeuence öğesinden, belirtilen sıralama koşuluna sahip bir ilk denetimli sıra belirtmek için bunu kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// cliext_priority_queue_construct.cpp
// compile with: /clr
#include <cliext/queue>
#include <cliext/deque>

typedef cliext::priority_queue<wchar_t> Mypriority_queue;
typedef cliext::deque<wchar_t> Mydeque;
int main()
    {
// construct an empty container
    Mypriority_queue c1;
    Mypriority_queue::container_type^ wc1 = c1.get_container();
    System::Console::WriteLine("size() = {0}", c1.size());

    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');
    for each (wchar_t elem in wc1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct with an ordering rule
    Mypriority_queue c2 = cliext::greater<wchar_t>();
    System::Console::WriteLine("size() = {0}", c2.size());

    for each (wchar_t elem in wc1)
        c2.push(elem);
    for each (wchar_t elem in c2.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct with an ordering rule by copying an underlying container
    Mypriority_queue c2x =
        gcnew Mypriority_queue(cliext::greater<wchar_t>(), *wc1);
   for each (wchar_t elem in c2x.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct with an iterator range
    Mypriority_queue c3(wc1->begin(), wc1->end());
    for each (wchar_t elem in c3.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct with an iterator range and an ordering rule
    Mypriority_queue c4(wc1->begin(), wc1->end(),
        cliext::greater<wchar_t>());
    for each (wchar_t elem in c4.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct with an iterator range, another container, and an ordering rule
    Mypriority_queue c5(wc1->begin(), wc1->end(),
        cliext::greater<wchar_t>(), *wc1);
    for each (wchar_t elem in c5.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct from a generic container
    Mypriority_queue c6(c3);
    for each (wchar_t elem in c6.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct by copying another container
    Mypriority_queue c7(%c3);
    for each (wchar_t elem in c7.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct with an ordering rule, by copying an underlying container
    Mypriority_queue c8 =
        gcnew Mypriority_queue(cliext::greater<wchar_t>(), *wc1);
    for each (wchar_t elem in c8.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    return (0);
    }
```

```Output
size() = 0
c a b
size() = 0
a c b
a c b
c a b
a c b
a a b c c b
c a b
c a b
a c b
```

## <a name="priority_queuepush-stlclr"></a><a name="push"></a>priority_queue::p USH (STL/CLR)

Yeni bir öğesi ekler.

### <a name="syntax"></a>Sözdizimi

```cpp
void push(value_type val);
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi denetlenen diziye değeri olan bir öğesi ekler `val` ve yığın disiplinini sürdürmek için denetimli diziyi yeniden sıralar. Kuyruğa başka bir öğe eklemek için bunu kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// cliext_priority_queue_push.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::priority_queue<wchar_t> Mypriority_queue;
int main()
    {
    Mypriority_queue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

    // display contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
c a b
```

## <a name="priority_queuereference-stlclr"></a><a name="reference"></a>priority_queue:: Reference (STL/CLR)

Bir öğe için bir başvuru türü.

### <a name="syntax"></a>Sözdizimi

```cpp
typedef value_type% reference;
```

### <a name="remarks"></a>Açıklamalar

Türü bir öğesi başvurusunu tanımlar.

### <a name="example"></a>Örnek

```cpp
// cliext_priority_queue_reference.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::priority_queue<wchar_t> Mypriority_queue;
int main()
    {
    Mypriority_queue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // modify top of priority_queue and redisplay
    Mypriority_queue::reference ref = c1.top();
    ref = L'x';
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
c a b
x a b
```

## <a name="priority_queuesize-stlclr"></a><a name="size"></a>priority_queue:: size (STL/CLR)

Öğe sayısını sayar.

### <a name="syntax"></a>Sözdizimi

```cpp
size_type size();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi denetlenen sıranın uzunluğunu döndürür. Bu, şu anda denetlenen dizideki öğelerin sayısını tespit etmek için kullanılır. Her şey için, sıranın sıfır dışında bir boyut içerip içermediğini öğrenmek için bkz. [priority_queue:: Empty (STL/CLR)](../dotnet/priority-queue-empty-stl-clr.md) `()` .

### <a name="example"></a>Örnek

```cpp
// cliext_priority_queue_size.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::priority_queue<wchar_t> Mypriority_queue;
int main()
    {
    Mypriority_queue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    System::Console::WriteLine("size() = {0} starting with 3", c1.size());

    // pop an item and reinspect
    c1.pop();
    System::Console::WriteLine("size() = {0} after popping", c1.size());

    // add two elements and reinspect
    c1.push(L'a');
    c1.push(L'b');
    System::Console::WriteLine("size() = {0} after adding 2", c1.size());
    return (0);
    }
```

```Output
c a b
size() = 3 starting with 3
size() = 2 after popping
size() = 4 after adding 2
```

## <a name="priority_queuesize_type-stlclr"></a><a name="size_type"></a>priority_queue:: size_type (STL/CLR)

İki öğe arasındaki işaretli bir mesafe türü.

### <a name="syntax"></a>Sözdizimi

```cpp
typedef int size_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, negatif olmayan bir öğe sayısını tanımlar.

### <a name="example"></a>Örnek

```cpp
// cliext_priority_queue_size_type.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::priority_queue<wchar_t> Mypriority_queue;
int main()
    {
    Mypriority_queue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // compute positive difference
    Mypriority_queue::size_type diff = c1.size();
    c1.pop();
    c1.pop();
    diff -= c1.size();
    System::Console::WriteLine("size difference = {0}", diff);
    return (0);
    }
```

```Output
c a b
size difference = 2
```

## <a name="priority_queueto_array-stlclr"></a><a name="to_array"></a>priority_queue:: to_array (STL/CLR)

Denetimli sırayı yeni bir diziye kopyalar.

### <a name="syntax"></a>Sözdizimi

```cpp
cli::array<Value>^ to_array();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi denetlenen sırayı içeren bir dizi döndürür. Dizi biçiminde denetlenen sıranın bir kopyasını almak için bunu kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// cliext_priority_queue_to_array.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::priority_queue<wchar_t> Mypriority_queue;
int main()
    {
    Mypriority_queue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

    // copy the container and modify it
    cli::array<wchar_t>^ a1 = c1.to_array();

    c1.push(L'd');
    for each (wchar_t elem in c1.get_container())
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
d c b a
c a b
```

## <a name="priority_queuetop-stlclr"></a><a name="top"></a>priority_queue:: top (STL/CLR)

En yüksek önceliğe sahip öğeye erişir.

### <a name="syntax"></a>Sözdizimi

```cpp
reference top();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, denetimli sıranın en üst (en yüksek öncelik) öğesine bir başvuru döndürür ve bu değer boş olmamalıdır. Bunu, olduğunu bildiğiniz en yüksek öncelikli öğeye erişmek için kullanabilirsiniz.

### <a name="example"></a>Örnek

```cpp
// cliext_priority_queue_top.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::priority_queue<wchar_t> Mypriority_queue;
int main()
    {
    Mypriority_queue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // inspect last item
    System::Console::WriteLine("top() = {0}", c1.top());

    // alter last item and reinspect
    c1.top() = L'x';
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

## <a name="priority_queuetop_item-stlclr"></a><a name="top_item"></a>priority_queue:: top_item (STL/CLR)

En yüksek önceliğe sahip öğeye erişir.

### <a name="syntax"></a>Sözdizimi

```cpp
property value_type back_item;
```

### <a name="remarks"></a>Açıklamalar

Özelliği, denetimli sıranın en üst (en yüksek öncelik) öğesine erişir, bu da boş olmamalıdır. Mevcut olduğunu bildiğiniz en yüksek öncelikli öğeyi okumak veya yazmak için bunu kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// cliext_priority_queue_top_item.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::priority_queue<wchar_t> Mypriority_queue;
int main()
    {
    Mypriority_queue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // inspect last item
    System::Console::WriteLine("top_item = {0}", c1.top_item);

    // alter last item and reinspect
    c1.top_item = L'x';
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
c a b
top_item = c
x a b
```

## <a name="priority_queuevalue_comp-stlclr"></a><a name="value_comp"></a>priority_queue:: value_comp (STL/CLR)

Sıralama temsilcisini iki öğe için kopyalar.

### <a name="syntax"></a>Sözdizimi

```cpp
value_compare^ value_comp();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, denetimli sırayı sıralamak için kullanılan sıralama temsilcisini döndürür. İki değeri karşılaştırmak için bunu kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// cliext_priority_queue_value_comp.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::priority_queue<wchar_t> Mypriority_queue;
int main()
    {
    Mypriority_queue c1;
    Mypriority_queue::value_compare^ vcomp = c1.value_comp();

    System::Console::WriteLine("compare(L'a', L'a') = {0}",
        vcomp(L'a', L'a'));
    System::Console::WriteLine("compare(L'a', L'b') = {0}",
        vcomp(L'a', L'b'));
    System::Console::WriteLine("compare(L'b', L'a') = {0}",
        vcomp(L'b', L'a'));
    System::Console::WriteLine();

    // test a different ordering rule
    Mypriority_queue c2 = cliext::greater<wchar_t>();
    vcomp = c2.value_comp();

    System::Console::WriteLine("compare(L'a', L'a') = {0}",
        vcomp(L'a', L'a'));
    System::Console::WriteLine("compare(L'a', L'b') = {0}",
        vcomp(L'a', L'b'));
    System::Console::WriteLine("compare(L'b', L'a') = {0}",
        vcomp(L'b', L'a'));
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

## <a name="priority_queuevalue_compare-stlclr"></a><a name="value_compare"></a>priority_queue:: value_compare (STL/CLR)

İki değer için sıralama temsilcisi.

### <a name="syntax"></a>Sözdizimi

```cpp
binary_delegate<value_type, value_type, int> value_compare;
```

### <a name="remarks"></a>Açıklamalar

Tür, ilk bağımsız değişkenin ikinciden önce sıralı olup olmadığını belirleyen temsilcinin bir eş anlamlısıdır.

### <a name="example"></a>Örnek

```cpp
// cliext_priority_queue_value_compare.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::priority_queue<wchar_t> Mypriority_queue;
int main()
    {
    Mypriority_queue c1;
    Mypriority_queue::value_compare^ vcomp = c1.value_comp();

    System::Console::WriteLine("compare(L'a', L'a') = {0}",
        vcomp(L'a', L'a'));
    System::Console::WriteLine("compare(L'a', L'b') = {0}",
        vcomp(L'a', L'b'));
    System::Console::WriteLine("compare(L'b', L'a') = {0}",
        vcomp(L'b', L'a'));
    System::Console::WriteLine();

    // test a different ordering rule
    Mypriority_queue c2 = cliext::greater<wchar_t>();
    vcomp = c2.value_comp();

    System::Console::WriteLine("compare(L'a', L'a') = {0}",
        vcomp(L'a', L'a'));
    System::Console::WriteLine("compare(L'a', L'b') = {0}",
        vcomp(L'a', L'b'));
    System::Console::WriteLine("compare(L'b', L'a') = {0}",
        vcomp(L'b', L'a'));
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

## <a name="priority_queuevalue_type-stlclr"></a><a name="value_type"></a>priority_queue:: value_type (STL/CLR)

Öğenin türü.

### <a name="syntax"></a>Sözdizimi

```cpp
typedef Value value_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, şablon parametre *değeri*için bir eş anlamlı.

### <a name="example"></a>Örnek

```cpp
// cliext_priority_queue_value_type.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::priority_queue<wchar_t> Mypriority_queue;
int main()
    {
    Mypriority_queue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

    // display reversed contents " a b c" using value_type
    for (; !c1.empty(); c1.pop())
        {   // store element in value_type object
        Mypriority_queue::value_type val = c1.top();

        System::Console::Write("{0} ", val);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
c b a
```
