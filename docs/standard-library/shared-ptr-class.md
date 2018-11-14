---
title: shared_ptr Sınıfı
ms.date: 11/04/2016
f1_keywords:
- memory/std::shared_ptr
- memory/std::shared_ptr::element_type
- memory/std::shared_ptr::get
- memory/std::shared_ptr::owner_before
- memory/std::shared_ptr::reset
- memory/std::shared_ptr::swap
- memory/std::shared_ptr::unique
- memory/std::shared_ptr::use_count
- memory/std::shared_ptr::operator boolean-type
- memory/std::shared_ptr::operator*
- memory/std::shared_ptr::operator=
- memory/std::shared_ptr::operator->
helpviewer_keywords:
- std::shared_ptr [C++]
- std::shared_ptr [C++], element_type
- std::shared_ptr [C++], get
- std::shared_ptr [C++], owner_before
- std::shared_ptr [C++], reset
- std::shared_ptr [C++], swap
- std::shared_ptr [C++], unique
- std::shared_ptr [C++], use_count
- std::shared_ptr [C++], element_type
- std::shared_ptr [C++], get
- std::shared_ptr [C++], owner_before
- std::shared_ptr [C++], reset
- std::shared_ptr [C++], swap
- std::shared_ptr [C++], unique
- std::shared_ptr [C++], use_count
ms.assetid: 1469fc51-c658-43f1-886c-f4530dd84860
ms.openlocfilehash: 791a18461b3a0ee8237dec47c87f9d441221141d
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/10/2018
ms.locfileid: "51519366"
---
# <a name="sharedptr-class"></a>shared_ptr Sınıfı

Dinamik olarak tahsis edilen bir nesnenin çevresine bir başvuru sayılan akıllı işaretçi sarar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class T>
class shared_ptr;
```

## <a name="remarks"></a>Açıklamalar

Shared_ptr sınıfı, kaynakları yönetmek için referans sayımı kullanan bir nesneyi tanımlar. A `shared_ptr` nesne kaynak sahibi veya bir null işaretçiyi tuttuğu için etkili bir şekilde bir işaretçi tutar. Kaynak birden fazla tarafından sahiplenilebilir `shared_ptr` nesne; olduğunda son `shared_ptr` belirli bir kaynağa sahip nesnesi yok edildiğinde, kaynak serbest bırakılır.

A `shared_ptr` yeniden atandığında veya sıfırlandığında kaynağa sahip olmayı durdurur.

Şablon bağımsız değişkeni `T` belirli üye işlevleri belirtilenler dışında bir eksik tür olabilir.

Olduğunda bir `shared_ptr<T>` nesnesi, bir kaynak türü işaretçisinden oluşturulduğunda `G*` veya bir `shared_ptr<G>`, işaretçi türünün `G*` dönüştürülebilmelidir `T*`. Yüklü değilse, kod derlemeyecektir. Örneğin:

```cpp
#include <memory>
using namespace std;

class F {};
class G : public F {};

shared_ptr<G> sp0(new G);   // okay, template parameter G and argument G*
shared_ptr<G> sp1(sp0);     // okay, template parameter G and argument shared_ptr<G>
shared_ptr<F> sp2(new G);   // okay, G* convertible to F*
shared_ptr<F> sp3(sp0);     // okay, template parameter F and argument shared_ptr<G>
shared_ptr<F> sp4(sp2);     // okay, template parameter F and argument shared_ptr<F>
shared_ptr<int> sp5(new G); // error, G* not convertible to int*
shared_ptr<int> sp6(sp2);   // error, template parameter int and argument shared_ptr<F>
```

A `shared_ptr` nesnesi bir kaynağa sahiptir:

- Bu kaynağa bir işaretçi ile oluşturulmuşsa,

- öğesinden oluşturulmuşsa bir `shared_ptr` bu kaynağa sahip nesne

- öğesinden oluşturulmuşsa bir [weak_ptr sınıfı](../standard-library/weak-ptr-class.md) konusu kaynağı işaret eden bir nesne veya

- Bu kaynağın sahipliği ona ile atanmışsa [shared_ptr::operator =](#op_eq) veya üye işlevini çağırarak [shared_ptr::reset](#reset).

`shared_ptr` Bir kaynağa sahip nesneleri bir denetim bloğunu paylaşır. Denetim bloğu şunları tutar:

- sayısını `shared_ptr` kaynağa sahip nesneleri

- sayısını `weak_ptr` kaynağa işaret nesneleri

- varsa, o kaynak için Silici,

- varsa, Denetim bloğunun özel bellek ayırıcısı.

A `shared_ptr` bir null işaretçi kullanılarak başlatılan bir nesne bir denetim bloğu yoktur ve boş değil. Sonra bir `shared_ptr` nesnesi bir kaynağı serbest bıraktıktan, artık bu kaynağa sahip değildir. Sonra bir `weak_ptr` nesnesi bir kaynağı serbest bıraktıktan, artık o kaynağa işaret eder.

Zaman sayısını `shared_ptr` kendi kaynak sıfır olduğunda, kaynak, silmek ya da adresini kaynağının sahipliğinin orijinal olarak nasıl oluşturulduğuna bağlı olarak bir Silici geçirerek serbest nesneleri. Zaman sayısını `shared_ptr` bir kaynağa sahip nesneleri, sıfır ve sayısını, `weak_ptr` nesneleri işaret kaynak sıfırsa, denetim bloğu, varsa, denetim bloğu özel ayırıcı kullanılarak serbest bırakılır.

Boş bir `shared_ptr` nesnesi bir kaynağı bulunmaz ve denetim bloğu yoktur.

Silici üye işleve sahip bir işlev nesnesidir `operator()`. Türü kopya atmamalıdır olmalıdır ve kopya oluşturucusu ve yıkıcısı özel durum oluşturmamalıdır. Bu, bir parametre, silinecek nesneyi kabul eder.

Bazı işlevler ortaya çıkan özelliklerini tanımlayan bir bağımsız değişken listesi alır `shared_ptr<T>` veya `weak_ptr<T>` nesne. Böyle bir bağımsız değişken listesini birkaç şekilde belirtebilirsiniz:

bağımsız değişken yok--sonuç nesnesi boş bir `shared_ptr` nesnesidir veya boş bir `weak_ptr` nesne.

`ptr` --türünde bir işaretçi `Other*` yönetilecek kaynağa. `T` tam bir tür olmalıdır. (Denetim bloğu ayrılamadığından), işlev başarısız olursa ifadesini değerlendirir `delete ptr`.

`ptr, dtor` --türünde bir işaretçi `Other*` kaynağın yönetilmesini ve bu kaynak için Silici. (Denetim bloğu ayrılamadığından), işlev başarısız olursa çağrı `dtor(ptr)`, iyi tanımlanmış olmalıdır.

`ptr, dtor, alloc` --türünde bir işaretçi `Other*` yönetilecek kaynağın, ayrılan ve serbest gereken herhangi bir depolama alanı yönetmek için ayırıcı yanı sıra bu kaynak için Silici. (Denetim bloğu ayrılamadığından), işlev başarısız olursa çağrı `dtor(ptr)`, iyi tanımlanmış olmalıdır.

`sp` --bir `shared_ptr<Other>` yönetilecek kaynağın sahibi nesne.

`wp` --bir `weak_ptr<Other>` yönetilecek kaynağı işaret eden bir nesne.

`ap` --bir `auto_ptr<Other>` yönetilecek kaynağa bir işaretçi tutan nesne. İsteğe bağlı olarak işlev çağrıları başarılı olursa `ap.release()`; Aksi halde bırakır `ap` değişmez.

Tüm durumlarda, işaretçi türünün `Other*` dönüştürülebilmelidir `T*`.

## <a name="thread-safety"></a>İş Parçacığı Güvenliği

Birden çok iş parçacığı okuma ve yazma farklı `shared_ptr` nesneler bu paylaşım sahipliğinin kopyası bile aynı anda nesneleri.

## <a name="members"></a>Üyeler

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[shared_ptr](#shared_ptr)|Oluşturur bir `shared_ptr`.|
|[shared_ptr:: ~ shared_ptr](#dtorshared_ptr)|Yok eder bir `shared_ptr`.|

### <a name="types"></a>Türler

|Tür adı|Açıklama|
|-|-|
|[element_type](#element_type)|Öğenin türü.|

### <a name="functions"></a>İşlevler

|İşlev|Açıklama|
|-|-|
|[get](#get)|Sahip olunan kaynağının adresini alır.|
|[owner_before](#owner_before)|Bu, true döndürür `shared_ptr` önceyse (veya küçüktür) sağlanan işaretçi.|
|[Sıfırlama](#reset)|Sahip olunan Kaynağı Değiştir.|
|[değiştirme](#swap)|İki değiştirir `shared_ptr` nesneleri.|
|[unique](#unique)|Sahip olunan kaynağın benzersiz olup olmadığını sınar.|
|[use_count](#use_count)|Kaynak sahiplerinin sayısını sayar.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[shared_ptr::operator bool](#op_bool)|Sahip olunan bir kaynağın varolup olmadığını test eder.|
|[shared_ptr::operator *](#op_star)|Belirtilen değeri alır.|
|[shared_ptr::operator=](#op_eq)|Sahip olunan kaynağı değiştirir.|
|[shared_ptr::operator-&gt;](#op_arrow)|Belirtilen değer için bir işaretçi alır.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<bellek >

**Namespace:** std

## <a name="element_type"></a>  shared_ptr::ELEMENT_TYPE

Öğenin türü.

```cpp
typedef T element_type;
```

### <a name="remarks"></a>Açıklamalar

Şablon parametresi için bir eşanlamlı türüdür `T`.

### <a name="example"></a>Örnek

```cpp
// std__memory__shared_ptr_element_type.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

int main()
{
    std::shared_ptr<int> sp0(new int(5));
    std::shared_ptr<int>::element_type val = *sp0;

    std::cout << "*sp0 == " << val << std::endl;

    return (0);
}
```

```Output
*sp0 == 5
```

## <a name="get"></a>  shared_ptr::get

Sahip olunan kaynağının adresini alır.

```cpp
T *get() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, sahip olunan kaynağının adresini döndürür. Nesnesi bir kaynağa sahip değilse, 0 döndürür.

### <a name="example"></a>Örnek

```cpp
// std__memory__shared_ptr_get.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

int main()
{
    std::shared_ptr<int> sp0;
    std::shared_ptr<int> sp1(new int(5));

    std::cout << "sp0.get() == 0 == " << std::boolalpha
        << (sp0.get() == 0) << std::endl;
    std::cout << "*sp1.get() == " << *sp1.get() << std::endl;

    return (0);
}
```

```Output
sp0.get() == 0 == true
*sp1.get() == 5
```

## <a name="op_bool"></a>  shared_ptr::operator bool

Sahip olunan bir kaynağın varolup olmadığını test eder.

```cpp
explicit operator bool() const noexcept;
```

### <a name="remarks"></a>Açıklamalar

İşleç değerini döndürür **true** olduğunda `get() != nullptr`, aksi takdirde **false**.

### <a name="example"></a>Örnek

```cpp
// std__memory__shared_ptr_operator_bool.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

int main()
{
    std::shared_ptr<int> sp0;
    std::shared_ptr<int> sp1(new int(5));

    std::cout << "(bool)sp0 == " << std::boolalpha
        << (bool)sp0 << std::endl;
    std::cout << "(bool)sp1 == " << std::boolalpha
        << (bool)sp1 << std::endl;

    return (0);
}
```

```Output
(bool)sp0 == false
(bool)sp1 == true
```

## <a name="op_star"></a>  shared_ptr::operator *

Belirtilen değeri alır.

```cpp
T& operator*() const;
```

### <a name="remarks"></a>Açıklamalar

Yöneltme işleci döndürür `*get()`. Bu nedenle, depolanmış işaretçiyi null olmamalıdır.

### <a name="example"></a>Örnek

```cpp
// std__memory__shared_ptr_operator_st.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

int main()
{
    std::shared_ptr<int> sp0(new int(5));

    std::cout << "*sp0 == " << *sp0 << std::endl;

    return (0);
}
```

```Output
*sp0 == 5
```

## <a name="op_eq"></a>  shared_ptr::operator =

Sahip olunan kaynağı değiştirir.

```cpp
shared_ptr& operator=(const shared_ptr& sp);

template <class Other>
shared_ptr& operator=(const shared_ptr<Other>& sp);

template <class Other>
shared_ptr& operator=(auto_ptr<Other>& ap);

template <class Other>
shared_ptr& operator=(auto_ptr<Other>& ap);

template <class Other>
shared_ptr& operator=(auto_ptr<Other>&& ap);

template <class Other, class Deletor>
shared_ptr& operator=(unique_ptr<Other, Deletor>&& ap);
```

### <a name="parameters"></a>Parametreler

*SP*<br/>
Kopyalamak için paylaşılan işaretçi.

*AP*<br/>
Kopyalamak için otomatik işaretçi.

### <a name="remarks"></a>Açıklamalar

Tüm işleçleri tarafından sahip olunan kaynağı için başvuru sayısını azaltma `*this` ve işlenen dizinin tarafından adlı kaynağın sahipliğini Ata `*this`. Başvuru sayısı sıfıra düşerse, kaynak serbest bırakılır. İsteğe bağlı olarak bir işleç leaves başarısız olursa `*this` değişmez.

### <a name="example"></a>Örnek

```cpp
// std__memory__shared_ptr_operator_as.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

int main()
{
    std::shared_ptr<int> sp0;
    std::shared_ptr<int> sp1(new int(5));
    std::auto_ptr<int> ap(new int(10));

    sp0 = sp1;
    std::cout << "*sp0 == " << *sp0 << std::endl;

    sp0 = ap;
    std::cout << "*sp0 == " << *sp0 << std::endl;

    return (0);
}
```

```Output
*sp0 == 5
*sp0 == 10
```

## <a name="op_arrow"></a>  shared_ptr::operator-&gt;

Belirtilen değer için bir işaretçi alır.

```cpp
T * operator->() const;
```

### <a name="remarks"></a>Açıklamalar

Seçim operatörü döndürür `get()`, böylece ifade `sp->member` gibi davranır `(sp.get())->member` burada `sp` sınıfın bir nesnesi `shared_ptr<T>`. Bu nedenle, depolanmış işaretçiyi null olmamalıdır ve `T` sınıf, yapı veya birleşim türü bir üyeyle olmalıdır `member`.

### <a name="example"></a>Örnek

```cpp
// std__memory__shared_ptr_operator_ar.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

typedef std::pair<int, int> Mypair;
int main()
{
    std::shared_ptr<Mypair> sp0(new Mypair(1, 2));

    std::cout << "sp0->first == " << sp0->first << std::endl;
    std::cout << "sp0->second == " << sp0->second << std::endl;

    return (0);
}
```

```Output
sp0->first == 1
sp0->second == 2
```

## <a name="owner_before"></a>  shared_ptr::owner_before

Bu, true döndürür `shared_ptr` önceyse (veya küçüktür) sağlanan işaretçi.

```cpp
template <class Other>
bool owner_before(const shared_ptr<Other>& ptr);

template <class Other>
bool owner_before(const weak_ptr<Other>& ptr);
```

### <a name="parameters"></a>Parametreler

*ptr*<br/>
Bir `lvalue` başvuru ya da bir `shared_ptr` veya `weak_ptr`.

### <a name="remarks"></a>Açıklamalar

Şablon üye işlev true döndürür `*this` olduğu `ordered before` `ptr`.

## <a name="reset"></a>  shared_ptr::reset

Sahip olunan Kaynağı Değiştir.

```cpp
void reset();

template <class Other>
void reset(Other *ptr;);

template <class Other, class D>
void reset(Other *ptr, D dtor);

template <class Other, class D, class A>
void reset(Other *ptr, D dtor, A alloc);
```

### <a name="parameters"></a>Parametreler

*Diğer*<br/>
Bağımsız değişken işaretçiyle kontrol edilen tür.

*D*<br/>
Silici türü.

*ptr*<br/>
Kopya işaretçisi.

*dtor*<br/>
Kopyalamak için Silici.

*A*<br/>
Ayırıcı türü.

*Ayırma*<br/>
Kopyalanacak kaynak ayırıcı.

### <a name="remarks"></a>Açıklamalar

Tüm işleçleri tarafından sahip olunan kaynağı için başvuru sayısını azaltma `*this` ve işlenen dizinin tarafından adlı kaynağın sahipliğini Ata `*this`. Başvuru sayısı sıfıra düşerse, kaynak serbest bırakılır. İsteğe bağlı olarak bir işleç leaves başarısız olursa `*this` değişmez.

### <a name="example"></a>Örnek

```cpp
// std__memory__shared_ptr_reset.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

struct deleter
{
    void operator()(int *p)
    {
        delete p;
    }
};

int main()
{
    std::shared_ptr<int> sp(new int(5));

    std::cout << "*sp == " << std::boolalpha
        << *sp << std::endl;

    sp.reset();
    std::cout << "(bool)sp == " << std::boolalpha
        << (bool)sp << std::endl;

    sp.reset(new int(10));
    std::cout << "*sp == " << std::boolalpha
        << *sp << std::endl;

    sp.reset(new int(15), deleter());
    std::cout << "*sp == " << std::boolalpha
        << *sp << std::endl;

    return (0);
}
```

```Output
*sp == 5
(bool)sp == false
*sp == 10
*sp == 15
```

## <a name="shared_ptr"></a>  shared_ptr::shared_ptr

Oluşturur bir `shared_ptr`.

```cpp
shared_ptr();

shared_ptr(nullptr_t);

shared_ptr(const shared_ptr& sp);

shared_ptr(shared_ptr&& sp);

template <class Other>
explicit shared_ptr(Other* ptr);

template <class Other, class D>
shared_ptr(Other* ptr, D dtor);

template <class D>
shared_ptr(nullptr_t ptr, D dtor);

template <class Other, class D, class A>
shared_ptr(Other* ptr, D dtor, A  alloc);

template <class D, class A>
shared_ptr(nullptr_t ptr, D dtor, A alloc);

template <class Other>
shared_ptr(const shared_ptr<Other>& sp);

template <class Other>
shared_ptr(const weak_ptr<Other>& wp);

template <class &>
shared_ptr(std::auto_ptr<Other>& ap);

template <class &>
shared_ptr(std::auto_ptr<Other>&& ap);

template <class Other, class D>
shared_ptr(unique_ptr<Other, D>&& up);

template <class Other>
shared_ptr(const shared_ptr<Other>& sp, T* ptr);

template <class Other, class D>
shared_ptr(const unique_ptr<Other, D>& up) = delete;
```

### <a name="parameters"></a>Parametreler

*Diğer*<br/>
Bağımsız değişken işaretçiyle kontrol edilen tür.

*ptr*<br/>
Kopya işaretçisi.

*D*<br/>
Silici türü.

*A*<br/>
Ayırıcı türü.

*dtor*<br/>
Silici.

*etmeni*<br/>
Ayırıcı.

*SP*<br/>
Kopyalamak için akıllı işaretçi.

*WP*<br/>
Zayıf işaretçi.

*AP*<br/>
Kopyalamak için otomatik işaretçi.

### <a name="remarks"></a>Açıklamalar

Her oluşturucular tarafından işlenen dizisi adlı kaynağına sahip olan bir nesne oluşturur. Oluşturucu `shared_ptr(const weak_ptr<Other>& wp)` türünde bir özel durum nesnesi oluşturur [bad_weak_ptr sınıfı](../standard-library/bad-weak-ptr-class.md) varsa `wp.expired()`.

### <a name="example"></a>Örnek

```cpp
// std__memory__shared_ptr_construct.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

struct deleter
{
    void operator()(int *p)
    {
        delete p;
    }
};

int main()
{
    std::shared_ptr<int> sp0;
    std::cout << "(bool)sp0 == " << std::boolalpha
        << (bool)sp0 << std::endl;

    std::shared_ptr<int> sp1(new int(5));
    std::cout << "*sp1 == " << *sp1 << std::endl;

    std::shared_ptr<int> sp2(new int(10), deleter());
    std::cout << "*sp2 == " << *sp2 << std::endl;

    std::shared_ptr<int> sp3(sp2);
    std::cout << "*sp3 == " << *sp3 << std::endl;

    std::weak_ptr<int> wp(sp3);
    std::shared_ptr<int> sp4(wp);
    std::cout << "*sp4 == " << *sp4 << std::endl;

    std::auto_ptr<int> ap(new int(15));
    std::shared_ptr<int> sp5(ap);
    std::cout << "*sp5 == " << *sp5 << std::endl;

    return (0);
}
```

```Output
(bool)sp0 == false
*sp1 == 5
*sp2 == 10
*sp3 == 10
*sp4 == 10
*sp5 == 15
```

## <a name="dtorshared_ptr"></a>  shared_ptr:: ~ shared_ptr

Yok eder bir `shared_ptr`.

```cpp
~shared_ptr();
```

### <a name="remarks"></a>Açıklamalar

Yıkıcı azaltır sahibi şu anda kaynak başvuru sayımını `*this`. Başvuru sayısı sıfıra düşerse, kaynak serbest bırakılır.

### <a name="example"></a>Örnek

```cpp
// std__memory__shared_ptr_destroy.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

struct deleter
{
    void operator()(int *p)
    {
        delete p;
    }
};

int main()
{
    std::shared_ptr<int> sp1(new int(5));
    std::cout << "*sp1 == " << *sp1 << std::endl;
    std::cout << "use count == " << sp1.use_count() << std::endl;

    {
        std::shared_ptr<int> sp2(sp1);
        std::cout << "*sp2 == " << *sp2 << std::endl;
        std::cout << "use count == " << sp1.use_count() << std::endl;
    }

    // check use count after sp2 is destroyed
    std::cout << "use count == " << sp1.use_count() << std::endl;

    return (0);
}
```

```Output
*sp1 == 5
use count == 1
*sp2 == 5
use count == 2
use count == 1
```

## <a name="swap"></a>  shared_ptr::Swap

İki değiştirir `shared_ptr` nesneleri.

```cpp
void swap(shared_ptr& sp);
```

### <a name="parameters"></a>Parametreler

*SP*<br/>
Paylaşılan işaretçi ile değiştirilecek.

### <a name="remarks"></a>Açıklamalar

Üye işlevi başlangıçta tarafından sahip olunan kaynağı bırakır `*this` sonradan tarafından sahip olunan *sp*ve başlangıçta tarafından sahip olunan kaynağı *sp* sonradan tarafından sahip olunan `*this`. İşlev iki kaynaklar için başvuru sayılarını değiştirmez ve özel durumlar oluşturmaz.

### <a name="example"></a>Örnek

```cpp
// std__memory__shared_ptr_swap.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

struct deleter
{
    void operator()(int *p)
    {
        delete p;
    }
};

int main()
{
    std::shared_ptr<int> sp1(new int(5));
    std::shared_ptr<int> sp2(new int(10));
    std::cout << "*sp1 == " << *sp1 << std::endl;

    sp1.swap(sp2);
    std::cout << "*sp1 == " << *sp1 << std::endl;

    swap(sp1, sp2);
    std::cout << "*sp1 == " << *sp1 << std::endl;
    std::cout << std::endl;

    std::weak_ptr<int> wp1(sp1);
    std::weak_ptr<int> wp2(sp2);
    std::cout << "*wp1 == " << *wp1.lock() << std::endl;

    wp1.swap(wp2);
    std::cout << "*wp1 == " << *wp1.lock() << std::endl;

    swap(wp1, wp2);
    std::cout << "*wp1 == " << *wp1.lock() << std::endl;

    return (0);
}
```

```Output
*sp1 == 5
*sp1 == 10
*sp1 == 5

*wp1 == 5
*wp1 == 10
*wp1 == 5
```

## <a name="unique"></a>  shared_ptr::Unique

Sahip olunan kaynağın benzersiz olup olmadığını sınar.

```cpp
bool unique() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevinin döndürdüğü **true** başka hiçbir varsa `shared_ptr` nesnenin sahibi tarafından sahip olunan kaynağı `*this`, aksi takdirde **false**.

### <a name="example"></a>Örnek

```cpp
// std__memory__shared_ptr_unique.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

struct deleter
{
    void operator()(int *p)
    {
        delete p;
    }
};

int main()
{
    std::shared_ptr<int> sp1(new int(5));
    std::cout << "sp1.unique() == " << std::boolalpha
        << sp1.unique() << std::endl;

    std::shared_ptr<int> sp2(sp1);
    std::cout << "sp1.unique() == " << std::boolalpha
        << sp1.unique() << std::endl;

    return (0);
}
```

```Output
sp1.unique() == true
sp1.unique() == false
```

## <a name="use_count"></a>  shared_ptr::use_count

Kaynak sahiplerinin sayısını sayar.

```cpp
long use_count() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi döndürür `shared_ptr` tarafından sahip olunan bir kaynağa sahip nesneleri `*this`.

### <a name="example"></a>Örnek

```cpp
// std__memory__shared_ptr_use_count.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

int main()
{
    std::shared_ptr<int> sp1(new int(5));
    std::cout << "sp1.use_count() == "
        << sp1.use_count() << std::endl;

    std::shared_ptr<int> sp2(sp1);
    std::cout << "sp1.use_count() == "
        << sp1.use_count() << std::endl;

    return (0);
}
```

```Output
sp1.use_count() == 1
sp1.use_count() == 2
```

## <a name="see-also"></a>Ayrıca bkz.

[weak_ptr Sınıfı](../standard-library/weak-ptr-class.md)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
