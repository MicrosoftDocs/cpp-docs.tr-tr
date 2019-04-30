---
title: yığın (STL/CLR)
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- cliext::stack
- cliext::operator!=
- cliext::operator<
- cliext::operator<=
- cliext::operator==
- cliext::operator>
- cliext::operator>=
- cliext::stack::assign
- cliext::stack::const_reference
- cliext::stack::container_type
- cliext::stack::difference_type
- cliext::stack::empty
- cliext::stack::generic_container
- cliext::stack::generic_value
- cliext::stack::get_container
- cliext::stack::operator=
- cliext::stack::pop
- cliext::stack::push
- cliext::stack::reference
- cliext::stack::size
- cliext::stack::size_type
- cliext::stack::stack
- cliext::stack::to_array
- cliext::stack::top
- cliext::stack::top_item
- cliext::stack::value_type
helpviewer_keywords:
- <stack> header [STL/CLR]
- <cliext/stack> header [STL/CLR]
- stack class [STL/CLR]
- operator!= member [STL/CLR]
- operator< member [STL/CLR]
- operator<= member [STL/CLR]
- operator== member [STL/CLR]
- operator> member [STL/CLR]
- operator>= member [STL/CLR]
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
- push member [STL/CLR]
- reference member [STL/CLR]
- size member [STL/CLR]
- size_type member [STL/CLR]
- stack member [STL/CLR]
- to_array member [STL/CLR]
- top member [STL/CLR]
- top_item member [STL/CLR]
- value_type member [STL/CLR]
ms.assetid: 6ee96b9f-8a33-4cf7-b7e0-6535c24bdefb
ms.openlocfilehash: ec3863796f7c49c155af61576c15c1ca8a9d5109
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62384614"
---
# <a name="stack-stlclr"></a>yığın (STL/CLR)

Şablon sınıfı, son giren ilk çıkar erişimi olan öğelerin değişen uzunluktaki dizisini denetleyen bir nesneyi tanımlar. Kapsayıcı bağdaştırıcısı kullandığınız `stack` temel alınan bir kapsayıcı göndererek yığını olarak yönetilecek.

Aşağıdaki açıklamada `GValue` aynı *değer* ikinci bir başvuru türü olmadığı sürece olduğu durumda `Value^`. Benzer şekilde, `GContainer` aynı *kapsayıcı* ikinci bir başvuru türü olmadığı sürece olduğu durumda `Container^`.

## <a name="syntax"></a>Sözdizimi

```cpp
template<typename Value,
    typename Container>
    ref class stack
        :   public
        System::ICloneable,
        Microsoft::VisualC::StlClr::IStack<GValue, GContainer>
    { ..... };
```

### <a name="parameters"></a>Parametreler

*Değer*<br/>
Denetlenen sıradaki öğenin türü.

*Kapsayıcı*<br/>
Temel alınan kapsayıcı türü.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<cliext/stack >

**Namespace:** cliext

## <a name="declarations"></a>Bildirimler

|Tür Tanımlaması|Açıklama|
|---------------------|-----------------|
|[stack::const_reference (STL/CLR)](#const_reference)|Bir öğe için sabit bir başvuru türü.|
|[stack::container_type (STL/CLR)](#container_type)|Temel alınan kapsayıcı türü.|
|[stack::difference_type (STL/CLR)](#difference_type)|İki öğe arasındaki işaretli mesafenin türü.|
|[stack::generic_container (STL/CLR)](#generic_container)|Kapsayıcı bağdaştırıcısı için genel arabirim türü.|
|[stack::generic_value (STL/CLR)](#generic_value)|Kapsayıcı bağdaştırıcısı için genel arabirimi için bir öğe türü.|
|[stack::reference (STL/CLR)](#reference)|Bir öğe için bir başvuru türü.|
|[stack::size_type (STL/CLR)](#size_type)|İki öğe arasındaki işaretli mesafenin türü.|
|[stack::value_type (STL/CLR)](#value_type)|Öğenin türü.|

|Üye İşlevi|Açıklama|
|---------------------|-----------------|
|[stack::assign (STL/CLR)](#assign)|Tüm öğeleri değiştirir.|
|[stack::empty (STL/CLR)](#empty)|Bir öğe olup olmadığını sınar.|
|[stack::get_container (STL/CLR)](#get_container)|Temel alınan kapsayıcı erişir.|
|[stack::pop (STL/CLR)](#pop)|Son öğeyi kaldırır.|
|[stack::push (STL/CLR)](#push)|Yeni bir son öğesi ekler.|
|[stack::size (STL/CLR)](#size)|Öğe sayısını sayar.|
|[stack::stack (STL/CLR)](#stack)|Bir kapsayıcı nesnesi oluşturur.|
|[stack::top (STL/CLR)](#top)|Son öğeyi erişir.|
|[stack::to_array (STL/CLR)](#to_array)|Denetlenen dizideki, yeni bir diziye kopyalar.|

|Özellik|Açıklama|
|--------------|-----------------|
|[stack::top_item (STL/CLR)](#top_item)|Son öğeyi erişir.|

|İşleç|Açıklama|
|--------------|-----------------|
|[stack::operator= (STL/CLR)](#op_as)|Denetlenen dizi değiştirir.|
|[operator!= (stack) (STL/CLR)](#op_neq)|Belirler bir `stack` nesnesi, diğerine eşit değil `stack` nesne.|
|[operator< (stack) (STL/CLR)](#op_lt)|Belirler bir `stack` nesnedir daha az `stack` nesne.|
|[operator<= (stack) (STL/CLR)](#op_lteq)|Belirler bir `stack` nesnedir küçüktür veya eşittir diğerine `stack` nesne.|
|[operator== (stack) (STL/CLR)](#op_eq)|Belirler bir `stack` nesnedir diğerine eşit `stack` nesne.|
|[operator> (stack) (STL/CLR)](#op_gt)|Belirler bir `stack` nesnedir diğerinden daha büyük `stack` nesne.|
|[operator>= (stack) (STL/CLR)](#op_gteq)|Belirler bir `stack` nesnedir büyüktür veya eşittir diğerine `stack` nesne.|

## <a name="interfaces"></a>Arabirimler

|Arabirim|Açıklama|
|---------------|-----------------|
|<xref:System.ICloneable>|Bir nesne çoğaltın.|
|IStack\<değeri, kapsayıcı >|Genel bir kapsayıcı bağdaştırıcısı korur.|

## <a name="remarks"></a>Açıklamalar

Nesneyi ayırır ve serbest bırakma türü temel alınan bir kapsayıcının denetlediği dizi için depolama *kapsayıcı*, depolayan *değer* öğeleri ve istek üzerine büyür. Nesne, gönderme ve son giren ilk çıkar (olarak da bilinen bir LIFO kuyruk veya yığın) kuyruk uygulama yalnızca son öğe, yığından erişimi kısıtlar.

## <a name="members"></a>Üyeler

## <a name="assign"></a> Stack::Assign (STL/CLR)

Tüm öğeleri değiştirir.

### <a name="syntax"></a>Sözdizimi

```cpp
void assign(stack<Value, Container>% right);
```

#### <a name="parameters"></a>Parametreler

*sağ*<br/>
Eklenecek kapsayıcı Bağdaştırıcısı'nı tıklatın.

### <a name="remarks"></a>Açıklamalar

Üye işlevi atar `right.get_container()` temel alınan kapsayıcısı. Yığın tüm içeriğini değiştirmek için kullanın.

### <a name="example"></a>Örnek

```cpp
// cliext_stack_assign.cpp
// compile with: /clr
#include <cliext/stack>

typedef cliext::stack<wchar_t> Mystack;
int main()
    {
    Mystack c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// assign a repetition of values
    Mystack c2;
    c2.assign(c1);
    for each (wchar_t elem in c2.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
a b c
```

## <a name="const_reference"></a> Stack::const_reference (STL/CLR)

Bir öğe için sabit bir başvuru türü.

### <a name="syntax"></a>Sözdizimi

```cpp
typedef value_type% const_reference;
```

### <a name="remarks"></a>Açıklamalar

Bir öğe için sabit bir başvuru türü açıklar.

### <a name="example"></a>Örnek

```cpp
// cliext_stack_const_reference.cpp
// compile with: /clr
#include <cliext/stack>

typedef cliext::stack<wchar_t> Mystack;
int main()
    {
    Mystack c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

// display reversed contents " c b a"
    for (; !c1.empty(); c1.pop())
        {   // get a const reference to an element
        Mystack::const_reference cref = c1.top();
        System::Console::Write("{0} ", cref);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
c b a
```

## <a name="container_type"></a> Stack::container_type (STL/CLR)

Temel alınan kapsayıcı türü.

### <a name="syntax"></a>Sözdizimi

```cpp
typedef Container value_type;
```

### <a name="remarks"></a>Açıklamalar

Şablon parametresi için bir eşanlamlı türüdür *kapsayıcı*.

### <a name="example"></a>Örnek

```cpp
// cliext_stack_container_type.cpp
// compile with: /clr
#include <cliext/stack>

typedef cliext::stack<wchar_t> Mystack;
int main()
    {
    Mystack c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

// display contents " a b c" using container_type
    Mystack::container_type wc1 = c1.get_container();
    for each (wchar_t elem in wc1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="difference_type"></a> Stack::difference_type (STL/CLR)

İki öğe arasındaki işaretli mesafenin türü.

### <a name="syntax"></a>Sözdizimi

```cpp
typedef int difference_type;
```

### <a name="remarks"></a>Açıklamalar

Büyük olasılıkla negatif öğe sayısını tanımlayan bir tür.

### <a name="example"></a>Örnek

```cpp
// cliext_stack_difference_type.cpp
// compile with: /clr
#include <cliext/stack>

typedef cliext::stack<wchar_t> Mystack;
int main()
    {
    Mystack c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// compute negative difference
    Mystack::difference_type diff = c1.size();
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
a b c
pushing 2 = -2
popping 3 = 3
```

## <a name="empty"></a> Stack::Empty (STL/CLR)

Bir öğe olup olmadığını sınar.

### <a name="syntax"></a>Sözdizimi

```cpp
bool empty();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi boş bir denetlenmiş dizi için true değerini döndürür. Eşdeğerdir [stack::size (STL/CLR)](../dotnet/stack-size-stl-clr.md)`() == 0`. Yığını boş olup olmadığını sınamak için kullanın.

### <a name="example"></a>Örnek

```cpp
// cliext_stack_empty.cpp
// compile with: /clr
#include <cliext/stack>

typedef cliext::stack<wchar_t> Mystack;
int main()
    {
    Mystack c1;
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
a b c
size() = 3
empty() = False
size() = 0
empty() = True
```

## <a name="generic_container"></a> Stack::generic_container (STL/CLR)

Kapsayıcı bağdaştırıcısı için genel arabirim türü.

### <a name="syntax"></a>Sözdizimi

```cpp
typedef Microsoft::VisualC::StlClr::IStack<Value>
    generic_container;
```

### <a name="remarks"></a>Açıklamalar

Bu şablon kapsayıcı bağdaştırıcısı sınıfın genel arabirim tanımlayan bir tür.

### <a name="example"></a>Örnek

```cpp
// cliext_stack_generic_container.cpp
// compile with: /clr
#include <cliext/stack>

typedef cliext::stack<wchar_t> Mystack;
int main()
    {
    Mystack c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// get interface to container
    Mystack::generic_container^ gc1 = %c1;
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
a b c
a b c
a b c d
a b c d e
```

## <a name="generic_value"></a> Stack::generic_value (STL/CLR)

Kapsayıcı için genel arabirimi ile kullanmak için bir öğe türü.

### <a name="syntax"></a>Sözdizimi

```cpp
typedef GValue generic_value;
```

### <a name="remarks"></a>Açıklamalar

Türünde bir nesneyi tanımlayan bir tür `GValue` açıklayan yönelik genel arabirimi için bu şablonu kapsayıcı sınıfı ile kullanmak için depolanan öğenin değeri. (`GValue` ya da `value_type` veya `value_type^` varsa `value_type` bir başvuru türüdür.)

### <a name="example"></a>Örnek

```cpp
// cliext_stack_generic_value.cpp
// compile with: /clr
#include <cliext/stack>

typedef cliext::stack<wchar_t> Mystack;
int main()
    {
    Mystack c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// get interface to container
    Mystack::generic_container^ gc1 = %c1;
    for each (wchar_t elem in gc1->get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// display in reverse using generic_value
    for (; !gc1->empty(); gc1->pop())
        {
        Mystack::generic_value elem = gc1->top();

        System::Console::Write("{0} ", elem);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
a b c
c b a
```

## <a name="get_container"></a> Stack::get_container (STL/CLR)

Temel alınan kapsayıcı erişir.

### <a name="syntax"></a>Sözdizimi

```cpp
container_type^ get_container();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, temel alınan kapsayıcısı için bir tanıtıcı döndürür. Kapsayıcı sarmalayıcı tarafından uygulanan kısıtlamalar atlamak için kullanın.

### <a name="example"></a>Örnek

```cpp
// cliext_stack_get_container.cpp
// compile with: /clr
#include <cliext/stack>

typedef cliext::stack<wchar_t> Mystack;
int main()
    {
    Mystack c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

// display contents " a b c" using container_type
    Mystack::container_type wc1 = c1.get_container();
    for each (wchar_t elem in wc1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="op_as"></a> Stack::operator (STL/CLR) =

Denetlenen dizi değiştirir.

### <a name="syntax"></a>Sözdizimi

```cpp
stack <Value, Container>% operator=(stack <Value, Container>% right);
```

#### <a name="parameters"></a>Parametreler

*sağ*<br/>
Kopyalanacak kapsayıcı Bağdaştırıcısı'nı tıklatın.

### <a name="remarks"></a>Açıklamalar

Üye işleci kopyaları *doğru* ardından nesneye döndürür `*this`. Denetlenen dizi denetlenen dizide bir kopyasını değiştirmek için kullandığınız *doğru*.

### <a name="example"></a>Örnek

```cpp
// cliext_stack_operator_as.cpp
// compile with: /clr
#include <cliext/stack>

typedef cliext::stack<wchar_t> Mystack;
int main()
    {
    Mystack c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// assign to a new container
    Mystack c2;
    c2 = c1;
    for each (wchar_t elem in c2.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
a b c
```

## <a name="pop"></a> Stack::POP (STL/CLR)

Son öğeyi kaldırır.

### <a name="syntax"></a>Sözdizimi

```cpp
void pop();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, denetlenen dizinin boş olması gereken son öğeyi kaldırır. Yığın arkasındaki bir öğe tarafından kısaltmak için kullanın.

### <a name="example"></a>Örnek

```cpp
// cliext_stack_pop.cpp
// compile with: /clr
#include <cliext/stack>

typedef cliext::stack<wchar_t> Mystack;
int main()
    {
    Mystack c1;
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
a b c
a b
```

## <a name="push"></a> Stack::push (STL/CLR)

Yeni bir son öğesi ekler.

### <a name="syntax"></a>Sözdizimi

```cpp
void push(value_type val);
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi değere sahip bir öğe ekler `val` denetlenen dizinin sonunda. Yığın için başka bir öğe eklemek için kullanın.

### <a name="example"></a>Örnek

```cpp
// cliext_stack_push.cpp
// compile with: /clr
#include <cliext/stack>

typedef cliext::stack<wchar_t> Mystack;
int main()
    {
    Mystack c1;
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
a b c
```

## <a name="reference"></a> Stack::Reference (STL/CLR)

Bir öğe için bir başvuru türü.

### <a name="syntax"></a>Sözdizimi

```cpp
typedef value_type% reference;
```

### <a name="remarks"></a>Açıklamalar

Öğeye bir başvuru türü açıklar.

### <a name="example"></a>Örnek

```cpp
// cliext_stack_reference.cpp
// compile with: /clr
#include <cliext/stack>

typedef cliext::stack<wchar_t> Mystack;
int main()
    {
    Mystack c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// modify top of stack and redisplay
    Mystack::reference ref = c1.top();
    ref = L'x';
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
a b x
```

## <a name="size"></a> Stack::size (STL/CLR)

Öğe sayısını sayar.

### <a name="syntax"></a>Sözdizimi

```cpp
size_type size();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, denetlenen dizinin uzunluğunu döndürür. Şu anda denetlenen dizideki öğelerin sayısını belirlemek için kullanın. Tümü, önem verdiğiniz ise dizisi bakın, sıfır olmayan boyutu olup [stack::empty (STL/CLR)](../dotnet/stack-empty-stl-clr.md)`()`.

### <a name="example"></a>Örnek

```cpp
// cliext_stack_size.cpp
// compile with: /clr
#include <cliext/stack>

typedef cliext::stack<wchar_t> Mystack;
int main()
    {
    Mystack c1;
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
a b c
size() = 3 starting with 3
size() = 2 after popping
size() = 4 after adding 2
```

## <a name="size_type"></a> Stack::size_type (STL/CLR)

İki öğe arasındaki işaretli mesafenin türü.

### <a name="syntax"></a>Sözdizimi

```cpp
typedef int size_type;
```

### <a name="remarks"></a>Açıklamalar

Bir negatif olmayan öğe sayısını tanımlayan bir tür.

### <a name="example"></a>Örnek

```cpp
// cliext_stack_size_type.cpp
// compile with: /clr
#include <cliext/stack>

typedef cliext::stack<wchar_t> Mystack;
int main()
    {
    Mystack c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// compute positive difference
    Mystack::size_type diff = c1.size();
    c1.pop();
    c1.pop();
    diff -= c1.size();
    System::Console::WriteLine("size difference = {0}", diff);
    return (0);
    }
```

```Output
a b c
size difference = 2
```

## <a name="stack"></a> Stack::Stack (STL/CLR)

Bir kapsayıcı bağdaştırıcısı nesnesi oluşturur.

### <a name="syntax"></a>Sözdizimi

```cpp
stack();
stack(stack<Value, Container>% right);
stack(stack<Value, Container>^ right);
explicit stack(container_type% wrapped);
```

#### <a name="parameters"></a>Parametreler

*sağ*<br/>
Kopyalanacak nesneye.

*Sarmalanan*<br/>
Kullanılacak Sarmalanan kapsayıcısı.

### <a name="remarks"></a>Açıklamalar

Oluşturucu:

`stack();`

boş bir Sarmalanan kapsayıcı oluşturur. Boş bir başlangıç denetlenmiş dizi belirtmek için kullanın.

Oluşturucu:

`stack(stack<Value, Container>% right);`

kopyası olan bir sarmalanmış bir kapsayıcı oluşturur `right.get_container()`. Yığın nesnesi tarafından denetlenen dizinin bir kopyasını olan ilk denetimli bir sıra belirtmek için kullandığınız *doğru*.

Oluşturucu:

`stack(stack<Value, Container>^ right);`

kopyası olan bir sarmalanmış bir kapsayıcı oluşturur `right->get_container()`. Yığın nesnesi tarafından denetlenen dizinin bir kopyasını olan ilk denetimli bir sıra belirtmek için kullandığınız `*right`.

Oluşturucu:

`explicit stack(container_type% wrapped);`

var olan bir kapsayıcı kullanan *sarmalanmış* Sarmalanan kapsayıcısı. Var olan bir kapsayıcı yığından oluşturmak için kullanın.

### <a name="example"></a>Örnek

```cpp
// cliext_stack_construct.cpp
// compile with: /clr
#include <cliext/stack>
#include <cliext/vector>

typedef cliext::stack<wchar_t> Mystack;
typedef cliext::vector<wchar_t> Myvector;
typedef cliext::stack<wchar_t, Myvector> Mystack_vec;
int main()
    {
// construct an empty container
    Mystack c1;
    System::Console::WriteLine("size() = {0}", c1.size());

// construct from an underlying container
    Myvector v2(5, L'x');
    Mystack_vec c2(v2);
    for each (wchar_t elem in c2.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// construct by copying another container
    Mystack_vec c3(c2);
    for each (wchar_t elem in c3.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// construct by copying another container through handle
    Mystack_vec c4(%c2);
    for each (wchar_t elem in c4.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
size() = 0
x x x x x
x x x x x
x x x x x
```

## <a name="to_array"></a> Stack::to_array (STL/CLR)

Denetlenen dizideki, yeni bir diziye kopyalar.

### <a name="syntax"></a>Sözdizimi

```cpp
cli::array<Value>^ to_array();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, denetlenen bir dizi içeren bir dizi döndürür. Dizi formunda denetlenen dizinin bir kopyasını almak için kullanın.

### <a name="example"></a>Örnek

```cpp
// cliext_stack_to_array.cpp
// compile with: /clr
#include <cliext/stack>

typedef cliext::stack<wchar_t> Mystack;
int main()
    {
    Mystack c1;
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
a b c d
a b c
```

## <a name="top"></a> Stack::Top (STL/CLR)

Son öğeyi erişir.

### <a name="syntax"></a>Sözdizimi

```cpp
reference top();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, denetlenen dizinin boş olması gereken son öğeye bir başvuru döndürür. Son öğe mevcut bildiğinizde erişmek için kullanın.

### <a name="example"></a>Örnek

```cpp
// cliext_stack_top.cpp
// compile with: /clr
#include <cliext/stack>

typedef cliext::stack<wchar_t> Mystack;
int main()
    {
    Mystack c1;
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

```Output
a b c
top() = c
a b x
```

## <a name="top_item"></a> Stack::top_item (STL/CLR)

Son öğeyi erişir.

### <a name="syntax"></a>Sözdizimi

```cpp
property value_type top_item;
```

### <a name="remarks"></a>Açıklamalar

Özellik, son öğe boş olmalıdır denetlenen dizinin erişir. Okumak veya son öğe mevcut bildiğinizde yazmak için kullanın.

### <a name="example"></a>Örnek

```cpp
// cliext_stack_top_item.cpp
// compile with: /clr
#include <cliext/stack>

typedef cliext::stack<wchar_t> Mystack;
int main()
    {
    Mystack c1;
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
a b c
top_item = c
a b x
```

## <a name="value_type"></a> Stack::value_type (STL/CLR)

Öğenin türü.

### <a name="syntax"></a>Sözdizimi

```cpp
typedef Value value_type;
```

### <a name="remarks"></a>Açıklamalar

Şablon parametresi için bir eşanlamlı türüdür *değer*.

### <a name="example"></a>Örnek

```cpp
// cliext_stack_value_type.cpp
// compile with: /clr
#include <cliext/stack>

typedef cliext::stack<wchar_t> Mystack;
int main()
    {
    Mystack c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

// display reversed contents " a b c" using value_type
    for (; !c1.empty(); c1.pop())
        {   // store element in value_type object
        Mystack::value_type val = c1.top();

        System::Console::Write("{0} ", val);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
c b a
```

## <a name="op_neq"></a> işleç! = (yığın) (STL/CLR)

Eşit değildir karşılaştırma yığın.

### <a name="syntax"></a>Sözdizimi

```cpp
template<typename Value,
    typename Container>
    bool operator!=(stack<Value, Container>% left,
        stack<Value, Container>% right);
```

#### <a name="parameters"></a>Parametreler

*Sol*<br/>
Karşılaştırılacak sol kapsayıcısı.

*sağ*<br/>
Karşılaştırılacak doğru kapsayıcısı.

### <a name="remarks"></a>Açıklamalar

İşleç işlevini döndürür `!(left == right)`. Test etmek için kullandığınız olmadığını *sol* aynı sıralı değil *doğru* iki yığınları karşılaştırılan öğe öğe olduğunda.

### <a name="example"></a>Örnek

```cpp
// cliext_stack_operator_ne.cpp
// compile with: /clr
#include <cliext/stack>

typedef cliext::stack<wchar_t> Mystack;
int main()
    {
    Mystack c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// assign to a new container
    Mystack c2;
    c2.push(L'a');
    c2.push(L'b');
    c2.push(L'd');

// display contents " a b d"
    for each (wchar_t elem in c2.get_container())
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

## <a name="op_lt"></a> İşleç&lt; (yığın) (STL/CLR)

Yığın değerinden karşılaştırma.

### <a name="syntax"></a>Sözdizimi

```cpp
template<typename Value,
    typename Container>
    bool operator<(stack<Value, Container>% left,
        stack<Value, Container>% right);
```

#### <a name="parameters"></a>Parametreler

*Sol*<br/>
Karşılaştırılacak sol kapsayıcısı.

*sağ*<br/>
Karşılaştırılacak doğru kapsayıcısı.

### <a name="remarks"></a>Açıklamalar

İşleç işlevi döndürür true ise, en düşük konumu için `i` hangi `!(right[i] < left[i])` de true olduğu `left[i] < right[i]`. Aksi halde `left->` [stack::size (STL/CLR)](../dotnet/stack-size-stl-clr.md) `() <` `right->size()` test etmek için kullandığınız olmadığını *sol* önceyse *doğru* iki yığınları karşılaştırılan öğe öğe olduğunda.

### <a name="example"></a>Örnek

```cpp
// cliext_stack_operator_lt.cpp
// compile with: /clr
#include <cliext/stack>

typedef cliext::stack<wchar_t> Mystack;
int main()
    {
    Mystack c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// assign to a new container
    Mystack c2;
    c2.push(L'a');
    c2.push(L'b');
    c2.push(L'd');

// display contents " a b d"
    for each (wchar_t elem in c2.get_container())
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

## <a name="op_lteq"></a> İşleç&lt;(yığın) (STL/CLR) =

Küçüktür veya eşittir yığın karşılaştırma.

### <a name="syntax"></a>Sözdizimi

```cpp
template<typename Value,
    typename Container>
    bool operator<=(stack<Value, Container>% left,
        stack<Value, Container>% right);
```

#### <a name="parameters"></a>Parametreler

*Sol*<br/>
Karşılaştırılacak sol kapsayıcısı.

*sağ*<br/>
Karşılaştırılacak doğru kapsayıcısı.

### <a name="remarks"></a>Açıklamalar

İşleç işlevini döndürür `!(right < left)`. Test etmek için kullandığınız olmadığını *sol* sonra sıralı değil *doğru* iki yığınları karşılaştırılan öğe öğe olduğunda.

### <a name="example"></a>Örnek

```cpp
// cliext_stack_operator_le.cpp
// compile with: /clr
#include <cliext/stack>

typedef cliext::stack<wchar_t> Mystack;
int main()
    {
    Mystack c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// assign to a new container
    Mystack c2;
    c2.push(L'a');
    c2.push(L'b');
    c2.push(L'd');

// display contents " a b d"
    for each (wchar_t elem in c2.get_container())
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

## <a name="op_eq"></a> işleç == (yığın) (STL/CLR)

Yığın eşit karşılaştırması.

### <a name="syntax"></a>Sözdizimi

```cpp
template<typename Value,
    typename Container>
    bool operator==(stack<Value, Container>% left,
        stack<Value, Container>% right);
```

#### <a name="parameters"></a>Parametreler

*Sol*<br/>
Karşılaştırılacak sol kapsayıcısı.

*sağ*<br/>
Karşılaştırılacak doğru kapsayıcısı.

### <a name="remarks"></a>Açıklamalar

İşleç işlevini dizileri denetlediği yalnızca, true değerini döndürür *sol* ve *doğru* aynı uzunluğa sahip ve her konum için `i`, `left[i] ==` `right[i]`. Test etmek için kullandığınız olmadığını *sol* aynı sıralı *doğru* iki yığınları karşılaştırılan öğe öğe olduğunda.

### <a name="example"></a>Örnek

```cpp
// cliext_stack_operator_eq.cpp
// compile with: /clr
#include <cliext/stack>

typedef cliext::stack<wchar_t> Mystack;
int main()
    {
    Mystack c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// assign to a new container
    Mystack c2;
    c2.push(L'a');
    c2.push(L'b');
    c2.push(L'd');

// display contents " a b d"
    for each (wchar_t elem in c2.get_container())
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

## <a name="op_gt"></a> İşleç&gt; (yığın) (STL/CLR)

Yığını karşılaştırma büyük.

### <a name="syntax"></a>Sözdizimi

```cpp
template<typename Value,
    typename Container>
    bool operator>(stack<Value, Container>% left,
        stack<Value, Container>% right);
```

#### <a name="parameters"></a>Parametreler

*Sol*<br/>
Karşılaştırılacak sol kapsayıcısı.

*sağ*<br/>
Karşılaştırılacak doğru kapsayıcısı.

### <a name="remarks"></a>Açıklamalar

İşleç işlevini döndürür `right` `<` `left`. Test etmek için kullandığınız olmadığını *sol* sonra sıralı *doğru* iki yığınları karşılaştırılan öğe öğe olduğunda.

### <a name="example"></a>Örnek

```cpp
// cliext_stack_operator_gt.cpp
// compile with: /clr
#include <cliext/stack>

typedef cliext::stack<wchar_t> Mystack;
int main()
    {
    Mystack c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// assign to a new container
    Mystack c2;
    c2.push(L'a');
    c2.push(L'b');
    c2.push(L'd');

// display contents " a b d"
    for each (wchar_t elem in c2.get_container())
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

## <a name="op_gteq"></a> İşleç&gt;(yığın) (STL/CLR) =

Yığın büyüktür veya eşittir karşılaştırma.

### <a name="syntax"></a>Sözdizimi

```cpp
template<typename Value,
    typename Container>
    bool operator>=(stack<Value, Container>% left,
        stack<Value, Container>% right);
```

#### <a name="parameters"></a>Parametreler

*Sol*<br/>
Karşılaştırılacak sol kapsayıcısı.

*sağ*<br/>
Karşılaştırılacak doğru kapsayıcısı.

### <a name="remarks"></a>Açıklamalar

İşleç işlevini döndürür `!(left < right)`. Test etmek için kullandığınız olmadığını *sol* önce sıralı değil *doğru* iki yığınları karşılaştırılan öğe öğe olduğunda.

### <a name="example"></a>Örnek

```cpp
// cliext_stack_operator_ge.cpp
// compile with: /clr
#include <cliext/stack>

typedef cliext::stack<wchar_t> Mystack;
int main()
    {
    Mystack c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// assign to a new container
    Mystack c2;
    c2.push(L'a');
    c2.push(L'b');
    c2.push(L'd');

// display contents " a b d"
    for each (wchar_t elem in c2.get_container())
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