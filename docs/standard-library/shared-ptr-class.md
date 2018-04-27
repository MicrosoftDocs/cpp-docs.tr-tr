---
title: shared_ptr sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
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
dev_langs:
- C++
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
caps.latest.revision: 28
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a6d00fe34a03c33faa92f481e7eece69e586eeea
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="sharedptr-class"></a>shared_ptr Sınıfı

Dinamik olarak tahsis edilen bir nesnenin çevresine bir başvuru sayılan akıllı işaretçi sarar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class T>
class shared_ptr;
```

## <a name="remarks"></a>Açıklamalar

Shared_ptr sınıfı başvuru kaynakları yönetmek için sayım kullanan bir nesneyi tanımlar. A `shared_ptr` nesnesi sahibi veya bir null işaretçinin tutan kaynak için etkili bir şekilde bir işaretçi tutar. Bir kaynak birden fazla tarafından ait olabilir `shared_ptr` nesne; zaman son `shared_ptr` belirli bir kaynak sahibi nesnesi yok, kaynak serbest bırakılır.

A `shared_ptr` yeniden atandığında veya sıfırlandığında kaynak sahibi olan durdurur.

Şablon bağımsız değişken `T` dışında tamamlanmamış bir türü belirli üye işlevleri belirtildiği gibi olabilir.

Zaman bir `shared_ptr<T>` nesne türü kaynak işaretçi oluşturulan `G*` veya bir `shared_ptr<G>`, işaretçi türü `G*` dönüştürülebilir olmalıdır `T*`. Değilse, kod derlenmez. Örneğin:

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

A `shared_ptr` nesneye sahip olan bir kaynak:

- Bu kaynak için bir işaretçi ile oluşturulan

- Bunu olacak oluşturulan varsa bir `shared_ptr` , kaynağın sahibi nesnesi

- Bunu olacak oluşturulan varsa bir [weak_ptr sınıfı](../standard-library/weak-ptr-class.md) bu kaynağa işaret nesnesi veya

- Bu kaynak sahipliğini ona biriyle atanmışsa [shared_ptr::operator =](#op_eq) veya üye işlevini çağırarak [shared_ptr::reset](#reset).

`shared_ptr` Bir kaynağa sahip nesneleri bir denetim bloğu paylaşır. Denetim bloğu tutar:

- sayısı `shared_ptr` kaynağa sahip nesneleri

- sayısı `weak_ptr` kaynak noktasına nesneleri

- Silici varsa, bu kaynak için

- varsa, denetim bloğu için özel ayırıcı.

A `shared_ptr` null işaretçi kullanarak başlatılır nesne denetim bloğu var ve boş değil. Sonra bir `shared_ptr` nesne serbest kaynak, artık bu kaynağına sahip. Sonra bir `weak_ptr` nesne serbest kaynak, artık bu kaynağa işaret eder.

Zaman sayısını `shared_ptr` nesneleri kendi kaynak sıfır olur, silmek veya kaynak sahipliğini başlangıçta nasıl oluşturulduğuna bağlı olarak bir Silici adresini geçirilmesi kaynak bırakıldığını. Zaman sayısını `shared_ptr` bir kaynağa sahip nesneleri, sıfır ve sayısı `weak_ptr` işaret kaynak sıfırsa, denetim bloğu varsa, özel ayırıcı denetim bloğu kullanarak serbest bırakılır nesneleri.

Boş bir `shared_ptr` nesne herhangi bir kaynağa sahip değil ve hiçbir denetim bloğu sahiptir.

Bir Silici üye işlevine sahip bir işlev nesnesidir `operator()`. Türü kopya oluşturulabilir olmalıdır ve kopya oluşturucu ve yıkıcı özel durumlar oluşturma gerekir değil. Bu, bir parametre, Silinecek nesnenin kabul eder.

Bazı işlevler elde edilen özelliklerini tanımlayan bir bağımsız değişken listesi ele `shared_ptr<T>` veya `weak_ptr<T>` nesnesi. Bu tür bir bağımsız değişken listesi çeşitli yollarla belirtebilirsiniz:

bağımsız değişkenler--elde edilen nesnenin boş olduğundan `shared_ptr` nesne ya da boş bir `weak_ptr` nesnesi.

`ptr` --bir işaretçi türü `Other*` yönetilecek kaynağa. `T` tam bir tür olması gerekir. (Denetim bloğu ayrılamıyor çünkü) işlevi başarısız olursa ifadeyi hesaplar `delete ptr`.

`ptr, dtor` --bir işaretçi türü `Other*` yönetilmek üzere kaynak ve bu kaynak için bir Silici. (Denetim bloğu ayrılamıyor çünkü) işlevi başarısız olursa, çağıran `dtor(ptr)`, hangi olmalıdır iyi tanımlanmış.

`ptr, dtor, alloc` --bir işaretçi türü `Other*` yönetilecek olan kaynak, bir Silici ayrılmış ve serbest gereken herhangi bir depolama alanı yönetmek için bir ayırıcı ve bu kaynak için. (Denetim bloğu ayrılamıyor çünkü) işlevi başarısız olursa çağırır `dtor(ptr)`, hangi olmalıdır iyi tanımlanmış.

`sp` --bir `shared_ptr<Other>` yönetilecek kaynağına sahip bir nesne.

`wp` --bir `weak_ptr<Other>` yönetilecek kaynağa işaret eden nesne.

`ap` --bir `auto_ptr<Other>` yönetilecek kaynak için bir işaretçi tutan nesne. İşlev çağrıları başarılı olursa `ap.release()`; Aksi halde bırakır `ap` değişmez.

Tüm durumlarda işaretçi türü `Other*` dönüştürülebilir olmalıdır `T*`.

## <a name="thread-safety"></a>İş Parçacığı Güvenliği

Birden çok iş parçacığı okuma ve farklı yazma `shared_ptr` nesnelerin sahipliği paylaşmak kopyaları olduğunda bile aynı anda nesneleri.

## <a name="members"></a>Üyeler

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[shared_ptr](#shared_ptr)|Oluşturan bir `shared_ptr`.|
|[shared_ptr:: ~ shared_ptr](#dtorshared_ptr)|Bozar bir `shared_ptr`.|

### <a name="types"></a>Türler

|Tür adı|Açıklama|
|-|-|
|[element_type](#element_type)|Öğenin türü.|

### <a name="functions"></a>İşlevler

|İşlev|Açıklama|
|-|-|
|[get](#get)|Ait kaynak adresi alır.|
|[owner_before](#owner_before)|Bu, true döndürür `shared_ptr` önce sıralanır (veya küçüktür) sağlanan işaretçi.|
|[Sıfırla](#reset)|Ait kaynak değiştirin.|
|[Değiştirme](#swap)|İki değiştirir `shared_ptr` nesneleri.|
|[Benzersiz](#unique)|Kaynak sahibi testleri benzersizdir.|
|[use_count](#use_count)|Kaynak sahiplerine sayısını sayar.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[shared_ptr::operator bool](#op_bool)|Testleri ait kaynak varsa.|
|[shared_ptr::operator *](#op_star)|Belirlenen değer alır.|
|[shared_ptr::operator=](#op_eq)|Ait kaynak yerini alır.|
|[shared_ptr::operator-&gt;](#op_arrow)|Bir işaretçi için belirlenen değer alır.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<bellek >

**Namespace:** std

## <a name="element_type"></a>  shared_ptr::ELEMENT_TYPE

Öğenin türü.

```cpp
typedef T element_type;
```

### <a name="remarks"></a>Açıklamalar

Şablon parametresi için bir eş anlamlı türüdür `T`.

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

Ait kaynak adresi alır.

```cpp
T *get() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevini ait kaynak adresini döndürür. Nesne bir kaynağın sahibi değil ise 0 döndürür.

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

Testleri ait kaynak varsa.

```cpp
explicit operator bool() const noexcept;
```

### <a name="remarks"></a>Açıklamalar

İşleç değerini döndürür `true` zaman `get() != nullptr`, aksi takdirde `false`.

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

Belirlenen değer alır.

```cpp
T& operator*() const;
```

### <a name="remarks"></a>Açıklamalar

İndirection işleci döndürür `*get()`. Bu nedenle, depolanan işaretçisi null olmamalıdır.

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

Ait kaynak yerini alır.

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

`sp` Kopyalamak için paylaşılan işaretçi.

`ap` Kopyalamak için otomatik işaretçi.

### <a name="remarks"></a>Açıklamalar

Şu anda sahibi kaynak için başvuru sayısı azaltma işleçleri tüm `*this` ve işlenen sırası tarafından adlı kaynağı sahipliğini Ata `*this`. Başvuru sayısı sıfıra düşerse, kaynak yayımlanır. İsteğe bağlı olarak bir işleç bırakır başarısız olursa `*this` değişmez.

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

Bir işaretçi için belirlenen değer alır.

```cpp
T * operator->() const;
```

### <a name="remarks"></a>Açıklamalar

Seçim operatörü döndürür `get()`, böylece ifade `sp->member` aynı şekilde davranır `(sp.get())->member` nerede `sp` sınıfın bir nesnesi olup `shared_ptr<T>`. Bu nedenle, depolanan işaretçisi null olmamalıdır ve `T` sınıf, yapı veya birleşim türü bir üyeyle olmalıdır `member`.

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

Bu, true döndürür `shared_ptr` önce sıralanır (veya küçüktür) sağlanan işaretçi.

```cpp
template <class Other>
bool owner_before(const shared_ptr<Other>& ptr);

template <class Other>
bool owner_before(const weak_ptr<Other>& ptr);
```

### <a name="parameters"></a>Parametreler

`ptr` Bir `lvalue` başvuru ya da bir `shared_ptr` veya `weak_ptr`.

### <a name="remarks"></a>Açıklamalar

Şablon üye işlevi varsa true değerini döndürür `*this` olan `ordered before` `ptr`.

## <a name="reset"></a>  shared_ptr::reset

Ait kaynak değiştirin.

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

`Other` Bağımsız değişken işaretçiyi tarafından denetlenen türü.

`D` Silici türü.

`ptr` Kopyalamak için işaretçi.

`dtor` Kopyalamak için Silici.

`A` Ayırıcı türü.

`alloc` Kopyalamak için ayırıcısı.

### <a name="remarks"></a>Açıklamalar

Şu anda sahibi kaynak için başvuru sayısı azaltma işleçleri tüm `*this` ve işlenen sırası tarafından adlı kaynağı sahipliğini Ata `*this`. Başvuru sayısı sıfıra düşerse, kaynak yayımlanır. İsteğe bağlı olarak bir işleç bırakır başarısız olursa `*this` değişmez.

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

Oluşturan bir `shared_ptr`.

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

`Other` Bağımsız değişken işaretçiyi tarafından denetlenen türü.

`ptr` Kopyalamak için işaretçi.

`D` Silici türü.

`A` Ayırıcı türü.

`dtor` Silici.

`ator` Ayırıcı.

`sp` Kopyalamak için akıllı işaretçi.

`wp` Zayıf işaretçi.

`ap` Kopyalamak için otomatik işaretçi.

### <a name="remarks"></a>Açıklamalar

Her oluşturucular tarafından işlenen dizisi adlı kaynağına sahip bir nesne oluşturur. Oluşturucusu `shared_ptr(const weak_ptr<Other>& wp)` türünde bir özel durum nesnesi oluşturur [bad_weak_ptr sınıfı](../standard-library/bad-weak-ptr-class.md) varsa `wp.expired()`.

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

Bozar bir `shared_ptr`.

```cpp
~shared_ptr();
```

### <a name="remarks"></a>Açıklamalar

Yok Edicisi azaltır sahibi şu anda kaynak için başvuru sayısı `*this`. Başvuru sayısı sıfıra düşerse, kaynak yayımlanır.

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

`sp` Paylaşılan işaretçisi ile değiştirilecek.

### <a name="remarks"></a>Açıklamalar

Üye fonksiyonu tarafından başlangıçta ait kaynak bırakır `*this` sonradan sahibi `sp`ve başlangıçta ait kaynak `sp` sonradan sahibi `*this`. İşlev iki kaynaklar için başvuru sayıları değiştirmez ve özel durumlar oluşturmadığını.

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

Kaynak sahibi testleri benzersizdir.

```cpp
bool unique() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi döndürür `true` Hayır başka `shared_ptr` nesnenin sahibi tarafından ait kaynak `*this`, aksi takdirde `false`.

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

Kaynak sahiplerine sayısını sayar.

```cpp
long use_count() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevini sayısını döndürür `shared_ptr` tarafından ait kaynak sahibi nesneleri `*this`.

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
