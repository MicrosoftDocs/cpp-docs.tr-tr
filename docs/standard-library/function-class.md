---
title: function Sınıfı
ms.date: 11/04/2016
f1_keywords:
- functional/std::function
- functional/std::function::result_type
- functional/std::function::assign
- functional/std::function::swap
- functional/std::function::target
- functional/std::function::target_type
- functional/std::function::operator unspecified
- functional/std::function::operator()
helpviewer_keywords:
- std::function [C++]
- std::function [C++], result_type
- std::function [C++], assign
- std::function [C++], swap
- std::function [C++], target
- std::function [C++], target_type
ms.assetid: 7b5ca76b-9ca3-4d89-8fcf-cad70a4aeae6
ms.openlocfilehash: 432b61c7bc5b7f0e6f82e5bfeca7758c70785774
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2019
ms.locfileid: "72689632"
---
# <a name="function-class"></a>function Sınıfı

Çağrılabilir bir nesne için sarmalayıcı.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Fty>
class function  // Fty of type Ret(T1, T2, ..., TN)
    : public unary_function<T1, Ret>       // when Fty is Ret(T1)
    : public binary_function<T1, T2, Ret>  // when Fty is Ret(T1, T2)
{
public:
    typedef Ret result_type;

    function();
    function(nullptr_t);
    function(const function& right);
    template <class Fty2>
        function(Fty2 fn);
    template <class Fty2, class Alloc>
        function(reference_wrapper<Fty2>, const Alloc& Ax);

    template <class Fty2, class Alloc>
        void assign(Fty2, const Alloc& Ax);
    template <class Fty2, class Alloc>
        void assign(reference_wrapper<Fty2>, const Alloc& Ax);
    function& operator=(nullptr_t);
    function& operator=(const function&);
    template <class Fty2>
        function& operator=(Fty2);
    template <class Fty2>
        function& operator=(reference_wrapper<Fty2>);

    void swap(function&);
    explicit operator bool() const;

    result_type operator()(T1, T2, ....., TN) const;
    const std::type_info& target_type() const;
    template <class Fty2>
        Fty2 *target();

    template <class Fty2>
        const Fty2 *target() const;

    template <class Fty2>
        void operator==(const Fty2&) const = delete;
    template <class Fty2>
        void operator!=(const Fty2&) const = delete;
};
```

### <a name="parameters"></a>Parametreler

*Fty* \
Sarılacağı işlev türü.

*Ax* \
Ayırıcı işlevi.

## <a name="remarks"></a>Açıklamalar

Sınıf şablonu, çağrı imzası `Ret(T1, T2, ..., TN)` olan bir çağrı sarmalayıcısıdır. Tek biçimli bir sarmalayıcı içinde çeşitli çağrılabilir nesneleri çevrelemek için kullanılır.

Bazı üye işlevleri, istenen hedef nesneyi isimeden bir işlenen alır. Böyle bir işleneni birkaç şekilde belirtebilirsiniz:

`fn`--çağrılabilir nesne `fn`; çağrıdan sonra `function` nesnesi `fn` bir kopyasını tutar

`fnref`--`fnref.get()` tarafından adlandırılan çağrılabilir nesne çağrıdan sonra `function` nesnesi `fnref.get()` bir başvuru tutar

`right`--varsa, `function` nesne tarafından tutulan çağrılabilir nesne `right`

`npc`--null işaretçisi; çağrıdan sonra `function` nesnesi boş olur

Her durumda, `f` çağrılabilir nesne olduğu `INVOKE(f, t1, t2, ..., tN)` ve `t1, t2, ..., tN` lvalues `T1, T2, ..., TN`, sırasıyla `Ret`, doğru biçimlendirilmiş olması gerekir ve `Ret` void değilse dönüştürülebilir.

Boş bir `function` nesnesi çağrılabilir bir nesne veya çağrılabilir bir nesneye başvuru içermiyor.

## <a name="members"></a>Üyeler

### <a name="constructors"></a>Oluşturucular

|||
|-|-|
|[çalışmayacaktır](#function)|Boş olan veya sabit imzaya sahip bir rastgele türdeki çağrılabilir nesneyi depolayan bir sarmalayıcı oluşturur.|

### <a name="typedefs"></a>Tür tanımları

|||
|-|-|
|[result_type](#result_type)|Depolanan çağrılabilir nesnenin dönüş türü.|

### <a name="functions"></a>İşlevler

|||
|-|-|
|[ata](#assign)|Bu işlev nesnesine çağrılabilir bir nesne atar.|
|[Kur](#swap)|İki çağrılabilir nesne takas et.|
|[hedef](#target)|Depolanan çağrılabilir nesne belirtilen şekilde çağrılabilir ise sınar.|
|[target_type](#target_type)|Çağrılabilir nesne üzerindeki tür bilgilerini alır.|

### <a name="operators"></a>İşleçler

|||
|-|-|
|[işleç belirtilmemiş](#op_unspecified)|Depolanan çağrılabilir nesne varsa sınar.|
|[operator ()](#op_call)|Çağrılabilir bir nesne çağırır.|
|[işleç =](#op_eq)|Depolanan çağrılabilir nesneyi değiştirir.|

## <a name="assign"></a>ata

Bu işlev nesnesine çağrılabilir bir nesne atar.

```cpp
template <class Fx, class Alloc>
    void assign(
        Fx _Func,
        const Alloc& Ax);

template <class Fx, class Alloc>
    void assign(
        reference_wrapper<Fx> _Fnref,
        const Alloc& Ax);
```

### <a name="parameters"></a>Parametreler

*_Func* \
Çağrılabilir nesne.

*_@No__t_1 başvurusu*
Çağrılabilir bir nesne içeren bir başvuru sarmalayıcısı.

*Ax* \
Ayırıcı nesne.

### <a name="remarks"></a>Açıklamalar

Üye işlevleri, `*this` tarafından tutulan `callable object` `operand` olarak geçirilmiş çağrılabilir nesne ile değiştirir. Her ikisi de, *AX*ayırıcı nesnesi ile depolama ayırır.

## <a name="function"></a>çalışmayacaktır

Boş olan veya sabit imzaya sahip bir rastgele türdeki çağrılabilir nesneyi depolayan bir sarmalayıcı oluşturur.

```cpp
function();
function(nullptr_t npc);
function(const function& right);
template <class Fx>
    function(Fx _Func);
template <class Fx>
    function(reference_wrapper<Fx> _Fnref);
template <class Fx, class Alloc>
    function(
        Fx _Func,
        const Alloc& Ax);

template <class Fx, class Alloc>
    function(
        reference_wrapper<Fx> _Fnref,
        const Alloc& Ax);
```

### <a name="parameters"></a>Parametreler

*sağ* \
Kopyalanacak işlev nesnesi.

*Fx* \
Çağrılabilir nesnenin türü.

*_Func* \
Sarılacağı çağrılabilir nesne.

*Ayırma* \
Ayırıcı türü.

*Ax* \
Ayırıcı.

*_@No__t_1 başvurusu*
Sarılacağı çağrılabilir nesne başvurusu.

### <a name="remarks"></a>Açıklamalar

İlk iki Oluşturucu boş bir `function` nesnesi oluşturur. Sonraki üç Oluşturucu, işlenen olarak geçirilen çağrılabilir nesneyi tutan bir `function` nesnesi oluşturur. Son iki Oluşturucu, AX ayırıcı nesnesi ile depolama ayırır.

### <a name="example"></a>Örnek

```cpp
// std__functional__function_function.cpp
// compile with: /EHsc
#include <functional>
#include <iostream>
#include <vector>

int square(int val)
{
    return val * val;
}

class multiply_by
{
public:
    explicit multiply_by(const int n) : m_n(n) { }

    int operator()(const int x) const
    {
        return m_n * x;
    }

private:
    int m_n;
};

int main()
{

    typedef std::vector< std::function<int (int)> > vf_t;

    vf_t v;
    v.push_back(square);
    v.push_back(std::negate<int>());
    v.push_back(multiply_by(3));

    for (vf_t::const_iterator i = v.begin(); i != v.end(); ++i)
    {
        std::cout << (*i)(10) << std::endl;
    }

    std::function<int (int)> f = v[0];
    std::function<int (int)> g;

    if (f) {
        std::cout << "f is non-empty (correct)." << std::endl;
    } else {
        std::cout << "f is empty (can't happen)." << std::endl;
    }

    if (g) {
        std::cout << "g is non-empty (can't happen)." << std::endl;
    } else {
        std::cout << "g is empty (correct)." << std::endl;
    }

    return 0;
}
```

```Output
100
-10
30
f is non-empty (correct).
g is empty (correct).
```

## <a name="op_unspecified"></a>işleç belirtilmemiş

Depolanan çağrılabilir nesne varsa sınar.

```cpp
operator unspecified();
```

### <a name="remarks"></a>Açıklamalar

İşleci yalnızca nesne boş değilse true değeri olan **bool** değerine dönüştürülebilir bir değer döndürür. Nesnenin boş olup olmadığını test etmek için kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// std__functional__function_operator_bool.cpp
// compile with: /EHsc
#include <functional>
#include <iostream>

int neg(int val)
    {
    return (-val);
    }

int main()
    {
    std::function<int (int)> fn0;
    std::cout << std::boolalpha << "not empty == " << (bool)fn0 << std::endl;

    std::function<int (int)> fn1(neg);
    std::cout << std::boolalpha << "not empty == " << (bool)fn1 << std::endl;

    return (0);
    }
```

```Output
not empty == false
not empty == true
```

## <a name="op_call"></a>operator ()

Çağrılabilir bir nesne çağırır.

```cpp
result_type operator()(
    T1 t1,
    T2 t2, ...,
    TN tN);
```

### <a name="parameters"></a>Parametreler

*TN* \
Nth Call bağımsız değişkeninin türü.

*tN* \
Nth Call bağımsız değişkeni.

### <a name="remarks"></a>Açıklamalar

Üye işlevi, `fn` `*this` depolanan hedef nesne olduğu `INVOKE(fn, t1, t2, ..., tN, Ret)` döndürür. Sarmalanmış çağrılabilir nesneyi çağırmak için kullanılır.

### <a name="example"></a>Örnek

```cpp
// std__functional__function_operator_call.cpp
// compile with: /EHsc
#include <functional>
#include <iostream>

int neg(int val)
    {
    return (-val);
    }

int main()
    {
    std::function<int (int)> fn1(neg);
    std::cout << std::boolalpha << "empty == " << !fn1 << std::endl;
    std::cout << "val == " << fn1(3) << std::endl;

    return (0);
    }
```

```Output
empty == false
val == -3
```

## <a name="op_eq"></a>işleç =

Depolanan çağrılabilir nesneyi değiştirir.

```cpp
function& operator=(null_ptr_type npc);
function& operator=(const function& right);
template <class Fty>
    function& operator=(Fty fn);
template <class Fty>
    function& operator=(reference_wrapper<Fty> fnref);
```

### <a name="parameters"></a>Parametreler

*NPC* \
Null işaretçi sabiti.

*sağ* \
Kopyalanacak işlev nesnesi.

*fn* \
Sarılacağı çağrılabilir nesne.

*\*
Sarılacağı çağrılabilir nesne başvurusu.

### <a name="remarks"></a>Açıklamalar

İşleçler her biri, `*this` tarafından tutulan çağrılabilir nesne, işlenen olarak geçirilen çağrılabilir nesne ile değiştirilir.

### <a name="example"></a>Örnek

```cpp
// std__functional__function_operator_as.cpp
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
    fn1 = 0;
    std::cout << std::boolalpha << "empty == " << !fn1 << std::endl;

    fn1 = neg;
    std::cout << std::boolalpha << "empty == " << !fn1 << std::endl;
    std::cout << "val == " << fn1(3) << std::endl;

    fn1 = fn0;
    std::cout << std::boolalpha << "empty == " << !fn1 << std::endl;
    std::cout << "val == " << fn1(3) << std::endl;

    fn1 = std::cref(fn1);
    std::cout << std::boolalpha << "empty == " << !fn1 << std::endl;
    std::cout << "val == " << fn1(3) << std::endl;

    return (0);
    }
```

```Output
empty == false
val == -3
empty == true
empty == false
val == -3
empty == false
val == -3
empty == false
val == -3
```

## <a name="result_type"></a>result_type

Depolanan çağrılabilir nesnenin dönüş türü.

```cpp
typedef Ret result_type;
```

### <a name="remarks"></a>Açıklamalar

TypeDef, şablonun çağrı imzasında `Ret` türün bir eş anlamlısıdır. Sarmalanmış çağrılabilir nesnenin dönüş türünü öğrenmek için bunu kullanırsınız.

### <a name="example"></a>Örnek

```cpp
// std__functional__function_result_type.cpp
// compile with: /EHsc
#include <functional>
#include <iostream>

int neg(int val)
    {
    return (-val);
    }

int main()
    {
    std::function<int (int)> fn1(neg);
    std::cout << std::boolalpha << "empty == " << !fn1 << std::endl;

    std::function<int (int)>::result_type val = fn1(3);
    std::cout << "val == " << val << std::endl;

    return (0);
    }
```

```Output
empty == false
val == -3
```

## <a name="swap"></a>Kur

İki çağrılabilir nesne takas et.

```cpp
void swap(function& right);
```

### <a name="parameters"></a>Parametreler

*sağ* \
İle takas edilecek işlev nesnesi.

### <a name="remarks"></a>Açıklamalar

Üye işlevi, hedef nesneleri `*this` ve *sağa*değiştirir. Bu, sabit zamanlı olarak yapar ve özel durum oluşturmaz.

### <a name="example"></a>Örnek

```cpp
// std__functional__function_swap.cpp
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

    fn0.swap(fn1);
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

## <a name="target"></a>hedef

Depolanan çağrılabilir nesne belirtilen şekilde çağrılabilir ise sınar.

```cpp
template <class Fty2>
    Fty2 *target();
template <class Fty2>
    const Fty2 *target() const;
```

### <a name="parameters"></a>Parametreler

*Fty2* \
Sınanacak hedef çağrılabilir nesne türü.

### <a name="remarks"></a>Açıklamalar

Tür *Fty2* , `T1, T2, ..., TN` bağımsız değişken türleri için çağrılabilir olmalıdır ve dönüş türü `Ret`. @No__t_0, üye şablonu işlevi hedef nesnenin adresini döndürür; Aksi takdirde, 0 döndürür.

Bir tür *Fty2* bağımsız değişken türleri için çağrılabilir `T1, T2, ..., TN` ve `Ret` türü `Fty2, T1, T2, ..., TN` `fn, t1, t2, ..., tN`, sırasıyla `INVOKE(fn, t1, t2, ..., tN)` doğru biçimlendirilmiş ve `Ret` **void**değilse `Ret` 'e dönüştürülebilir.

### <a name="example"></a>Örnek

```cpp
// std__functional__function_target.cpp
// compile with: /EHsc
#include <functional>
#include <iostream>

int neg(int val)
    {
    return (-val);
    }

int main()
    {
    typedef int (*Myfun)(int);
    std::function<int (int)> fn0(neg);
    std::cout << std::boolalpha << "empty == " << !fn0 << std::endl;
    std::cout << "no target == " << (fn0.target<Myfun>() == 0) << std::endl;

    Myfun *fptr = fn0.target<Myfun>();
    std::cout << "val == " << (*fptr)(3) << std::endl;

    std::function<int (int)> fn1;
    std::cout << std::boolalpha << "empty == " << !fn1 << std::endl;
    std::cout << "no target == " << (fn1.target<Myfun>() == 0) << std::endl;

    return (0);
    }
```

```Output
empty == false
no target == false
val == -3
empty == true
no target == true
```

## <a name="target_type"></a>target_type

Çağrılabilir nesne üzerindeki tür bilgilerini alır.

```cpp
const std::type_info& target_type() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, `*this` boşsa `typeid(void)` döndürür, aksi takdirde `typeid(T)` döndürür; burada `T` hedef nesnenin türüdür.

### <a name="example"></a>Örnek

```cpp
// std__functional__function_target_type.cpp
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
    std::cout << "type == " << fn0.target_type().name() << std::endl;

    std::function<int (int)> fn1;
    std::cout << std::boolalpha << "empty == " << !fn1 << std::endl;
    std::cout << "type == " << fn1.target_type().name() << std::endl;

    return (0);
    }
```

```Output
empty == false
type == int (__cdecl*)(int)
empty == true
type == void
```
