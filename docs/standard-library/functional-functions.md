---
title: '&lt;işlevsel&gt; işlevleri'
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
ms.openlocfilehash: 93b61f1d0342d7d4b7ddfc7fce4d64ea5e10a2eb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62159580"
---
# <a name="ltfunctionalgt-functions"></a>&lt;işlevsel&gt; işlevleri

||||
|-|-|-|
| [bağlama](#bind) | [bit_and](#bit_and) | [bit_not](#bit_not) |
| [bit_or](#bit_or) | [bit_xor](#bit_xor) | [cref](#cref) |
| [çağırma](#invoke) | [mem_fn](#mem_fn) | [not_fn](#not_fn) |
| [ref](#ref) | [değiştirme](#swap) | |

Bu işlevler C ++ 11'de kullanım dışı ve C ++ 17 sürümünde kaldırılmıştır:

||||
|-|-|-|
| [bind1st](#bind1st) | [bind2nd](#bind2nd) | [mem_fun](#mem_fun) |
| [mem_fun_ref](#mem_fun_ref) | [ptr_fun](#ptr_fun) | |

Bu işlevler, C ++ 17'de kullanım dışı bırakılmıştır:

|||
|-|-|
| [Not1](#not1) | [not2](#not2) |

## <a name="bind"></a> bağlama

Bağımsız değişkenler çağrılabilir nesnesine bağlar.

```cpp
template <class FT, class T1, class T2, ..., class TN>
unspecified bind(FT fn, T1 t1, T2 t2, ..., TN tN);

template <class RTy, class FT, class T1, class T2, ..., class TN>
unspecified bind(FT fn, T1 t1, T2 t2, ..., TN tN);
```

### <a name="parameters"></a>Parametreler

*Fey*<br/>
Aranacak nesne türü.

*TN*<br/>
Çağrı bağımsız değişken türü n.

*fn*<br/>
Aranacak nesne.

*TN*<br/>
Nth çağrı bağımsız değişkeni.

### <a name="remarks"></a>Açıklamalar

Türleri `FT, T1, T2, ..., TN` kopyalama atmamalıdır, olmalıdır ve `INVOKE(fn, t1, ..., tN)` bazı değerler için geçerli bir ifade olmalıdır `w1, w2, ..., wN`.

Bir iletme çağrı ilk şablon işlevinin döndürdüğü sarmalayıcı `g` zayıf sonuç türü. Etkisini `g(u1, u2, ..., uM)` olduğu `INVOKE(f, v1, v2, ..., vN, ` [invoke_result](../standard-library/invoke-result-class.md)`<FT cv (V1, V2, ..., VN)>::type)`burada `cv` , cv niteleyicileri olan `g` ve değerleri ve de ilişkili bağımsız değişken türlerinin `v1, v2, ..., vN` belirlenir Aşağıda belirtildiği gibi. Bir özel olarak uyarlanmış bir bağımsız değişken listesi ile çağrılabilir bir nesne haline getirmek için çağrılabilen bir nesne bağımsız değişkenleri bağlamak için kullanın.

Bir iletme çağrı ikinci şablon işlevinin döndürdüğü sarmalayıcı `g` iç içe geçmiş bir tür ile `result_type` diğer bir deyişle ilişkin bir eşanlam `RTy`. Etkisini `g(u1, u2, ..., uM)` olduğu `INVOKE(f, v1, v2, ..., vN, RTy)`burada `cv` , cv niteleyicileri olan `g` ve değerleri ve de ilişkili bağımsız değişken türlerinin `v1, v2, ..., vN` aşağıda belirtildiği gibi belirlendikten. Belirtilen dönüş türüne sahip bir özel olarak uyarlanmış bir bağımsız değişken listesi ile çağrılabilir bir nesne haline getirmek için çağrılabilen bir nesne bağımsız değişkenleri bağlamak için kullanın.

İlişkili bağımsız değişkenler değerlerini `v1, v2, ..., vN` ve bunların karşılık gelen türlerine `V1, V2, ..., VN` karşılık gelen bağımsız değişkenin türüne bağlıdır `ti` türü `Ti` çağrısında `bind` ve cv niteleyicileri `cv` , sarmalayıcı çağrı `g` gibi:

varsa `ti` türünde `reference_wrapper<T>` bağımsız değişken `vi` olduğu `ti.get()` türünü `Vi` olduğu `T&`;

varsa değerini `std::is_bind_expression<Ti>::value` olduğu **true** bağımsız değişken `vi` olduğu `ti(u1, u2, ..., uM)` türünü `Vi` olduğu `result_of<Ti` `cv` `(U1&, U2&, ..., UN&>::type`;

varsa değeri `j` , `std::is_placeholder<Ti>::value` bağımsız değişkeni sıfır olmayan `vi` olduğu `uj` türünü `Vi` olduğu `Uj&`;

Aksi takdirde bağımsız değişken `vi` olduğu `ti` türünü `Vi` olduğu `Ti` `cv` `&`.

Örneğin, bir işlev belirtilen `f(int, int)` ifade `bind(f, _1, 0)` iletme döndürür çağrı sarmalayıcı `cw` şekilde `cw(x)` çağrıları `f(x, 0)`. İfade `bind(f, 0, _1)` iletme döndürür çağrı sarmalayıcı `cw` şekilde `cw(x)` çağrıları `f(0, x)`.

Bir çağrıda bağımsız değişken sayısı `bind` ve bağımsız değişken `fn` çağrılabilir nesnesine geçirilen bağımsız değişkenlerin sayısı eşit olmalıdır `fn`. Örneğin, `bind(cos, 1.0)` doğru olduğundan ve her ikisi de `bind(cos)` ve `bind(cos, _1, 0.0)` yanlış.

İşlev bağımsız değişken sayısı çağrı tarafından döndürülen çağrı sarmalayıcı `bind` yüksek numaralı değeri olarak en az olmalıdır `is_placeholder<PH>::value` tüm çağrısında yer tutucu bağımsız değişkenleri için `bind`. Örneğin, `bind(cos, _2)(0.0, 1.0)` doğru (ve döndürür `cos(1.0)`), ve `bind(cos, _2)(0.0)` yanlış.

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

## <a name="bind1st"></a> bind1st

Bir ikili fonksiyon nesnesi bir birli işlevi nesnesine dönüştürmek için bir bağdaştırıcı oluşturan yardımcı şablonu işlev. Bu ikili işlevinin ilk bağımsız değişkeni için belirtilen bir değere bağlar. C ++ 17 sürümünde kaldırılmıştır C ++ 11'de kullanım dışı.

```cpp
template <class Operation, class Type>
binder1st <Operation> bind1st (const Operation& func, const Type& left);
```

### <a name="parameters"></a>Parametreler

*FUNC*<br/>
Birli işlevi nesnesine dönüştürülecek ikili fonksiyon nesnesi.

*Sol*<br/>
İlk bağımsız değişken ikili işlev nesnesine bağlı olduğu değeri.

### <a name="return-value"></a>Dönüş Değeri

İkili fonksiyon nesnesi öğesinin ilk bağımsız değişkeninin değeri bağlama gelen sonuçları birli işlev nesnesi *sol*.

### <a name="remarks"></a>Açıklamalar

İşlev bağlayıcıları işlevi bağdaştırıcı türü var. İşlev nesneleri döndürmeleri olduğundan, bunlar belirli işlev bileşimi türlerinde daha karmaşık ve güçlü ifadelerini oluşturmak için kullanılabilir.

Varsa *func* türünde bir nesnedir `Operation` ve `c` bir sabit ise `bind1st( func, c )` aynı [binder1st](../standard-library/binder1st-class.md) sınıf oluşturucusu `binder1st<Operation>( func, c )`ve daha kolay kullanın.

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

## <a name="bind2nd"></a> bind2nd

Bir ikili fonksiyon nesnesi bir birli işlevi nesnesine dönüştürmek için bir bağdaştırıcı oluşturan yardımcı şablonu işlev. Bu ikili işlevinin ikinci bağımsız değişkeni için belirtilen bir değere bağlar. C ++ 17 sürümünde kaldırılmıştır C ++ 11'de kullanım dışı.

```cpp
template <class Operation, class Type>
binder2nd <Operation> bind2nd(const Operation& func, const Type& right);
```

### <a name="parameters"></a>Parametreler

*FUNC*<br/>
Birli işlevi nesnesine dönüştürülecek ikili fonksiyon nesnesi.

*sağ*<br/>
İkinci bağımsız değişken ikili işlev nesnesine bağlı olduğu değeri.

### <a name="return-value"></a>Dönüş Değeri

İkinci bağımsız değişkeni ikili fonksiyon nesnesi bağlamanın birli işlevi nesne sonucunu *doğru*.

### <a name="remarks"></a>Açıklamalar

İşlev bağlayıcıları işlevi bağdaştırıcı türü var. İşlev nesneleri döndürmeleri olduğundan, bunlar belirli işlev bileşimi türlerinde daha karmaşık ve güçlü ifadelerini oluşturmak için kullanılabilir.

Varsa *func* türünde bir nesnedir `Operation` ve `c` bir sabit ise `bind2nd( func, c )` aynı [binder2nd](../standard-library/binder2nd-class.md) sınıf oluşturucusu `binder2nd<Operation>( func, c )`ve daha rahat kullanmak.

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

## <a name="bit_and"></a> bit_and

Bit düzeyinde bir AND işlemi yapan bir önceden tanımlanmış bir işlev nesnesi (ikili `operator&`) üzerinde bağımsız değişkenleri.

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

*Tür*, *T*, *U* destekleyen herhangi bir türü bir `operator&` , belirtilen veya çıkarsanan tür işlenen alır.

*Sol*<br/>
Bit düzeyinde AND işlemi sol işleneni. Uzmanlaşmamış şablon türü bir lvalue başvuru bağımsız değişkeni alır *türü*. Özelleşmiş şablon lvalue iletilmesini mükemmel ve rvalue başvuru bağımsız değişkenleri tür çıkarımı yapılan *T*.

*sağ*<br/>
Bit düzeyinde AND işlemi sağ işleneni. Uzmanlaşmamış şablon türü bir lvalue başvuru bağımsız değişkeni alır *türü*. Özelleşmiş şablon lvalue iletilmesini mükemmel ve rvalue başvuru bağımsız değişkenleri tür çıkarımı yapılan *U*.

### <a name="return-value"></a>Dönüş Değeri

Sonucu `Left & Right`. Özelleşmiş şablon tarafından döndürülen türünde sonuç iletilmesini mükemmel `operator&`.

### <a name="remarks"></a>Açıklamalar

`bit_and` Functor temel veri türleri için tam sayı türleri sınırlı olduğundan veya bu uygulama ikili türleri için kullanıcı tanımlı `operator&`.

## <a name="bit_not"></a> bit_not

Bir bit düzeyinde tamamlayıcı (değil) işlemi yapan bir önceden tanımlanmış bir işlev nesnesi (birli `operator~`) bağımsız değişken üzerinde. C ++ 14'te eklendi.

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

*Tür*<br/>
Bir birli destekleyen bir türü `operator~`.

*sağ*<br/>
Bit düzeyinde tamamlayıcı işleminin işleneni. Uzmanlaşmamış şablon türü bir lvalue başvuru bağımsız değişkeni alır *türü*. Özelleşmiş şablon lvalue veya rvalue başvuru türünde bir bağımsız değişken çıkarsanan iletilmesini mükemmel *türü*.

### <a name="return-value"></a>Dönüş Değeri

Sonucu `~ Right`. Özelleşmiş şablon tarafından döndürülen türünde sonuç iletilmesini mükemmel `operator~`.

### <a name="remarks"></a>Açıklamalar

`bit_not` Functor temel veri türleri için tam sayı türleri sınırlı olduğundan veya bu uygulama ikili türleri için kullanıcı tanımlı `operator~`.

## <a name="bit_or"></a> bit_or

Bir bit düzeyinde OR işlem yapan bir önceden tanımlanmış bir işlev nesnesi (`operator|`) üzerinde bağımsız değişkenleri.

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

*Tür*, *T*, *U* destekleyen herhangi bir türü bir `operator|` , belirtilen veya çıkarsanan tür işlenen alır.

*Sol*<br/>
Bit düzeyinde OR işleminin sol işleneni. Uzmanlaşmamış şablon türü bir lvalue başvuru bağımsız değişkeni alır *türü*. Özelleşmiş şablon lvalue iletilmesini mükemmel ve rvalue başvuru bağımsız değişkenleri tür çıkarımı yapılan *T*.

*sağ*<br/>
Bit düzeyinde OR işleminde sağ işleneni. Uzmanlaşmamış şablon türü bir lvalue başvuru bağımsız değişkeni alır *türü*. Özelleşmiş şablon lvalue iletilmesini mükemmel ve rvalue başvuru bağımsız değişkenleri tür çıkarımı yapılan *U*.

### <a name="return-value"></a>Dönüş Değeri

Sonucu `Left | Right`. Özelleşmiş şablon tarafından döndürülen türünde sonuç iletilmesini mükemmel `operator|`.

### <a name="remarks"></a>Açıklamalar

`bit_or` Functor temel veri türleri için tam sayı türleri sınırlı olduğundan veya uygulayan türler için kullanıcı tanımlı `operator|`.

## <a name="bit_xor"></a> bit_xor

Bir bit düzeyinde XOR işlem yapan bir önceden tanımlanmış bir işlev nesnesi (ikili `operator^`) üzerinde bağımsız değişkenleri.

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

*Tür*, *T*, *U* destekleyen herhangi bir türü bir `operator^` , belirtilen veya çıkarsanan tür işlenen alır.

*Sol*<br/>
Bit düzeyinde XOR işleminin sol işleneni. Uzmanlaşmamış şablon türü bir lvalue başvuru bağımsız değişkeni alır *türü*. Özelleşmiş şablon lvalue iletilmesini mükemmel ve rvalue başvuru bağımsız değişkenleri tür çıkarımı yapılan *T*.

*sağ*<br/>
Bit düzeyinde XOR işlem sağ işleneni. Uzmanlaşmamış şablon türü bir lvalue başvuru bağımsız değişkeni alır *türü*. Özelleşmiş şablon lvalue iletilmesini mükemmel ve rvalue başvuru bağımsız değişkenleri tür çıkarımı yapılan *U*.

### <a name="return-value"></a>Dönüş Değeri

Sonucu `Left ^ Right`. Özelleşmiş şablon tarafından döndürülen türünde sonuç iletilmesini mükemmel `operator^`.

### <a name="remarks"></a>Açıklamalar

`bit_xor` Functor temel veri türleri için tam sayı türleri sınırlı olduğundan veya bu uygulama ikili türleri için kullanıcı tanımlı `operator^`.

## <a name="cref"></a> cref

Bir const yapıları `reference_wrapper` bir bağımsız.

```cpp
template <class Ty>
reference_wrapper<const Ty> cref(const Ty& arg);

template <class Ty>
reference_wrapper<const Ty> cref(const reference_wrapper<Ty>& arg);
```

### <a name="parameters"></a>Parametreler

*Ty*<br/>
Kaydırmak için bağımsız değişken türü.

*bağımsız değişken*<br/>
Kaydırmak için bağımsız değişken.

### <a name="remarks"></a>Açıklamalar

İşlev `reference_wrapper<const Ty>(arg.get())`. Const başvuru sarmalamak için kullanın. İkinci işlevi döndürür `reference_wrapper<const Ty>(arg)`. Sarmalanan bir başvurusu const başvuru olarak yeniden sarmalamanız kullanın.

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

## <a name="invoke"></a> çağırma

Belirtilen bağımsız değişkenlerle çağrılabilir herhangi bir nesne çağırır. C ++ 17'de eklendi.

```cpp
template <class Callable, class... Args>
invoke_result_t<Callable, Args...>
    invoke(Callable&& fn, Args&&... args) noexcept(/* specification */);
```

### <a name="parameters"></a>Parametreler

*Çağrılabilir*<br/>
Aranacak nesne türü.

*Args*<br/>
Çağrı bağımsız değişkenlerinin türleri.

*fn*<br/>
Aranacak nesne.

*bağımsız değişken*<br/>
Çağrı bağımsız değişkenleri.

*Belirtimi*<br/>
**Noexcept** belirtimi `std::is_nothrow_invocable_v<Callable, Args>)`.

### <a name="remarks"></a>Açıklamalar

Çağrılabilir nesne çağırır *fn* parametreleri kullanarak *args*. Etkili bir şekilde `INVOKE(std::forward<Callable>(fn), std::forward<Args>(args)...)`burada sözde işlevi `INVOKE(f, t1, t2, ..., tN)` aşağıdaki şeylerden biri anlamına gelir:

- `(t1.*f)(t2, ..., tN)` zaman `f` sınıfının üye işlevinde işaretçisidir `T` ve `t1` türünde bir nesnedir `T` veya türünde bir nesne başvurusu `T` veya türetilmiş bir türde bir nesne başvuru `T`. Diğer bir deyişle, `std::is_base_of<T, std::decay_t<decltype(t1)>>::value` geçerlidir.

- `(t1.get().*f)(t2, ..., tN)` zaman `f` sınıfının üye işlevinde işaretçisidir `T` ve `std::decay_t<decltype(t1)>` özelleştirmesi olan `std::reference_wrapper`.

- `((*t1).*f)(t2, ..., tN)` zaman `f` sınıfının üye işlevinde işaretçisidir `T` ve `t1` önceki türlerinden biri değil.

- `t1.*f` zaman N 1 == ve `f` bir sınıfın üye verileri işaretçisidir `T` ve `t1` türünde bir nesnedir `T` veya türünde bir nesne başvurusu `T` veya türetilmiş bir türde bir nesne başvuru `T`.  Diğer bir deyişle, `std::is_base_of<T, std::decay_t<decltype(t1)>>::value` geçerlidir.

- `t1.get().*f` zaman N 1 == ve `f` bir sınıfın üye verileri işaretçisidir `T` ve `std::decay_t<decltype(t1)>` özelleştirmesi olan `std::reference_wrapper`.

- `(*t1).*f` zaman N 1 == ve `f` bir sınıfın üye verileri işaretçisidir `T` ve `t1` önceki türlerinden biri değil.

- `f(t1, t2, ..., tN)` Diğer durumlarda.

Çağrılabilir nesnesinin sonucu türü hakkında daha fazla bilgi için bkz: [invoke_result](invoke-result-class.md). Çağrılabilir türleri hakkında daha fazla doğrulamaları için bkz: [is_invocable, is_invocable_r, is_nothrow_invocable, is_nothrow_invocable_r sınıfları](is-invocable-classes.md).

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

## <a name="mem_fn"></a> mem_fn

Basit Arama bir sarmalayıcı oluşturur.

```cpp
template <class RTy, class Ty>
unspecified mem_fn(RTy Ty::*pm);
```

### <a name="parameters"></a>Parametreler

*RTy*<br/>
Sarılan işlevin dönüş türü.

*Ty*<br/>
Üye işlev işaretçisi türü.

### <a name="remarks"></a>Açıklamalar

Basit çağrısı sarmalayıcı şablon işlevinin döndürdüğü `cw`, bir zayıf sonuç türü, gibi ifade `cw(t, a2, ..., aN)` aynı `INVOKE(pm, t, a2, ..., aN)`. Bu özel durumları oluşturmaz.

Döndürülen arama sarmalayıcı türetilir `std::unary_function<cv Ty*, RTy>` (ve iç içe geçmiş tür tanımlama `result_type` eşanlamlısı olarak *RTy* ve iç içe türün `argument_type` eşanlamlısı olarak `cv Ty*`) yalnızca türü *Ty*  cv niteleyicisi olan üye işlevi işaretçisi olan `cv` , hiçbir bağımsız değişkeni alır.

Döndürülen arama sarmalayıcı türetilir `std::binary_function<cv Ty*, T2, RTy>` (ve iç içe geçmiş tür tanımlama `result_type` eşanlamlısı olarak *RTy*, iç içe türü `first argument_type` eşanlamlısı olarak `cv Ty*`ve iç içe türün `second argument_type` eşanlamlısı olarak `T2`) yalnızca türü *Ty* cv niteleyicisi olan üye işlevi işaretçisi olan `cv` türünde bir bağımsız değişken almayan `T2`.

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

## <a name="mem_fun"></a> mem_fun

İşaretçi bağımsız değişkenler ile hazırlarken üye işlevler için işlev nesnesi bağdaştırıcıları oluşturmak için kullanılan yardımcı şablon işlevleri. C ++ 11'de kullanımdan [mem_fn](#mem_fn) ve [bağlama](#bind)ve C ++ 17 sürümünde kaldırılmıştır.

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

*pMem*<br/>
Bir sınıfın üye işlevi işaretçisi `Type` bir işlev nesnesi için dönüştürülecek.

### <a name="return-value"></a>Dönüş Değeri

A **const** veya **non_const** türünün işlev nesnesini `mem_fun_t` veya `mem_fun1_t`.

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

## <a name="mem_fun_ref"></a> mem_fun_ref

İşlev nesnesi bağdaştırıcılarını başvuru bağımsız değişkenleri kullanılarak başlatılan, üye işlevleri oluşturmak için kullanılan yardımcı şablon işlevleri. C ++ 17 sürümünde kaldırılmıştır C ++ 11'de kullanım dışı.

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

*pMem*<br/>
Bir sınıfın üye işlevi işaretçisi `Type` bir işlev nesnesi için dönüştürülecek.

### <a name="return-value"></a>Dönüş Değeri

A **const** veya `non_const` türünün işlev nesnesini `mem_fun_ref_t` veya `mem_fun1_ref_t`.

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

## <a name="not1"></a> Not1

Birli koşulu tümleme döndürür. İçin kullanım dışı [not_fn](#not_fn) içinde C ++ 17.

```cpp
template <class UnaryPredicate>
unary_negate<UnaryPredicate> not1(const UnaryPredicate& predicate);
```

### <a name="parameters"></a>Parametreler

*Karşılaştırma*<br/>
Negatif birli koşul.

### <a name="return-value"></a>Dönüş Değeri

Değişiklik birli koşul değilleme işlemi, birli koşulu.

### <a name="remarks"></a>Açıklamalar

Varsa bir `unary_negate` birli koşulu oluşturulur `predicate( x )`, sonra da döndürür `!predicate( x )`.

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

## <a name="not2"></a> not2

Bir ikili koşula tümleme döndürür. İçin kullanım dışı [not_fn](#not_fn) içinde C ++ 17.

```cpp
template <class BinaryPredicate>
binary_negate<BinaryPredicate> not2(const BinaryPredicate& func);
```

### <a name="parameters"></a>Parametreler

*FUNC*<br/>
Negatif için ikili koşul.

### <a name="return-value"></a>Dönüş Değeri

İkili koşul, değilleme işlemi, bir ikili koşula değiştirildi.

### <a name="remarks"></a>Açıklamalar

Varsa bir `binary_negate` bir ikili koşul oluşturulur `binary_predicate( x, y )`, sonra da döndürür `!binary_predicate( x, y )`.

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

## <a name="not_fn"></a> not_fn

`not_fn` İşlev şablonu çağrılabilir nesnesini alır ve aranabilir bir nesne döndürür. Döndürülen çağrılabilir nesnesi daha sonra bazı bağımsız değişkenlerle çağrılır, bunları çağrılabilir özgün nesneye geçirir ve mantıksal olarak sonucu olumsuz duruma getirir. Bu, sarmalanmış çağrılabilir nesnesinin const nitelik ve değer kategori davranışı korur. `not_fn` C ++ 17'de yenidir ve kullanım dışı değiştirir `std::not1`, `std::not2`, `std::unary_negate`, ve `std::binary_negate`.

```cpp
template <class Callable>
/* unspecified */ not_fn(Callable&& func);
```

### <a name="parameters"></a>Parametreler

*FUNC*<br/>
İletme çağrı oluşturmak için kullanılan çağrılabilir bir nesne sarmalayıcı.

### <a name="remarks"></a>Açıklamalar

Gibi bir çağrı sarmalayıcı şablon işlevinin döndürdüğü `return call_wrapper(std::forward<Callable>(func))`bağlı olarak bu yalnızca exposition sınıfı:

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

Çağrılabilir nesne üzerinde açık Oluşturucu *func* ihtiyaç duyacağı `std::decay_t<Callable>` gereksinimlerini karşılamak için `MoveConstructible`, ve `is_constructible_v<FD, Callable>` doğru olması gerekir. Sarmalanan çağrılabilir nesneyi başlatır `fd` gelen `std::forward<Callable>(func)`ve, oluşumunu tarafından oluşturulan tüm özel durumları oluşturabilir `fd`.

Burada gösterildiği gibi lvalue veya rvalue başvuru kategoriye ve const nitelenmiş göre ayırt edilen çağrısı işleçleri sarmalayıcı sunar:

```cpp
template<class... Args> auto operator()(Args&&... args) & -> decltype(!declval<invoke_result_t<FD&(Args...)>>());
template<class... Args> auto operator()(Args&&... args) const& -> decltype(!declval<invoke_result_t<FD const&(Args...)>>());
template<class... Args> auto operator()(Args&&... args) && -> decltype(!declval<invoke_result_t<FD(Args...)>>());
template<class... Args> auto operator()(Args&&... args) const&& -> decltype(!declval<invoke_result_t<FD const(Args...)>>());
```

İlk iki aynıdır `return !std::invoke(fd, std::forward<Args>(args)...)`. İkinci iki aynıdır `return !std::invoke(std::move(fd), std::forward<Args>(args)...)`.

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

## <a name="ptr_fun"></a> ptr_fun

Tekli veya ikili fonksiyon işaretçileri, tekli veya ikili uyarlanabilir işlevleri sırasıyla dönüştürmek için kullanılan yardımcı şablon işlevleri. C ++ 17 sürümünde kaldırılmıştır C ++ 11'de kullanım dışı.

```cpp
template <class Arg, class Result>
pointer_to_unary_function<Arg, Result, Result (*)(Arg)> ptr_fun(Result (*pfunc)(Arg));

template <class Arg1, class Arg2, class Result>
pointer_to_binary_function<Arg1, Arg2, Result, Result (*)(Arg1, Arg2)> ptr_fun(Result (*pfunc)(Arg1, Arg2));
```

### <a name="parameters"></a>Parametreler

*pfunc*<br/>
Uyarlanabilir bir işleve dönüştürülecek birli veya ikili fonksiyon işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Birli işlevi ilk şablon işlevinin döndürdüğü [pointer_to_unary_function](../standard-library/pointer-to-unary-function-class.md) < `Arg`, **sonucu**> (\* `pfunc`).

İkili fonksiyon ikinci şablon işlevinin döndürdüğü [pointer_to_binary_function](../standard-library/pointer-to-binary-function-class.md) \< **Arg1**, **Arg2**, **sonucu**> (\* `pfunc`).

### <a name="remarks"></a>Açıklamalar

Bir işlev işaretçisi, bir işlev nesnesidir. Bir işlev bir parametre olarak bekliyor tüm algoritmalar için geçirilebilir ancak uyarlanabilir değil. Örneğin bir bağdaştırıcı ile kullanmak için bir değer bağlamak veya onu negatif yapılacak kendi iç içe geçmiş türleri hakkında bilgi gereklidir. Tekli veya ikili işlev işaretçilerine dönüştürme `ptr_fun` tekli veya ikili işlev işaretçileri ile çalışmak işlev bağdaştırıcıları yardımcı işlevini sağlar.

### <a name="example"></a>Örnek

[!code-cpp[functional_ptr_fun#1](../standard-library/codesnippet/CPP/functional-functions_1.cpp)]

## <a name="ref"></a> başvuru

Oluşturur bir `reference_wrapper` bir bağımsız.

```cpp
template <class Ty>
reference_wrapper<Ty> ref(Ty& arg);

template <class Ty>
reference_wrapper<Ty> ref(reference_wrapper<Ty>& arg);
```

### <a name="return-value"></a>Dönüş Değeri

Bir başvuru `arg`; özellikle `reference_wrapper<Ty>(arg)`.

### <a name="example"></a>Örnek

Aşağıdaki örnek iki işlevleri tanımlar: bir bağlı bir dize değişkeni için olan bir sınır dize değişkeninin bir başvuru için bir çağrı tarafından hesaplanan `ref`. Değişkenin değerini değiştiğinde, ilk işlev eski değeri kullanmaya devam eder ve yeni değer ikinci işlevi kullanır.

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

## <a name="swap"></a> değiştirme

İki değiştirir `function` nesneleri.

```cpp
template <class FT>
void swap(function<FT>& f1, function<FT>& f2);
```

### <a name="parameters"></a>Parametreler

*FT*<br/>
İşlev nesneleri tarafından kontrol edilen tür.

*f1*<br/>
İlk işlev nesnesi.

*F2*<br/>
İkinci işlev nesnesi.

### <a name="remarks"></a>Açıklamalar

İşlev döndürür `f1.swap(f2)`.

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

## <a name="see-also"></a>Ayrıca bkz.

[\<işlev >](../standard-library/functional.md)<br/>
