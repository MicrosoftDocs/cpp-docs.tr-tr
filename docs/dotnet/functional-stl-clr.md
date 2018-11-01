---
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
ms.openlocfilehash: f4a99ea972c6d2ea9b9721664cc75dec257fd7b3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50472910"
---
# <a name="functional-stlclr"></a>işlevsel (STL/CLR)

STL/CLR üstbilgisini `<cliext/functional>` tanımlamak için şablon sınıfları, ilgili şablon Temsilciler ve İşlevler bir sayı.

## <a name="syntax"></a>Sözdizimi

```
#include <functional>
```

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<cliext/işlev >

**Namespace:** cliext

## <a name="declarations"></a>Bildirimler

|Temsilci|Açıklama|
|--------------|-----------------|
|[binary_delegate (STL/CLR)](#binary_delegate)|İki bağımsız temsilcisi.|
|[binary_delegate_noreturn (STL/CLR)](#binary_delegate_noreturn)|İki bağımsız temsilci döndüren **void**.|
|[unary_delegate (STL/CLR)](#unary_delegate)|Tek bağımsız değişkenli temsilcisi.|
|[unary_delegate_noreturn (STL/CLR)](#unary_delegate_noreturn)|Döndüren tek bağımsız değişkenli temsilci **void**.|

|örneği|Açıklama|
|-----------|-----------------|
|[binary_negate (STL/CLR)](#binary_negate)|İki bağımsız functor negatif yapılacak functor.|
|[binder1st (STL/CLR)](#binder1st)|İlk bağımsız değişken için bir iki bağımsız functor bağlamak için functor.|
|[binder2nd (STL/CLR)](#binder2nd)|İkinci bağımsız değişkeni için bir iki bağımsız functor bağlamak için functor.|
|[divides (STL/CLR)](#divides)|Functor bölün.|
|[equal_to (STL/CLR)](#equal_to)|Karşılaştırma functor eşit.|
|[greater (STL/CLR)](#greater)|Büyük karşılaştırma functor.|
|[greater_equal (STL/CLR)](#greater_equal)|Büyük veya buna eşit karşılaştırma functor.|
|[less (STL/CLR)](#less)|Daha az karşılaştırma functor.|
|[less_equal (STL/CLR)](#less_equal)|Küçük veya buna eşit karşılaştırma functor.|
|[logical_and (STL/CLR)](#logical_and)|Mantıksal AND functor.|
|[logical_not (STL/CLR)](#logical_not)|Mantıksal functor değil.|
|[logical_or (STL/CLR)](#logical_or)|Mantıksal OR functor.|
|[minus (STL/CLR)](#minus)|Functor çıkarın.|
|[modulus (STL/CLR)](#modulus)|Modulus functor.|
|[multiplies (STL/CLR)](#multiplies)|Functor çarpın.|
|[negate (STL/CLR)](#negate)|Değilleme kendi bağımsız değişkenini döndürmesine izin functor.|
|[not_equal_to (STL/CLR)](#not_equal_to)|Eşit değildir karşılaştırma functor.|
|[plus (STL/CLR)](#plus)|Functor ekleyin.|
|[unary_negate (STL/CLR)](#unary_negate)|Tek bağımsız değişkenli functor negatif yapılacak functor.|

|İşlev|Açıklama|
|--------------|-----------------|
|[bind1st (STL/CLR)](#bind1st)|Bir bağımsız değişken ve functor bir binder1st oluşturur.|
|[bind2nd (STL/CLR)](#bind2nd)|Bir bağımsız değişken ve functor bir binder2nd oluşturur.|
|[not1 (STL/CLR)](#not1)|Bir functor için bir unary_negate oluşturur.|
|[not2 (STL/CLR)](#not2)|Bir functor için bir binary_negate oluşturur.|

## <a name="members"></a>Üyeler

## <a name="binary_delegate"></a> binary_delegate (STL/CLR)

İki bağımsız temsilci genereic sınıfı açıklar. Bunu bir temsilci, bağımsız değişkenin ve dönüş türleri açısından belirtin.

### <a name="syntax"></a>Sözdizimi

```cpp
generic<typename Arg1,
    typename Arg2,
    typename Result>
    delegate Result binary_delegate(Arg1, Arg2);
```

#### <a name="parameters"></a>Parametreler

*arg1*<br/>
İlk bağımsız değişken türü.

*arg2*<br/>
İkinci bağımsız değişken türü.

*Sonuç*<br/>
Dönüş türü.

### <a name="remarks"></a>Açıklamalar

İki bağımsız işlevi genereic temsilci açıklar.

Unutmayın:

`binary_delegate<int, int, int> Fun1;`

`binary_delegate<int, int, int> Fun2;`

türleri `Fun1` ve `Fun2` eşanlamlıdır, while için:

`delegate int Fun1(int, int);`

`delegate int Fun2(int, int);`

Bunlar aynı türde değil.

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

## <a name="binary_delegate_noreturn"></a> binary_delegate_noreturn (STL/CLR)

Döndüren iki bağımsız temsilci genereic sınıfı açıklar **void**. Bunu bir temsilcinin bağımsız değişkenini açısından belirtin.

### <a name="syntax"></a>Sözdizimi

```cpp
generic<typename Arg1,
    typename Arg2>
    delegate void binary_delegate(Arg1, Arg2);
```

#### <a name="parameters"></a>Parametreler

*arg1*<br/>
İlk bağımsız değişken türü.

*arg2*<br/>
İkinci bağımsız değişken türü.

### <a name="remarks"></a>Açıklamalar

Döndüren bir işlev iki bağımsız genereic temsilci açıklar **void**.

Unutmayın:

`binary_delegate_noreturn<int, int> Fun1;`

`binary_delegate_noreturn<int, int> Fun2;`

türleri `Fun1` ve `Fun2` eşanlamlıdır, while için:

`delegate void Fun1(int, int);`

`delegate void Fun2(int, int);`

Bunlar aynı türde değil.

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

## <a name="binary_negate"></a> binary_negate (STL/CLR)

Şablon sınıfı bir functor tanımlar, çağrıldığında, mantıksal döndürür, depolanan iki bağımsız functor, değil. Bunu kendi saklı functor açısından bir işlev nesnesi belirtin.

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

*Eğlence*<br/>
Saklı functor türü.

## <a name="member-functions"></a>Üye İşlevleri

|Tür Tanımlaması|Açıklama|
|---------------------|-----------------|
|delegate_type|Genel temsilci türü.|
|first_argument_type|Functor ilk bağımsız değişken türü.|
|result_type|Functor sonuç türü.|
|second_argument_type|Functor ikinci bağımsız değişken türü.|
|stored_function_type|Bir functor türü.|

|Üye|Açıklama|
|------------|-----------------|
|binary_negate|İşlev nesnesini oluşturur.|

|İşleç|Açıklama|
|--------------|-----------------|
|operator()|İstenen işlev hesaplar.|
|işleç delegate_type^()|Bir temsilci functor çevirir.|

### <a name="remarks"></a>Açıklamalar

Şablon sınıfı, başka bir iki bağımsız functor depolayan bir iki bağımsız functor açıklar. Üye işleci tanımlar `operator()` nesne bir işlev olarak ne zaman çağrıldığını böylece, mantıksal döndürür değil saklı functor iki bağımsız değişkenlerle çağrılır.

Nesne türü olan bir işlev bağımsız değişkeni geçirebilirsiniz `delegate_type^` ve uygun şekilde dönüştürülür.

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

## <a name="bind1st"></a> bind1st (STL/CLR)

Oluşturur bir `binder1st` bir bağımsız değişken ve functor.

### <a name="syntax"></a>Sözdizimi

```cpp
template<typename Fun,
    typename Arg>
    binder1st<Fun> bind1st(Fun% functor,
        Arg left);
```

#### <a name="template-parameters"></a>Şablon Parametreleri

*bağımsız değişken*<br/>
Bağımsız değişken türü.

*Eğlence*<br/>
Bir functor türü.

#### <a name="function-parameters"></a>İşlev parametreleri

*functor*<br/>
Sarılacak functor.

*Sol*<br/>
Kaydırmak için ilk bağımsız değişken.

### <a name="remarks"></a>Açıklamalar

Şablon işlevinin döndürdüğü [binder1st (STL/CLR)](../dotnet/binder1st-stl-clr.md)`<Fun>(functor, left)`. İki bağımsız functor ve ilk bağımsız değişken bir ikinci bağımsız değişkeni ile çağıran bir tek bağımsız değişkenli functor içine almanız için kullanışlı bir yol olarak kullanın.

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

## <a name="bind2nd"></a> bind2nd (STL/CLR)

Oluşturur bir `binder2nd` bir bağımsız değişken ve functor.

### <a name="syntax"></a>Sözdizimi

```cpp
template<typename Fun,
    typename Arg>
    binder2nd<Fun> bind2nd(Fun% functor,
        Arg right);
```

#### <a name="template-parameters"></a>Şablon Parametreleri

*bağımsız değişken*<br/>
Bağımsız değişken türü.

*Eğlence*<br/>
Bir functor türü.

#### <a name="function-parameters"></a>İşlev parametreleri

*functor*<br/>
Sarılacak functor.

*sağ*<br/>
Kaydırmak için ikinci bağımsız değişkeni.

### <a name="remarks"></a>Açıklamalar

Şablon işlevinin döndürdüğü [binder2nd (STL/CLR)](../dotnet/binder2nd-stl-clr.md)`<Fun>(functor, right)`. İki bağımsız functor ve ikinci bağımsız değişkeni, ilk bağımsız değişkenle çağıran bir tek bağımsız değişkenli işlev içinde sarmalamak için kullanışlı bir yol olarak kullanın.

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

## <a name="binder1st"></a> binder1st (STL/CLR)

Şablon sınıfı bir tek bağımsız değişkenli functor tanımlar, çağrıldığında, depolanan ilk bağımsız değişkeni ile belirtilen ikinci bağımsız değişken adında kendi saklı iki bağımsız functor döndürür. Bunu kendi saklı functor açısından bir işlev nesnesi belirtin.

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

*Eğlence*<br/>
Saklı functor türü.

### <a name="member-functions"></a>Üye İşlevleri

|Tür Tanımlaması|Açıklama|
|---------------------|-----------------|
|delegate_type|Genel temsilci türü.|
|first_argument_type|Functor ilk bağımsız değişken türü.|
|result_type|Functor sonuç türü.|
|second_argument_type|Functor ikinci bağımsız değişken türü.|
|stored_function_type|Bir functor türü.|

|Üye|Açıklama|
|------------|-----------------|
|binder1st|İşlev nesnesini oluşturur.|

|İşleç|Açıklama|
|--------------|-----------------|
|operator()|İstenen işlev hesaplar.|
|işleç delegate_type^()|Bir temsilci functor çevirir.|

### <a name="remarks"></a>Açıklamalar

Şablon sınıfı, iki bağımsız functor ve bir ilk bağımsız değişken depolayan bir tek bağımsız değişkenli functor açıklar. Üye işleci tanımlar `operator()` nesne bir işlev olarak ne zaman çağrıldığını böylece, saklı functor saklı ilk bağımsız değişken ve belirtilen ikinci bağımsız değişkeni ile arama sonucunu döndürür.

Nesne türü olan bir işlev bağımsız değişkeni geçirebilirsiniz `delegate_type^` ve uygun şekilde dönüştürülür.

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

## <a name="binder2nd"></a> binder2nd (STL/CLR)

Şablon sınıfı bir tek bağımsız değişkenli functor tanımlar, çağrıldığında, sağlanan ilk bağımsız değişken ve depolanan ikinci bağımsız değişkeni ile adlı depolanan, iki bağımsız functor döndürür. Bunu kendi saklı functor açısından bir işlev nesnesi belirtin.

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

*Eğlence*<br/>
Saklı functor türü.

## <a name="member-functions"></a>Üye İşlevleri

|Tür Tanımlaması|Açıklama|
|---------------------|-----------------|
|delegate_type|Genel temsilci türü.|
|first_argument_type|Functor ilk bağımsız değişken türü.|
|result_type|Functor sonuç türü.|
|second_argument_type|Functor ikinci bağımsız değişken türü.|
|stored_function_type|Bir functor türü.|

|Üye|Açıklama|
|------------|-----------------|
|binder2nd|İşlev nesnesini oluşturur.|

|İşleç|Açıklama|
|--------------|-----------------|
|operator()|İstenen işlev hesaplar.|
|işleç delegate_type^()|Bir temsilci functor çevirir.|

### <a name="remarks"></a>Açıklamalar

Şablon sınıfı, iki bağımsız functor ve ikinci bir bağımsız değişken depolayan bir tek bağımsız değişkenli functor açıklar. Üye işleci tanımlar `operator()` nesne bir işlev olarak ne zaman çağrıldığını böylece, sağlanan ilk bağımsız değişken ve depolanan ikinci bağımsız değişkeni ile saklı functor arama sonucunu döndürür.

Nesne türü olan bir işlev bağımsız değişkeni geçirebilirsiniz `delegate_type^` ve uygun şekilde dönüştürülür.

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

## <a name="divides"></a> böler (STL/CLR)

Şablon sınıfı bir functor tanımlar, çağrıldığında, ilk bağımsız değişken ikinciye göre bölünmüş döndürür. Bunu, bağımsız değişken türü açısından bir işlev nesnesi belirtin.

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

*bağımsız değişken*<br/>
Bağımsız değişkenler ve dönüş değeri türü.

### <a name="member-functions"></a>Üye İşlevleri

|Tür Tanımlaması|Açıklama|
|---------------------|-----------------|
|delegate_type|Genel temsilci türü.|
|first_argument_type|Functor ilk bağımsız değişken türü.|
|result_type|Functor sonuç türü.|
|second_argument_type|Functor ikinci bağımsız değişken türü.|

|Üye|Açıklama|
|------------|-----------------|
|böler|İşlev nesnesini oluşturur.|

|İşleç|Açıklama|
|--------------|-----------------|
|operator()|İstenen işlev hesaplar.|
|işleç delegate_type^()|Bir temsilci functor çevirir.|

### <a name="remarks"></a>Açıklamalar

Şablon sınıfı, iki bağımsız functor açıklar. Üye işleci tanımlar `operator()` nesne bir işlev olarak ne zaman çağrıldığını böylece, ikinciye göre bölünmüş ilk bağımsız değişkeni döndürür.

Nesne türü olan bir işlev bağımsız değişkeni geçirebilirsiniz `delegate_type^` ve uygun şekilde dönüştürülür.

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

## <a name="equal_to"></a> equal_to (STL/CLR)

Şablon sınıfı bir functor açıklar. yalnızca ilk bağımsız değişken ikinci eşittir, çağrıldığında, true değerini döndürür. Bunu, bağımsız değişken türü açısından bir işlev nesnesi belirtin.

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

*bağımsız değişken*<br/>
Bağımsız değişken türü.

### <a name="member-functions"></a>Üye İşlevleri

|Tür Tanımlaması|Açıklama|
|---------------------|-----------------|
|delegate_type|Genel temsilci türü.|
|first_argument_type|Functor ilk bağımsız değişken türü.|
|result_type|Functor sonuç türü.|
|second_argument_type|Functor ikinci bağımsız değişken türü.|

|Üye|Açıklama|
|------------|-----------------|
|equal_to|İşlev nesnesini oluşturur.|

|İşleç|Açıklama|
|--------------|-----------------|
|operator()|İstenen işlev hesaplar.|
|işleç delegate_type^()|Bir temsilci functor çevirir.|

### <a name="remarks"></a>Açıklamalar

Şablon sınıfı, iki bağımsız functor açıklar. Üye işleci tanımlar `operator()` nesne bir işlev olarak ne zaman çağrıldığını böylece, yalnızca ilk bağımsız değişken ikinci eşitse true değerini döndürür.

Nesne türü olan bir işlev bağımsız değişkeni geçirebilirsiniz `delegate_type^` ve uygun şekilde dönüştürülür.

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

## <a name="greater"></a> büyük (STL/CLR)

Şablon sınıfı bir functor açıklar. yalnızca ilk bağımsız değişken ikinciden büyükse, çağrıldığında, true değerini döndürür. Bunu, bağımsız değişken türü açısından bir işlev nesnesi belirtin.

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

*bağımsız değişken*<br/>
Bağımsız değişken türü.

### <a name="member-functions"></a>Üye İşlevleri

|Tür Tanımlaması|Açıklama|
|---------------------|-----------------|
|delegate_type|Genel temsilci türü.|
|first_argument_type|Functor ilk bağımsız değişken türü.|
|result_type|Functor sonuç türü.|
|second_argument_type|Functor ikinci bağımsız değişken türü.|

|Üye|Açıklama|
|------------|-----------------|
|büyüktür|İşlev nesnesini oluşturur.|

|İşleç|Açıklama|
|--------------|-----------------|
|operator()|İstenen işlev hesaplar.|
|işleç delegate_type ^|Bir temsilci functor çevirir.|

### <a name="remarks"></a>Açıklamalar

Şablon sınıfı, iki bağımsız functor açıklar. Üye işleci tanımlar `operator()` nesne bir işlev olarak ne zaman çağrıldığını böylece, yalnızca, ilk bağımsız değişken ikinciden büyükse true değerini döndürür.

Nesne türü olan bir işlev bağımsız değişkeni geçirebilirsiniz `delegate_type^` ve uygun şekilde dönüştürülür.

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

## <a name="greater_equal"></a> greater_equal (STL/CLR)

Şablon sınıfı bir functor tanımlar, çağrıldığında, yalnızca ilk bağımsız değişken büyük veya ikincisine eşitse true değerini döndürür. Bunu, bağımsız değişken türü açısından bir işlev nesnesi belirtin.

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

*bağımsız değişken*<br/>
Bağımsız değişken türü.

### <a name="member-functions"></a>Üye İşlevleri

|Tür Tanımlaması|Açıklama|
|---------------------|-----------------|
|delegate_type|Genel temsilci türü.|
|first_argument_type|Functor ilk bağımsız değişken türü.|
|result_type|Functor sonuç türü.|
|second_argument_type|Functor ikinci bağımsız değişken türü.|

|Üye|Açıklama|
|------------|-----------------|
|greater_equal|İşlev nesnesini oluşturur.|

|İşleç|Açıklama|
|--------------|-----------------|
|operator()|İstenen işlev hesaplar.|
|işleç delegate_type ^|Bir temsilci functor çevirir.|

### <a name="remarks"></a>Açıklamalar

Şablon sınıfı, iki bağımsız functor açıklar. Üye işleci tanımlar `operator()` nesne bir işlev olarak ne zaman çağrıldığını böylece, yalnızca ilk bağımsız değişken büyük veya ikincisine eşitse true değerini döndürür.

Nesne türü olan bir işlev bağımsız değişkeni geçirebilirsiniz `delegate_type^` ve uygun şekilde dönüştürülür.

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

## <a name="less"></a> daha az (STL/CLR)

Şablon sınıfı bir functor açıklar. yalnızca ilk bağımsız değişken ikinciden küçükse, çağrıldığında, true değerini döndürür, ikinci daha. Bunu, bağımsız değişken türü açısından bir işlev nesnesi belirtin.

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

*bağımsız değişken*<br/>
Bağımsız değişken türü.

### <a name="member-functions"></a>Üye İşlevleri

|Tür Tanımlaması|Açıklama|
|---------------------|-----------------|
|delegate_type|Genel temsilci türü.|
|first_argument_type|Functor ilk bağımsız değişken türü.|
|result_type|Functor sonuç türü.|
|second_argument_type|Functor ikinci bağımsız değişken türü.|

|Üye|Açıklama|
|------------|-----------------|
|daha az|İşlev nesnesini oluşturur.|

|İşleç|Açıklama|
|--------------|-----------------|
|operator()|İstenen işlev hesaplar.|
|işleç delegate_type ^|Bir temsilci functor çevirir.|

### <a name="remarks"></a>Açıklamalar

Şablon sınıfı, iki bağımsız functor açıklar. Üye işleci tanımlar `operator()` nesne bir işlev olarak ne zaman çağrıldığını böylece, yalnızca ilk bağımsız değişken ikinciden küçükse varsa true değerini döndürür ikinciden.

Nesne türü olan bir işlev bağımsız değişkeni geçirebilirsiniz `delegate_type^` ve uygun şekilde dönüştürülür.

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

## <a name="less_equal"></a> less_equal (STL/CLR)

Şablon sınıfı bir functor tanımlar, çağrıldığında, yalnızca ilk bağımsız değişken ikinciden küçük veya eşit ise true değerini döndürür. Bunu, bağımsız değişken türü açısından bir işlev nesnesi belirtin.

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

*bağımsız değişken*<br/>
Bağımsız değişken türü.

### <a name="member-functions"></a>Üye İşlevleri

|Tür Tanımlaması|Açıklama|
|---------------------|-----------------|
|delegate_type|Genel temsilci türü.|
|first_argument_type|Functor ilk bağımsız değişken türü.|
|result_type|Functor sonuç türü.|
|second_argument_type|Functor ikinci bağımsız değişken türü.|

|Üye|Açıklama|
|------------|-----------------|
|less_equal|İşlev nesnesini oluşturur.|

|İşleç|Açıklama|
|--------------|-----------------|
|operator()|İstenen işlev hesaplar.|
|işleç delegate_type ^|Bir temsilci functor çevirir.|

### <a name="remarks"></a>Açıklamalar

Şablon sınıfı, iki bağımsız functor açıklar. Üye işleci tanımlar `operator()` nesne bir işlev olarak ne zaman çağrıldığını böylece, yalnızca ilk bağımsız değişken ikinciden küçük veya eşit ise true değerini döndürür.

Nesne türü olan bir işlev bağımsız değişkeni geçirebilirsiniz `delegate_type^` ve uygun şekilde dönüştürülür.

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

## <a name="logical_and"></a> logical_and (STL/CLR)

Şablon sınıfı bir functor açıklar. yalnızca ilk bağımsız değişken hem de ikinci test olarak true, çağrıldığında, true değerini döndürür. Bunu, bağımsız değişken türü açısından bir işlev nesnesi belirtin.

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

*bağımsız değişken*<br/>
Bağımsız değişken türü.

### <a name="member-functions"></a>Üye İşlevleri

|Tür Tanımlaması|Açıklama|
|---------------------|-----------------|
|delegate_type|Genel temsilci türü.|
|first_argument_type|Functor ilk bağımsız değişken türü.|
|result_type|Functor sonuç türü.|
|second_argument_type|Functor ikinci bağımsız değişken türü.|

|Üye|Açıklama|
|------------|-----------------|
|logical_and|İşlev nesnesini oluşturur.|

|İşleç|Açıklama|
|--------------|-----------------|
|operator()|İstenen işlev hesaplar.|
|işleç delegate_type ^|Bir temsilci functor çevirir.|

### <a name="remarks"></a>Açıklamalar

Şablon sınıfı, iki bağımsız functor açıklar. Üye işleci tanımlar `operator()` nesne bir işlev olarak ne zaman çağrıldığını böylece, yalnızca ilk bağımsız değişken hem de ikinci test olarak true ise true değerini döndürür.

Nesne türü olan bir işlev bağımsız değişkeni geçirebilirsiniz `delegate_type^` ve uygun şekilde dönüştürülür.

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

## <a name="logical_not"></a> logical_not (STL/CLR)

Şablon sınıfı bir functor tanımlar çağrıldığında, ya da yalnızca doğru değerini döndürür, bağımsız değişkeninin değerini false sınar. Bunu, bağımsız değişken türü açısından bir işlev nesnesi belirtin.

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

*bağımsız değişken*<br/>
Bağımsız değişken türü.

### <a name="member-functions"></a>Üye İşlevleri

|Tür Tanımlaması|Açıklama|
|---------------------|-----------------|
|argument_type|Functor bağımsız değişken türü.|
|delegate_type|Genel temsilci türü.|
|result_type|Functor sonuç türü.|

|Üye|Açıklama|
|------------|-----------------|
|logical_not|İşlev nesnesini oluşturur.|

|İşleç|Açıklama|
|--------------|-----------------|
|operator()|İstenen işlev hesaplar.|
|işleç delegate_type ^|Bir temsilci functor çevirir.|

### <a name="remarks"></a>Açıklamalar

Şablon sınıfı, bir tek bağımsız değişkenli functor açıklar. Üye işleci tanımlar `operator()` nesne bir işlev olarak ne zaman çağrıldığını böylece, yalnızca bağımsız değişkeninin değerini false test varsa true değerini döndürür.

Nesne türü olan bir işlev bağımsız değişkeni geçirebilirsiniz `delegate_type^` ve uygun şekilde dönüştürülür.

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

## <a name="logical_or"></a> logical_or (STL/CLR)

Şablon sınıfı bir functor açıklar. yalnızca ilk bağımsız değişken ya da ikinci testler true, çağrıldığında, true değerini döndürür. Bunu, bağımsız değişken türü açısından bir işlev nesnesi belirtin.

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

*bağımsız değişken*<br/>
Bağımsız değişken türü.

### <a name="member-functions"></a>Üye İşlevleri

|Tür Tanımlaması|Açıklama|
|---------------------|-----------------|
|delegate_type|Genel temsilci türü.|
|first_argument_type|Functor ilk bağımsız değişken türü.|
|result_type|Functor sonuç türü.|
|second_argument_type|Functor ikinci bağımsız değişken türü.|

|Üye|Açıklama|
|------------|-----------------|
|logical_or|İşlev nesnesini oluşturur.|

|İşleç|Açıklama|
|--------------|-----------------|
|operator()|İstenen işlev hesaplar.|
|işleç delegate_type ^|Bir temsilci functor çevirir.|

### <a name="remarks"></a>Açıklamalar

Şablon sınıfı, iki bağımsız functor açıklar. Üye işleci tanımlar `operator()` nesne bir işlev olarak ne zaman çağrıldığını böylece, yalnızca ilk bağımsız değişken ya da ikinci testler true ise true değerini döndürür.

Nesne türü olan bir işlev bağımsız değişkeni geçirebilirsiniz `delegate_type^` ve uygun şekilde dönüştürülür.

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

## <a name="minus"></a> (STL/CLR)

Şablon sınıfı bir functor tanımlar, çağrıldığında, ilk bağımsız değişken ikinci eksi döndürür. Bunu, bağımsız değişken türü açısından bir işlev nesnesi belirtin.

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

*bağımsız değişken*<br/>
Bağımsız değişkenler ve dönüş değeri türü.

### <a name="member-functions"></a>Üye İşlevleri

|Tür Tanımlaması|Açıklama|
|---------------------|-----------------|
|delegate_type|Genel temsilci türü.|
|first_argument_type|Functor ilk bağımsız değişken türü.|
|result_type|Functor sonuç türü.|
|second_argument_type|Functor ikinci bağımsız değişken türü.|

|Üye|Açıklama|
|------------|-----------------|
|eksi|İşlev nesnesini oluşturur.|

|İşleç|Açıklama|
|--------------|-----------------|
|operator()|İstenen işlev hesaplar.|
|işleç delegate_type ^|Bir temsilci functor çevirir.|

### <a name="remarks"></a>Açıklamalar

Şablon sınıfı, iki bağımsız functor açıklar. Üye işleci tanımlar `operator()` nesne bir işlev olarak ne zaman çağrıldığını böylece, ilk bağımsız değişken ikinci eksi döndürür.

Nesne türü olan bir işlev bağımsız değişkeni geçirebilirsiniz `delegate_type^` ve uygun şekilde dönüştürülür.

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

## <a name="modulus"></a> mod (STL/CLR)

Şablon sınıfı bir functor tanımlar, çağrıldığında, ilk bağımsız değişken ikinci modül döndürür. Bunu, bağımsız değişken türü açısından bir işlev nesnesi belirtin.

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

*bağımsız değişken*<br/>
Bağımsız değişkenler ve dönüş değeri türü.

### <a name="member-functions"></a>Üye İşlevleri

|Tür Tanımlaması|Açıklama|
|---------------------|-----------------|
|delegate_type|Genel temsilci türü.|
|first_argument_type|Functor ilk bağımsız değişken türü.|
|result_type|Functor sonuç türü.|
|second_argument_type|Functor ikinci bağımsız değişken türü.|

|Üye|Açıklama|
|------------|-----------------|
|mod|İşlev nesnesini oluşturur.|

|İşleç|Açıklama|
|--------------|-----------------|
|operator()|İstenen işlev hesaplar.|
|işleç delegate_type ^|Bir temsilci functor çevirir.|

### <a name="remarks"></a>Açıklamalar

Şablon sınıfı, iki bağımsız functor açıklar. Üye işleci tanımlar `operator()` nesne bir işlev olarak ne zaman çağrıldığını böylece, ilk bağımsız değişken ikinci modül döndürür.

Nesne türü olan bir işlev bağımsız değişkeni geçirebilirsiniz `delegate_type^` ve uygun şekilde dönüştürülür.

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

## <a name="multiplies"></a> çarpar (STL/CLR)

Şablon sınıfı bir functor tanımlar, çağrıldığında, ilk bağımsız değişken ikinci kez döndürür. Bunu, bağımsız değişken türü açısından bir işlev nesnesi belirtin.

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

*bağımsız değişken*<br/>
Bağımsız değişkenler ve dönüş değeri türü.

### <a name="member-functions"></a>Üye İşlevleri

|Tür Tanımlaması|Açıklama|
|---------------------|-----------------|
|delegate_type|Genel temsilci türü.|
|first_argument_type|Functor ilk bağımsız değişken türü.|
|result_type|Functor sonuç türü.|
|second_argument_type|Functor ikinci bağımsız değişken türü.|

|Üye|Açıklama|
|------------|-----------------|
|çarpar|İşlev nesnesini oluşturur.|

|İşleç|Açıklama|
|--------------|-----------------|
|operator()|İstenen işlev hesaplar.|
|işleç delegate_type ^|Bir temsilci functor çevirir.|

### <a name="remarks"></a>Açıklamalar

Şablon sınıfı, iki bağımsız functor açıklar. Üye işleci tanımlar `operator()` nesne bir işlev olarak ne zaman çağrıldığını böylece, ilk bağımsız değişken ikinci kez döndürür.

Nesne türü olan bir işlev bağımsız değişkeni geçirebilirsiniz `delegate_type^` ve uygun şekilde dönüştürülür.

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

## <a name="negate"></a> negate (STL/CLR)

Şablon sınıfı bir functor tanımlar, çağrıldığında, bağımsız değişken negatif döndürür. Bunu, bağımsız değişken türü açısından bir işlev nesnesi belirtin.

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

*bağımsız değişken*<br/>
Bağımsız değişken türü.

### <a name="member-functions"></a>Üye İşlevleri

|Tür Tanımlaması|Açıklama|
|---------------------|-----------------|
|argument_type|Functor bağımsız değişken türü.|
|delegate_type|Genel temsilci türü.|
|result_type|Functor sonuç türü.|

|Üye|Açıklama|
|------------|-----------------|
|olumsuzlaştırma|İşlev nesnesini oluşturur.|

|İşleç|Açıklama|
|--------------|-----------------|
|operator()|İstenen işlev hesaplar.|
|işleç delegate_type ^|Bir temsilci functor çevirir.|

### <a name="remarks"></a>Açıklamalar

Şablon sınıfı, bir tek bağımsız değişkenli functor açıklar. Üye işleci tanımlar `operator()` nesne bir işlev olarak ne zaman çağrıldığını böylece, tasarruflarını bağımsız değişkenini döndürür.

Nesne türü olan bir işlev bağımsız değişkeni geçirebilirsiniz `delegate_type^` ve uygun şekilde dönüştürülür.

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

## <a name="not_equal_to"></a> not_equal_to (STL/CLR)

Şablon sınıfı bir functor açıklar. yalnızca ilk bağımsız değişken ikinci eşit değil, çağrıldığında, true değerini döndürür. Bunu, bağımsız değişken türü açısından bir işlev nesnesi belirtin.

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

*bağımsız değişken*<br/>
Bağımsız değişken türü.

### <a name="member-functions"></a>Üye İşlevleri

|Tür Tanımlaması|Açıklama|
|---------------------|-----------------|
|delegate_type|Genel temsilci türü.|
|first_argument_type|Functor ilk bağımsız değişken türü.|
|result_type|Functor sonuç türü.|
|second_argument_type|Functor ikinci bağımsız değişken türü.|

|Üye|Açıklama|
|------------|-----------------|
|not_equal_to|İşlev nesnesini oluşturur.|

|İşleç|Açıklama|
|--------------|-----------------|
|operator()|İstenen işlev hesaplar.|
|işleç delegate_type ^|Bir temsilci functor çevirir.|

### <a name="remarks"></a>Açıklamalar

Şablon sınıfı, iki bağımsız functor açıklar. Üye işleci tanımlar `operator()` nesne bir işlev olarak ne zaman çağrıldığını böylece, yalnızca ilk bağımsız değişken ikinci eşit değilse true değerini döndürür.

Nesne türü olan bir işlev bağımsız değişkeni geçirebilirsiniz `delegate_type^` ve uygun şekilde dönüştürülür.

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

## <a name="not1"></a> Not1 (STL/CLR)

Oluşturur bir `unary_negate` bir functor için.

### <a name="syntax"></a>Sözdizimi

```cpp
template<typename Fun>
    unary_negate<Fun> not1(Fun% functor);
```

#### <a name="template-parameters"></a>Şablon Parametreleri

*Eğlence*<br/>
Bir functor türü.

#### <a name="function-parameters"></a>İşlev parametreleri

*functor*<br/>
Sarılacak functor.

### <a name="remarks"></a>Açıklamalar

Şablon işlevinin döndürdüğü [unary_negate (STL/CLR)](../dotnet/unary-negate-stl-clr.md)`<Fun>(functor)`. Tek bağımsız değişkenli functor, mantıksal değil sunan bir functor içinde sarmalamak için kullanışlı bir yol olarak kullanın.

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

## <a name="not2"></a> not2 (STL/CLR)

Oluşturur bir `binary_negate` bir functor için.

### <a name="syntax"></a>Sözdizimi

```cpp
template<typename Fun>
    binary_negate<Fun> not2(Fun% functor);
```

#### <a name="template-parameters"></a>Şablon Parametreleri

*Eğlence*<br/>
Bir functor türü.

#### <a name="function-parameters"></a>İşlev parametreleri

*functor*<br/>
Sarılacak functor.

### <a name="remarks"></a>Açıklamalar

Şablon işlevinin döndürdüğü [binary_negate (STL/CLR)](../dotnet/binary-negate-stl-clr.md)`<Fun>(functor)`. İki bağımsız functor, mantıksal değil sunan bir functor içinde sarmalamak için kullanışlı bir yol olarak kullanın.

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

## <a name="plus"></a> artı (STL/CLR)

Şablon sınıfı bir functor tanımlar, çağrıldığında, ilk bağımsız değişken artı saniyeyi döndürür. Bunu, bağımsız değişken türü açısından bir işlev nesnesi belirtin.

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

*bağımsız değişken*<br/>
Bağımsız değişkenler ve dönüş değeri türü.

### <a name="member-functions"></a>Üye İşlevleri

|Tür Tanımlaması|Açıklama|
|---------------------|-----------------|
|delegate_type|Genel temsilci türü.|
|first_argument_type|Functor ilk bağımsız değişken türü.|
|result_type|Functor sonuç türü.|
|second_argument_type|Functor ikinci bağımsız değişken türü.|

|Üye|Açıklama|
|------------|-----------------|
|artı|İşlev nesnesini oluşturur.|

|İşleç|Açıklama|
|--------------|-----------------|
|operator()|İstenen işlev hesaplar.|
|işleç delegate_type ^|Bir temsilci functor çevirir.|

### <a name="remarks"></a>Açıklamalar

Şablon sınıfı, iki bağımsız functor açıklar. Üye işleci tanımlar `operator()` nesne bir işlev olarak ne zaman çağrıldığını böylece, ilk bağımsız değişken artı saniyeyi döndürür.

Nesne türü olan bir işlev bağımsız değişkeni geçirebilirsiniz `delegate_type^` ve uygun şekilde dönüştürülür.

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

## <a name="unary_delegate"></a> unary_delegate (STL/CLR)

Tek bağımsız değişkenli temsilci genereic sınıfı açıklar. Bunu bir temsilci, bağımsız değişkenin ve dönüş türleri açısından belirtin.

### <a name="syntax"></a>Sözdizimi

```cpp
generic<typename Arg,
    typename Result>
    delegate Result unary_delegate(Arg);
```

#### <a name="parameters"></a>Parametreler

*bağımsız değişken*<br/>
Bağımsız değişken türü.

*Sonuç*<br/>
Dönüş türü.

### <a name="remarks"></a>Açıklamalar

Genereic temsilci tek bağımsız değişkenli işlev açıklar.

Unutmayın:

`unary_delegare<int, int> Fun1;`

`unary_delegare<int, int> Fun2;`

türleri `Fun1` ve `Fun2` eşanlamlıdır, while için:

`delegate int Fun1(int);`

`delegate int Fun2(int);`

Bunlar aynı türde değil.

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

## <a name="unary_delegate_noreturn"></a> unary_delegate_noreturn (STL/CLR)

Döndüren tek bağımsız değişkenli temsilci genereic sınıfı açıklar **void**. Kullanmanız açısından, bağımsız değişken türü temsilci belirtin.

### <a name="syntax"></a>Sözdizimi

```cpp
generic<typename Arg>
    delegate void unary_delegate_noreturn(Arg);
```

#### <a name="parameters"></a>Parametreler

*bağımsız değişken*<br/>
Bağımsız değişken türü.

### <a name="remarks"></a>Açıklamalar

Döndüren tek bağımsız değişkenli işlev genereic temsilci açıklar **void**.

Unutmayın:

`unary_delegare_noreturn<int> Fun1;`

`unary_delegare_noreturn<int> Fun2;`

türleri `Fun1` ve `Fun2` eşanlamlıdır, while için:

`delegate void Fun1(int);`

`delegate void Fun2(int);`

Bunlar aynı türde değil.

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

## <a name="unary_negate"></a> unary_negate (STL/CLR)

Şablon sınıfı bir functor tanımlar, çağrıldığında, mantıksal döndürür, saklı tek bağımsız değişkenli functor, değil. Bunu kendi saklı functor açısından bir işlev nesnesi belirtin.

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

*Eğlence*<br/>
Saklı functor türü.

### <a name="member-functions"></a>Üye İşlevleri

|Tür Tanımlaması|Açıklama|
|---------------------|-----------------|
|argument_type|Functor bağımsız değişken türü.|
|delegate_type|Genel temsilci türü.|
|result_type|Functor sonuç türü.|

|Üye|Açıklama|
|------------|-----------------|
|unary_negate|İşlev nesnesini oluşturur.|

|İşleç|Açıklama|
|--------------|-----------------|
|operator()|İstenen işlev hesaplar.|
|delegate_type ^|Bir temsilci functor çevirir.|

### <a name="remarks"></a>Açıklamalar

Şablon sınıfı, başka bir tek bağımsız değişkenli functor depolayan bir tek bağımsız değişkenli functor açıklar. Üye işleci tanımlar `operator()` nesne bir işlev olarak ne zaman çağrıldığını böylece, mantıksal döndürür saklı functor değil bağımsız değişkeniyle çağrılır.

Nesne türü olan bir işlev bağımsız değişkeni geçirebilirsiniz `delegate_type^` ve uygun şekilde dönüştürülür.

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