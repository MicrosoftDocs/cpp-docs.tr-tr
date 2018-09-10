---
title: Sınıf işlev | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- functional/std::function
- functional/std::function::result_type
- functional/std::function::assign
- functional/std::function::swap
- functional/std::function::target
- functional/std::function::target_type
- functional/std::function::operator unspecified
- functional/std::function::operator()
dev_langs:
- C++
helpviewer_keywords:
- std::function [C++]
- std::function [C++], result_type
- std::function [C++], assign
- std::function [C++], swap
- std::function [C++], target
- std::function [C++], target_type
ms.assetid: 7b5ca76b-9ca3-4d89-8fcf-cad70a4aeae6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3cfafc2c17ef804cb8d87c1189c8a7f3163d3c46
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/07/2018
ms.locfileid: "44104140"
---
# <a name="function-class"></a>function Sınıfı

Aranabilir bir nesne için sarmalayıcı.

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

*Fty*<br/>
Kaydırmak için işlev türü.

*AX*<br/>
Allocator işlev.

## <a name="remarks"></a>Açıklamalar

Şablon sınıfı, çağrı imzası olan bir çağrı sarmalayıcıdır `Ret(T1, T2, ..., TN)`. Tekdüzen bir kapsayıcı içinde çeşitli çağrılabilir nesneleri kapsamak için kullanın.

Bazı üye işlevleri, istenen hedef nesne adları bir bir işlenen alır. Böyle bir işlenen birkaç şekilde belirtebilirsiniz:

`fn` --çağrılabilir nesne `fn`; çağrısından sonra `function` nesnesi bir kopyasını tutar `fn`

`fnref` --tarafından adlandırılan çağrılabilir nesne `fnref.get()`; çağrısından sonra `function` nesnesi bir başvuru tutar `fnref.get()`

`right` --tarafından varsa aranabilir nesne tutulan `function` nesnesi `right`

`npc` --bir null işaretçi; çağrısından sonra `function` nesnedir boş

Tüm durumlarda `INVOKE(f, t1, t2, ..., tN)`burada `f` çağrılabilir nesne ve `t1, t2, ..., tN` türlerinin lvalues `T1, T2, ..., TN` sırasıyla iyi biçimlendirilmiş olmalıdır ve `Ret` void, dönüştürülebilir değil `Ret`.

Boş bir `function` nesne değil basılı çağrılabilir bir nesne ya da çağrılabilir nesnesine bir başvuru.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[İşlevi](#function)|Rastgele tür sabit bir imza ile çağrılabilen bir nesne depolar veya boş bir sarmalayıcı oluşturur.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[result_type](#result_type)|Saklı çağrılabilir nesnenin dönüş türü.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[Ata](#assign)|Bu işlev nesnesi için çağrılabilen bir nesnesi atar.|
|[değiştirme](#swap)|İki çağrılabilir nesneleri değiştirme.|
|[Hedef](#target)|Çağrılabilir nesne depolanan olup olmadığını test eder belirtildiği şekilde çağrılabilir.|
|[target_type](#target_type)|Çağrılabilir nesne türü bilgileri alır.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[function::operator belirtilmemiş](#op_unspecified)|Depolanan çağrılabilir nesne varolup olmadığını test eder.|
|[function::operator()](#op_call)|Aranabilir bir nesne çağırır.|
|[function::operator=](#op_eq)|Saklı çağrılabilir nesnenin yerini alır.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<işlev >

**Namespace:** std

## <a name="assign"></a>  Function::Assign

Bu işlev nesnesi için çağrılabilen bir nesnesi atar.

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

*_Func*<br/>
Aranabilir bir nesne.

*_Fnref*<br/>
Çağrılabilir nesnesi içeren bir başvuru sarmalayıcı.

*AX*<br/>
Ayırıcı nesnesi.

### <a name="remarks"></a>Açıklamalar

Her Değiştir üye işlevleri `callable object` tutulan `*this` olarak geçirilen çağrılabilir nesnesi ile `operand`. Her ikisi de ayırıcı nesnesi ile depolama tahsis *Ax*.

## <a name="function"></a>  Function::Function

Rastgele tür sabit bir imza ile çağrılabilen bir nesne depolar veya boş bir sarmalayıcı oluşturur.

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

*sağ*<br/>
Kopyalamak için işlev nesnesi.

*FX*<br/>
Çağrılabilir nesnenin türü.

*_Func*<br/>
Kaydırmak için çağrılabilir nesne.

*Ayırma*<br/>
Ayırıcı türü.

*AX*<br/>
Ayırıcı.

*_Fnref*<br/>
Kaydırmak için çağrılabilir nesne başvurusu.

### <a name="remarks"></a>Açıklamalar

İlk iki Oluşturucu boş bir oluşturmak `function` nesne. Sonraki üç oluşturucular oluşturmak bir `function` çağrılabilir nesne tutan nesne işlenen olarak geçirildi. Son iki oluşturucular ayırıcı nesnesi Ax depolamayla ayırın.

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

## <a name="op_unspecified"></a>  function::operator belirtilmemiş

Depolanan çağrılabilir nesne varolup olmadığını test eder.

```cpp
operator unspecified();
```

### <a name="remarks"></a>Açıklamalar

İşleç dönüştürülebilen bir değer döndürür **bool** yalnızca nesne boş değilse true değerine sahip. Nesne boş olup olmadığını sınamak için kullanın.

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

## <a name="op_call"></a>  işlev:: operator()

Aranabilir bir nesne çağırır.

```cpp
result_type operator()(
    T1 t1,
    T2 t2, ...,
    TN tN);
```

### <a name="parameters"></a>Parametreler

*TN*<br/>
Çağrı bağımsız değişken türü n.

*TN*<br/>
Nth çağrı bağımsız değişkeni.

### <a name="remarks"></a>Açıklamalar

Üye işlevinin döndürdüğü `INVOKE(fn, t1, t2, ..., tN, Ret)`burada `fn` depolanan hedef nesnesi `*this`. Sarmalanan çağrılabilir nesne çağırmak için kullanın.

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

## <a name="op_eq"></a>  Function::operator =

Saklı çağrılabilir nesnenin yerini alır.

```cpp
function& operator=(null_ptr_type npc);
function& operator=(const function& right);
template <class Fty>
    function& operator=(Fty fn);
template <class Fty>
    function& operator=(reference_wrapper<Fty> fnref);
```

### <a name="parameters"></a>Parametreler

*npc*<br/>
Boş işaretçi sabiti.

*sağ*<br/>
Kopyalamak için işlev nesnesi.

*fn*<br/>
Kaydırmak için çağrılabilir nesne.

*fnref*<br/>
Kaydırmak için çağrılabilir nesne başvurusu.

### <a name="remarks"></a>Açıklamalar

Her işleçleri çağrılabilir nesne tarafından tutulan değiştirin `*this` çağrılabilir nesnesiyle işlenen olarak geçirildi.

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

## <a name="result_type"></a>  Function::result_type

Saklı çağrılabilir nesnenin dönüş türü.

```cpp
typedef Ret result_type;
```

### <a name="remarks"></a>Açıklamalar

Typedef türü eşanlamlıdır `Ret` şablonun çağrı imzası. Sarmalanan çağrılabilir nesnenin dönüş türünü belirlemek için kullanın.

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

## <a name="swap"></a>  Function::Swap

İki çağrılabilir nesneleri değiştirme.

```cpp
void swap(function& right);
```

### <a name="parameters"></a>Parametreler

*sağ*<br/>
İle takas için işlev nesnesi.

### <a name="remarks"></a>Açıklamalar

Üye işlevi hedef nesneler arasında değiştirir `*this` ve *doğru*. Bu sabit sürede yazılabilmesine ve hiçbir özel durum oluşturur.

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

## <a name="target"></a>  Function::target

Çağrılabilir nesne depolanan olup olmadığını test eder belirtildiği şekilde çağrılabilir.

```cpp
template <class Fty2>
    Fty2 *target();
template <class Fty2>
    const Fty2 *target() const;
```

### <a name="parameters"></a>Parametreler

*Fty2*<br/>
Test etmek için hedef çağrılabilir nesne türü.

### <a name="remarks"></a>Açıklamalar

Türü *Fty2* bağımsız değişken türleri için çağrılabilir olmalıdır `T1, T2, ..., TN` ve dönüş türü `Ret`. Varsa `target_type() == typeid(Fty2)`, üye şablon işlevi hedef nesnenin adresini döndürür; Aksi takdirde 0 değerini döndürür.

Bir tür *Fty2* bağımsız değişken türleri için çağrılabilir `T1, T2, ..., TN` ve dönüş türü `Ret` örneğin lvalues `fn, t1, t2, ..., tN` türlerinin `Fty2, T1, T2, ..., TN`sırasıyla `INVOKE(fn, t1, t2, ..., tN)` iyi biçimlendirilmemiş ve `Ret`değil **void**, dönüştürülebilir `Ret`.

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

## <a name="target_type"></a>  Function::target_type

Çağrılabilir nesne türü bilgileri alır.

```cpp
const std::type_info& target_type() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevinin döndürdüğü `typeid(void)` varsa `*this` olan boş, aksi halde döndürür `typeid(T)`burada `T` hedef nesne türü.

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

## <a name="see-also"></a>Ayrıca bkz.

[mem_fn](../standard-library/functional-functions.md#mem_fn)<br/>
[reference_wrapper Sınıfı](../standard-library/reference-wrapper-class.md)<br/>
