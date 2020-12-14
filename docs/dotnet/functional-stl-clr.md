---
description: 'Daha fazla bilgi edinin: işlevsel (STL/CLR)'
title: işlevsel (STL/CLR)
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- <cliext/functional>
- cliext::binary_delegate
- cliext::binary_delegate_noreturn
- cliext::binary_negate
- cliext::bind1st
- cliext::bind2nd
- cliext::binder1st
- cliext::binder2nd
- cliext::divides
- cliext::equal_to
- cliext::greater
- cliext::greater_equal
- cliext::less
- cliext::less_equal
- cliext::logical_and
- cliext::logical_not
- cliext::logical_or
- cliext::minus
- cliext::modulus
- cliext::multiplies
- cliext::negate
- cliext::not_equal_to
- cliext::not1
- cliext::not2
- cliext::plus
- cliext::unary_delegate
- cliext::unary_delegate_noreturn
- cliext::unary_negate
helpviewer_keywords:
- <functional> header [STL/CLR]
- <cliext/functional> header [STL/CLR]
- functional functions [STL/CLR]
- binary_delegate function [STL/CLR]
- binary_delegate_noreturn function [STL/CLR]
- binary_negate function [STL/CLR]
- bind1st function [STL/CLR]
- bind2nd function [STL/CLR]
- binder1st function [STL/CLR]
- binder2nd function [STL/CLR]
- divides function [STL/CLR]
- equal_to function [STL/CLR]
- greater function [STL/CLR]
- greater_equal function [STL/CLR]
- less function [STL/CLR]
- less_equal function [STL/CLR]
- logical_and function [STL/CLR]
- logical_not function [STL/CLR]
- logical_or function [STL/CLR]
- minus function [STL/CLR]
- modulus function [STL/CLR]
- multiplies function [STL/CLR]
- negate function [STL/CLR]
- not_equal_to function [STL/CLR]
- not1 function [STL/CLR]
- not2 function [STL/CLR]
- plus function [STL/CLR]
- unary_delegate function [STL/CLR]
- unary_delegate_noreturn function [STL/CLR]
- unary_negate function [STL/CLR]
ms.assetid: 88738b8c-5d37-4375-970e-a4442bf5efde
ms.openlocfilehash: 48db11b7a30ae46eb52ff73cd961759e6be93fc5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97223574"
---
# <a name="functional-stlclr"></a>işlevsel (STL/CLR)

`<cliext/functional>`Bir dizi şablon sınıfı ve ilgili şablon temsilcileri ve işlevleri tanımlamak IÇIN STL/CLR üstbilgisini ekleyin.

## <a name="syntax"></a>Syntax

```
#include <functional>
```

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<cliext/functional>

**Ad alanı:** cliext

## <a name="declarations"></a>Bildirimler

|Temsilci|Açıklama|
|--------------|-----------------|
|[binary_delegate (STL/CLR)](#binary_delegate)|İki bağımsız değişken temsilcisi.|
|[binary_delegate_noreturn (STL/CLR)](#binary_delegate_noreturn)|İki bağımsız değişken temsilcisi döndürüyor **`void`** .|
|[unary_delegate (STL/CLR)](#unary_delegate)|Bir bağımsız değişken temsilcisi.|
|[unary_delegate_noreturn (STL/CLR)](#unary_delegate_noreturn)|Bir bağımsız değişken temsilcisi döndürüyor **`void`** .|

|Sınıf|Açıklama|
|-----------|-----------------|
|[binary_negate (STL/CLR)](#binary_negate)|İki bağımsız değişkenli functor ile Negate 'e kadar functor.|
|[binder1st (STL/CLR)](#binder1st)|Birinci bağımsız değişkeni bir iki bağımsız değişken olan functor 'a bağlamak için functor.|
|[binder2nd (STL/CLR)](#binder2nd)|İkinci bağımsız değişkeni bir iki bağımsız değişken olan functor 'a bağlamak için functor.|
|[divides (STL/CLR)](#divides)|Functor 'ı bölün.|
|[equal_to (STL/CLR)](#equal_to)|Eşit karşılaştırma functor.|
|[greater (STL/CLR)](#greater)|Daha fazla karşılaştırma functor.|
|[greater_equal (STL/CLR)](#greater_equal)|Daha büyük veya eşit karşılaştırma functor.|
|[less (STL/CLR)](#less)|Daha az karşılaştırma functor.|
|[less_equal (STL/CLR)](#less_equal)|Daha az veya eşit karşılaştırma functor.|
|[logical_and (STL/CLR)](#logical_and)|Mantıksal ve functor.|
|[logical_not (STL/CLR)](#logical_not)|Mantıksal DEĞIL, functor.|
|[logical_or (STL/CLR)](#logical_or)|Mantıksal veya functor.|
|[minus (STL/CLR)](#minus)|Functor 'u çıkarın.|
|[modulus (STL/CLR)](#modulus)|Mod, functor.|
|[multiplies (STL/CLR)](#multiplies)|Functor 'ı çarpın.|
|[negate (STL/CLR)](#negate)|Bağımsız değişkenini döndürmek için functor.|
|[not_equal_to (STL/CLR)](#not_equal_to)|Eşit karşılaştırma functor.|
|[plus (STL/CLR)](#plus)|Functor ekleyin.|
|[unary_negate (STL/CLR)](#unary_negate)|Bir bağımsız değişken olan functor ile Negate 'e kadar functor.|

|İşlev|Açıklama|
|--------------|-----------------|
|[bind1st (STL/CLR)](#bind1st)|Bağımsız değişken ve functor için bir binder1st oluşturur.|
|[bind2nd (STL/CLR)](#bind2nd)|Bağımsız değişken ve functor için bir binder2nd oluşturur.|
|[not1 (STL/CLR)](#not1)|Functor için bir unary_negate oluşturur.|
|[not2 (STL/CLR)](#not2)|Functor için bir binary_negate oluşturur.|

## <a name="members"></a>Üyeler

## <a name="binary_delegate-stlclr"></a><a name="binary_delegate"></a> binary_delegate (STL/CLR)

Genereic sınıfı iki bağımsız değişkenli bir temsilciyi açıklar. Bağımsız değişkeni ve dönüş türleri bakımından bir temsilci belirtin.

### <a name="syntax"></a>Sözdizimi

```cpp
generic<typename Arg1,
    typename Arg2,
    typename Result>
    delegate Result binary_delegate(Arg1, Arg2);
```

#### <a name="parameters"></a>Parametreler

*Arg1*<br/>
İlk bağımsız değişkenin türü.

*Arg2*<br/>
İkinci bağımsız değişkenin türü.

*Sonuç*<br/>
Dönüş türü.

### <a name="remarks"></a>Açıklamalar

Genereic temsilcisi iki bağımsız değişkenli bir işlevi tanımlar.

Şunları unutmayın:

`binary_delegate<int, int, int> Fun1;`

`binary_delegate<int, int, int> Fun2;`

türler `Fun1` ve `Fun2` Şu şekilde eş anlamlılar:

`delegate int Fun1(int, int);`

`delegate int Fun2(int, int);`

aynı türde değildir.

### <a name="example"></a>Örnek

```cpp
// cliext_binary_delegate.cpp
// compile with: /clr
#include <cliext/functional>

bool key_compare(wchar_t left, wchar_t right)
    {
    return (left < right);
    }

typedef cliext::binary_delegate<wchar_t, wchar_t, bool> Mydelegate;
int main()
    {
    Mydelegate^ kcomp = gcnew Mydelegate(&key_compare);

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

## <a name="binary_delegate_noreturn-stlclr"></a><a name="binary_delegate_noreturn"></a> binary_delegate_noreturn (STL/CLR)

Genereic sınıfı, döndüren iki bağımsız değişkenli bir temsilciyi açıklar **`void`** . Bağımsız değişkeni olarak bir temsilci belirtin.

### <a name="syntax"></a>Sözdizimi

```cpp
generic<typename Arg1,
    typename Arg2>
    delegate void binary_delegate(Arg1, Arg2);
```

#### <a name="parameters"></a>Parametreler

*Arg1*<br/>
İlk bağımsız değişkenin türü.

*Arg2*<br/>
İkinci bağımsız değişkenin türü.

### <a name="remarks"></a>Açıklamalar

Genereic temsilcisi, döndüren iki bağımsız değişken işlevini tanımlar **`void`** .

Şunları unutmayın:

`binary_delegate_noreturn<int, int> Fun1;`

`binary_delegate_noreturn<int, int> Fun2;`

türler `Fun1` ve `Fun2` Şu şekilde eş anlamlılar:

`delegate void Fun1(int, int);`

`delegate void Fun2(int, int);`

aynı türde değildir.

### <a name="example"></a>Örnek

```cpp
// cliext_binary_delegate_noreturn.cpp
// compile with: /clr
#include <cliext/functional>

void key_compare(wchar_t left, wchar_t right)
    {
    System::Console::WriteLine("compare({0}, {1}) = {2}",
        left, right, left < right);
    }

typedef cliext::binary_delegate_noreturn<wchar_t, wchar_t> Mydelegate;
int main()
    {
    Mydelegate^ kcomp = gcnew Mydelegate(&key_compare);

    kcomp(L'a', L'a');
    kcomp(L'a', L'b');
    kcomp(L'b', L'a');
    System::Console::WriteLine();
    return (0);
    }
```

```Output
compare(a, a) = False
compare(a, b) = True
compare(b, a) = False
```

## <a name="binary_negate-stlclr"></a><a name="binary_negate"></a> binary_negate (STL/CLR)

Şablon sınıfı, çağrıldığında, depolanan iki bağımsız değişkenli functor mantıksal DEĞIL ' i döndüren bir functor tanımlar. Bu uygulamayı, depolanan functor açısından bir işlev nesnesi belirtmektir.

### <a name="syntax"></a>Sözdizimi

```cpp
template<typename Fun>
    ref class binary_negate
    { // wrap operator()
public:
    typedef Fun stored_function_type;
    typedef typename Fun::first_argument_type first_argument_type;
    typedef typename Fun::second_argument_type second_argument_type;
    typedef bool result_type;
    typedef Microsoft::VisualC::StlClr::BinaryDelegate<
        first_argument_type, second_argument_type, result_type>
        delegate_type;

    explicit binary_negate(Fun% functor);
    binary_negate(binary_negate<Arg>% right);

    result_type operator()(first_argument_type left,
        second_argument_type right);
    operator delegate_type^();
    };
```

#### <a name="parameters"></a>Parametreler

*Tablolar*<br/>
Depolanan functor türü.

### <a name="member-functions"></a>Üye İşlevleri

|Tür Tanımı|Açıklama|
|---------------------|-----------------|
|delegate_type|Genel temsilcinin türü.|
|first_argument_type|Functor ilk bağımsız değişkeninin türü.|
|result_type|Functor sonucunun türü.|
|second_argument_type|Functor ikinci bağımsız değişkeninin türü.|
|stored_function_type|Functor türü.|

|Üye|Açıklama|
|------------|-----------------|
|binary_negate|Functor 'ı oluşturur.|

|İşleç|Açıklama|
|--------------|-----------------|
|operator ()|İstenen işlevi hesaplar.|
|işleç delegate_type ^ ()|Bir temsilciye functor yayınlar.|

### <a name="remarks"></a>Açıklamalar

Şablon sınıfı, başka bir iki bağımsız değişken olan farklı bir iki bağımsız değişkeni depolayan bir iki bağımsız değişkenli functor tanımlar. Üye işlecini tanımlar, `operator()` böylece nesne bir işlev olarak çağrıldığında, bu, iki bağımsız değişkenle çağrılan depolanan functor 'un mantıksal değerini döndürür.

Ayrıca, nesneyi türü olan bir işlev bağımsız değişkeni olarak geçirebilir `delegate_type^` ve uygun şekilde dönüştürülecektir.

### <a name="example"></a>Örnek

```cpp
// cliext_binary_negate.cpp
// compile with: /clr
#include <cliext/algorithm>
#include <cliext/functional>
#include <cliext/vector>

typedef cliext::vector<int> Myvector;
int main()
    {
    Myvector c1;
    c1.push_back(4);
    c1.push_back(3);
    Myvector c2;
    c2.push_back(4);
    c2.push_back(4);
    Myvector c3(2, 0);

// display initial contents " 4 3" and " 4 4"
    for each (int elem in c1)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

    for each (int elem in c2)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display
    cliext::less<int> less_op;

    cliext::transform(c1.begin(), c1.begin() + 2,
        c2.begin(), c3.begin(),
        cliext::binary_negate<cliext::less<int> >(less_op));
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display with function
    cliext::transform(c1.begin(), c1.begin() + 2,
        c2.begin(), c3.begin(), cliext::not2(less_op));
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
4 3
4 4
1 0
1 0
```

## <a name="bind1st-stlclr"></a><a name="bind1st"></a> bind1st (STL/CLR)

`binder1st`Bağımsız değişken ve functor için bir üretir.

### <a name="syntax"></a>Syntax

```cpp
template<typename Fun,
    typename Arg>
    binder1st<Fun> bind1st(Fun% functor,
        Arg left);
```

#### <a name="template-parameters"></a>Şablon Parametreleri

*Değişkeni*<br/>
Bağımsız değişkenin türü.

*Tablolar*<br/>
Functor türü.

#### <a name="function-parameters"></a>İşlev parametreleri

*functor*<br/>
Kaydırmak için functor.

*tarafta*<br/>
Kaydıramanın ilk bağımsız değişkeni.

### <a name="remarks"></a>Açıklamalar

Şablon işlevi [binder1st (STL/CLR)](#binder1st)döndürür `<Fun>(functor, left)` . İki bağımsız değişkenli bir functor ve ilk bağımsız değişkenini ikinci bir bağımsız değişkenle çağıran bir tek değişkenli functor 'da sarmanın kolay bir yolu olarak kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// cliext_bind1st.cpp
// compile with: /clr
#include <cliext/algorithm>
#include <cliext/functional>
#include <cliext/vector>

typedef cliext::vector<int> Myvector;
int main()
    {
    Myvector c1;
    c1.push_back(4);
    c1.push_back(3);
    Myvector c3(2, 0);

// display initial contents " 4 3"
    for each (int elem in c1)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display
    cliext::minus<int> sub_op;
    cliext::binder1st<cliext::minus<int> > subfrom3(sub_op, 3);

    cliext::transform(c1.begin(), c1.begin() + 2, c3.begin(),
        subfrom3);
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display with function
    cliext::transform(c1.begin(), c1.begin() + 2, c3.begin(),
        bind1st(sub_op, 3));
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
4 3
-1 0
-1 0
```

## <a name="bind2nd-stlclr"></a><a name="bind2nd"></a> bind2nd (STL/CLR)

`binder2nd`Bağımsız değişken ve functor için bir üretir.

### <a name="syntax"></a>Syntax

```cpp
template<typename Fun,
    typename Arg>
    binder2nd<Fun> bind2nd(Fun% functor,
        Arg right);
```

#### <a name="template-parameters"></a>Şablon Parametreleri

*Değişkeni*<br/>
Bağımsız değişkenin türü.

*Tablolar*<br/>
Functor türü.

#### <a name="function-parameters"></a>İşlev parametreleri

*functor*<br/>
Kaydırmak için functor.

*Right*<br/>
Sarılacağı ikinci bağımsız değişken.

### <a name="remarks"></a>Açıklamalar

Şablon işlevi [binder2nd (STL/CLR)](#binder2nd)döndürür `<Fun>(functor, right)` . İki bağımsız değişken değerli bir functor ve ikinci bağımsız değişkenini bir ilk bağımsız değişkenle çağıran bir tek değişkenli functor 'da sarmanın kolay bir yolu olarak kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// cliext_bind2nd.cpp
// compile with: /clr
#include <cliext/algorithm>
#include <cliext/functional>
#include <cliext/vector>

typedef cliext::vector<int> Myvector;
int main()
    {
    Myvector c1;
    c1.push_back(4);
    c1.push_back(3);
    Myvector c3(2, 0);

// display initial contents " 4 3"
    for each (int elem in c1)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display
    cliext::minus<int> sub_op;
    cliext::binder2nd<cliext::minus<int> > sub4(sub_op, 4);

    cliext::transform(c1.begin(), c1.begin() + 2, c3.begin(),
        sub4);
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display with function
    cliext::transform(c1.begin(), c1.begin() + 2, c3.begin(),
        bind2nd(sub_op, 4));
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
4 3
0 -1
0 -1
```

## <a name="binder1st-stlclr"></a><a name="binder1st"></a> binder1st (STL/CLR)

Şablon sınıfı, çağrıldığında bir bağımsız değişken functor tanımlar, bu, çağrıldığında, depolanan ilk bağımsız değişkeni ve sağlanan ikinci bağımsız değişkeni ile çağrılan, depolanan iki bağımsız değişkenli functor 'u döndürür. Bu uygulamayı, depolanan functor açısından bir işlev nesnesi belirtmektir.

### <a name="syntax"></a>Sözdizimi

```cpp
template<typename Fun>
    ref class binder1st
    { // wrap operator()
public:
    typedef Fun stored_function_type;
    typedef typename Fun::first_argument_type first_argument_type;
    typedef typename Fun::second_argument_type second_argument_type;
    typedef typename Fun:result_type result_type;
    typedef Microsoft::VisualC::StlClr::UnaryDelegate<
        second_argument_type, result_type>
        delegate_type;

    binder1st(Fun% functor, first_argument_type left);
    binder1st(binder1st<Arg>% right);

    result_type operator()(second_argument_type right);
    operator delegate_type^();
    };
```

#### <a name="parameters"></a>Parametreler

*Tablolar*<br/>
Depolanan functor türü.

### <a name="member-functions"></a>Üye İşlevleri

|Tür Tanımı|Açıklama|
|---------------------|-----------------|
|delegate_type|Genel temsilcinin türü.|
|first_argument_type|Functor ilk bağımsız değişkeninin türü.|
|result_type|Functor sonucunun türü.|
|second_argument_type|Functor ikinci bağımsız değişkeninin türü.|
|stored_function_type|Functor türü.|

|Üye|Açıklama|
|------------|-----------------|
|binder1st|Functor 'ı oluşturur.|

|İşleç|Açıklama|
|--------------|-----------------|
|operator ()|İstenen işlevi hesaplar.|
|işleç delegate_type ^ ()|Bir temsilciye functor yayınlar.|

### <a name="remarks"></a>Açıklamalar

Şablon sınıfı, iki bağımsız değişkenli bir functor ve ilk bağımsız değişkeni depolayan bir bağımsız değişken functor tanımlar. Üye işlecini tanımlar, `operator()` böylece nesne bir işlev olarak çağrıldığında, depolanan functor 'u depolanan ilk bağımsız değişkenle ve sağlanan ikinci bağımsız değişkenle çağırma sonucunu döndürür.

Ayrıca, nesneyi türü olan bir işlev bağımsız değişkeni olarak geçirebilir `delegate_type^` ve uygun şekilde dönüştürülecektir.

### <a name="example"></a>Örnek

```cpp
// cliext_binder1st.cpp
// compile with: /clr
#include <cliext/algorithm>
#include <cliext/functional>
#include <cliext/vector>

typedef cliext::vector<int> Myvector;
int main()
    {
    Myvector c1;
    c1.push_back(4);
    c1.push_back(3);
    Myvector c3(2, 0);

// display initial contents " 4 3"
    for each (int elem in c1)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display
    cliext::minus<int> sub_op;
    cliext::binder1st<cliext::minus<int> > subfrom3(sub_op, 3);

    cliext::transform(c1.begin(), c1.begin() + 2, c3.begin(),
        subfrom3);
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display with function
    cliext::transform(c1.begin(), c1.begin() + 2, c3.begin(),
        bind1st(sub_op, 3));
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
4 3
-1 0
-1 0
```

## <a name="binder2nd-stlclr"></a><a name="binder2nd"></a> binder2nd (STL/CLR)

Şablon sınıfı, çağrıldığında bir bağımsız değişken functor tanımlar, çağrıldığında, sağlanan ilk bağımsız değişkeni ve depolanan ikinci bağımsız değişkeni ile çağrılan, depolanan iki bağımsız değişkenli functor ' ı döndürür. Bu uygulamayı, depolanan functor açısından bir işlev nesnesi belirtmektir.

### <a name="syntax"></a>Sözdizimi

```cpp
template<typename Fun>
    ref class binder2nd
    { // wrap operator()
public:
    typedef Fun stored_function_type;
    typedef typename Fun::first_argument_type first_argument_type;
    typedef typename Fun::second_argument_type second_argument_type;
    typedef typename Fun:result_type result_type;
    typedef Microsoft::VisualC::StlClr::UnaryDelegate<
        first_argument_type, result_type>
        delegate_type;

    binder2nd(Fun% functor, second_argument_type left);
    binder2nd(binder2nd<Arg>% right);

    result_type operator()(first_argument_type right);
    operator delegate_type^();
    };
```

#### <a name="parameters"></a>Parametreler

*Tablolar*<br/>
Depolanan functor türü.

### <a name="member-functions"></a>Üye İşlevleri

|Tür Tanımı|Açıklama|
|---------------------|-----------------|
|delegate_type|Genel temsilcinin türü.|
|first_argument_type|Functor ilk bağımsız değişkeninin türü.|
|result_type|Functor sonucunun türü.|
|second_argument_type|Functor ikinci bağımsız değişkeninin türü.|
|stored_function_type|Functor türü.|

|Üye|Açıklama|
|------------|-----------------|
|binder2nd|Functor 'ı oluşturur.|

|İşleç|Açıklama|
|--------------|-----------------|
|operator ()|İstenen işlevi hesaplar.|
|işleç delegate_type ^ ()|Bir temsilciye functor yayınlar.|

### <a name="remarks"></a>Açıklamalar

Şablon sınıfı, iki bağımsız değişkenli bir functor ve ikinci bir bağımsız değişken depolayan bir bağımsız değişken functor tanımlar. Üye işlecini tanımlar, `operator()` böylece nesne bir işlev olarak çağrıldığında, depolanan functor 'u sağlanan ilk bağımsız değişkenle ve depolanan ikinci bağımsız değişkenle çağırma sonucunu döndürür.

Ayrıca, nesneyi türü olan bir işlev bağımsız değişkeni olarak geçirebilir `delegate_type^` ve uygun şekilde dönüştürülecektir.

### <a name="example"></a>Örnek

```cpp
// cliext_binder2nd.cpp
// compile with: /clr
#include <cliext/algorithm>
#include <cliext/functional>
#include <cliext/vector>

typedef cliext::vector<int> Myvector;
int main()
    {
    Myvector c1;
    c1.push_back(4);
    c1.push_back(3);
    Myvector c3(2, 0);

// display initial contents " 4 3"
    for each (int elem in c1)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display
    cliext::minus<int> sub_op;
    cliext::binder2nd<cliext::minus<int> > sub4(sub_op, 4);

    cliext::transform(c1.begin(), c1.begin() + 2, c3.begin(),
        sub4);
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display with function
    cliext::transform(c1.begin(), c1.begin() + 2, c3.begin(),
        bind2nd(sub_op, 4));
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
4 3
0 -1
0 -1
```

## <a name="divides-stlclr"></a><a name="divides"></a> böler (STL/CLR)

Şablon sınıfı, çağrıldığında, ikinciden bölünen ilk bağımsız değişkeni döndüren bir functor tanımlar. Bağımsız değişken türü açısından bir işlev nesnesi belirtin.

### <a name="syntax"></a>Sözdizimi

```cpp
template<typename Arg>
    ref class divides
    { // wrap operator()
public:
    typedef Arg first_argument_type;
    typedef Arg second_argument_type;
    typedef Arg result_type;
    typedef Microsoft::VisualC::StlClr::BinaryDelegate<
        first_argument_type, second_argument_type, result_type>
        delegate_type;

    divides();
    divides(divides<Arg>% right);

    result_type operator()(first_argument_type left,
        second_argument_type right);
    operator delegate_type^();
    };
```

#### <a name="parameters"></a>Parametreler

*Değişkeni*<br/>
Bağımsız değişkenlerin türü ve dönüş değeri.

### <a name="member-functions"></a>Üye İşlevleri

|Tür Tanımı|Açıklama|
|---------------------|-----------------|
|delegate_type|Genel temsilcinin türü.|
|first_argument_type|Functor ilk bağımsız değişkeninin türü.|
|result_type|Functor sonucunun türü.|
|second_argument_type|Functor ikinci bağımsız değişkeninin türü.|

|Üye|Açıklama|
|------------|-----------------|
|böler|Functor 'ı oluşturur.|

|İşleç|Açıklama|
|--------------|-----------------|
|operator ()|İstenen işlevi hesaplar.|
|işleç delegate_type ^ ()|Bir temsilciye functor yayınlar.|

### <a name="remarks"></a>Açıklamalar

Şablon sınıfı, bir iki bağımsız değişken olan functor tanımlar. Üye işlecini tanımlar, `operator()` böylece nesne bir işlev olarak çağrıldığında, ikinciden bölünen ilk bağımsız değişkeni döndürür.

Ayrıca, nesneyi türü olan bir işlev bağımsız değişkeni olarak geçirebilir `delegate_type^` ve uygun şekilde dönüştürülecektir.

### <a name="example"></a>Örnek

```cpp
// cliext_divides.cpp
// compile with: /clr
#include <cliext/algorithm>
#include <cliext/functional>
#include <cliext/vector>

typedef cliext::vector<int> Myvector;
int main()
    {
    Myvector c1;
    c1.push_back(4);
    c1.push_back(3);
    Myvector c2;
    c2.push_back(2);
    c2.push_back(1);
    Myvector c3(2, 0);

// display initial contents " 4 3" and " 2 1"
    for each (int elem in c1)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

    for each (int elem in c2)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display
    cliext::transform(c1.begin(), c1.begin() + 2,
        c2.begin(), c3.begin(), cliext::divides<int>());
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
4 3
2 1
2 3
```

## <a name="equal_to-stlclr"></a><a name="equal_to"></a> equal_to (STL/CLR)

Şablon sınıfı, çağrıldığında, yalnızca ilk bağımsız değişken ikinciye eşitse true değerini döndüren bir functor tanımlar. Bağımsız değişken türü açısından bir işlev nesnesi belirtin.

### <a name="syntax"></a>Sözdizimi

```cpp
template<typename Arg>
    ref class equal_to
    { // wrap operator()
public:
    typedef Arg first_argument_type;
    typedef Arg second_argument_type;
    typedef bool result_type;
    typedef Microsoft::VisualC::StlClr::BinaryDelegate<
        first_argument_type, second_argument_type, result_type>
        delegate_type;

    equal_to();
    equal_to(equal_to<Arg>% right);

    result_type operator()(first_argument_type left,
        second_argument_type right);
    operator delegate_type^();
    };
```

#### <a name="parameters"></a>Parametreler

*Değişkeni*<br/>
Bağımsız değişkenlerin türü.

### <a name="member-functions"></a>Üye İşlevleri

|Tür Tanımı|Açıklama|
|---------------------|-----------------|
|delegate_type|Genel temsilcinin türü.|
|first_argument_type|Functor ilk bağımsız değişkeninin türü.|
|result_type|Functor sonucunun türü.|
|second_argument_type|Functor ikinci bağımsız değişkeninin türü.|

|Üye|Açıklama|
|------------|-----------------|
|equal_to|Functor 'ı oluşturur.|

|İşleç|Açıklama|
|--------------|-----------------|
|operator ()|İstenen işlevi hesaplar.|
|işleç delegate_type ^ ()|Bir temsilciye functor yayınlar.|

### <a name="remarks"></a>Açıklamalar

Şablon sınıfı, bir iki bağımsız değişken olan functor tanımlar. Üye işlecini tanımlar, `operator()` böylece nesne bir işlev olarak çağrıldığında true, yalnızca ilk bağımsız değişken ikinciye eşitse true değerini döndürür.

Ayrıca, nesneyi türü olan bir işlev bağımsız değişkeni olarak geçirebilir `delegate_type^` ve uygun şekilde dönüştürülecektir.

### <a name="example"></a>Örnek

```cpp
// cliext_equal_to.cpp
// compile with: /clr
#include <cliext/algorithm>
#include <cliext/functional>
#include <cliext/vector>

typedef cliext::vector<int> Myvector;
int main()
    {
    Myvector c1;
    c1.push_back(4);
    c1.push_back(3);
    Myvector c2;
    c2.push_back(4);
    c2.push_back(4);
    Myvector c3(2, 0);

// display initial contents " 4 3" and " 4 4"
    for each (int elem in c1)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

    for each (int elem in c2)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display
    cliext::transform(c1.begin(), c1.begin() + 2,
        c2.begin(), c3.begin(), cliext::equal_to<int>());
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
4 3
4 4
1 0
```

## <a name="greater-stlclr"></a><a name="greater"></a> daha büyük (STL/CLR)

Şablon sınıfı, çağrıldığında, yalnızca ilk bağımsız değişken ikinciden büyükse true değerini döndüren bir functor tanımlar. Bağımsız değişken türü açısından bir işlev nesnesi belirtin.

### <a name="syntax"></a>Sözdizimi

```cpp
template<typename Arg>
    ref class greater
    { // wrap operator()
public:
    typedef Arg first_argument_type;
    typedef Arg second_argument_type;
    typedef bool result_type;
    typedef Microsoft::VisualC::StlClr::BinaryDelegate<
        first_argument_type, second_argument_type, result_type>
        delegate_type;

    greater();
    greater(greater<Arg>% right);

    result_type operator()(first_argument_type left,
        second_argument_type right);
    operator delegate_type^();
    };
```

#### <a name="parameters"></a>Parametreler

*Değişkeni*<br/>
Bağımsız değişkenlerin türü.

### <a name="member-functions"></a>Üye İşlevleri

|Tür Tanımı|Açıklama|
|---------------------|-----------------|
|delegate_type|Genel temsilcinin türü.|
|first_argument_type|Functor ilk bağımsız değişkeninin türü.|
|result_type|Functor sonucunun türü.|
|second_argument_type|Functor ikinci bağımsız değişkeninin türü.|

|Üye|Açıklama|
|------------|-----------------|
|büyüktür|Functor 'ı oluşturur.|

|İşleç|Açıklama|
|--------------|-----------------|
|operator ()|İstenen işlevi hesaplar.|
|işleç delegate_type ^|Bir temsilciye functor yayınlar.|

### <a name="remarks"></a>Açıklamalar

Şablon sınıfı, bir iki bağımsız değişken olan functor tanımlar. Üye işlecini tanımlar, `operator()` böylece nesne bir işlev olarak çağrıldığında true, yalnızca ilk bağımsız değişken ikinciden büyükse true değerini döndürür.

Ayrıca, nesneyi türü olan bir işlev bağımsız değişkeni olarak geçirebilir `delegate_type^` ve uygun şekilde dönüştürülecektir.

### <a name="example"></a>Örnek

```cpp
// cliext_greater.cpp
// compile with: /clr
#include <cliext/algorithm>
#include <cliext/functional>
#include <cliext/vector>

typedef cliext::vector<int> Myvector;
int main()
    {
    Myvector c1;
    c1.push_back(4);
    c1.push_back(3);
    Myvector c2;
    c2.push_back(3);
    c2.push_back(3);
    Myvector c3(2, 0);

// display initial contents " 4 3" and " 3 3"
    for each (int elem in c1)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

    for each (int elem in c2)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display
    cliext::transform(c1.begin(), c1.begin() + 2,
        c2.begin(), c3.begin(), cliext::greater<int>());
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
4 3
3 3
1 0
```

## <a name="greater_equal-stlclr"></a><a name="greater_equal"></a> greater_equal (STL/CLR)

Şablon sınıfı, çağrıldığında, yalnızca ilk bağımsız değişken ikinciden büyük veya buna eşitse true değerini döndüren bir functor tanımlar. Bağımsız değişken türü açısından bir işlev nesnesi belirtin.

### <a name="syntax"></a>Sözdizimi

```cpp
template<typename Arg>
    ref class greater_equal
    { // wrap operator()
public:
    typedef Arg first_argument_type;
    typedef Arg second_argument_type;
    typedef bool result_type;
    typedef Microsoft::VisualC::StlClr::BinaryDelegate<
        first_argument_type, second_argument_type, result_type>
        delegate_type;

    greater_equal();
    greater_equal(greater_equal<Arg>% right);

    result_type operator()(first_argument_type left,
        second_argument_type right);
    operator delegate_type^();
    };
```

#### <a name="parameters"></a>Parametreler

*Değişkeni*<br/>
Bağımsız değişkenlerin türü.

### <a name="member-functions"></a>Üye İşlevleri

|Tür Tanımı|Açıklama|
|---------------------|-----------------|
|delegate_type|Genel temsilcinin türü.|
|first_argument_type|Functor ilk bağımsız değişkeninin türü.|
|result_type|Functor sonucunun türü.|
|second_argument_type|Functor ikinci bağımsız değişkeninin türü.|

|Üye|Açıklama|
|------------|-----------------|
|greater_equal|Functor 'ı oluşturur.|

|İşleç|Açıklama|
|--------------|-----------------|
|operator ()|İstenen işlevi hesaplar.|
|işleç delegate_type ^|Bir temsilciye functor yayınlar.|

### <a name="remarks"></a>Açıklamalar

Şablon sınıfı, bir iki bağımsız değişken olan functor tanımlar. Üye işlecini tanımlar, `operator()` böylece nesne bir işlev olarak çağrıldığında true, yalnızca ilk bağımsız değişken ikinciden büyük veya buna eşitse true değerini döndürür.

Ayrıca, nesneyi türü olan bir işlev bağımsız değişkeni olarak geçirebilir `delegate_type^` ve uygun şekilde dönüştürülecektir.

### <a name="example"></a>Örnek

```cpp
// cliext_greater_equal.cpp
// compile with: /clr
#include <cliext/algorithm>
#include <cliext/functional>
#include <cliext/vector>

typedef cliext::vector<int> Myvector;
int main()
    {
    Myvector c1;
    c1.push_back(4);
    c1.push_back(3);
    Myvector c2;
    c2.push_back(4);
    c2.push_back(4);
    Myvector c3(2, 0);

// display initial contents " 4 3" and " 4 4"
    for each (int elem in c1)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

    for each (int elem in c2)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display
    cliext::transform(c1.begin(), c1.begin() + 2,
        c2.begin(), c3.begin(), cliext::greater_equal<int>());
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
4 3
4 4
1 0
```

## <a name="less-stlclr"></a><a name="less"></a> daha az (STL/CLR)

Şablon sınıfı, çağrıldığında, yalnızca ilk bağımsız değişken ikinciden küçükse true değerini döndüren bir functor tanımlar. Bağımsız değişken türü açısından bir işlev nesnesi belirtin.

### <a name="syntax"></a>Sözdizimi

```cpp
template<typename Arg>
    ref class less
    { // wrap operator()
public:
    typedef Arg first_argument_type;
    typedef Arg second_argument_type;
    typedef bool result_type;
    typedef Microsoft::VisualC::StlClr::BinaryDelegate<
        first_argument_type, second_argument_type, result_type>
        delegate_type;

    less();
    less(less<Arg>% right);

    result_type operator()(first_argument_type left,
        second_argument_type right);
    operator delegate_type^();
    };
```

#### <a name="parameters"></a>Parametreler

*Değişkeni*<br/>
Bağımsız değişkenlerin türü.

### <a name="member-functions"></a>Üye İşlevleri

|Tür Tanımı|Açıklama|
|---------------------|-----------------|
|delegate_type|Genel temsilcinin türü.|
|first_argument_type|Functor ilk bağımsız değişkeninin türü.|
|result_type|Functor sonucunun türü.|
|second_argument_type|Functor ikinci bağımsız değişkeninin türü.|

|Üye|Açıklama|
|------------|-----------------|
|daha az|Functor 'ı oluşturur.|

|İşleç|Açıklama|
|--------------|-----------------|
|operator ()|İstenen işlevi hesaplar.|
|işleç delegate_type ^|Bir temsilciye functor yayınlar.|

### <a name="remarks"></a>Açıklamalar

Şablon sınıfı, bir iki bağımsız değişken olan functor tanımlar. Üye işlecini tanımlar, `operator()` böylece nesne bir işlev olarak çağrıldığında true, yalnızca ilk bağımsız değişken ikinciden küçükse true değerini döndürür.

Ayrıca, nesneyi türü olan bir işlev bağımsız değişkeni olarak geçirebilir `delegate_type^` ve uygun şekilde dönüştürülecektir.

### <a name="example"></a>Örnek

```cpp
// cliext_less.cpp
// compile with: /clr
#include <cliext/algorithm>
#include <cliext/functional>
#include <cliext/vector>

typedef cliext::vector<int> Myvector;
int main()
    {
    Myvector c1;
    c1.push_back(4);
    c1.push_back(3);
    Myvector c2;
    c2.push_back(4);
    c2.push_back(4);
    Myvector c3(2, 0);

// display initial contents " 4 3" and " 4 4"
    for each (int elem in c1)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

    for each (int elem in c2)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display
    cliext::transform(c1.begin(), c1.begin() + 2,
        c2.begin(), c3.begin(), cliext::less<int>());
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
4 3
4 4
0 1
```

## <a name="less_equal-stlclr"></a><a name="less_equal"></a> less_equal (STL/CLR)

Şablon sınıfı, çağrıldığında, yalnızca ilk bağımsız değişken ikinciden küçük veya ona eşitse true değerini döndüren bir functor tanımlar. Bağımsız değişken türü açısından bir işlev nesnesi belirtin.

### <a name="syntax"></a>Sözdizimi

```cpp
template<typename Arg>
    ref class less_equal
    { // wrap operator()
public:
    typedef Arg first_argument_type;
    typedef Arg second_argument_type;
    typedef bool result_type;
    typedef Microsoft::VisualC::StlClr::BinaryDelegate<
        first_argument_type, second_argument_type, result_type>
        delegate_type;

    less_equal();
    less_equal(less_equal<Arg>% right);

    result_type operator()(first_argument_type left,
        second_argument_type right);
    operator delegate_type^();
    };
```

#### <a name="parameters"></a>Parametreler

*Değişkeni*<br/>
Bağımsız değişkenlerin türü.

### <a name="member-functions"></a>Üye İşlevleri

|Tür Tanımı|Açıklama|
|---------------------|-----------------|
|delegate_type|Genel temsilcinin türü.|
|first_argument_type|Functor ilk bağımsız değişkeninin türü.|
|result_type|Functor sonucunun türü.|
|second_argument_type|Functor ikinci bağımsız değişkeninin türü.|

|Üye|Açıklama|
|------------|-----------------|
|less_equal|Functor 'ı oluşturur.|

|İşleç|Açıklama|
|--------------|-----------------|
|operator ()|İstenen işlevi hesaplar.|
|işleç delegate_type ^|Bir temsilciye functor yayınlar.|

### <a name="remarks"></a>Açıklamalar

Şablon sınıfı, bir iki bağımsız değişken olan functor tanımlar. Üye işlecini tanımlar, `operator()` böylece nesne bir işlev olarak çağrıldığında true, yalnızca ilk bağımsız değişken ikinciden küçükse true değerini döndürür.

Ayrıca, nesneyi türü olan bir işlev bağımsız değişkeni olarak geçirebilir `delegate_type^` ve uygun şekilde dönüştürülecektir.

### <a name="example"></a>Örnek

```cpp
// cliext_less_equal.cpp
// compile with: /clr
#include <cliext/algorithm>
#include <cliext/functional>
#include <cliext/vector>

typedef cliext::vector<int> Myvector;
int main()
    {
    Myvector c1;
    c1.push_back(4);
    c1.push_back(3);
    Myvector c2;
    c2.push_back(3);
    c2.push_back(3);
    Myvector c3(2, 0);

// display initial contents " 4 3" and " 3 3"
    for each (int elem in c1)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

    for each (int elem in c2)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display
    cliext::transform(c1.begin(), c1.begin() + 2,
        c2.begin(), c3.begin(), cliext::less_equal<int>());
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
4 3
3 3
0 1
```

## <a name="logical_and-stlclr"></a><a name="logical_and"></a> logical_and (STL/CLR)

Şablon sınıfı, çağrıldığında, yalnızca ilk bağımsız değişken ve ikinci test doğru olduğunda true değeri döndüren bir functor tanımlar. Bağımsız değişken türü açısından bir işlev nesnesi belirtin.

### <a name="syntax"></a>Sözdizimi

```cpp
template<typename Arg>
    ref class logical_and
    { // wrap operator()
public:
    typedef Arg first_argument_type;
    typedef Arg second_argument_type;
    typedef bool result_type;
    typedef Microsoft::VisualC::StlClr::BinaryDelegate<
        first_argument_type, second_argument_type, result_type>
        delegate_type;

    logical_and();
    logical_and(logical_and<Arg>% right);

    result_type operator()(first_argument_type left,
        second_argument_type right);
    operator delegate_type^();
    };
```

#### <a name="parameters"></a>Parametreler

*Değişkeni*<br/>
Bağımsız değişkenlerin türü.

### <a name="member-functions"></a>Üye İşlevleri

|Tür Tanımı|Açıklama|
|---------------------|-----------------|
|delegate_type|Genel temsilcinin türü.|
|first_argument_type|Functor ilk bağımsız değişkeninin türü.|
|result_type|Functor sonucunun türü.|
|second_argument_type|Functor ikinci bağımsız değişkeninin türü.|

|Üye|Açıklama|
|------------|-----------------|
|logical_and|Functor 'ı oluşturur.|

|İşleç|Açıklama|
|--------------|-----------------|
|operator ()|İstenen işlevi hesaplar.|
|işleç delegate_type ^|Bir temsilciye functor yayınlar.|

### <a name="remarks"></a>Açıklamalar

Şablon sınıfı, bir iki bağımsız değişken olan functor tanımlar. Üye işlecini tanımlar, `operator()` böylece nesne bir işlev olarak çağrıldığında true, yalnızca ilk bağımsız değişken ve ikinci test doğru olarak döndürülür.

Ayrıca, nesneyi türü olan bir işlev bağımsız değişkeni olarak geçirebilir `delegate_type^` ve uygun şekilde dönüştürülecektir.

### <a name="example"></a>Örnek

```cpp
// cliext_logical_and.cpp
// compile with: /clr
#include <cliext/algorithm>
#include <cliext/functional>
#include <cliext/vector>

typedef cliext::vector<int> Myvector;
int main()
    {
    Myvector c1;
    c1.push_back(2);
    c1.push_back(0);
    Myvector c2;
    c2.push_back(3);
    c2.push_back(0);
    Myvector c3(2, 0);

// display initial contents " 1 0" and " 1 0"
    for each (int elem in c1)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

    for each (int elem in c2)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display
    cliext::transform(c1.begin(), c1.begin() + 2,
        c2.begin(), c3.begin(), cliext::logical_and<int>());
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
2 0
3 0
1 0
```

## <a name="logical_not-stlclr"></a><a name="logical_not"></a> logical_not (STL/CLR)

Şablon sınıfı, çağrıldığında, yalnızca bağımsız değişkeninin yanlış olarak test edildiğinde true değerini döndüren bir functor tanımlar. Bağımsız değişken türü açısından bir işlev nesnesi belirtin.

### <a name="syntax"></a>Sözdizimi

```cpp
template<typename Arg>
    ref class logical_not
    { // wrap operator()
public:
    typedef Arg argument_type;
    typedef bool result_type;
    typedef Microsoft::VisualC::StlClr::UnaryDelegate<
        argument_type, result_type>
        delegate_type;

    logical_not();
    logical_not(logical_not<Arg> %right);

    result_type operator()(argument_type left);
    operator delegate_type^();
    };
```

#### <a name="parameters"></a>Parametreler

*Değişkeni*<br/>
Bağımsız değişkenlerin türü.

### <a name="member-functions"></a>Üye İşlevleri

|Tür Tanımı|Açıklama|
|---------------------|-----------------|
|argument_type|Functor bağımsız değişkeninin türü.|
|delegate_type|Genel temsilcinin türü.|
|result_type|Functor sonucunun türü.|

|Üye|Açıklama|
|------------|-----------------|
|logical_not|Functor 'ı oluşturur.|

|İşleç|Açıklama|
|--------------|-----------------|
|operator ()|İstenen işlevi hesaplar.|
|işleç delegate_type ^|Bir temsilciye functor yayınlar.|

### <a name="remarks"></a>Açıklamalar

Şablon sınıfı, bir bağımsız değişken functor tanımlar. Üye işlecini tanımlar, `operator()` böylece nesne bir işlev olarak çağrıldığında true, yalnızca bağımsız değişkeni false olarak test edildiğinde true değerini döndürür.

Ayrıca, nesneyi türü olan bir işlev bağımsız değişkeni olarak geçirebilir `delegate_type^` ve uygun şekilde dönüştürülecektir.

### <a name="example"></a>Örnek

```cpp
// cliext_logical_not.cpp
// compile with: /clr
#include <cliext/algorithm>
#include <cliext/functional>
#include <cliext/vector>

typedef cliext::vector<int> Myvector;
int main()
    {
    Myvector c1;
    c1.push_back(4);
    c1.push_back(0);
    Myvector c3(2, 0);

// display initial contents " 4 0"
    for each (int elem in c1)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display
    cliext::transform(c1.begin(), c1.begin() + 2,
        c3.begin(), cliext::logical_not<int>());
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
4 0
0 1
```

## <a name="logical_or-stlclr"></a><a name="logical_or"></a> logical_or (STL/CLR)

Şablon sınıfı, çağrıldığında, yalnızca ilk bağımsız değişken ya da ikinci testlerin true olması durumunda true değerini döndüren bir functor tanımlar. Bağımsız değişken türü açısından bir işlev nesnesi belirtin.

### <a name="syntax"></a>Sözdizimi

```cpp
template<typename Arg>
    ref class logical_or
    { // wrap operator()
public:
    typedef Arg first_argument_type;
    typedef Arg second_argument_type;
    typedef bool result_type;
    typedef Microsoft::VisualC::StlClr::BinaryDelegate<
        first_argument_type, second_argument_type, result_type>
        delegate_type;

    logical_or();
    logical_or(logical_or<Arg>% right);

    result_type operator()(first_argument_type left,
        second_argument_type right);
    operator delegate_type^();
    };
```

#### <a name="parameters"></a>Parametreler

*Değişkeni*<br/>
Bağımsız değişkenlerin türü.

### <a name="member-functions"></a>Üye İşlevleri

|Tür Tanımı|Açıklama|
|---------------------|-----------------|
|delegate_type|Genel temsilcinin türü.|
|first_argument_type|Functor ilk bağımsız değişkeninin türü.|
|result_type|Functor sonucunun türü.|
|second_argument_type|Functor ikinci bağımsız değişkeninin türü.|

|Üye|Açıklama|
|------------|-----------------|
|logical_or|Functor 'ı oluşturur.|

|İşleç|Açıklama|
|--------------|-----------------|
|operator ()|İstenen işlevi hesaplar.|
|işleç delegate_type ^|Bir temsilciye functor yayınlar.|

### <a name="remarks"></a>Açıklamalar

Şablon sınıfı, bir iki bağımsız değişken olan functor tanımlar. Üye işlecini tanımlar, `operator()` böylece nesne bir işlev olarak çağrıldığında true, yalnızca ilk bağımsız değişken ya da ikinci test true olduğunda true değerini döndürür.

Ayrıca, nesneyi türü olan bir işlev bağımsız değişkeni olarak geçirebilir `delegate_type^` ve uygun şekilde dönüştürülecektir.

### <a name="example"></a>Örnek

```cpp
// cliext_logical_or.cpp
// compile with: /clr
#include <cliext/algorithm>
#include <cliext/functional>
#include <cliext/vector>

typedef cliext::vector<int> Myvector;
int main()
    {
    Myvector c1;
    c1.push_back(2);
    c1.push_back(0);
    Myvector c2;
    c2.push_back(0);
    c2.push_back(0);
    Myvector c3(2, 0);

// display initial contents " 2 0" and " 0 0"
    for each (int elem in c1)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

    for each (int elem in c2)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display
    cliext::transform(c1.begin(), c1.begin() + 2,
        c2.begin(), c3.begin(), cliext::logical_or<int>());
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
2 0
0 0
1 0
```

## <a name="minus-stlclr"></a><a name="minus"></a> eksi (STL/CLR)

Şablon sınıfı, çağrıldığında ilk bağımsız değişkeni ikinci kez döndüren bir functor tanımlar. Bağımsız değişken türü açısından bir işlev nesnesi belirtin.

### <a name="syntax"></a>Sözdizimi

```cpp
template<typename Arg>
    ref class minus
    { // wrap operator()
public:
    typedef Arg first_argument_type;
    typedef Arg second_argument_type;
    typedef Arg result_type;
    typedef Microsoft::VisualC::StlClr::BinaryDelegate<
        first_argument_type, second_argument_type, result_type>
        delegate_type;

    minus();
    minus(minus<Arg>% right);

    result_type operator()(first_argument_type left,
        second_argument_type right);
    operator delegate_type^();
    };
```

#### <a name="parameters"></a>Parametreler

*Değişkeni*<br/>
Bağımsız değişkenlerin türü ve dönüş değeri.

### <a name="member-functions"></a>Üye İşlevleri

|Tür Tanımı|Açıklama|
|---------------------|-----------------|
|delegate_type|Genel temsilcinin türü.|
|first_argument_type|Functor ilk bağımsız değişkeninin türü.|
|result_type|Functor sonucunun türü.|
|second_argument_type|Functor ikinci bağımsız değişkeninin türü.|

|Üye|Açıklama|
|------------|-----------------|
|eksi|Functor 'ı oluşturur.|

|İşleç|Açıklama|
|--------------|-----------------|
|operator ()|İstenen işlevi hesaplar.|
|işleç delegate_type ^|Bir temsilciye functor yayınlar.|

### <a name="remarks"></a>Açıklamalar

Şablon sınıfı, bir iki bağımsız değişken olan functor tanımlar. Üye işlecini tanımlar, `operator()` böylece nesne bir işlev olarak çağrıldığında ilk bağımsız değişkeni ikinci kez döndürür.

Ayrıca, nesneyi türü olan bir işlev bağımsız değişkeni olarak geçirebilir `delegate_type^` ve uygun şekilde dönüştürülecektir.

### <a name="example"></a>Örnek

```cpp
// cliext_minus.cpp
// compile with: /clr
#include <cliext/algorithm>
#include <cliext/functional>
#include <cliext/vector>

typedef cliext::vector<int> Myvector;
int main()
    {
    Myvector c1;
    c1.push_back(4);
    c1.push_back(3);
    Myvector c2;
    c2.push_back(2);
    c2.push_back(1);
    Myvector c3(2, 0);

// display initial contents " 4 3" and " 2 1"
    for each (int elem in c1)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

    for each (int elem in c2)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display
    cliext::transform(c1.begin(), c1.begin() + 2,
        c2.begin(), c3.begin(), cliext::minus<int>());
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
4 3
2 1
2 2
```

## <a name="modulus-stlclr"></a><a name="modulus"></a> mod (STL/CLR)

Şablon sınıfı, çağrıldığında ilk bağımsız değişkeni döndürür bir, çağrıldığında bir functor tanımlar. Bağımsız değişken türü açısından bir işlev nesnesi belirtin.

### <a name="syntax"></a>Sözdizimi

```cpp
template<typename Arg>
    ref class modulus
    { // wrap operator()
public:
    typedef Arg first_argument_type;
    typedef Arg second_argument_type;
    typedef Arg result_type;
    typedef Microsoft::VisualC::StlClr::BinaryDelegate<
        first_argument_type, second_argument_type, result_type>
        delegate_type;

    modulus();
    modulus(modulus<Arg>% right);

    result_type operator()(first_argument_type left,
        second_argument_type right);
    operator delegate_type^();
    };
```

#### <a name="parameters"></a>Parametreler

*Değişkeni*<br/>
Bağımsız değişkenlerin türü ve dönüş değeri.

### <a name="member-functions"></a>Üye İşlevleri

|Tür Tanımı|Açıklama|
|---------------------|-----------------|
|delegate_type|Genel temsilcinin türü.|
|first_argument_type|Functor ilk bağımsız değişkeninin türü.|
|result_type|Functor sonucunun türü.|
|second_argument_type|Functor ikinci bağımsız değişkeninin türü.|

|Üye|Açıklama|
|------------|-----------------|
|mod|Functor 'ı oluşturur.|

|İşleç|Açıklama|
|--------------|-----------------|
|operator ()|İstenen işlevi hesaplar.|
|işleç delegate_type ^|Bir temsilciye functor yayınlar.|

### <a name="remarks"></a>Açıklamalar

Şablon sınıfı, bir iki bağımsız değişken olan functor tanımlar. Üye işlecini tanımlar, `operator()` böylece nesne bir işlev olarak çağrıldığında ilk bağımsız değişkeni ikinci kez döndürür.

Ayrıca, nesneyi türü olan bir işlev bağımsız değişkeni olarak geçirebilir `delegate_type^` ve uygun şekilde dönüştürülecektir.

### <a name="example"></a>Örnek

```cpp
// cliext_modulus.cpp
// compile with: /clr
#include <cliext/algorithm>
#include <cliext/functional>
#include <cliext/vector>

typedef cliext::vector<int> Myvector;
int main()
    {
    Myvector c1;
    c1.push_back(4);
    c1.push_back(2);
    Myvector c2;
    c2.push_back(3);
    c2.push_back(1);
    Myvector c3(2, 0);

// display initial contents " 4 2" and " 3 1"
    for each (int elem in c1)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

    for each (int elem in c2)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display
    cliext::transform(c1.begin(), c1.begin() + 2,
        c2.begin(), c3.begin(), cliext::modulus<int>());
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
4 2
3 1
1 0
```

## <a name="multiplies-stlclr"></a><a name="multiplies"></a> çarpar (STL/CLR)

Şablon sınıfı, çağrıldığında ilk bağımsız değişkeni ikinci kez döndüren bir functor tanımlar. Bağımsız değişken türü açısından bir işlev nesnesi belirtin.

### <a name="syntax"></a>Sözdizimi

```cpp
template<typename Arg>
    ref class multiplies
    { // wrap operator()
public:
    typedef Arg first_argument_type;
    typedef Arg second_argument_type;
    typedef Arg result_type;
    typedef Microsoft::VisualC::StlClr::BinaryDelegate<
        first_argument_type, second_argument_type, result_type>
        delegate_type;

    multiplies();
    multiplies(multiplies<Arg>% right);

    result_type operator()(first_argument_type left,
        second_argument_type right);
    operator delegate_type^();
    };
```

#### <a name="parameters"></a>Parametreler

*Değişkeni*<br/>
Bağımsız değişkenlerin türü ve dönüş değeri.

### <a name="member-functions"></a>Üye İşlevleri

|Tür Tanımı|Açıklama|
|---------------------|-----------------|
|delegate_type|Genel temsilcinin türü.|
|first_argument_type|Functor ilk bağımsız değişkeninin türü.|
|result_type|Functor sonucunun türü.|
|second_argument_type|Functor ikinci bağımsız değişkeninin türü.|

|Üye|Açıklama|
|------------|-----------------|
|çarpar|Functor 'ı oluşturur.|

|İşleç|Açıklama|
|--------------|-----------------|
|operator ()|İstenen işlevi hesaplar.|
|işleç delegate_type ^|Bir temsilciye functor yayınlar.|

### <a name="remarks"></a>Açıklamalar

Şablon sınıfı, bir iki bağımsız değişken olan functor tanımlar. Üye işlecini tanımlar, `operator()` böylece nesne bir işlev olarak çağrıldığında ilk bağımsız değişkeni ikinci kez döndürür.

Ayrıca, nesneyi türü olan bir işlev bağımsız değişkeni olarak geçirebilir `delegate_type^` ve uygun şekilde dönüştürülecektir.

### <a name="example"></a>Örnek

```cpp
// cliext_multiplies.cpp
// compile with: /clr
#include <cliext/algorithm>
#include <cliext/functional>
#include <cliext/vector>

typedef cliext::vector<int> Myvector;
int main()
    {
    Myvector c1;
    c1.push_back(4);
    c1.push_back(3);
    Myvector c2;
    c2.push_back(2);
    c2.push_back(1);
    Myvector c3(2, 0);

// display initial contents " 4 3" and " 2 1"
    for each (int elem in c1)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

    for each (int elem in c2)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display
    cliext::transform(c1.begin(), c1.begin() + 2,
        c2.begin(), c3.begin(), cliext::multiplies<int>());
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
4 3
2 1
8 3
```

## <a name="negate-stlclr"></a><a name="negate"></a> Negate (STL/CLR)

Şablon sınıfı, çağrıldığında bağımsız değişkenini döndüren bir functor tanımlar. Bağımsız değişken türü açısından bir işlev nesnesi belirtin.

### <a name="syntax"></a>Sözdizimi

```cpp
template<typename Arg>
    ref class negate
    { // wrap operator()
public:
    typedef Arg argument_type;
    typedef bool result_type;
    typedef Microsoft::VisualC::StlClr::UnaryDelegate<
        argument_type, result_type>
        delegate_type;

    negate();
    negate(negate<Arg>% right);

    result_type operator()(argument_type left);
    operator delegate_type^();
    };
```

#### <a name="parameters"></a>Parametreler

*Değişkeni*<br/>
Bağımsız değişkenlerin türü.

### <a name="member-functions"></a>Üye İşlevleri

|Tür Tanımı|Açıklama|
|---------------------|-----------------|
|argument_type|Functor bağımsız değişkeninin türü.|
|delegate_type|Genel temsilcinin türü.|
|result_type|Functor sonucunun türü.|

|Üye|Açıklama|
|------------|-----------------|
|olumsuzlaştırma|Functor 'ı oluşturur.|

|İşleç|Açıklama|
|--------------|-----------------|
|operator ()|İstenen işlevi hesaplar.|
|işleç delegate_type ^|Bir temsilciye functor yayınlar.|

### <a name="remarks"></a>Açıklamalar

Şablon sınıfı, bir bağımsız değişken functor tanımlar. Üye işlecini tanımlar, `operator()` böylece nesne bir işlev olarak çağrıldığında, bağımsız değişkenini döndürür.

Ayrıca, nesneyi türü olan bir işlev bağımsız değişkeni olarak geçirebilir `delegate_type^` ve uygun şekilde dönüştürülecektir.

### <a name="example"></a>Örnek

```cpp
// cliext_negate.cpp
// compile with: /clr
#include <cliext/algorithm>
#include <cliext/functional>
#include <cliext/vector>

typedef cliext::vector<int> Myvector;
int main()
    {
    Myvector c1;
    c1.push_back(4);
    c1.push_back(-3);
    Myvector c3(2, 0);

// display initial contents " 4 -3"
    for each (int elem in c1)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display
    cliext::transform(c1.begin(), c1.begin() + 2,
        c3.begin(), cliext::negate<int>());
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
4 -3
-4 3
```

## <a name="not_equal_to-stlclr"></a><a name="not_equal_to"></a> not_equal_to (STL/CLR)

Şablon sınıfı, çağrıldığında, yalnızca ilk bağımsız değişken ikinciye eşit değilse true değerini döndüren bir functor tanımlar. Bağımsız değişken türü açısından bir işlev nesnesi belirtin.

### <a name="syntax"></a>Sözdizimi

```cpp
template<typename Arg>
    ref class not_equal_to
    { // wrap operator()
public:
    typedef Arg first_argument_type;
    typedef Arg second_argument_type;
    typedef bool result_type;
    typedef Microsoft::VisualC::StlClr::BinaryDelegate<
        first_argument_type, second_argument_type, result_type>
        delegate_type;

    not_equal_to();
    not_equal_to(not_equal_to<Arg>% right);

    result_type operator()(first_argument_type left,
        second_argument_type right);
    operator delegate_type^();
    };
```

#### <a name="parameters"></a>Parametreler

*Değişkeni*<br/>
Bağımsız değişkenlerin türü.

### <a name="member-functions"></a>Üye İşlevleri

|Tür Tanımı|Açıklama|
|---------------------|-----------------|
|delegate_type|Genel temsilcinin türü.|
|first_argument_type|Functor ilk bağımsız değişkeninin türü.|
|result_type|Functor sonucunun türü.|
|second_argument_type|Functor ikinci bağımsız değişkeninin türü.|

|Üye|Açıklama|
|------------|-----------------|
|not_equal_to|Functor 'ı oluşturur.|

|İşleç|Açıklama|
|--------------|-----------------|
|operator ()|İstenen işlevi hesaplar.|
|işleç delegate_type ^|Bir temsilciye functor yayınlar.|

### <a name="remarks"></a>Açıklamalar

Şablon sınıfı, bir iki bağımsız değişken olan functor tanımlar. Üye işlecini tanımlar, `operator()` böylece nesne bir işlev olarak çağrıldığında true, yalnızca ilk bağımsız değişken ikinciye eşit değilse true değerini döndürür.

Ayrıca, nesneyi türü olan bir işlev bağımsız değişkeni olarak geçirebilir `delegate_type^` ve uygun şekilde dönüştürülecektir.

### <a name="example"></a>Örnek

```cpp
// cliext_not_equal_to.cpp
// compile with: /clr
#include <cliext/algorithm>
#include <cliext/functional>
#include <cliext/vector>

typedef cliext::vector<int> Myvector;
int main()
    {
    Myvector c1;
    c1.push_back(4);
    c1.push_back(3);
    Myvector c2;
    c2.push_back(4);
    c2.push_back(4);
    Myvector c3(2, 0);

// display initial contents " 4 3" and " 4 4"
    for each (int elem in c1)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

    for each (int elem in c2)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display
    cliext::transform(c1.begin(), c1.begin() + 2,
        c2.begin(), c3.begin(), cliext::not_equal_to<int>());
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
4 3
4 4
0 1
```

## <a name="not1-stlclr"></a><a name="not1"></a> Not1 (STL/CLR)

Bir `unary_negate` functor için bir üretir.

### <a name="syntax"></a>Syntax

```cpp
template<typename Fun>
    unary_negate<Fun> not1(Fun% functor);
```

#### <a name="template-parameters"></a>Şablon Parametreleri

*Tablolar*<br/>
Functor türü.

#### <a name="function-parameters"></a>İşlev parametreleri

*functor*<br/>
Kaydırmak için functor.

### <a name="remarks"></a>Açıklamalar

Şablon işlevi [unary_negate (STL/CLR)](#unary_negate)döndürür `<Fun>(functor)` . Bu değeri, mantıksal olmayan bir functor 'da tek değişkenli bir functor 'ı sarmanın kolay bir yolu olarak kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// cliext_not1.cpp
// compile with: /clr
#include <cliext/algorithm>
#include <cliext/functional>
#include <cliext/vector>

typedef cliext::vector<int> Myvector;
int main()
    {
    Myvector c1;
    c1.push_back(4);
    c1.push_back(0);
    Myvector c3(2, 0);

// display initial contents " 4 0"
    for each (int elem in c1)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display
    cliext::logical_not<int> not_op;

    cliext::transform(c1.begin(), c1.begin() + 2, c3.begin(),
        cliext::unary_negate<cliext::logical_not<int> >(not_op));
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display with function
    cliext::transform(c1.begin(), c1.begin() + 2, c3.begin(),
        cliext::not1(not_op));
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
4 0
1 0
1 0
```

## <a name="not2-stlclr"></a><a name="not2"></a> NOT2 (STL/CLR)

Bir `binary_negate` functor için bir üretir.

### <a name="syntax"></a>Syntax

```cpp
template<typename Fun>
    binary_negate<Fun> not2(Fun% functor);
```

#### <a name="template-parameters"></a>Şablon Parametreleri

*Tablolar*<br/>
Functor türü.

#### <a name="function-parameters"></a>İşlev parametreleri

*functor*<br/>
Kaydırmak için functor.

### <a name="remarks"></a>Açıklamalar

Şablon işlevi [binary_negate (STL/CLR)](#negate)döndürür `<Fun>(functor)` . Bunu, mantıksal olmayan bir komik bir ctor 'da iki bağımsız değişkenli bir functor sarmak için kullanışlı bir yol olarak kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// cliext_not2.cpp
// compile with: /clr
#include <cliext/algorithm>
#include <cliext/functional>
#include <cliext/vector>

typedef cliext::vector<int> Myvector;
int main()
    {
    Myvector c1;
    c1.push_back(4);
    c1.push_back(3);
    Myvector c2;
    c2.push_back(4);
    c2.push_back(4);
    Myvector c3(2, 0);

// display initial contents " 4 3" and " 4 4"
    for each (int elem in c1)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

    for each (int elem in c2)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display
    cliext::less<int> less_op;

    cliext::transform(c1.begin(), c1.begin() + 2,
        c2.begin(), c3.begin(),
        cliext::binary_negate<cliext::less<int> >(less_op));
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display with function
    cliext::transform(c1.begin(), c1.begin() + 2,
        c2.begin(), c3.begin(), cliext::not2(less_op));
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
4 3
4 4
1 0
1 0
```

## <a name="plus-stlclr"></a><a name="plus"></a> Plus (STL/CLR)

Şablon sınıfı, çağrıldığında ilk bağımsız değişkeni artı ikinci değeri döndüren bir functor tanımlar. Bağımsız değişken türü açısından bir işlev nesnesi belirtin.

### <a name="syntax"></a>Sözdizimi

```cpp
template<typename Arg>
    ref class plus
    { // wrap operator()
public:
    typedef Arg first_argument_type;
    typedef Arg second_argument_type;
    typedef Arg result_type;
    typedef Microsoft::VisualC::StlClr::BinaryDelegate<
        first_argument_type, second_argument_type, result_type>
        delegate_type;

    plus();
    plus(plus<Arg>% right);

    result_type operator()(first_argument_type left,
        second_argument_type right);
    operator delegate_type^();
    };
```

#### <a name="parameters"></a>Parametreler

*Değişkeni*<br/>
Bağımsız değişkenlerin türü ve dönüş değeri.

### <a name="member-functions"></a>Üye İşlevleri

|Tür Tanımı|Açıklama|
|---------------------|-----------------|
|delegate_type|Genel temsilcinin türü.|
|first_argument_type|Functor ilk bağımsız değişkeninin türü.|
|result_type|Functor sonucunun türü.|
|second_argument_type|Functor ikinci bağımsız değişkeninin türü.|

|Üye|Açıklama|
|------------|-----------------|
|artı|Functor 'ı oluşturur.|

|İşleç|Açıklama|
|--------------|-----------------|
|operator ()|İstenen işlevi hesaplar.|
|işleç delegate_type ^|Bir temsilciye functor yayınlar.|

### <a name="remarks"></a>Açıklamalar

Şablon sınıfı, bir iki bağımsız değişken olan functor tanımlar. Üye işlecini tanımlar, `operator()` böylece nesne bir işlev olarak çağrıldığında ilk bağımsız değişkeni artı ikincisini döndürür.

Ayrıca, nesneyi türü olan bir işlev bağımsız değişkeni olarak geçirebilir `delegate_type^` ve uygun şekilde dönüştürülecektir.

### <a name="example"></a>Örnek

```cpp
// cliext_plus.cpp
// compile with: /clr
#include <cliext/algorithm>
#include <cliext/functional>
#include <cliext/vector>

typedef cliext::vector<int> Myvector;
int main()
    {
    Myvector c1;
    c1.push_back(4);
    c1.push_back(3);
    Myvector c2;
    c2.push_back(2);
    c2.push_back(1);
    Myvector c3(2, 0);

// display initial contents " 4 3" and " 2 1"
    for each (int elem in c1)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

    for each (int elem in c2)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display
    cliext::transform(c1.begin(), c1.begin() + 2,
        c2.begin(), c3.begin(), cliext::plus<int>());
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
4 3
2 1
6 4
```

## <a name="unary_delegate-stlclr"></a><a name="unary_delegate"></a> unary_delegate (STL/CLR)

Genereic sınıfı, tek değişkenli bir temsilciyi açıklar. Bağımsız değişkeni ve dönüş türleri bakımından bir temsilci belirtin.

### <a name="syntax"></a>Sözdizimi

```cpp
generic<typename Arg,
    typename Result>
    delegate Result unary_delegate(Arg);
```

#### <a name="parameters"></a>Parametreler

*Değişkeni*<br/>
Bağımsız değişkenin türü.

*Sonuç*<br/>
Dönüş türü.

### <a name="remarks"></a>Açıklamalar

Genereic temsilcisi bir bağımsız değişken işlevini tanımlar.

Şunları unutmayın:

`unary_delegare<int, int> Fun1;`

`unary_delegare<int, int> Fun2;`

türler `Fun1` ve `Fun2` Şu şekilde eş anlamlılar:

`delegate int Fun1(int);`

`delegate int Fun2(int);`

aynı türde değildir.

### <a name="example"></a>Örnek

```cpp
// cliext_unary_delegate.cpp
// compile with: /clr
#include <cliext/functional>

int hash_val(wchar_t val)
    {
    return ((val * 17 + 31) % 67);
    }

typedef cliext::unary_delegate<wchar_t, int> Mydelegate;
int main()
    {
    Mydelegate^ myhash = gcnew Mydelegate(&hash_val);

    System::Console::WriteLine("hash(L'a') = {0}", myhash(L'a'));
    System::Console::WriteLine("hash(L'b') = {0}", myhash(L'b'));
    return (0);
    }
```

```Output
hash(L'a') = 5
hash(L'b') = 22
```

## <a name="unary_delegate_noreturn-stlclr"></a><a name="unary_delegate_noreturn"></a> unary_delegate_noreturn (STL/CLR)

Genereic sınıfı, döndüren tek değişkenli bir temsilciyi açıklar **`void`** . Bağımsız değişken türü açısından bir temsilci belirtin.

### <a name="syntax"></a>Sözdizimi

```cpp
generic<typename Arg>
    delegate void unary_delegate_noreturn(Arg);
```

#### <a name="parameters"></a>Parametreler

*Değişkeni*<br/>
Bağımsız değişkenin türü.

### <a name="remarks"></a>Açıklamalar

Genereic temsilcisi, döndüren tek değişkenli bir işlevi tanımlar **`void`** .

Şunları unutmayın:

`unary_delegare_noreturn<int> Fun1;`

`unary_delegare_noreturn<int> Fun2;`

türler `Fun1` ve `Fun2` Şu şekilde eş anlamlılar:

`delegate void Fun1(int);`

`delegate void Fun2(int);`

aynı türde değildir.

### <a name="example"></a>Örnek

```cpp
// cliext_unary_delegate_noreturn.cpp
// compile with: /clr
#include <cliext/functional>

void hash_val(wchar_t val)
    {
    System::Console::WriteLine("hash({0}) = {1}",
       val, (val * 17 + 31) % 67);
    }

typedef cliext::unary_delegate_noreturn<wchar_t> Mydelegate;
int main()
    {
    Mydelegate^ myhash = gcnew Mydelegate(&hash_val);

    myhash(L'a');
    myhash(L'b');
    return (0);
    }
```

```Output
hash(a) = 5
hash(b) = 22
```

## <a name="unary_negate-stlclr"></a><a name="unary_negate"></a> unary_negate (STL/CLR)

Şablon sınıfı, çağrıldığında, depolanan tek değişkenli functor mantıksal DEĞIL ' i döndüren bir functor tanımlar. Bu uygulamayı, depolanan functor açısından bir işlev nesnesi belirtmektir.

### <a name="syntax"></a>Sözdizimi

```cpp
template<typename Fun>
    ref class unary_negate
    { // wrap operator()
public:
    typedef Fun stored_function_type;
    typedef typename Fun::argument_type argument_type;
    typedef bool result_type;
    typedef Microsoft::VisualC::StlClr::UnaryDelegate<
        argument_type, result_type>
        delegate_type;

    unary_negate(Fun% functor);
    unary_negate(unary_negate<Fun>% right);

    result_type operator()(argument_type left);
    operator delegate_type^();
    };
```

#### <a name="parameters"></a>Parametreler

*Tablolar*<br/>
Depolanan functor türü.

### <a name="member-functions"></a>Üye İşlevleri

|Tür Tanımı|Açıklama|
|---------------------|-----------------|
|argument_type|Functor bağımsız değişkeninin türü.|
|delegate_type|Genel temsilcinin türü.|
|result_type|Functor sonucunun türü.|

|Üye|Açıklama|
|------------|-----------------|
|unary_negate|Functor 'ı oluşturur.|

|İşleç|Açıklama|
|--------------|-----------------|
|operator ()|İstenen işlevi hesaplar.|
|delegate_type ^|Bir temsilciye functor yayınlar.|

### <a name="remarks"></a>Açıklamalar

Şablon sınıfı, farklı bir bağımsız değişken olan functor 'u depolayan bir bağımsız değişken functor tanımlar. Üye işlecini tanımlar, `operator()` böylece nesne bir işlev olarak çağrıldığında, bağımsız değişkeniyle çağrılan depolanan functor 'un mantıksal değerini döndürür.

Ayrıca, nesneyi türü olan bir işlev bağımsız değişkeni olarak geçirebilir `delegate_type^` ve uygun şekilde dönüştürülecektir.

### <a name="example"></a>Örnek

```cpp
// cliext_unary_negate.cpp
// compile with: /clr
#include <cliext/algorithm>
#include <cliext/functional>
#include <cliext/vector>

typedef cliext::vector<int> Myvector;
int main()
    {
    Myvector c1;
    c1.push_back(4);
    c1.push_back(0);
    Myvector c3(2, 0);

// display initial contents " 4 0"
    for each (int elem in c1)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display
    cliext::logical_not<int> not_op;

    cliext::transform(c1.begin(), c1.begin() + 2, c3.begin(),
        cliext::unary_negate<cliext::logical_not<int> >(not_op));
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display with function
    cliext::transform(c1.begin(), c1.begin() + 2, c3.begin(),
        cliext::not1(not_op));
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
4 0
1 0
1 0
```
