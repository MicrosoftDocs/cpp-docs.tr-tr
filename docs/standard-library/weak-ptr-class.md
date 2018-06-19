---
title: weak_ptr sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- memory/std::weak_ptr
- memory/std::weak_ptr::element_type
- memory/std::weak_ptr::expired
- memory/std::weak_ptr::lock
- memory/std::weak_ptr::owner_before
- memory/std::weak_ptr::reset
- memory/std::weak_ptr::swap
- memory/std::weak_ptr::use_count
- memory/std::weak_ptr::operator=
dev_langs:
- C++
helpviewer_keywords:
- std::weak_ptr [C++]
- std::weak_ptr [C++], element_type
- std::weak_ptr [C++], expired
- std::weak_ptr [C++], lock
- std::weak_ptr [C++], owner_before
- std::weak_ptr [C++], reset
- std::weak_ptr [C++], swap
- std::weak_ptr [C++], use_count
- std::weak_ptr [C++], element_type
- std::weak_ptr [C++], expired
- std::weak_ptr [C++], lock
- std::weak_ptr [C++], owner_before
- std::weak_ptr [C++], reset
- std::weak_ptr [C++], swap
- std::weak_ptr [C++], use_count
ms.assetid: 2db4afb2-c7be-46fc-9c20-34ec2f8cc7c2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 03cd10d3efac16521cf826f3d9081ec533b9abec
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33861785"
---
# <a name="weakptr-class"></a>weak_ptr Sınıfı

Zayıf bağlantılı bir işaretçi sarar.

## <a name="syntax"></a>Sözdizimi

```cpp
template<class _Ty>
   class weak_ptr {
public:
   typedef Ty element_type;
   weak_ptr();
   weak_ptr(const weak_ptr&);
   template <class Other>
      weak_ptr(const weak_ptr<Other>&);
   template <class Other>
      weak_ptr(const shared_ptr<Other>&);
   weak_ptr& operator=(const weak_ptr&);
   template <class Other>
      weak_ptr& operator=(const weak_ptr<Other>&);
   template <class Other>
      weak_ptr& operator=(shared_ptr<Other>&);
   void swap(weak_ptr&);
   void reset();
   long use_count() const;
   bool expired() const;
   shared_ptr<Ty> lock() const;
   };
```

### <a name="parameters"></a>Parametreler

`Ty` Zayıf işaretçiyi tarafından denetlenen türü.

## <a name="remarks"></a>Açıklamalar

Bir veya daha fazla yönetilen bir kaynağa işaret eden bir nesne şablonu sınıf tanımlar [shared_ptr sınıfı](../standard-library/shared-ptr-class.md) nesneleri. `weak_ptr` Bir kaynak noktasına nesneleri kaynağın başvuru sayısı etkilemez. Bu nedenle, son `shared_ptr` bu kaynağı yöneten nesnesi yok kaynak olsa bile serbest `weak_ptr` o kaynağa işaret eden nesneler. Bu, veri yapılarını Döngülerde kaçınmak için önemlidir.

A `weak_ptr` nesne bu olacak oluşturulan varsa bir kaynağa işaret eden bir `shared_ptr` onu olacak oluşturulan varsa, o kaynağına sahip nesne bir `weak_ptr` bu kaynağa işaret nesnesi ya da bu kaynak için ile atanmışsa [ operator =](#op_eq). A `weak_ptr` nesne işaret kaynak doğrudan erişim sağlamaz. Kaynak kullanması gereken kodu yapar böylece aracılığıyla bir `shared_ptr` üye işlevini çağırarak oluşturulan, kaynağın sahibi nesne [kilit](#lock). A `weak_ptr` nesne sona erdi işaret kaynak çünkü serbest bırakılmış olduğunda tüm `shared_ptr` kaynak sahibi nesneler yok. Çağırma `lock` üzerinde bir `weak_ptr` süresi doldu nesnesi boş shared_ptr nesnesi oluşturur.

Boş weak_ptr nesne için herhangi bir kaynağa işaret etmiyor ve hiçbir denetim bloğu sahiptir. Üye işlevini `lock` boş shared_ptr nesneyi döndürür.

İki veya daha fazla kaynak tarafından denetlenen bir döngü oluşur `shared_ptr` nesneleri tutun birbirini başvuran `shared_ptr` nesneleri. Örneğin, döngüsel bir bağlantılı listesi üç öğeye sahip bir baş düğüm içeriyor `N0`; bu düğüme tutan bir `shared_ptr` bir sonraki düğüme sahip nesnesine `N1`; bu düğüme tutan bir `shared_ptr` bir sonraki düğüme sahip nesne `N2`; bu düğüm, kapatma, ayrı tutma bir `shared_ptr` baş düğümüne sahip nesnesine `N0`, döngü kapatma. Bu durumda, başvuru sayıları hiçbiri hiç sıfır olur ve döngüsü düğümlerin serbest. Son düğümü döngüsü ortadan kaldırmak için `N2` tutun bir `weak_ptr` gösteren nesne `N0` yerine bir `shared_ptr` nesnesi. Bu yana `weak_ptr` nesne kendi değil `N0` bu etkilemez `N0`'s başvuru sayısı ve programın son başvuru baş düğümüne bozulduğunda düğümleri listesinde de yok edilir.

## <a name="members"></a>Üyeler

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[weak_ptr](#weak_ptr)|Oluşturan bir `weak_ptr`.|

### <a name="methods"></a>Yöntemler

|||
|-|-|
|[element_type](#element_type)|Öğe türü.|
|[Süresi dolmuş](#expired)|Testleri sahipliği sona erdi.|
|[lock](#lock)|Özel bir kaynak sahipliğini alır.|
|[owner_before](#owner_before)|Döndürür `true` bu `weak_ptr` önce sıralanır (veya küçüktür) sağlanan işaretçi.|
|[Sıfırla](#reset)|Sürümler kaynak sahibi.|
|[Değiştirme](#swap)|İki değiştirir `weak_ptr` nesneleri.|
|[use_count](#use_count)|Sayıları sayısı atanan `shared_ptr` nesneleri.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[operator=](#op_eq)|Değiştirir kaynak sahibi.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<bellek >

**Namespace:** std

## <a name="element_type"></a>  ELEMENT_TYPE

Öğe türü.

```cpp
typedef Ty element_type;
```

### <a name="remarks"></a>Açıklamalar

Şablon parametresi için bir eş anlamlı türüdür `Ty`.

### <a name="example"></a>Örnek

```cpp
// std__memory__weak_ptr_element_type.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

int main()
    {
    std::shared_ptr<int> sp0(new int(5));
    std::weak_ptr<int> wp0(sp0);
    std::weak_ptr<int>::element_type val = *wp0.lock();

    std::cout << "*wp0.lock() == " << val << std::endl;

    return (0);
    }

```

```Output
*wp0.lock() == 5
```

## <a name="expired"></a>  Süresi dolmuş

Testleri sahipliği sona erdi.

```cpp
bool expired() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi döndürür `true` varsa `*this` , aksi takdirde süresi doldu `false`.

### <a name="example"></a>Örnek

```cpp
// std__memory__weak_ptr_expired.cpp
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
    std::weak_ptr<int> wp;

    {
        std::shared_ptr<int> sp(new int(10));
        wp = sp;
        std::cout << "wp.expired() == " << std::boolalpha
            << wp.expired() << std::endl;
        std::cout << "*wp.lock() == " << *wp.lock() << std::endl;
    }

    // check expired after sp is destroyed
    std::cout << "wp.expired() == " << std::boolalpha
        << wp.expired() << std::endl;
    std::cout << "(bool)wp.lock() == " << std::boolalpha
        << (bool)wp.lock() << std::endl;

    return (0);
}

```

```Output
wp.expired() == false
*wp.lock() == 10
wp.expired() == true
(bool)wp.lock() == false
```

## <a name="lock"></a>  kilitleme

Özel bir kaynak sahipliğini alır.

```cpp
shared_ptr<Ty> lock() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi boş shared_ptr nesneyi döndürür `*this` süresi doldu; Aksi takdirde döndürür bir [shared_ptr sınıfı](../standard-library/shared-ptr-class.md)\<Ty > kaynağına sahip nesne `*this` işaret eder.

### <a name="example"></a>Örnek

```cpp
// std__memory__weak_ptr_lock.cpp
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
    std::weak_ptr<int> wp;

    {
        std::shared_ptr<int> sp(new int(10));
        wp = sp;
        std::cout << "wp.expired() == " << std::boolalpha
            << wp.expired() << std::endl;
        std::cout << "*wp.lock() == " << *wp.lock() << std::endl;
    }

    // check expired after sp is destroyed
    std::cout << "wp.expired() == " << std::boolalpha
        << wp.expired() << std::endl;
    std::cout << "(bool)wp.lock() == " << std::boolalpha
        << (bool)wp.lock() << std::endl;

    return (0);
}
```

```Output
wp.expired() == false
*wp.lock() == 10
wp.expired() == true
(bool)wp.lock() == false
```

## <a name="op_eq"></a>  işleç =

Değiştirir kaynak sahibi.

```cpp
weak_ptr& operator=(const weak_ptr& wp);

template <class Other>
weak_ptr& operator=(const weak_ptr<Other>& wp);

template <class Other>
weak_ptr& operator=(const shared_ptr<Other>& sp);
```

### <a name="parameters"></a>Parametreler

`Other` Bağımsız değişken paylaşılan zayıf işaretçiyi tarafından denetlenen türü.

`wp` Kopyalamak için zayıf işaretçi.

`sp` Kopyalamak için paylaşılan işaretçi.

### <a name="remarks"></a>Açıklamalar

Şu anda işaret kaynak tüm işleçleri yayın `*this` ve işlenen sırası tarafından adlı kaynağı sahipliğini Ata `*this`. İsteğe bağlı olarak bir işleç bırakır başarısız olursa `*this` değişmez.

### <a name="example"></a>Örnek

```cpp
// std__memory__weak_ptr_operator_as.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

int main()
{
    std::shared_ptr<int> sp0(new int(5));
    std::weak_ptr<int> wp0(sp0);
    std::cout << "*wp0.lock() == " << *wp0.lock() << std::endl;

    std::shared_ptr<int> sp1(new int(10));
    wp0 = sp1;
    std::cout << "*wp0.lock() == " << *wp0.lock() << std::endl;

    std::weak_ptr<int> wp1;
    wp1 = wp0;
    std::cout << "*wp1.lock() == " << *wp1.lock() << std::endl;

    return (0);
}
```

```Output
*wp0.lock() == 5
*wp0.lock() == 10
*wp1.lock() == 10
```

## <a name="owner_before"></a>  owner_before

Döndürür `true` bu `weak_ptr` önce sıralanır (veya küçüktür) sağlanan işaretçi.

```cpp
template <class Other>
bool owner_before(const shared_ptr<Other>& ptr);

template <class Other>
bool owner_before(const weak_ptr<Other>& ptr);
```

### <a name="parameters"></a>Parametreler

`ptr` Bir `lvalue` başvuru ya da bir `shared_ptr` veya `weak_ptr`.

### <a name="remarks"></a>Açıklamalar

Şablon üye işlevinin döndürdüğü `true` varsa `*this` olan `ordered before` `ptr`.

## <a name="reset"></a>  Sıfırla

Sürümler kaynak sahibi.

```cpp
void reset();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevini gösterdiği kaynak serbest `*this` ve dönüştürür `*this` boş weak_ptr nesneye.

### <a name="example"></a>Örnek

```cpp
// std__memory__weak_ptr_reset.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

int main()
{
    std::shared_ptr<int> sp(new int(5));
    std::weak_ptr<int> wp(sp);
    std::cout << "*wp.lock() == " << *wp.lock() << std::endl;
    std::cout << "wp.expired() == " << std::boolalpha
        << wp.expired() << std::endl;

    wp.reset();
    std::cout << "wp.expired() == " << std::boolalpha
        << wp.expired() << std::endl;

    return (0);
}

```

```Output
*wp.lock() == 5
wp.expired() == false
wp.expired() == true
```

## <a name="swap"></a>  Değiştirme

İki değiştirir `weak_ptr` nesneleri.

```cpp
void swap(weak_ptr& wp);
```

### <a name="parameters"></a>Parametreler

`wp` Zayıf işaretçisi ile değiştirilecek.

### <a name="remarks"></a>Açıklamalar

İlk olarak gösterdiği kaynak üye fonksiyonu bırakır `*this` sonradan gösterdiği `wp`ve başlangıçta gösterdiği kaynak `wp` sonradan gösterdiği `*this`. İşlev iki kaynaklar için başvuru sayıları değiştirmez ve özel durumlar oluşturmadığını.

### <a name="example"></a>Örnek

```cpp
// std__memory__weak_ptr_swap.cpp
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

## <a name="use_count"></a>  use_count

Sayıları sayısı atanan `shared_ptr` nesneleri.

```cpp
long use_count() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevini sayısını döndürür `shared_ptr` tarafından için kaynak sahibi nesneleri işaret `*this`.

### <a name="example"></a>Örnek

```cpp
// std__memory__weak_ptr_use_count.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

int main()
{
    std::shared_ptr<int> sp1(new int(5));
    std::weak_ptr<int> wp(sp1);
    std::cout << "wp.use_count() == "
        << wp.use_count() << std::endl;

    std::shared_ptr<int> sp2(sp1);
    std::cout << "wp.use_count() == "
        << wp.use_count() << std::endl;

    return (0);
}

```

```Output
wp.use_count() == 1
wp.use_count() == 2
```

## <a name="weak_ptr"></a>  weak_ptr

Oluşturan bir `weak_ptr`.

```cpp
weak_ptr();

weak_ptr(const weak_ptr& wp);

template <class Other>
weak_ptr(const weak_ptr<Other>& wp);

template <class Other>
weak_ptr(const shared_ptr<Other>& sp);
```

### <a name="parameters"></a>Parametreler

`Other` Bağımsız değişken paylaşılan zayıf işaretçiyi tarafından denetlenen türü.

`wp` Kopyalamak için zayıf işaretçi.

`sp` Kopyalamak için paylaşılan işaretçi.

### <a name="remarks"></a>Açıklamalar

Her oluşturucular tarafından işlenen dizisi adlı kaynağa işaret eden bir nesne oluşturur.

### <a name="example"></a>Örnek

```cpp
// std__memory__weak_ptr_construct.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

int main()
{
    std::weak_ptr<int> wp0;
    std::cout << "wp0.expired() == " << std::boolalpha
        << wp0.expired() << std::endl;

    std::shared_ptr<int> sp1(new int(5));
    std::weak_ptr<int> wp1(sp1);
    std::cout << "*wp1.lock() == "
        << *wp1.lock() << std::endl;

    std::weak_ptr<int> wp2(wp1);
    std::cout << "*wp2.lock() == "
        << *wp2.lock() << std::endl;

    return (0);
}

```

```Output
wp0.expired() == true
*wp1.lock() == 5
*wp2.lock() == 5
```

## <a name="see-also"></a>Ayrıca bkz.

[shared_ptr Sınıfı](../standard-library/shared-ptr-class.md)<br/>
