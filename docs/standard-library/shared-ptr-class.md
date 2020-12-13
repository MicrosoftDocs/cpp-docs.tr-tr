---
description: 'Hakkında daha fazla bilgi edinin: shared_ptr Sınıfı'
title: shared_ptr sınıfı
ms.date: 07/29/2019
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
ms.openlocfilehash: 973bda9cb769eff339a02cbc43838e8c94516408
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97154051"
---
# <a name="shared_ptr-class"></a>shared_ptr sınıfı

Dinamik olarak tahsis edilen bir nesnenin çevresine bir başvuru sayılan akıllı işaretçi sarar.

## <a name="syntax"></a>Syntax

```cpp
template <class T>
class shared_ptr;
```

## <a name="remarks"></a>Açıklamalar

`shared_ptr`Sınıfı, kaynakları yönetmek için başvuru sayımı kullanan bir nesneyi tanımlar. Bir `shared_ptr` nesne, sahip olduğu veya null bir işaretçi tutan kaynak işaretçisini etkin bir şekilde tutar. Bir kaynak birden fazla nesneye ait olabilir `shared_ptr` ; `shared_ptr` belirli bir kaynağa sahip olan son nesne yok edildiğinde, kaynak serbest bırakılır.

`shared_ptr`Yeniden atandığında veya sıfırlandığında bir kaynağın sahip olduğu bir yanıt vermez.

Şablon bağımsız değişkeni, `T` belirli üye işlevleri için belirtilmedikçe, tamamlanmamış bir tür olabilir.

Bir `shared_ptr<T>` nesne türü veya bir kaynak işaretçisinden oluşturulduğunda `G*` `shared_ptr<G>` , işaretçi türü `G*` öğesine dönüştürülebilir olmalıdır `T*` . Dönüştürülemeyen kod derlenmez. Örneğin:

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

Bir `shared_ptr` nesne bir kaynağa sahip:

- Bu kaynak için bir işaretçi ile oluşturulduysa,

- Bu `shared_ptr` kaynağın sahibi olan bir nesneden oluşturulmuşsa,

- Bu kaynağı işaret eden bir [weak_ptr](weak-ptr-class.md) nesnesinden oluşturulmuşsa veya

- Bu kaynağın sahipliği kendisine atanmışsa, [shared_ptr:: operator =](#op_eq) ile ya da [shared_ptr:: Reset](#reset)üye işlevini çağırarak.

`shared_ptr`Bir kaynağın sahibi olan nesneler bir denetim bloğunu paylaşır. Denetim bloğu şunları barındırır:

- `shared_ptr`kaynağa sahip olan nesne sayısı,

- `weak_ptr`kaynağı işaret eden nesne sayısı,

- varsa, bu kaynak için silici

- Denetim bloğunun varsa özel ayırıcısı.

`shared_ptr`Null işaretçi kullanılarak başlatılan bir nesne denetim bloğuna sahip ve boş değil. Bir `shared_ptr` nesne bir kaynağı yayınladıktan sonra, o kaynağa artık sahip olmaz. Bir `weak_ptr` nesne bir kaynağı yayınladıktan sonra, o kaynağa artık işaret alınmaz.

`shared_ptr`Bir kaynağa sahip olan nesne sayısı sıfır olduğunda, kaynak onu silerek ya da kaynağın sahipliğinin ilk olarak oluşturulma şekline bağlı olarak bir silice geçirerek kaynak serbest bırakılır. `shared_ptr`Bir kaynağa sahip olan nesne sayısı sıfır olduğunda ve bu kaynağı işaret eden nesne sayısı sıfır olduğunda, denetim bloğu, varsa `weak_ptr` denetim bloğu için özel ayırıcı kullanılarak serbest bırakılır.

Boş bir `shared_ptr` nesne herhangi bir kaynağa sahip değildir ve denetim bloğuna sahip değildir.

Bir silici, üye işlevine sahip bir işlev nesnesidir `operator()` . Türünün kopya oluşturulabilir olması gerekir ve kopya Oluşturucusu ve yıkıcısı özel durum oluşturmamalıdır. Bir parametreyi kabul eder, silinecek nesne.

Bazı işlevler, sonuçta elde edilen veya nesnesinin özelliklerini tanımlayan bir bağımsız değişken listesi alır `shared_ptr<T>` `weak_ptr<T>` . Böyle bir bağımsız değişken listesini birkaç şekilde belirtebilirsiniz:

bağımsız değişken yok--elde edilen nesne boş bir `shared_ptr` nesne veya boş bir nesne `weak_ptr` .

`ptr` --yönetilecek kaynağa bir tür işaretçisi `Other*` . `T` tamamen bir tür olmalıdır. İşlev başarısız olursa (denetim bloğu ayrılamadığından), ifadeyi değerlendirir `delete ptr` .

`ptr, deleter` --yönetilecek kaynağa bir tür işaretçisi `Other*` ve bu kaynak için bir silici. İşlev başarısız olursa (denetim bloğu ayrılamadığından), `deleter(ptr)` iyi tanımlanmış olması gereken, çağırır.

`ptr, deleter, alloc` --yönetilecek kaynağa bir tür işaretçisi `Other*` , bu kaynak için bir silici ve ayrılması ve serbest olması gereken herhangi bir depolamayı yönetmek için bir ayırıcı. İşlev başarısız olursa (denetim bloğu ayrılamadığından), `deleter(ptr)` iyi tanımlanmış olması gereken, çağırır.

`sp` -- `shared_ptr<Other>` Yönetilecek kaynağın sahibi olan bir nesne.

`wp` -- `weak_ptr<Other>` Yönetilecek kaynağı işaret eden bir nesnesi.

`ap` -- `auto_ptr<Other>` Yönetilecek kaynak için bir işaretçi tutan nesne. İşlev başarılı olursa, çağırır `ap.release()` ; Aksi takdirde, `ap` değiştirilmez.

Her durumda, işaretçi türü `Other*` öğesine dönüştürülebilir olmalıdır `T*` .

## <a name="thread-safety"></a>İş Parçacığı Güvenliği

Birden çok iş parçacığı, aynı anda farklı nesneleri okuyabilir ve yazabilir `shared_ptr` , ancak nesneler paylaşımın sahipliğini paylaşan kopyalardır.

## <a name="members"></a>Üyeler

|Ad|Açıklama|
|-|-|
| **Oluşturucular** | |
|[shared_ptr](#shared_ptr)|Bir oluşturur `shared_ptr` .|
|[~ shared_ptr](#dtorshared_ptr)|Yok eder `shared_ptr` .|
| **Tür tanımları** | |
|[element_type](#element_type)|Öğenin türü.|
|[weak_type](#weak_type)|Bir öğeye zayıf işaretçinin türü.|
| **Üye işlevleri** | |
|[get](#get)|Sahip olunan kaynağın adresini alır.|
|[owner_before](#owner_before)|Bu, `shared_ptr` belirtilen işaretçiden önce (veya ondan küçük) daha önce sipariş alıyorsa true değerini döndürür.|
|[döndürmek](#reset)|Sahip olunan kaynağı değiştirin.|
|[Kur](#swap)|İki `shared_ptr` nesneyi değiştirir.|
|[eşi](#unique)|Sahip olunan kaynak benzersiz ise sınar.|
|[use_count](#use_count)|Kaynak sahiplerinin numaralarını sayar.|
| **İşleçler** | |
|[işleç bool](#op_bool)|Sahip olunan bir kaynağın mevcut olup olmadığını sınar.|
|[işlecinde](#op_star)|Belirlenen değeri alır.|
|[işleç =](#op_eq)|Sahip olunan kaynağı değiştirir.|
|[işlecinde&gt;](#op_arrow)|Belirlenen değere bir işaretçi alır.|

## <a name="element_type"></a><a name="element_type"></a> element_type

Öğenin türü.

```cpp
typedef T element_type;                  // before C++17
using element_type = remove_extent_t<T>; // C++17
```

### <a name="remarks"></a>Açıklamalar

`element_type`Tür, şablon parametresi için bir eş anlamlı `T` .

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

## <a name="get"></a><a name="get"></a> Al

Sahip olunan kaynağın adresini alır.

```cpp
element_type* get() const noexcept;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, sahip olunan kaynağın adresini döndürür. Nesne bir kaynak içermiyorsa, 0 döndürür.

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

## <a name="operator-bool"></a><a name="op_bool"></a> işleç bool

Sahip olunan bir kaynağın mevcut olup olmadığını sınar.

```cpp
explicit operator bool() const noexcept;
```

### <a name="remarks"></a>Açıklamalar

İşleci ne zaman bir değeri döndürür **`true`** `get() != nullptr` , aksi takdirde **`false`** .

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

## <a name="operator"></a><a name="op_star"></a> işlecinde

Belirlenen değeri alır.

```cpp
T& operator*() const noexcept;
```

### <a name="remarks"></a>Açıklamalar

Yöneltme işleci döndürülür `*get()` . Bu nedenle, saklı işaretçi null olmamalıdır.

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

## <a name="operator"></a><a name="op_eq"></a> işleç =

Sahip olunan kaynağı değiştirir.

```cpp
shared_ptr& operator=(const shared_ptr& sp) noexcept;

shared_ptr& operator=(shared_ptr&& sp) noexcept;

template <class Other>
shared_ptr& operator=(const shared_ptr<Other>& sp) noexcept;

template <class Other>
shared_ptr& operator=(shared_ptr<Other>&& sp) noexcept;

template <class Other>
shared_ptr& operator=(auto_ptr<Other>&& ap);    // deprecated in C++11, removed in C++17

template <class Other, class Deleter>
shared_ptr& operator=(unique_ptr<Other, Deleter>&& up);
```

### <a name="parameters"></a>Parametreler

*SP2*\
Kopyalanacak veya taşınacak paylaşılan işaretçi.

*sıfırlan*\
Taşınacak otomatik işaretçi. `auto_ptr`Aşırı yükleme, c++ 11 ' de kullanımdan kaldırılmıştır ve c++ 17 ' de kaldırılır.

*ayarlama*\
Sahipliğini benimsemek için nesnenin benzersiz işaretçisi. çağrıdan sonra hiç *nesne sahibi yok* .

*Farklı*\
*SP*, *AP* veya *up* tarafından işaret edilen nesnenin türü.

*Silici*\
Nesnenin daha sonra silinmesi için depolanan, sahip olunan nesnenin silici türü.

### <a name="remarks"></a>Açıklamalar

İşleçler, tarafından sahip olunan kaynak için başvuru sayısını azaltır **`*this`** ve işlenen dizi tarafından adlandırılan kaynağın sahipliğini atar **`*this`** . Başvuru sayısı sıfıra düşerse, kaynak serbest bırakılır. Bir operatör başarısız olursa, **`*this`** değiştirilmez.

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
    std::unique_ptr<int> up(new int(10));

    sp0 = sp1;
    std::cout << "*sp0 == " << *sp0 << std::endl;

    sp0 = up;
    std::cout << "*sp0 == " << *sp0 << std::endl;

    return (0);
}
```

```Output
*sp0 == 5
*sp0 == 10
```

## <a name="operator-"></a><a name="op_arrow"></a> operator->

Belirlenen değere bir işaretçi alır.

```cpp
T* operator->() const noexcept;
```

### <a name="remarks"></a>Açıklamalar

Seçim işleci döndürülür `get()` , böylece ifade `sp->member` `(sp.get())->member` `sp` sınıfının bir nesnesi olduğu ile aynı şekilde davranır `shared_ptr<T>` . Bu nedenle, saklı işaretçi null olmamalı ve `T` üye içeren bir sınıf, yapı veya birleşim türü olmalıdır `member` .

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

## <a name="owner_before"></a><a name="owner_before"></a> owner_before

Bu, `shared_ptr` belirtilen işaretçiden önce (veya ondan küçük) daha önce sipariş alıyorsa true değerini döndürür.

```cpp
template <class Other>
bool owner_before(const shared_ptr<Other>& ptr) const noexcept;

template <class Other>
bool owner_before(const weak_ptr<Other>& ptr) const noexcept;
```

### <a name="parameters"></a>Parametreler

*kaydetmeye*\
Bir veya öğesine lvalue başvurusu `shared_ptr` `weak_ptr` .

### <a name="remarks"></a>Açıklamalar

Şablon üye işlevi, daha **`*this`** önce sıralandıysanız true değerini döndürür `ptr` .

## <a name="reset"></a><a name="reset"></a> döndürmek

Sahip olunan kaynağı değiştirin.

```cpp
void reset() noexcept;

template <class Other>
void reset(Other *ptr);

template <class Other, class Deleter>
void reset(
    Other *ptr,
    Deleter deleter);

template <class Other, class Deleter, class Allocator>
void reset(
    Other *ptr,
    Deleter deleter,
    Allocator alloc);
```

### <a name="parameters"></a>Parametreler

*Farklı*\
Bağımsız değişken işaretçisi tarafından denetlenen tür.

*Silici*\
Deleter türü.

*kaydetmeye*\
Kopyalanacak işaretçi.

*silici*\
Kopyalanacak silici.

*Öğe*\
Ayırıcı türü.

*tahsis*\
Kopyalanacak ayırıcı.

### <a name="remarks"></a>Açıklamalar

İşleçler, tarafından sahip olunan kaynak için başvuru sayısını azaltır **`*this`** ve işlenen dizi tarafından adlandırılan kaynağın sahipliğini atar **`*this`** . Başvuru sayısı sıfıra düşerse, kaynak serbest bırakılır. Bir operatör başarısız olursa, **`*this`** değiştirilmez.

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

## <a name="shared_ptr"></a><a name="shared_ptr"></a> shared_ptr

Bir oluşturur `shared_ptr` .

```cpp
constexpr shared_ptr() noexcept;

constexpr shared_ptr(nullptr_t) noexcept : shared_ptr() {}

shared_ptr(const shared_ptr& sp) noexcept;

shared_ptr(shared_ptr&& sp) noexcept;

template <class Other>
explicit shared_ptr(Other* ptr);

template <class Other, class Deleter>
shared_ptr(
    Other* ptr,
    Deleter deleter);

template <class Deleter>
shared_ptr(
    nullptr_t ptr,
    Deleter deleter);

template <class Other, class Deleter, class Allocator>
shared_ptr(
    Other* ptr,
    Deleter deleter,
    Allocator alloc);

template <class Deleter, class Allocator>
shared_ptr(
    nullptr_t ptr,
    Deleter deleter,
    Allocator alloc);

template <class Other>
shared_ptr(
    const shared_ptr<Other>& sp) noexcept;

template <class Other>
explicit shared_ptr(
    const weak_ptr<Other>& wp);

template <class &>
shared_ptr(
    std::auto_ptr<Other>& ap);

template <class &>
shared_ptr(
    std::auto_ptr<Other>&& ap);

template <class Other, class Deleter>
shared_ptr(
    unique_ptr<Other, Deleter>&& up);

template <class Other>
shared_ptr(
    const shared_ptr<Other>& sp,
    element_type* ptr) noexcept;

template <class Other>
shared_ptr(
    shared_ptr<Other>&& sp,
    element_type* ptr) noexcept;

template <class Other, class Deleter>
shared_ptr(
    const unique_ptr<Other, Deleter>& up) = delete;
```

### <a name="parameters"></a>Parametreler

*Farklı*\
Bağımsız değişken işaretçisi tarafından denetlenen tür.

*kaydetmeye*\
Kopyalanacak işaretçi.

*Silici*\
Deleter türü.

*Öğe*\
Ayırıcı türü.

*silici*\
Silici.

*tahsis*\
Ayırıcı.

*SP2*\
Kopyalanacak akıllı işaretçi.

*WB*\
Zayıf işaretçi.

*sıfırlan*\
Kopyalamanın otomatik işaretçisi.

### <a name="remarks"></a>Açıklamalar

Oluşturucular her biri, işlenen sırası tarafından adlandırılan kaynağa sahip bir nesne oluşturur. Oluşturucu, `shared_ptr(const weak_ptr<Other>& wp)` [bad_weak_ptr](bad-weak-ptr-class.md) If türünde bir özel durum nesnesi oluşturur `wp.expired()` .

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

## <a name="shared_ptr"></a><a name="dtorshared_ptr"></a> ~ shared_ptr

Yok eder `shared_ptr` .

```cpp
~shared_ptr();
```

### <a name="remarks"></a>Açıklamalar

Yıkıcı, tarafından sahip olunan kaynağın başvuru sayısını azaltır **`*this`** . Başvuru sayısı sıfıra düşerse, kaynak serbest bırakılır.

### <a name="example"></a>Örnek

```cpp
// std__memory__shared_ptr_destroy.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

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

## <a name="swap"></a><a name="swap"></a> Kur

İki `shared_ptr` nesneyi değiştirir.

```cpp
void swap(shared_ptr& sp) noexcept;
```

### <a name="parameters"></a>Parametreler

*SP2*\
İle takas edilecek paylaşılan işaretçi.

### <a name="remarks"></a>Açıklamalar

Üye işlevi, bundan sonra SP tarafından sahip olunan kaynağı **`*this`** ve bundan sonra *SP* tarafından sahip olunan kaynak olan kaynağı bırakır **`*this`** . İşlev, iki kaynağın başvuru sayısını değiştirmez ve hiçbir özel durum oluşturmaz.

### <a name="example"></a>Örnek

```cpp
// std__memory__shared_ptr_swap.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

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

## <a name="unique"></a><a name="unique"></a> eşi

Sahip olunan kaynak benzersiz ise sınar. Bu işlev C++ 17 ' de kullanımdan kaldırılmıştır ve C++ 20 ' de kaldırılmıştır.

```cpp
bool unique() const noexcept;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, **`true`** `shared_ptr` sahip olduğu kaynağa sahip başka hiçbir nesne yoksa **`*this`** , tersi durumda döndürür **`false`** .

### <a name="example"></a>Örnek

```cpp
// std__memory__shared_ptr_unique.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

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

## <a name="use_count"></a><a name="use_count"></a> use_count

Kaynak sahiplerinin numaralarını sayar.

```cpp
long use_count() const noexcept;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, sahip olduğu kaynağa sahip `shared_ptr` olan nesne sayısını döndürür **`*this`** .

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

## <a name="weak_type"></a><a name="weak_type"></a> weak_type

Bir öğeye zayıf işaretçinin türü.

```cpp
using weak_type = weak_ptr<T>; // C++17
```

### <a name="remarks"></a>Açıklamalar

`weak_type`Tanım c++ 17 ' ye eklenmiştir.

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](cpp-standard-library-header-files.md)\
[\<memory>](memory.md)\
[unique_ptr](unique-ptr-class.md)\
[weak_ptr sınıfı](weak-ptr-class.md)
