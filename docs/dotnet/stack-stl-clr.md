---
description: 'Daha fazla bilgi edinin: Stack (STL/CLR)'
title: yığın (STL/CLR)
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- cliext::stack
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
ms.openlocfilehash: 2903af3bce3f4eba09324202dbb071b11e440573
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97335380"
---
# <a name="stack-stlclr"></a>yığın (STL/CLR)

Şablon sınıfı, en son ilk erişimi olan öğelerin değişen uzunluklu bir dizisini denetleyen bir nesneyi tanımlar. Kapsayıcı bağdaştırıcısını, `stack` bir alttaki kapsayıcıyı bir aşağı açılan yığın olarak yönetmek için kullanırsınız.

Aşağıdaki açıklamada, `GValue` Ikinci *değeri* bir başvuru türü olmadığı sürece, bu örnekte olduğu gibi olur `Value^` . Benzer şekilde, `GContainer` ikincinin bir başvuru türü olmadığı ve bu durumda olduğu sürece *kapsayıcı* ile aynıdır `Container^` .

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
Temel alınan kapsayıcının türü.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<cliext/stack>

**Ad alanı:** cliext

## <a name="declarations"></a>Bildirimler

|Tür Tanımı|Açıklama|
|---------------------|-----------------|
|[stack::const_reference (STL/CLR)](#const_reference)|Bir öğe için sabit bir başvuru türü.|
|[stack::container_type (STL/CLR)](#container_type)|Temel alınan kapsayıcının türü.|
|[stack::difference_type (STL/CLR)](#difference_type)|İki öğe arasındaki işaretli mesafenin türü.|
|[stack::generic_container (STL/CLR)](#generic_container)|Kapsayıcı bağdaştırıcısının genel arabiriminin türü.|
|[stack::generic_value (STL/CLR)](#generic_value)|Kapsayıcı bağdaştırıcısının genel arabirimi için bir öğe türü.|
|[stack::reference (STL/CLR)](#reference)|Bir öğe için bir başvuru türü.|
|[stack::size_type (STL/CLR)](#size_type)|İki öğe arasındaki işaretli mesafenin türü.|
|[stack::value_type (STL/CLR)](#value_type)|Öğenin türü.|

|Üye İşlevi|Açıklama|
|---------------------|-----------------|
|[stack::assign (STL/CLR)](#assign)|Tüm öğeleri değiştirir.|
|[stack::empty (STL/CLR)](#empty)|Bir öğe olup olmadığını sınar.|
|[stack::get_container (STL/CLR)](#get_container)|Temel alınan kapsayıcıya erişir.|
|[stack::pop (STL/CLR)](#pop)|Son öğeyi kaldırır.|
|[stack::push (STL/CLR)](#push)|Yeni bir son öğe ekler.|
|[stack::size (STL/CLR)](#size)|Öğe sayısını sayar.|
|[stack::stack (STL/CLR)](#stack)|Bir kapsayıcı nesnesi oluşturur.|
|[stack::top (STL/CLR)](#top)|Son öğeye erişir.|
|[stack::to_array (STL/CLR)](#to_array)|Denetimli sırayı yeni bir diziye kopyalar.|

|Özellik|Açıklama|
|--------------|-----------------|
|[stack::top_item (STL/CLR)](#top_item)|Son öğeye erişir.|

|İşleç|Açıklama|
|--------------|-----------------|
|[stack::operator= (STL/CLR)](#op_as)|Denetlenen sırayı değiştirir.|
|[işleç! = (yığın) (STL/CLR)](#op_neq)|Bir `stack` nesnenin başka bir nesneye eşit olup olmadığını belirler `stack` .|
|[operator< (stack) (STL/CLR)](#op_lt)|Bir `stack` nesnenin başka bir nesneden daha az olup olmadığını belirler `stack` .|
|[işleç<= (yığın) (STL/CLR)](#op_lteq)|Bir `stack` nesnenin başka bir nesneden küçük veya ona eşit olup olmadığını belirler `stack` .|
|[operator = = (Stack) (STL/CLR)](#op_eq)|Bir `stack` nesnenin başka bir nesneye eşit olup olmadığını belirler `stack` .|
|[işleç> (yığın) (STL/CLR)](#op_gt)|Bir `stack` nesnenin başka bir nesneden daha büyük olup olmadığını belirler `stack` .|
|[işleç>= (yığın) (STL/CLR)](#op_gteq)|Bir `stack` nesnenin başka bir nesneden büyük veya ona eşit olup olmadığını belirler `stack` .|

## <a name="interfaces"></a>Arabirimler

|Arabirim|Açıklama|
|---------------|-----------------|
|<xref:System.ICloneable>|Bir nesneyi çoğaltın.|
|IStack\<Value, Container>|Genel kapsayıcı bağdaştırıcısını koruyun.|

## <a name="remarks"></a>Açıklamalar

Nesnesi, *değer* öğelerini depolayan ve isteğe bağlı olarak büyüdüğü tür *kapsayıcısı* içindeki temeldeki bir kapsayıcı aracılığıyla denetlediği sıra için depolamayı ayırır ve boşaltır. Nesne, erişimi yalnızca son öğeyi alarak, son bir ilk çıkar kuyruğu (LıFO kuyruğu veya yığın olarak da bilinir) uygulayarak kısıtlar.

## <a name="members"></a>Üyeler

## <a name="stackassign-stlclr"></a><a name="assign"></a> Stack:: Assign (STL/CLR)

Tüm öğeleri değiştirir.

### <a name="syntax"></a>Sözdizimi

```cpp
void assign(stack<Value, Container>% right);
```

#### <a name="parameters"></a>Parametreler

*Right*<br/>
Eklenecek kapsayıcı bağdaştırıcısı.

### <a name="remarks"></a>Açıklamalar

Üye işlevi, `right.get_container()` temel alınan kapsayıcıya atar. Yığının tüm içeriğini değiştirmek için bunu kullanırsınız.

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

## <a name="stackconst_reference-stlclr"></a><a name="const_reference"></a> Stack:: const_reference (STL/CLR)

Bir öğe için sabit bir başvuru türü.

### <a name="syntax"></a>Syntax

```cpp
typedef value_type% const_reference;
```

### <a name="remarks"></a>Açıklamalar

Türü bir öğeye sabit bir başvuru tanımlar.

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

## <a name="stackcontainer_type-stlclr"></a><a name="container_type"></a> Stack:: container_type (STL/CLR)

Temel alınan kapsayıcının türü.

### <a name="syntax"></a>Syntax

```cpp
typedef Container value_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, şablon parametresi *kapsayıcısının* eşanlamlısıdır.

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

## <a name="stackdifference_type-stlclr"></a><a name="difference_type"></a> yığın::d ifference_type (STL/CLR)

İki öğe arasındaki işaretli bir mesafe türü.

### <a name="syntax"></a>Syntax

```cpp
typedef int difference_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, büyük olasılıkla negatif bir öğe sayısını tanımlar.

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

## <a name="stackempty-stlclr"></a><a name="empty"></a> Stack:: Empty (STL/CLR)

Bir öğe olup olmadığını sınar.

### <a name="syntax"></a>Syntax

```cpp
bool empty();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi boş bir denetlenen dizi için true döndürür. [Stack:: size (STL/CLR)](#size)eşdeğerdir `() == 0` . Yığının boş olup olmadığını test etmek için kullanırsınız.

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

## <a name="stackgeneric_container-stlclr"></a><a name="generic_container"></a> Stack:: generic_container (STL/CLR)

Kapsayıcı bağdaştırıcısının genel arabiriminin türü.

### <a name="syntax"></a>Syntax

```cpp
typedef Microsoft::VisualC::StlClr::IStack<Value>
    generic_container;
```

### <a name="remarks"></a>Açıklamalar

Tür, bu şablon kapsayıcı bağdaştırıcısı sınıfı için genel arabirimi tanımlar.

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

## <a name="stackgeneric_value-stlclr"></a><a name="generic_value"></a> Stack:: generic_value (STL/CLR)

Kapsayıcının genel arabirimiyle kullanılacak öğe türü.

### <a name="syntax"></a>Syntax

```cpp
typedef GValue generic_value;
```

### <a name="remarks"></a>Açıklamalar

Tür, `GValue` Bu şablon kapsayıcı sınıfı için genel arabirimle birlikte kullanılacak saklı öğe değerini açıklayan türünde bir nesne tanımlar. ( `GValue` ya da `value_type` `value_type^` `value_type` bir başvuru türüdür.)

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

## <a name="stackget_container-stlclr"></a><a name="get_container"></a> Stack:: get_container (STL/CLR)

Temel alınan kapsayıcıya erişir.

### <a name="syntax"></a>Syntax

```cpp
container_type^ get_container();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, temel alınan kapsayıcı için bir tanıtıcı döndürür. Kapsayıcı sarmalayıcı tarafından uygulanan kısıtlamaları atlamak için bunu kullanırsınız.

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

## <a name="stackoperator-stlclr"></a><a name="op_as"></a> Stack:: operator = (STL/CLR)

Denetlenen sırayı değiştirir.

### <a name="syntax"></a>Sözdizimi

```cpp
stack <Value, Container>% operator=(stack <Value, Container>% right);
```

#### <a name="parameters"></a>Parametreler

*Right*<br/>
Kopyalanacak kapsayıcı bağdaştırıcısı.

### <a name="remarks"></a>Açıklamalar

Üye işleci nesnesine *sağ* kopyalar ve ardından döndürür **`*this`** . Denetlenen diziyi, denetimli sıranın bir kopyasıyla değiştirmek için bunu *kullanırsınız.*

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

## <a name="stackpop-stlclr"></a><a name="pop"></a> yığın::p op (STL/CLR)

Son öğeyi kaldırır.

### <a name="syntax"></a>Syntax

```cpp
void pop();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, denetimli sıranın son öğesini kaldırır ve bu boş olmamalıdır. Yığın, arka arkaya bir öğe ile kısaltmak için kullanılır.

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

## <a name="stackpush-stlclr"></a><a name="push"></a> yığın::p USH (STL/CLR)

Yeni bir son öğe ekler.

### <a name="syntax"></a>Syntax

```cpp
void push(value_type val);
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi denetlenen sıranın sonunda değeri olan bir öğe ekler `val` . Yığına başka bir öğe eklemek için bunu kullanırsınız.

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

## <a name="stackreference-stlclr"></a><a name="reference"></a> Stack:: Reference (STL/CLR)

Bir öğe için bir başvuru türü.

### <a name="syntax"></a>Syntax

```cpp
typedef value_type% reference;
```

### <a name="remarks"></a>Açıklamalar

Türü bir öğesi başvurusunu tanımlar.

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

## <a name="stacksize-stlclr"></a><a name="size"></a> Stack:: size (STL/CLR)

Öğe sayısını sayar.

### <a name="syntax"></a>Syntax

```cpp
size_type size();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi denetlenen sıranın uzunluğunu döndürür. Bu, şu anda denetlenen dizideki öğelerin sayısını tespit etmek için kullanılır. Her şey için, sıranın sıfır dışında bir boyut içerip içermediğini öğrenmek için bkz. [Stack:: Empty (STL/CLR)](#empty) `()` .

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

## <a name="stacksize_type-stlclr"></a><a name="size_type"></a> Stack:: size_type (STL/CLR)

İki öğe arasındaki işaretli bir mesafe türü.

### <a name="syntax"></a>Syntax

```cpp
typedef int size_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, negatif olmayan bir öğe sayısını tanımlar.

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

## <a name="stackstack-stlclr"></a><a name="stack"></a> Stack:: Stack (STL/CLR)

Kapsayıcı bağdaştırıcı nesnesi oluşturur.

### <a name="syntax"></a>Sözdizimi

```cpp
stack();
stack(stack<Value, Container>% right);
stack(stack<Value, Container>^ right);
explicit stack(container_type% wrapped);
```

#### <a name="parameters"></a>Parametreler

*Right*<br/>
Kopyalanacak nesne.

*ılamadı*<br/>
Kullanılacak sarmalanmış kapsayıcı.

### <a name="remarks"></a>Açıklamalar

Oluşturucu:

`stack();`

boş bir sarmalanmış kapsayıcı oluşturur. Boş bir ilk denetimli sıra belirtmek için bunu kullanırsınız.

Oluşturucu:

`stack(stack<Value, Container>% right);`

bir kopyası olan sarmalanmış bir kapsayıcı oluşturur `right.get_container()` . Yığın *nesnesi tarafından* denetlenen sıranın bir kopyası olan ilk denetimli bir sıra belirtmek için bunu kullanırsınız.

Oluşturucu:

`stack(stack<Value, Container>^ right);`

bir kopyası olan sarmalanmış bir kapsayıcı oluşturur `right->get_container()` . Yığın nesnesi tarafından denetlenen sıranın bir kopyası olan ilk denetimli bir sıra belirtmek için bunu kullanırsınız `*right` .

Oluşturucu:

`explicit stack(container_type% wrapped);`

Sarmalanan kapsayıcı olarak *Sarmalanan* mevcut kapsayıcıyı kullanır. Mevcut bir kapsayıcıdan yığın oluşturmak için bunu kullanırsınız.

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

## <a name="stackto_array-stlclr"></a><a name="to_array"></a> Stack:: to_array (STL/CLR)

Denetimli sırayı yeni bir diziye kopyalar.

### <a name="syntax"></a>Syntax

```cpp
cli::array<Value>^ to_array();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi denetlenen sırayı içeren bir dizi döndürür. Dizi biçiminde denetlenen sıranın bir kopyasını almak için bunu kullanırsınız.

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

## <a name="stacktop-stlclr"></a><a name="top"></a> Stack:: top (STL/CLR)

Son öğeye erişir.

### <a name="syntax"></a>Syntax

```cpp
reference top();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, denetimli sıranın son öğesine bir başvuru döndürür ve bu değer boş olmamalıdır. Bunu, olduğunu bildiğiniz zaman son öğeye erişmek için kullanabilirsiniz.

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

## <a name="stacktop_item-stlclr"></a><a name="top_item"></a> Stack:: top_item (STL/CLR)

Son öğeye erişir.

### <a name="syntax"></a>Syntax

```cpp
property value_type top_item;
```

### <a name="remarks"></a>Açıklamalar

Özelliği, denetimli sıranın son öğesine erişir, bu da boş olmamalıdır. Bunu, olduğunu bildiğiniz zaman son öğeyi okumak veya yazmak için kullanırsınız.

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

## <a name="stackvalue_type-stlclr"></a><a name="value_type"></a> Stack:: value_type (STL/CLR)

Öğenin türü.

### <a name="syntax"></a>Syntax

```cpp
typedef Value value_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, şablon parametre *değeri* için bir eş anlamlı.

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

## <a name="operator-stack-stlclr"></a><a name="op_neq"></a> işleç! = (yığın) (STL/CLR)

Yığın eşit değil karşılaştırması.

### <a name="syntax"></a>Sözdizimi

```cpp
template<typename Value,
    typename Container>
    bool operator!=(stack<Value, Container>% left,
        stack<Value, Container>% right);
```

#### <a name="parameters"></a>Parametreler

*tarafta*<br/>
Karşılaştırılacak sol kapsayıcı.

*Right*<br/>
Karşılaştırılacak doğru kapsayıcı.

### <a name="remarks"></a>Açıklamalar

İşleç işlevi döndürülür `!(left == right)` . İki yığın öğe öğesine göre karşılaştırıldığı sürece *sol* öğenin *doğru* şekilde sıralanmadığını test etmek için bunu kullanırsınız.

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

## <a name="operatorlt-stack-stlclr"></a><a name="op_lt"></a> işleç &lt; (yığın) (STL/CLR)

Yığın karşılaştırmadan daha küçük.

### <a name="syntax"></a>Sözdizimi

```cpp
template<typename Value,
    typename Container>
    bool operator<(stack<Value, Container>% left,
        stack<Value, Container>% right);
```

#### <a name="parameters"></a>Parametreler

*tarafta*<br/>
Karşılaştırılacak sol kapsayıcı.

*Right*<br/>
Karşılaştırılacak doğru kapsayıcı.

### <a name="remarks"></a>Açıklamalar

İşleç işlevi, `i` `!(right[i] < left[i])` bunun da doğru olduğu en düşük konum için true değerini döndürür `left[i] < right[i]` . Aksi halde, iki yığın öğe öğesine `left->` göre karşılaştırıldığı zaman, sol taraftan ayrılmadığını test etmek için bunu kullanarak bir [yığın:: size (STL/CLR)](#size) döndürülür `() <` `right->size()` .  

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

## <a name="operatorlt-stack-stlclr"></a><a name="op_lteq"></a> operator &lt; = (Stack) (STL/CLR)

Yığın küçüktür veya eşittir karşılaştırması.

### <a name="syntax"></a>Sözdizimi

```cpp
template<typename Value,
    typename Container>
    bool operator<=(stack<Value, Container>% left,
        stack<Value, Container>% right);
```

#### <a name="parameters"></a>Parametreler

*tarafta*<br/>
Karşılaştırılacak sol kapsayıcı.

*Right*<br/>
Karşılaştırılacak doğru kapsayıcı.

### <a name="remarks"></a>Açıklamalar

İşleç işlevi döndürülür `!(right < left)` . İki yığın öğe öğesine göre karşılaştırıldığı zaman *farenin sağ* *tarafında* sıralı olup olmadığını test etmek için kullanırsınız.

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

## <a name="operator-stack-stlclr"></a><a name="op_eq"></a> operator = = (Stack) (STL/CLR)

Yığın eşit karşılaştırması.

### <a name="syntax"></a>Sözdizimi

```cpp
template<typename Value,
    typename Container>
    bool operator==(stack<Value, Container>% left,
        stack<Value, Container>% right);
```

#### <a name="parameters"></a>Parametreler

*tarafta*<br/>
Karşılaştırılacak sol kapsayıcı.

*Right*<br/>
Karşılaştırılacak doğru kapsayıcı.

### <a name="remarks"></a>Açıklamalar

İşleç işlevi yalnızca *sol* ve *sağ* tarafından denetlenen diziler aynı uzunlukta ve her bir konum için aynı uzunluğa sahip olursa true değerini döndürür `i` `left[i] ==` `right[i]` . İki yığın öğe öğesine göre karşılaştırıldığı zaman *solinin* *doğru* olup olmadığını test etmek için bunu kullanırsınız.

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

## <a name="operatorgt-stack-stlclr"></a><a name="op_gt"></a> işleç &gt; (yığın) (STL/CLR)

Yığın karşılaştırmadan daha büyük.

### <a name="syntax"></a>Sözdizimi

```cpp
template<typename Value,
    typename Container>
    bool operator>(stack<Value, Container>% left,
        stack<Value, Container>% right);
```

#### <a name="parameters"></a>Parametreler

*tarafta*<br/>
Karşılaştırılacak sol kapsayıcı.

*Right*<br/>
Karşılaştırılacak doğru kapsayıcı.

### <a name="remarks"></a>Açıklamalar

İşleç işlevi döndürülür `right` `<` `left` . İki yığın öğe öğesine göre karşılaştırıldığı zaman, *sol* taraftaki *doğru* olup olmadığını test etmek için kullanırsınız.

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

## <a name="operatorgt-stack-stlclr"></a><a name="op_gteq"></a> operator &gt; = (Stack) (STL/CLR)

Yığın daha büyük veya eşit karşılaştırması.

### <a name="syntax"></a>Sözdizimi

```cpp
template<typename Value,
    typename Container>
    bool operator>=(stack<Value, Container>% left,
        stack<Value, Container>% right);
```

#### <a name="parameters"></a>Parametreler

*tarafta*<br/>
Karşılaştırılacak sol kapsayıcı.

*Right*<br/>
Karşılaştırılacak doğru kapsayıcı.

### <a name="remarks"></a>Açıklamalar

İşleç işlevi döndürülür `!(left < right)` . İki yığın öğe öğesine göre karşılaştırıldığı zaman *sağdan* *sola* doğru sıralanmadığını test etmek için bunu kullanırsınız.

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
