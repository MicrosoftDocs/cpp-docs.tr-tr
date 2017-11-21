---
title: "Sınıf işlev | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- functional/std::function
- functional/std::function::result_type
- functional/std::function::assign
- functional/std::function::swap
- functional/std::function::target
- functional/std::function::target_type
- functional/std::function::operator unspecified
- functional/std::function::operator()
dev_langs: C++
helpviewer_keywords:
- std::function [C++]
- std::function [C++], result_type
- std::function [C++], assign
- std::function [C++], swap
- std::function [C++], target
- std::function [C++], target_type
ms.assetid: 7b5ca76b-9ca3-4d89-8fcf-cad70a4aeae6
caps.latest.revision: "26"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: da4c8dd6a3141b16b9960720c6bb1789cd06f317
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
 `Fty`  
 Sarmalamak için işlev türü.  
  
 `Ax`  
 Ayırıcı işlevi.  
  
## <a name="remarks"></a>Açıklamalar  
 Çağrı imzası çağrısı sarmalayıcı şablon sınıfıdır `Ret(T1, T2, ..., TN)`. Bir Tekdüzen sarmalayıcı çeşitli aranabilir nesneleri kapsamak için kullanın.  
  
 Bazı üye işlevleri istenen hedef nesne adları bir işlenen alır. Bu tür işleneni çeşitli yollarla belirtebilirsiniz:  
  
 `fn`--aranabilir nesne `fn`; çağrısından sonra `function` nesnesi bir kopyasını tutar`fn`  
  
 `fnref`--tarafından adlı aranabilir nesne `fnref.get()`; çağrısından sonra `function` nesnesi bir başvuru tutar`fnref.get()`  
  
 `right`--aranabilir nesne varsa, tutulan `function` nesnesi`right`  
  
 `npc`--bir null işaretçinin; çağrısından sonra `function` nesnesidir boş  
  
 Tüm durumlarda `INVOKE(f, t1, t2, ..., tN)`, burada `f` aranabilir nesnedir ve `t1, t2, ..., tN` lvalues türleri olan `T1, T2, ..., TN` sırasıyla, doğru biçimlendirilmiş olması gerekir ve `Ret` void, dönüştürülebilir değil `Ret`.  
  
 Boş bir `function` nesnesi değil tutun aranabilir bir nesne ya da aranabilir bir nesneye başvuru.  
  
### <a name="constructors"></a>Oluşturucular  
  
|||  
|-|-|  
|[işlevi](#function)|Boş veya sabit bir imza ile rastgele tür aranabilir bir nesne depolar bir sarmalayıcı oluşturur.|  
  
### <a name="typedefs"></a>Tür tanımları  
  
|||  
|-|-|  
|[result_type](#result_type)|Saklanan aranabilir nesne dönüş türü.|  
  
### <a name="member-functions"></a>Üye İşlevleri  
  
|||  
|-|-|  
|[Ata](#assign)|Aranabilir nesne bu işlev nesnesi atar.|  
|[değiştirme](#swap)|İki aranabilir nesneleri değiştirme.|  
|[Hedef](#target)|Aranabilir nesne depoladıysanız testleri belirtildiği şekilde çağrılabilir.|  
|[target_type](#target_type)|Alır aranabilir nesnede bilgileri yazın.|  
  
### <a name="operators"></a>İşleçler  
  
|||  
|-|-|  
|[function::operator belirtilmemiş](#op_unspecified)|Aranabilir nesne depoladıysanız testleri bulunmaktadır.|  
|[işlev:: operator()](#op_call)|Aranabilir nesnesi çağırır.|  
|[Function::operator =](#op_eq)|Depolanan aranabilir nesnesini değiştirir.|  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<işlevsel >  
  
 **Namespace:** std  
  
##  <a name="assign"></a>Function::Assign  
 Aranabilir nesne bu işlev nesnesi atar.  
  
```  
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
 `_Func`  
 Aranabilir bir nesne.  
  
 `_Fnref`  
 Aranabilir bir nesne içeren bir başvuru sarmalayıcı.  
  
 `Ax`  
 Bir ayırıcı nesne.  
  
### <a name="remarks"></a>Açıklamalar  
 Her Değiştir üye işlevlerini `callable object` tutulan `*this` olarak geçirilen aranabilir nesnesi ile `operand`. Her ikisi de ayırıcısı nesnesiyle depolama alanı Ayır `Ax`.  
  
##  <a name="function"></a>Function::Function  
 Boş veya sabit bir imza ile rastgele tür aranabilir bir nesne depolar bir sarmalayıcı oluşturur.  
  
```  
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
 `right`  
 Kopyalamak için işlev nesnesi.  
  
 `Fx`  
 Aranabilir nesnenin türü.  
  
 `_Func`  
 Sarılacak aranabilir nesne.  
  
 `Alloc`  
 Ayırıcı türü.  
  
 `Ax`  
 Ayırıcı.  
  
 `_Fnref`  
 Sarılacak aranabilir nesne başvurusu.  
  
### <a name="remarks"></a>Açıklamalar  
 Boş bir ilk iki oluşturucular oluşturmak `function` nesnesi. Sonraki üç oluşturucular oluşturmak bir `function` aranabilir nesnesi tutar nesnesi işleneni olarak geçirildi. Son iki oluşturucular depolama Ax ayırıcısı nesnesi ile ayırın.  
  
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
  
##  <a name="op_unspecified"></a>function::operator belirtilmemiş  
 Aranabilir nesne depoladıysanız testleri bulunmaktadır.  
  
```  
operator unspecified();
```   
  
### <a name="remarks"></a>Açıklamalar  
 İşleç parametresinin bir değer döndürür `bool` yalnızca nesne boş değilse true değerine sahip. Nesne boş olup olmadığını sınamak için kullanın.  
  
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
  
##  <a name="op_call"></a>işlev:: operator()  
 Aranabilir nesnesi çağırır.  
  
```  
result_type operator()(
    T1 t1,
    T2 t2, ...,
    TN tN);
```  
  
### <a name="parameters"></a>Parametreler  
 `TN`  
 N. tür bağımsız değişkeni çağırın.  
  
 `tN`  
 Nth çağrı bağımsız değişken.  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevi döndürür `INVOKE(fn, t1, t2, ..., tN, Ret)`, burada `fn` depolanan hedef nesnesi `*this`. Sarmalanan aranabilir nesne çağırmak için kullanın.  
  
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
  
##  <a name="op_eq"></a>Function::operator =  
 Depolanan aranabilir nesnesini değiştirir.  
  
```  
function& operator=(null_ptr_type npc);
function& operator=(const function& right);
template <class Fty>  
    function& operator=(Fty fn);
template <class Fty>  
    function& operator=(reference_wrapper<Fty> fnref);
```  
  
### <a name="parameters"></a>Parametreler  
 `npc`  
 Bir null işaretçinin sabiti.  
  
 `right`  
 Kopyalamak için işlev nesnesi.  
  
 `fn`  
 Sarılacak aranabilir nesne.  
  
 `fnref`  
 Sarılacak aranabilir nesne başvurusu.  
  
### <a name="remarks"></a>Açıklamalar  
 Her işleçleri tarafından tutulan aranabilir nesneyi değiştirmek `*this` aranabilir nesnesiyle işleneni olarak geçirildi.  
  
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
  
##  <a name="result_type"></a>Function::result_type  
 Saklanan aranabilir nesne dönüş türü.  
  
```  
typedef Ret result_type;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Typedef türü için eş anlamlı olduğundan `Ret` şablonun çağrısı imzada. Sarmalanan aranabilir nesne dönüş türünü belirlemek için kullanın.  
  
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
  
##  <a name="swap"></a>Function::Swap  
 İki aranabilir nesneleri değiştirme.  
  
```  
void swap(function& right);
```  
  
### <a name="parameters"></a>Parametreler  
 `right`  
 İle değiştirme işlev nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevini hedef nesneler arasında değiştirir `*this` ve `right`. Bunu Sabit sürede yapar ve hiçbir özel durum oluşturur.  
  
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
  
##  <a name="target"></a>Function::target  
 Aranabilir nesne depoladıysanız testleri belirtildiği şekilde çağrılabilir.  
  
```  
template <class Fty2>  
    Fty2 *target();
template <class Fty2>  
    const Fty2 *target() const;
```  
  
### <a name="parameters"></a>Parametreler  
 `Fty2`  
 Test etmek için hedef aranabilir nesne türü.  
  
### <a name="remarks"></a>Açıklamalar  
 Türü `Fty2` için bağımsız değişken türleri aranabilir olmalıdır `T1, T2, ..., TN` ve dönüş türü `Ret`. Varsa `target_type() == typeid(Fty2)`, hedef nesnenin adresi üye şablon fonksiyonunu döndürür; Aksi halde 0 döndürür.  
  
 Bir tür `Fty2` için bağımsız değişken türleri aranabilir olan `T1, T2, ..., TN` ve dönüş türü `Ret` örneğin lvalues `fn, t1, t2, ..., tN` türlerinin `Fty2, T1, T2, ..., TN`, sırasıyla `INVOKE(fn, t1, t2, ..., tN)` doğru biçimlendirildiğinden ve `Ret` değil `void`, dönüştürülebilir `Ret`.  
  
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
  
##  <a name="target_type"></a>Function::target_type  
 Alır aranabilir nesnede bilgileri yazın.  
  
```  
const std::type_info& target_type() const;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevi döndürür `typeid(void)` varsa `*this` Aksi takdirde döndürür boş olduğundan `typeid(T)`, burada `T` hedef nesne türü.  
  
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
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [mem_fn](../standard-library/functional-functions.md#mem_fn)   
 [reference_wrapper sınıfı](../standard-library/reference-wrapper-class.md)
