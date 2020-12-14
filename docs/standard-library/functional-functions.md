---
description: 'Daha fazla bilgi edinin: &lt; işlevsel &gt; işlevler'
title: '&lt;işlevsel &gt; işlevler'
ms.date: 02/21/2019
f1_keywords:
- functional/std::bind
- functional/std::bind1st
- functional/std::bind2nd
- functional/std::bit_and
- functional/std::bit_not
- functional/std::bit_or
- functional/std::bit_xor
- functional/std::cref
- type_traits/std::cref
- functional/std::mem_fn
- functional/std::mem_fun_ref
- functional/std::not1
- functional/std::not2
- functional/std::not_fn
- functional/std::ptr_fun
- functional/std::ref
- functional/std::swap
helpviewer_keywords:
- std::bind [C++]
- std::bind1st
- std::bind2nd
- std::bit_and [C++]
- std::bit_not [C++]
- std::bit_or [C++]
- std::bit_xor [C++]
- std::cref [C++]
ms.assetid: c34d0b45-50a7-447a-9368-2210d06339a4
ms.openlocfilehash: f3ae9fca75801555c0341923d0fc42db94546cd1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97232169"
---
# <a name="ltfunctionalgt-functions"></a>&lt;işlevsel &gt; işlevler

Bu işlevler C++ 11 ' de kullanımdan kaldırılmıştır ve C++ 17 ' de kaldırılır:

[bind1st](#bind1st)\
[bind2nd](#bind2nd)\
[mem_fun](#mem_fun)\
[mem_fun_ref](#mem_fun_ref)\
[ptr_fun](#ptr_fun)

Bu işlevler C++ 17 ' de kullanımdan kaldırılmıştır:

[Not1](#not1)\
[NOT2](#not2)

## <a name="bind"></a><a name="bind"></a> bağladığınızda

Bağımsız değişkenleri çağrılabilir bir nesneye bağlar.

```cpp
template <class FT, class T1, class T2, ..., class TN>
    unspecified bind(FT fn, T1 t1, T2 t2, ..., TN tN);

template <class RTy, class FT, class T1, class T2, ..., class TN>
    unspecified bind(FT fn, T1 t1, T2 t2, ..., TN tN);
```

### <a name="parameters"></a>Parametreler

*Fey*\
Çağrılacak nesnenin türü.

*TN*\
Nth Call bağımsız değişkeninin türü.

*FN*\
Çağrılacak nesne.

*tN*\
Nth Call bağımsız değişkeni.

### <a name="remarks"></a>Açıklamalar

Türler kopya oluşturulabilir olmalıdır `FT, T1, T2, ..., TN` ve `INVOKE(fn, t1, ..., tN)` bazı değerler için geçerli bir ifade olmalıdır `w1, w2, ..., wN` .

İlk şablon işlevi, `g` zayıf bir sonuç türü olan bir iletme çağrısı sarmalayıcısı döndürür. ' Nin etkisi `g(u1, u2, ..., uM)` `INVOKE(f, v1, v2, ..., vN,` [invoke_result](../standard-library/invoke-result-class.md) `<FT cv (V1, V2, ..., VN)>::type)` , burada, `cv` MF niteleyicisi, `g` ve bağlantılı bağımsız değişkenlerin değerlerinin ve türlerinin `v1, v2, ..., vN` aşağıda belirtilen şekilde belirlendiği şekilde belirlenir. Çağrılabilir bir nesne, özel bir bağımsız değişken listesiyle çağrılabilir bir nesne yapmak için bağımsız değişkenleri bir çağrılabilir nesneye bağlamak için kullanılır.

İkinci şablon işlevi, `g` `result_type` için bir eş anlamlı olan bir iletme çağrısı sarmalayıcısı döndürür `RTy` . ' Nin etkisi `g(u1, u2, ..., uM)` `INVOKE(f, v1, v2, ..., vN, RTy)` , burada `cv` CV niteleyicisi, `g` ve bağlantılı bağımsız değişkenlerin değerlerinin ve türlerinin `v1, v2, ..., vN` aşağıda belirtilen şekilde belirlendiği şekilde belirlenir. Çağrılabilir bir nesne ve belirli bir dönüş türü ile çağrılabilir bir nesne oluşturmak için bağımsız değişkenleri çağrılabilir bir nesneye bağlamak için kullanın.

Bağlı bağımsız değişkenlerin `v1, v2, ..., vN` ve bunlara karşılık gelen türlerin değerleri, `V1, V2, ..., VN` çağrısı içindeki karşılık gelen bağımsız değişken türüne `ti` `Ti` `bind` ve `cv` çağrı sarmalayıcının CV niteleyicilerine `g` aşağıdaki şekilde bağlıdır:

Eğer `ti` türünde `reference_wrapper<T>` bağımsız değişken ise `vi` `ti.get()` ve türü `Vi` `T&` ;

değeri `std::is_bind_expression<Ti>::value` **`true`** bağımsız değişkeni ise `vi` `ti(u1, u2, ..., uM)` ve türü `Vi` `result_of<Ti` `cv` `(U1&, U2&, ..., UN&>::type` ise,

değeri `j` `std::is_placeholder<Ti>::value` sıfır değilse bağımsız değişkeni `vi` `uj` ve türü `Vi` `Uj&` ;

Aksi takdirde bağımsız değişken olur `vi` `ti` ve türü `Vi` `Ti` `cv` `&` .

Örneğin, bir işlev verildiğinde `f(int, int)` ifade, `bind(f, _1, 0)` çağıran bir iletme Çağrı sarmalayıcısı döndürür `cw` `cw(x)` `f(x, 0)` . İfade, `bind(f, 0, _1)` çağıran bir iletme Çağrı sarmalayıcısı döndürür `cw` `cw(x)` `f(0, x)` .

Bir çağrıdaki bağımsız değişkenlerin sayısı `bind` ve bağımsız değişkeni, `fn` çağrılabilir nesnesine geçirilebilecek bağımsız değişken sayısına eşit olmalıdır `fn` . Örneğin, `bind(cos, 1.0)` doğru ve her ikisi de `bind(cos)` `bind(cos, _1, 0.0)` yanlıştır.

Tarafından döndürülen çağrı sarmalayıcısına yapılan işlev çağrısındaki bağımsız değişkenlerin sayısı en `bind` az, `is_placeholder<PH>::value` çağrısı içindeki tüm yer tutucu bağımsız değişkenleri için en yüksek Numaralandırılmış değer kadar büyük olmalıdır `bind` . Örneğin, `bind(cos, _2)(0.0, 1.0)` doğru (ve döndürür `cos(1.0)` ) ve `bind(cos, _2)(0.0)` yanlış.

### <a name="example"></a>Örnek

```cpp
// std__functional__bind.cpp
// compile with: /EHsc
#include <functional>
#include <algorithm>
#include <iostream>

using namespace std::placeholders;

void square(double x)
{
    std::cout << x << "^2 == " << x * x << std::endl;
}

void product(double x, double y)
{
    std::cout << x << "*" << y << " == " << x * y << std::endl;
}

int main()
{
    double arg[] = { 1, 2, 3 };

    std::for_each(&arg[0], arg + 3, square);
    std::cout << std::endl;

    std::for_each(&arg[0], arg + 3, std::bind(product, _1, 2));
    std::cout << std::endl;

    std::for_each(&arg[0], arg + 3, std::bind(square, _1));

    return (0);
}
```

```Output
1^2 == 1
2^2 == 4
3^2 == 9

1*2 == 2
2*2 == 4
3*2 == 6

1^2 == 1
2^2 == 4
3^2 == 9
```

## <a name="bind1st"></a><a name="bind1st"></a> bind1st

Bir ikili işlev nesnesini birli işlev nesnesine dönüştürmek için bir bağdaştırıcı oluşturan bir yardımcı şablon işlevi. İkili işlevin ilk bağımsız değişkenini belirtilen bir değere bağlar. C++ 11 ' de kullanım dışı bırakılmıştır ve C++ 17 ' de kaldırılmıştır.

```cpp
template <class Operation, class Type>
    binder1st <Operation> bind1st (const Operation& func, const Type& left);
```

### <a name="parameters"></a>Parametreler

*melerinin*\
Birli işlev nesnesine dönüştürülecek ikili işlev nesnesi.

*tarafta*\
İkili işlev nesnesinin ilk bağımsız değişkeninin bağlanacağı değer.

### <a name="return-value"></a>Dönüş Değeri

İkili işlev nesnesinin ilk bağımsız değişkenini *sol* değere bağlamayı sağlayan birli işlev nesnesi.

### <a name="remarks"></a>Açıklamalar

İşlev ciltleri bir tür işlev bağdaştırıcısından oluşur. İşlev nesnelerini döndürtikleri için, daha karmaşık ve güçlü ifadeler oluşturmak üzere belirli işlev kompozisyonu türlerinde kullanılabilirler.

*Func* , türünde bir nesnedir `Operation` ve `c` bir sabittir, `bind1st( func, c )` [binder1st](../standard-library/binder1st-class.md) sınıf oluşturucusuyla aynıdır `binder1st<Operation>(func, c)` ve kullanımı daha uygundur.

### <a name="example"></a>Örnek

```cpp
// functional_bind1st.cpp
// compile with: /EHsc
#include <vector>
#include <functional>
#include <algorithm>
#include <iostream>

using namespace std;

// Creation of a user-defined function object
// that inherits from the unary_function base class
class greaterthan5: unary_function<int, bool>
{
public:
    result_type operator()(argument_type i)
    {
        return (result_type)(i > 5);
    }
};

int main()
{
    vector<int> v1;
    vector<int>::iterator Iter;

    int i;
    for (i = 0; i <= 5; i++)
    {
        v1.push_back(5 * i);
    }

    cout << "The vector v1 = ( " ;
    for (Iter = v1.begin(); Iter != v1.end(); Iter++)
        cout << *Iter << " ";
    cout << ")" << endl;

    // Count the number of integers > 10 in the vector
    vector<int>::iterator::difference_type result1a;
    result1a = count_if(v1.begin(), v1.end(), bind1st(less<int>(), 10));
    cout << "The number of elements in v1 greater than 10 is: "
         << result1a << "." << endl;

    // Compare: counting the number of integers > 5 in the vector
    // with a user defined function object
    vector<int>::iterator::difference_type result1b;
    result1b = count_if(v1.begin(), v1.end(), greaterthan5());
    cout << "The number of elements in v1 greater than 5 is: "
         << result1b << "." << endl;

    // Count the number of integers < 10 in the vector
    vector<int>::iterator::difference_type result2;
    result2 = count_if(v1.begin(), v1.end(), bind2nd(less<int>(), 10));
    cout << "The number of elements in v1 less than 10 is: "
         << result2 << "." << endl;
}
```

```Output
The vector v1 = ( 0 5 10 15 20 25 )
The number of elements in v1 greater than 10 is: 3.
The number of elements in v1 greater than 5 is: 4.
The number of elements in v1 less than 10 is: 2.
```

## <a name="bind2nd"></a><a name="bind2nd"></a> bind2nd

Bir ikili işlev nesnesini birli işlev nesnesine dönüştürmek için bir bağdaştırıcı oluşturan bir yardımcı şablon işlevi. İkili işlevin ikinci bağımsız değişkenini belirtilen bir değere bağlar. C++ 11 ' de kullanım dışı bırakılmıştır ve C++ 17 ' de kaldırılmıştır.

```cpp
template <class Operation, class Type>
    binder2nd <Operation> bind2nd(const Operation& func, const Type& right);
```

### <a name="parameters"></a>Parametreler

*melerinin*\
Birli işlev nesnesine dönüştürülecek ikili işlev nesnesi.

*Right*\
İkili işlev nesnesinin ikinci bağımsız değişkeninin bağlanacağı değer.

### <a name="return-value"></a>Dönüş Değeri

Birli işlev nesnesi, ikili işlev nesnesinin ikinci bağımsız değişkenini *sağa* bağlamanın sonucu.

### <a name="remarks"></a>Açıklamalar

İşlev ciltleri bir tür işlev bağdaştırıcısından oluşur. İşlev nesnelerini döndürtikleri için, daha karmaşık ve güçlü ifadeler oluşturmak üzere belirli işlev kompozisyonu türlerinde kullanılabilirler.

*Func* , türünde bir nesnedir `Operation` ve `c` bir sabittir, `bind2nd(func, c)` [binder2nd](../standard-library/binder2nd-class.md) sınıf oluşturucusuyla aynı `binder2nd<Operation>(func, c)` ve kullanımı daha uygun olur.

### <a name="example"></a>Örnek

```cpp
// functional_bind2nd.cpp
// compile with: /EHsc
#include <vector>
#include <functional>
#include <algorithm>
#include <iostream>

using namespace std;

// Creation of a user-defined function object
// that inherits from the unary_function base class
class greaterthan15: unary_function<int, bool>
{
public:
    result_type operator()(argument_type i)
    {
        return (result_type)(i > 15);
    }
};

int main()
{
    vector<int> v1;
    vector<int>::iterator Iter;

    int i;
    for (i = 0; i <= 5; i++)
    {
        v1.push_back(5 * i);
    }

    cout << "The vector v1 = ( ";
    for (Iter = v1.begin(); Iter != v1.end(); Iter++)
        cout << *Iter << " ";
    cout << ")" << endl;

    // Count the number of integers > 10 in the vector
    vector<int>::iterator::difference_type result1a;
    result1a = count_if(v1.begin(), v1.end(), bind2nd(greater<int>(), 10));
    cout << "The number of elements in v1 greater than 10 is: "
         << result1a << "." << endl;

    // Compare counting the number of integers > 15 in the vector
    // with a user-defined function object
    vector<int>::iterator::difference_type result1b;
    result1b = count_if(v1.begin(), v1.end(), greaterthan15());
    cout << "The number of elements in v1 greater than 15 is: "
         << result1b << "." << endl;

    // Count the number of integers < 10 in the vector
    vector<int>::iterator::difference_type result2;
    result2 = count_if(v1.begin(), v1.end(), bind1st(greater<int>(), 10));
    cout << "The number of elements in v1 less than 10 is: "
         << result2 << "." << endl;
}
```

```Output
The vector v1 = ( 0 5 10 15 20 25 )
The number of elements in v1 greater than 10 is: 3.
The number of elements in v1 greater than 15 is: 2.
The number of elements in v1 less than 10 is: 2.
```

## <a name="bit_and"></a><a name="bit_and"></a> bit_and

Bağımsız değişkenlerinde bit düzeyinde ve işlem (ikili) yapan önceden tanımlanmış bir işlev nesnesi `operator&` .

```cpp
template <class Type = void>
struct bit_and : public binary_function<Type, Type, Type> {
    Type operator()(
    const Type& Left,
    const Type& Right) const;
};

// specialized transparent functor for operator&
template <>
struct bit_and<void>
{
    template <class T, class U>
    auto operator()(T&& Left, U&& Right) const  ->
        decltype(std::forward<T>(Left) & std::forward<U>(Right));
};
```

### <a name="parameters"></a>Parametreler

*Tür*, *T*, *U*\
`operator&`Belirtilen veya çıkartılan türlerin işlenenlerini destekleyen bir tür.

*Tarafta*\
Bit düzeyinde ve işlemin sol işleneni. Özelleştirilmemiş şablon *tür türünde bir* lvalue başvuru bağımsız değişkeni alır. Özel şablon, çıkarılan tür *T*'nin lvalue ve rvalue başvurusu bağımsız değişkenlerinin kusursuz bir şekilde iletilmesini yapar.

*Right*\
Bit düzeyinde ve işlemin sağ işleneni. Özelleştirilmemiş şablon *tür türünde bir* lvalue başvuru bağımsız değişkeni alır. Özel şablon, çıkarılan tür *U* için lvalue ve rvalue başvurusu bağımsız değişkenlerinin kusursuz bir şekilde iletilmesini yapar.

### <a name="return-value"></a>Dönüş Değeri

Sonucu `Left & Right` . Özel şablon, tarafından döndürülen türüne sahip olan sonucun kusursuz bir şekilde iletilmesini yapar `operator&` .

### <a name="remarks"></a>Açıklamalar

`bit_and`Functor temel veri türleri için tamsayı türleri veya ikili uygulayan kullanıcı tanımlı türler ile kısıtlıdır `operator&` .

## <a name="bit_not"></a><a name="bit_not"></a> bit_not

Bağımsız değişkeninde bir bit düzeyinde tamamlama (DEĞIL) işlemi (birli) yapan önceden tanımlanmış bir işlev nesnesi `operator~` . C++ 14 ' te eklendi.

```cpp
template <class Type = void>
struct bit_not : public unary_function<Type, Type>
{
    Type operator()(const Type& Right) const;
};

// specialized transparent functor for operator~
template <>
struct bit_not<void>
{
    template <class Type>
    auto operator()(Type&& Right) const -> decltype(~std::forward<Type>(Right));
};
```

### <a name="parameters"></a>Parametreler

*Türüyle*\
Birli destekleyen bir tür `operator~` .

*Right*\
Bit düzeyinde tamamlama işleminin işleneni. Özelleştirilmemiş şablon *tür türünde bir* lvalue başvuru bağımsız değişkeni alır. Özel şablon, Çıkarsanan tür *türünün* bir lvalue veya rvalue başvurusu bağımsız değişkeninin kusursuz bir şekilde iletilmesini yapar.

### <a name="return-value"></a>Dönüş Değeri

Sonucu `~ Right` . Özel şablon, tarafından döndürülen türüne sahip olan sonucun kusursuz bir şekilde iletilmesini yapar `operator~` .

### <a name="remarks"></a>Açıklamalar

`bit_not`Functor temel veri türleri için tamsayı türleri veya ikili uygulayan kullanıcı tanımlı türler ile kısıtlıdır `operator~` .

## <a name="bit_or"></a><a name="bit_or"></a> bit_or

Bağımsız değişkenlerinde bit düzeyinde OR işlemi () yapan önceden tanımlanmış bir işlev nesnesi `operator|` .

```cpp
template <class Type = void>
struct bit_or : public binary_function<Type, Type, Type> {
    Type operator()(
    const Type& Left,
    const Type& Right) const;
};

// specialized transparent functor for operator|
template <>
struct bit_or<void>
{
    template <class T, class U>
    auto operator()(T&& Left, U&& Right) const
        -> decltype(std::forward<T>(Left) | std::forward<U>(Right));
};
```

### <a name="parameters"></a>Parametreler

*Tür*, *T*, *U*\
`operator|`Belirtilen veya çıkartılan türlerin işlenenlerini destekleyen bir tür.

*Tarafta*\
Bit düzeyinde OR işleminin sol işleneni. Özelleştirilmemiş şablon *tür türünde bir* lvalue başvuru bağımsız değişkeni alır. Özel şablon, çıkarılan tür *T*'nin lvalue ve rvalue başvurusu bağımsız değişkenlerinin kusursuz bir şekilde iletilmesini yapar.

*Right*\
Bit düzeyinde veya işlemin sağ işleneni. Özelleştirilmemiş şablon *tür türünde bir* lvalue başvuru bağımsız değişkeni alır. Özel şablon, çıkarılan tür *U* için lvalue ve rvalue başvurusu bağımsız değişkenlerinin kusursuz bir şekilde iletilmesini yapar.

### <a name="return-value"></a>Dönüş Değeri

Sonucu `Left | Right` . Özel şablon, tarafından döndürülen türüne sahip olan sonucun kusursuz bir şekilde iletilmesini yapar `operator|` .

### <a name="remarks"></a>Açıklamalar

`bit_or`Functor temel veri türleri için tamsayı türleri veya uygulayan kullanıcı tanımlı türler ile kısıtlıdır `operator|` .

## <a name="bit_xor"></a><a name="bit_xor"></a> bit_xor

Bağımsız değişkenlerinde bit düzeyinde XOR işlemi (ikili) yapan önceden tanımlanmış bir işlev nesnesi `operator^` .

```cpp
template <class Type = void>
struct bit_xor : public binary_function<Type, Type, Type> {
    Type operator()(
    const Type& Left,
    const Type& Right) const;
};

// specialized transparent functor for operator^
template <>
struct bit_xor<void>
{
    template <class T, class U>
    auto operator()(T&& Left, U&& Right) const
        -> decltype(std::forward<T>(Left) ^ std::forward<U>(Right));
};
```

### <a name="parameters"></a>Parametreler

*Tür*, *T*, *U*\
`operator^`Belirtilen veya çıkartılan türlerin işlenenlerini destekleyen bir tür.

*Tarafta*\
Bit düzeyinde XOR işleminin sol işleneni. Özelleştirilmemiş şablon *tür türünde bir* lvalue başvuru bağımsız değişkeni alır. Özel şablon, çıkarılan tür *T*'nin lvalue ve rvalue başvurusu bağımsız değişkenlerinin kusursuz bir şekilde iletilmesini yapar.

*Right*\
Bit düzeyinde XOR işleminin sağ işleneni. Özelleştirilmemiş şablon *tür türünde bir* lvalue başvuru bağımsız değişkeni alır. Özel şablon, çıkarılan tür *U* için lvalue ve rvalue başvurusu bağımsız değişkenlerinin kusursuz bir şekilde iletilmesini yapar.

### <a name="return-value"></a>Dönüş Değeri

Sonucu `Left ^ Right` . Özel şablon, tarafından döndürülen türüne sahip olan sonucun kusursuz bir şekilde iletilmesini yapar `operator^` .

### <a name="remarks"></a>Açıklamalar

`bit_xor`Functor temel veri türleri için tamsayı türleri veya ikili uygulayan kullanıcı tanımlı türler ile kısıtlıdır `operator^` .

## <a name="cref"></a><a name="cref"></a> cref

`reference_wrapper`Bir bağımsız değişkenden const oluşturur.

```cpp
template <class Ty>
reference_wrapper<const Ty> cref(const Ty& arg);

template <class Ty>
reference_wrapper<const Ty> cref(const reference_wrapper<Ty>& arg);
```

### <a name="parameters"></a>Parametreler

*Kalite*\
Sarılacağı bağımsız değişkenin türü.

*değişkeni*\
Sarılacağı bağımsız değişken.

### <a name="remarks"></a>Açıklamalar

İlk işlev döndürür `reference_wrapper<const Ty>(arg.get())` . Const başvurusunu kaydırmak için bunu kullanırsınız. İkinci işlev döndürür `reference_wrapper<const Ty>(arg)` . Sarmalanan bir başvuruyu const başvurusu olarak yeniden sarmalamak için kullanabilirsiniz.

### <a name="example"></a>Örnek

```cpp
// std__functional__cref.cpp
// compile with: /EHsc
#include <functional>
#include <iostream>

int neg(int val)
    {
    return (-val);
    }

int main()
    {
    int i = 1;

    std::cout << "i = " << i << std::endl;
    std::cout << "cref(i) = " << std::cref(i) << std::endl;
    std::cout << "cref(neg)(i) = "
        << std::cref(&neg)(i) << std::endl;

    return (0);
    }
```

```Output
i = 1
cref(i) = 1
cref(neg)(i) = -1
```

## <a name="invoke"></a><a name="invoke"></a> Resync

Belirtilen bağımsız değişkenlerle çağrılabilir tüm nesneleri çağırır. C++ 17 ' ye eklenmiştir.

```cpp
template <class Callable, class... Args>
invoke_result_t<Callable, Args...>
    invoke(Callable&& fn, Args&&... args) noexcept(/* specification */);
```

### <a name="parameters"></a>Parametreler

*Çağrılabilir*\
Çağrılacak nesnenin türü.

*Args*\
Çağrı bağımsız değişkenlerinin türleri.

*FN*\
Çağrılacak nesne.

*args*\
Çağrı bağımsız değişkenleri.

*Min*\
**`noexcept`** Belirtimi `std::is_nothrow_invocable_v<Callable, Args>)` .

### <a name="remarks"></a>Açıklamalar

Parameters *bağımsız değişkenlerini* kullanarak çağrılabilir nesne *FN* çağırır. Etkin olarak, `INVOKE(std::forward<Callable>(fn), std::forward<Args>(args)...)` sözde işlevin aşağıdakilerden `INVOKE(f, t1, t2, ..., tN)` birini anlamı vardır:

- `(t1.*f)(t2, ..., tN)``f`, sınıfının üye işlevine yönelik bir işaretçi olduğunda ve türünde bir nesne ya da `T` `t1` ya da `T` `T` öğesinden türetilmiş bir türün `T` nesnesine başvuru olan bir nesnedir. Yani, true olduğunda `std::is_base_of<T, std::decay_t<decltype(t1)>>::value` .

- `(t1.get().*f)(t2, ..., tN)``f`, sınıfının üye işlevine yönelik bir işaretçidir `T` ve `std::decay_t<decltype(t1)>` bir özelleştirmesi olur `std::reference_wrapper` .

- `((*t1).*f)(t2, ..., tN)``f`, sınıfının üye işlevine yönelik bir işaretçidir `T` ve `t1` önceki türlerden biri değildir.

- `t1.*f` N = = 1 olduğunda ve bir `f` sınıfın üye verilerine yönelik bir işaretçisiyse ve türünde bir nesne ya da ya da `T` `t1` `T` `T` türetilmiş bir türün `T` nesnesine başvuru olan bir nesne ise.  Yani, true olduğunda `std::is_base_of<T, std::decay_t<decltype(t1)>>::value` .

- `t1.get().*f` N = = 1 olduğunda ve bir `f` sınıfın üye verilerine yönelik bir işaretçisiyse `T` ve `std::decay_t<decltype(t1)>` öğesinin bir özelleştirmesi olduğunda `std::reference_wrapper` .

- `(*t1).*f` N = = 1 olduğunda ve bir `f` sınıfın üye verilerine yönelik işaretçisiyse `T` ve `t1` önceki türlerden biri olmadığında.

- Diğer tüm durumlarda `f(t1, t2, ..., tN)`.

Çağrılabilir bir nesnenin sonuç türü hakkında bilgi için bkz. [invoke_result](invoke-result-class.md). Çağrılabilir türlerde koşullar için bkz. [is_invocable, is_invocable_r, is_nothrow_invocable, is_nothrow_invocable_r sınıfları](is-invocable-classes.md).

### <a name="example"></a>Örnek

```cpp
// functional_invoke.cpp
// compile using: cl /EHsc /std:c++17 functional_invoke.cpp
#include <functional>
#include <iostream>

struct Demo
{
    int n_;

    Demo(int const n) : n_{n} {}

    void operator()( int const i, int const j ) const
    {
        std::cout << "Demo operator( " << i << ", "
            << j << " ) is " << i * j << "\n";
    }

    void difference( int const i ) const
    {
        std::cout << "Demo.difference( " << i << " ) is "
            << n_ - i << "\n";
    }
};

void divisible_by_3(int const i)
{
    std::cout << i << ( i % 3 == 0 ? " is" : " isn't" )
        << " divisible by 3.\n";
}

int main()
{
    Demo d{ 42 };
    Demo * pd{ &d };
    auto pmf = &Demo::difference;
    auto pmd = &Demo::n_;

    // Invoke a function object, like calling d( 3, -7 )
    std::invoke( d, 3, -7 );

    // Invoke a member function, like calling
    // d.difference( 29 ) or (d.*pmf)( 29 )
    std::invoke( &Demo::difference, d, 29 );
    std::invoke( pmf, pd, 13 );

    // Invoke a data member, like access to d.n_ or d.*pmd
    std::cout << "d.n_: " << std::invoke( &Demo::n_, d ) << "\n";
    std::cout << "pd->n_: " << std::invoke( pmd, pd ) << "\n";

    // Invoke a stand-alone (free) function
    std::invoke( divisible_by_3, 42 );

    // Invoke a lambda
    auto divisible_by_7 = []( int const i ) {
        std::cout << i << ( i % 7 == 0 ? " is" : " isn't" )
            << " divisible by 7.\n";
        };
    std::invoke( divisible_by_7, 42 );
}
```

```Output
Demo operator( 3, -7 ) is -21
Demo.difference( 29 ) is 13
Demo.difference( 13 ) is 29
d.n_: 42
pd->n_: 42
42 is divisible by 3.
42 is divisible by 7.
```

## <a name="mem_fn"></a><a name="mem_fn"></a> mem_fn

Basit bir çağrı sarmalayıcısı üretir.

```cpp
template <class RTy, class Ty>
unspecified mem_fn(RTy Ty::*pm);
```

### <a name="parameters"></a>Parametreler

*RTy*\
Sarmalanan işlevin dönüş türü.

*Kalite*\
Üye işlev işaretçisinin türü.

### <a name="remarks"></a>Açıklamalar

Şablon işlevi, bir basit Çağrı sarmalayıcısı döndürür ve `cw` Bu gibi ifade aynı şekilde zayıf bir sonuç türü `cw(t, a2, ..., aN)` olur `INVOKE(pm, t, a2, ..., aN)` . Özel durum oluşturmaz.

Döndürülen Çağrı sarmalayıcısı, ' den türetilir `std::unary_function<cv Ty*, RTy>` (ve iç içe geçmiş türü `result_type` *rty* için bir eş anlamlı ve iç içe geçmiş türü `argument_type` ), `cv Ty*` yalnızca tür *Ty* bir `cv` bağımsız değişken alan CV niteleyicisi olan üye işlev işaretçisiyse.

Döndürülen Çağrı sarmalayıcısı, ' den türetilir `std::binary_function<cv Ty*, T2, RTy>` (ve iç içe türü `result_type` *rty* için bir eş anlamlı, iç içe geçmiş türü ve için eş anlamlı tür `first argument_type` ), `cv Ty*` `second argument_type` `T2` yalnızca tür *Ty* bir bağımsız değişken alan CV niteleyicisi olan bir üye işlev işaretçisiyse `cv` `T2` .

### <a name="example"></a>Örnek

```cpp
// std__functional__mem_fn.cpp
// compile with: /EHsc
#include <functional>
#include <iostream>

class Funs
    {
public:
    void square(double x)
        {
        std::cout << x << "^2 == " << x * x << std::endl;
        }

    void product(double x, double y)
        {
        std::cout << x << "*" << y << " == " << x * y << std::endl;
        }
    };

int main()
    {
    Funs funs;

    std::mem_fn(&Funs::square)(funs, 3.0);
    std::mem_fn(&Funs::product)(funs, 3.0, 2.0);

    return (0);
    }
```

```Output
3^2 == 9
3*2 == 6
```

## <a name="mem_fun"></a><a name="mem_fun"></a> mem_fun

İşaretçi bağımsız değişkenleriyle başlatıldığında üye işlevleri için işlev nesne bağdaştırıcıları oluşturmak için kullanılan yardımcı Şablon işlevleri. [Mem_fn](#mem_fn) ve [BIND](#bind)için c++ 11 ' de kullanımdan kaldırılmıştır ve c++ 17 ' de kaldırılır.

```cpp
template <class Result, class Type>
mem_fun_t<Result, Type> mem_fun (Result(Type::* pMem)());

template <class Result, class Type, class Arg>
mem_fun1_t<Result, Type, Arg> mem_fun(Result (Type::* pMem)(Arg));

template <class Result, class Type>
const_mem_fun_t<Result, Type> mem_fun(Result (Type::* pMem)() const);

template <class Result, class Type, class Arg>
const_mem_fun1_t<Result, Type, Arg> mem_fun(Result (Type::* pMem)(Arg) const);
```

### <a name="parameters"></a>Parametreler

*pMem*\
İşlev nesnesine dönüştürülecek sınıfın üye işlevine yönelik bir işaretçi `Type` .

### <a name="return-value"></a>Dönüş Değeri

Or **`const`** türünde bir veya **non_const** işlevi nesnesi `mem_fun_t` `mem_fun1_t` .

### <a name="example"></a>Örnek

```cpp
// functional_mem_fun.cpp
// compile with: /EHsc
#include <vector>
#include <functional>
#include <algorithm>
#include <iostream>

using namespace std;

class StoreVals
{
    int val;
public:
    StoreVals() { val = 0; }
    StoreVals(int j) { val = j; }

    bool display() { cout << val << " "; return true; }
    int squareval() { val *= val; return val; }
    int lessconst(int k) {val -= k; return val; }
};

int main( )
{
    vector<StoreVals *> v1;

    StoreVals sv1(5);
    v1.push_back(&sv1);
    StoreVals sv2(10);
    v1.push_back(&sv2);
    StoreVals sv3(15);
    v1.push_back(&sv3);
    StoreVals sv4(20);
    v1.push_back(&sv4);
    StoreVals sv5(25);
    v1.push_back(&sv5);

    cout << "The original values stored are: " ;
    for_each(v1.begin(), v1.end(), mem_fun<bool, StoreVals>(&StoreVals::display));
    cout << endl;

    // Use of mem_fun calling member function through a pointer
    // square each value in the vector using squareval ()
    for_each(v1.begin(), v1.end(), mem_fun<int, StoreVals>(&StoreVals::squareval));
    cout << "The squared values are: " ;
    for_each(v1.begin(), v1.end(), mem_fun<bool, StoreVals>(&StoreVals::display));
    cout << endl;

    // Use of mem_fun1 calling member function through a pointer
    // subtract 5 from each value in the vector using lessconst ()
    for_each(v1.begin(), v1.end(),
        bind2nd (mem_fun1<int, StoreVals,int>(&StoreVals::lessconst), 5));
    cout << "The squared values less 5 are: " ;
    for_each(v1.begin(), v1.end(), mem_fun<bool, StoreVals>(&StoreVals::display));
    cout << endl;
}
```

## <a name="mem_fun_ref"></a><a name="mem_fun_ref"></a> mem_fun_ref

Başvuru bağımsız değişkenleri kullanılarak başlatıldığında üye işlevleri için işlev nesne bağdaştırıcıları oluşturmak için kullanılan yardımcı Şablon işlevleri. C++ 11 ' de kullanım dışı bırakılmıştır ve C++ 17 ' de kaldırılmıştır.

```cpp
template <class Result, class Type>
mem_fun_ref_t<Result, Type> mem_fun_ref(Result (Type::* pMem)());

template <class Result, class Type, class Arg>
mem_fun1_ref_t<Result, Type, Arg> mem_fun_ref(Result (Type::* pMem)(Arg));

template <class Result, class Type>
const_mem_fun_ref_t<Result, Type> mem_fun_ref(Result Type::* pMem)() const);

template <class Result, class Type, class Arg>
const_mem_fun1_ref_t<Result, Type, Arg> mem_fun_ref(Result (T::* pMem)(Arg) const);
```

### <a name="parameters"></a>Parametreler

*pMem*\
İşlev nesnesine dönüştürülecek sınıfın üye işlevine yönelik bir işaretçi `Type` .

### <a name="return-value"></a>Dönüş Değeri

Veya **`const`** türünde bir veya `non_const` işlevi nesnesi `mem_fun_ref_t` `mem_fun1_ref_t` .

### <a name="example"></a>Örnek

```cpp
// functional_mem_fun_ref.cpp
// compile with: /EHsc
#include <vector>
#include <functional>
#include <algorithm>
#include <iostream>

using namespace std;

class NumVals
   {
   int val;
   public:
   NumVals ( ) { val = 0; }
   NumVals ( int j ) { val = j; }

   bool display ( ) { cout << val << " "; return true; }
   bool isEven ( ) { return ( bool )  !( val %2 ); }
   bool isPrime( )
   {
      if (val < 2) { return true; }
      for (int i = 2; i <= val / i; ++i)
      {
         if (val % i == 0) { return false; }
      }
      return true;
   }
};

int main( )
{
   vector <NumVals> v1 ( 13 ), v2 ( 13 );
   vector <NumVals>::iterator v1_Iter, v2_Iter;
   int i, k;

   for ( i = 0; i < 13; i++ ) v1 [ i ] = NumVals ( i+1 );
   for ( k = 0; k < 13; k++ ) v2 [ k ] = NumVals ( k+1 );

   cout << "The original values stored in v1 are: " ;
   for_each( v1.begin( ), v1.end( ),
   mem_fun_ref ( &NumVals::display ) );
   cout << endl;

   // Use of mem_fun_ref calling member function through a reference
   // remove the primes in the vector using isPrime ( )
   v1_Iter = remove_if ( v1.begin( ),  v1.end( ),
      mem_fun_ref ( &NumVals::isPrime ) );
   cout << "With the primes removed, the remaining values in v1 are: " ;
   for_each( v1.begin( ), v1_Iter,
   mem_fun_ref ( &NumVals::display ) );
   cout << endl;

   cout << "The original values stored in v2 are: " ;
   for_each( v2.begin( ), v2.end( ),
   mem_fun_ref ( &NumVals::display ) );
   cout << endl;

   // Use of mem_fun_ref calling member function through a reference
   // remove the even numbers in the vector v2 using isEven ( )
   v2_Iter = remove_if ( v2.begin( ),  v2.end( ),
      mem_fun_ref ( &NumVals::isEven ) );
   cout << "With the even numbers removed, the remaining values are: " ;
   for_each( v2.begin( ),  v2_Iter,
   mem_fun_ref ( &NumVals::display ) );
   cout << endl;
}
```

```Output
The original values stored in v1 are: 1 2 3 4 5 6 7 8 9 10 11 12 13
With the primes removed, the remaining values in v1 are: 4 6 8 9 10 12
The original values stored in v2 are: 1 2 3 4 5 6 7 8 9 10 11 12 13
With the even numbers removed, the remaining values are: 1 3 5 7 9 11 13
```

## <a name="not1"></a><a name="not1"></a> Not1

Birli koşulun tamamlayıcısını döndürür. C++ 17 ' de [not_fn](#not_fn) için kullanım dışı.

```cpp
template <class UnaryPredicate>
unary_negate<UnaryPredicate> not1(const UnaryPredicate& predicate);
```

### <a name="parameters"></a>Parametreler

*koşulunda*\
Değillenmiş birli koşul.

### <a name="return-value"></a>Dönüş Değeri

Değiştirilen birli koşulun olumsuzlama olan birli koşul.

### <a name="remarks"></a>Açıklamalar

Bir `unary_negate` birli koşuldan oluşturulmuşsa `predicate(x)` , döndürür `!predicate(x)` .

### <a name="example"></a>Örnek

```cpp
// functional_not1.cpp
// compile with: /EHsc
#include <vector>
#include <functional>
#include <algorithm>
#include <iostream>

using namespace std;

int main()
{
    vector<int> v1;
    vector<int>::iterator Iter;

    int i;
    for (i = 0; i <= 7; i++)
    {
        v1.push_back(5 * i);
    }

    cout << "The vector v1 = ( ";
    for (Iter = v1.begin(); Iter != v1.end(); Iter++)
        cout << *Iter << " ";
    cout << ")" << endl;

    vector<int>::iterator::difference_type result1;
    // Count the elements greater than 10
    result1 = count_if(v1.begin(), v1.end(), bind2nd(greater<int>(), 10));
    cout << "The number of elements in v1 greater than 10 is: "
         << result1 << "." << endl;

    vector<int>::iterator::difference_type result2;
    // Use the negator to count the elements less than or equal to 10
    result2 = count_if(v1.begin(), v1.end(),
        not1(bind2nd(greater<int>(), 10)));

    cout << "The number of elements in v1 not greater than 10 is: "
         << result2 << "." << endl;
}
```

```Output
The vector v1 = ( 0 5 10 15 20 25 30 35 )
The number of elements in v1 greater than 10 is: 5.
The number of elements in v1 not greater than 10 is: 3.
```

## <a name="not2"></a><a name="not2"></a> NOT2

İkili koşulun tamamlayıcısını döndürür. C++ 17 ' de [not_fn](#not_fn) için kullanım dışı.

```cpp
template <class BinaryPredicate>
binary_negate<BinaryPredicate> not2(const BinaryPredicate& func);
```

### <a name="parameters"></a>Parametreler

*melerinin*\
Değillenmiş ikili koşul.

### <a name="return-value"></a>Dönüş Değeri

Değiştirilen ikili koşulun değillemediği bir ikili koşul.

### <a name="remarks"></a>Açıklamalar

Bir `binary_negate` ikili koşuldan oluşturulmuşsa `binary_predicate(x, y)` , döndürür `!binary_predicate(x, y)` .

### <a name="example"></a>Örnek

```cpp
// functional_not2.cpp
// compile with: /EHsc
#include <vector>
#include <algorithm>
#include <functional>
#include <cstdlib>
#include <iostream>

int main( )
{
   using namespace std;
   vector <int> v1;
   vector <int>::iterator Iter1;

   int i;
   v1.push_back( 6262 );
   v1.push_back( 6262 );
   for ( i = 0 ; i < 5 ; i++ )
   {
      v1.push_back( rand( ) );
   }

   cout << "Original vector v1 = ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")" << endl;

   // To sort in ascending order,
   // use default binary predicate less<int>( )
   sort( v1.begin( ), v1.end( ) );
   cout << "Sorted vector v1 = ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")" << endl;

   // To sort in descending order,
   // use the binary_negate helper function not2
   sort( v1.begin( ), v1.end( ), not2(less<int>( ) ) );
   cout << "Resorted vector v1 = ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")" << endl;
}
```

```Output
Original vector v1 = ( 6262 6262 41 18467 6334 26500 19169 )
Sorted vector v1 = ( 41 6262 6262 6334 18467 19169 26500 )
Resorted vector v1 = ( 26500 19169 18467 6334 6262 6262 41 )
```

## <a name="not_fn"></a><a name="not_fn"></a> not_fn

`not_fn`İşlev şablonu çağrılabilir bir nesne alır ve çağrılabilir bir nesne döndürür. Döndürülen çağrılabilir nesne daha sonra bazı bağımsız değişkenlerle çağrıldığında, bunları özgün çağrılabilir nesnesine geçirir ve sonucu mantıksal olarak geçersiz kılar. Sarmalanmış çağrılabilir nesnenin const nitelemesini ve değer kategorisi davranışını korur. `not_fn` , c++ 17 ' de yenidir ve kullanım dışı, `std::not1` `std::not2` , `std::unary_negate` ve ' nin yerini alır `std::binary_negate` .

```cpp
template <class Callable>
/* unspecified */ not_fn(Callable&& func);
```

### <a name="parameters"></a>Parametreler

*melerinin*\
İletme çağrısı sarmalayıcısı oluşturmak için kullanılan çağrılabilir nesne.

### <a name="remarks"></a>Açıklamalar

Şablon işlevi `return call_wrapper(std::forward<Callable>(func))` , bu yalnızca Exposition sınıfına göre gibi bir çağrı sarmalayıcısı döndürür:

```cpp
class call_wrapper
{
   using FD = decay_t<Callable>;
   explicit call_wrapper(Callable&& func);

public:
   call_wrapper(call_wrapper&&) = default;
   call_wrapper(call_wrapper const&) = default;

   template<class... Args>
     auto operator()(Args&&...) & -> decltype(!declval<invoke_result_t<FD&(Args...)>>());

   template<class... Args>
     auto operator()(Args&&...) const& -> decltype(!declval<invoke_result_t<FD const&(Args...)>>());

   template<class... Args>
     auto operator()(Args&&...) && -> decltype(!declval<invoke_result_t<FD(Args...)>>());

   template<class... Args>
     auto operator()(Args&&...) const&& -> decltype(!declval<invoke_result_t<FD const(Args...)>>());

private:
  FD fd;
};
```

Çağrılabilir nesne *işlev* üzerindeki açık Oluşturucu `std::decay_t<Callable>` , gereksinimlerini karşılamak için tür gerektirir `MoveConstructible` ve `is_constructible_v<FD, Callable>` doğru olmalıdır. Sarmalanmış çağrılabilir nesneyi `fd` ' den başlatır `std::forward<Callable>(func)` ve oluşturma tarafından oluşturulan özel durumu oluşturur `fd` .

Sarmalayıcı, burada gösterildiği gibi lvalue veya rvalue başvuru kategorisi ve const nitelemesini ayırt eden çağrı işleçlerini kullanıma sunar:

```cpp
template<class... Args> auto operator()(Args&&... args) & -> decltype(!declval<invoke_result_t<FD&(Args...)>>());
template<class... Args> auto operator()(Args&&... args) const& -> decltype(!declval<invoke_result_t<FD const&(Args...)>>());
template<class... Args> auto operator()(Args&&... args) && -> decltype(!declval<invoke_result_t<FD(Args...)>>());
template<class... Args> auto operator()(Args&&... args) const&& -> decltype(!declval<invoke_result_t<FD const(Args...)>>());
```

İlk ikisi ile aynıdır `return !std::invoke(fd, std::forward<Args>(args)...)` . İkinci ikisi ile aynıdır `return !std::invoke(std::move(fd), std::forward<Args>(args)...)` .

### <a name="example"></a>Örnek

```cpp
// functional_not_fn_.cpp
// compile with: /EHsc /std:c++17
#include <vector>
#include <algorithm>
#include <functional>
#include <iostream>

int main()
{
    std::vector<int> v1 = { 99, 6264, 41, 18467, 6334, 26500, 19169 };
    auto divisible_by_3 = [](int i){ return i % 3 == 0; };

    std::cout << "Vector v1 = ( " ;
    for (const auto& item : v1)
    {
        std::cout << item << " ";
    }
    std::cout << ")" << std::endl;

    // Count the number of vector elements divisible by 3.
    int divisible =
        std::count_if(v1.begin(), v1.end(), divisible_by_3);
    std::cout << "Elements divisible by three: "
        << divisible << std::endl;

    // Count the number of vector elements not divisible by 3.
    int not_divisible =
        std::count_if(v1.begin(), v1.end(), std::not_fn(divisible_by_3));
    std::cout << "Elements not divisible by three: "
        << not_divisible << std::endl;
}
```

```Output
Vector v1 = ( 99 6264 41 18467 6334 26500 19169 )
Elements divisible by three: 2
Elements not divisible by three: 5
```

## <a name="ptr_fun"></a><a name="ptr_fun"></a> ptr_fun

Sırasıyla birli ve ikili işlev işaretçilerini tekil ve ikili Uyarlamalı tablo işlevlerine dönüştürmek için kullanılan yardımcı Şablon işlevleri. C++ 11 ' de kullanım dışı bırakılmıştır ve C++ 17 ' de kaldırılmıştır.

```cpp
template <class Arg, class Result>
pointer_to_unary_function<Arg, Result, Result (*)(Arg)> ptr_fun(Result (*pfunc)(Arg));

template <class Arg1, class Arg2, class Result>
pointer_to_binary_function<Arg1, Arg2, Result, Result (*)(Arg1, Arg2)> ptr_fun(Result (*pfunc)(Arg1, Arg2));
```

### <a name="parameters"></a>Parametreler

*pFunc*\
Bir utable işlevine dönüştürülecek birli veya ikili işlev işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

İlk şablon işlevi [pointer_to_unary_function](../standard-library/pointer-to-unary-function-class.md)birli işlevi döndürür  < `Arg` , **Result**> ( \* `pfunc` ).

İkinci şablon işlevi [pointer_to_binary_function](../standard-library/pointer-to-binary-function-class.md) \<**Arg1**, **Arg2**, **Result**> () ikili işlevini döndürür \* `pfunc` .

### <a name="remarks"></a>Açıklamalar

İşlev işaretçisi bir işlev nesnesidir. Parametre olarak işlev bekleyen herhangi bir algoritmaya geçirilebilir, ancak bu durum uyumlu değil. İç içe geçmiş türleri hakkındaki bilgiler, örneğin bir değeri bir bağdaştırıcı ile kullanmak için veya bir değer bağlamak veya onu bir bağlantı yapmak için gereklidir. Birli ve ikili işlev işaretçilerinin `ptr_fun` yardımcı işleve dönüştürülmesi, işlev bağdaştırıcılarını birli ve ikili işlev işaretçileriyle çalışacak şekilde sağlar.

### <a name="example"></a>Örnek

[!code-cpp[functional_ptr_fun#1](../standard-library/codesnippet/CPP/functional-functions_1.cpp)]

## <a name="ref"></a><a name="ref"></a> ref

Bir `reference_wrapper` bağımsız değişkenden bir oluşturur.

```cpp
template <class Ty>
    reference_wrapper<Ty> ref(Ty& arg);

template <class Ty>
    reference_wrapper<Ty> ref(reference_wrapper<Ty>& arg);
```

### <a name="return-value"></a>Dönüş Değeri

İçin bir başvuru `arg` ; özellikle, `reference_wrapper<Ty>(arg)` .

### <a name="example"></a>Örnek

Aşağıdaki örnek iki işlevi tanımlar: bir dize değişkenine, diğeri bir çağrısıyla hesaplanan dize değişkeninin başvurusuna bağlanır `ref` . Değişkenin değeri değiştiğinde, ilk işlev eski değeri kullanmaya devam eder ve ikinci işlev yeni değeri kullanır.

```cpp
#include <algorithm>
#include <functional>
#include <iostream>
#include <iterator>
#include <ostream>
#include <string>
#include <vector>
using namespace std;
using namespace std;
using namespace std::placeholders;

bool shorter_than(const string& l, const string& r) {
    return l.size() < r.size();
}

int main() {
    vector<string> v_original;
    v_original.push_back("tiger");
    v_original.push_back("cat");
    v_original.push_back("lion");
    v_original.push_back("cougar");

    copy(v_original.begin(), v_original.end(), ostream_iterator<string>(cout, " "));
    cout << endl;

    string s("meow");

    function<bool (const string&)> f = bind(shorter_than, _1, s);
    function<bool (const string&)> f_ref = bind(shorter_than, _1, ref(s));

    vector<string> v;

    // Remove elements that are shorter than s ("meow")

    v = v_original;
    v.erase(remove_if(v.begin(), v.end(), f), v.end());

    copy(v.begin(), v.end(), ostream_iterator<string>(cout, " "));
    cout << endl;

    // Now change the value of s.
    // f_ref, which is bound to ref(s), will use the
    // new value, while f is still bound to the old value.

    s = "kitty";

    // Remove elements that are shorter than "meow" (f is bound to old value of s)

    v = v_original;
    v.erase(remove_if(v.begin(), v.end(), f), v.end());

    copy(v.begin(), v.end(), ostream_iterator<string>(cout, " "));
    cout << endl;

    // Remove elements that are shorter than "kitty" (f_ref is bound to ref(s))

    v = v_original;
    v.erase(remove_if(v.begin(), v.end(), f_ref), v.end());

    copy(v.begin(), v.end(), ostream_iterator<string>(cout, " "));
    cout << endl;
}
```

```Output
tiger cat lion cougar
tiger lion cougar
tiger lion cougar
tiger cougar
```

## <a name="swap"></a><a name="swap"></a> Kur

İki `function` nesneyi değiştirir.

```cpp
template <class FT>
    void swap(function<FT>& f1, function<FT>& f2);
```

### <a name="parameters"></a>Parametreler

*MENIZ*\
İşlev nesneleri tarafından denetlenen tür.

*F1*\
İlk işlev nesnesi.

*F2*\
İkinci işlev nesnesi.

### <a name="remarks"></a>Açıklamalar

İşlev döndürür `f1.swap(f2)` .

### <a name="example"></a>Örnek

```cpp
// std__functional__swap.cpp
// compile with: /EHsc
#include <functional>
#include <iostream>

int neg(int val)
    {
    return (-val);
    }

int main()
    {
    std::function<int (int)> fn0(neg);
    std::cout << std::boolalpha << "empty == " << !fn0 << std::endl;
    std::cout << "val == " << fn0(3) << std::endl;

    std::function<int (int)> fn1;
    std::cout << std::boolalpha << "empty == " << !fn1 << std::endl;
    std::cout << std::endl;

    swap(fn0, fn1);
    std::cout << std::boolalpha << "empty == " << !fn0 << std::endl;
    std::cout << std::boolalpha << "empty == " << !fn1 << std::endl;
    std::cout << "val == " << fn1(3) << std::endl;

    return (0);
    }
```

```Output
empty == false
val == -3
empty == true

empty == true
empty == false
val == -3
```
