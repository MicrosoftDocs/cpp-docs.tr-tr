---
title: weak_ptr Sınıfı
ms.date: 11/04/2016
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
ms.openlocfilehash: e2efb5d534ad43e2492ac4fb0bf76db402dca272
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/10/2018
ms.locfileid: "51523269"
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

*Ty*<br/>
Zayıf işaretçiyle kontrol edilen tür.

## <a name="remarks"></a>Açıklamalar

Şablon sınıfı bir veya daha fazla yönetilen bir kaynağa işaret eden bir nesneyi tanımlayan [shared_ptr sınıfı](../standard-library/shared-ptr-class.md) nesneleri. `weak_ptr` Kaynağa işaret eden nesneler kaynağın başvuru sayısını etkilemez. Bu nedenle, son `shared_ptr` yönetir, kaynak nesnesi yok edildiğinde olsa bile kaynak boşaltılacak `weak_ptr` o kaynağa işaret eden nesneleri. Bu, veri yapılarını Döngülerde kaçınmak için gereklidir.

A `weak_ptr` nesne öğesinden oluşturulmuşsa bir kaynağa işaret eden bir `shared_ptr` öğesinden oluşturulmuşsa, o kaynağına sahip olan bir nesne bir `weak_ptr` konusu kaynağı işaret eden bir nesne veya bunu bu kaynağa atanmışsa [ İşleç =](#op_eq). A `weak_ptr` nesneyi işaret kaynağa doğrudan erişim sağlamaz. Kaynak kullanması gereken kod vermez böylece aracılığıyla bir `shared_ptr` üye işlevini çağırarak oluşturulan, bu kaynağa sahip nesne [kilit](#lock). A `weak_ptr` nesneyi işaret kaynak çünkü serbest bırakılmış olduğunda doldu tüm `shared_ptr` kaynağa sahip nesneler yok. Çağırma `lock` üzerinde bir `weak_ptr` doldu nesnesi boş shared_ptr nesneyi oluşturur.

Boş weak_ptr nesnenin herhangi bir kaynakta işaret etmiyor ve denetim bloğu yoktur. Onun üye işlevini `lock` boş shared_ptr nesneyi döndürür.

İki veya daha fazla kaynak tarafından denetlenen bir döngü gerçekleşir `shared_ptr` nesneleri depolamak birbirini başvuran `shared_ptr` nesneleri. Örneğin, üç öğelerle döngüsel bir bağlantılı liste bir baş düğüm vardır `N0`; düğüm tutan bir `shared_ptr` sonraki bir düğümün sahip olduğu nesne `N1`; düğüm tutan bir `shared_ptr` sonraki bir düğümün sahip olduğu nesne `N2`; düğüm, kapatma, ayrı tutma bir `shared_ptr` , baş düğümün sahip olduğu nesne `N0`, kapatma döngüsü. Bu durumda, başvuru sayılarını hiçbiri hiç olmadığı kadar sıfır olur ve düğümleri döngüsünde açılmayacaktır. Döngü, son düğümünü kaldırmak için `N2` tutmak zorunda bir `weak_ptr` işaret eden bir nesne `N0` yerine bir `shared_ptr` nesne. Bu yana `weak_ptr` nesnenin sahibi olmadığı `N0` bu etkilemez `N0`ait başvuru sayısı ve baş düğüme programın son başvuru kaldırıldığında listedeki düğümleri de edileceği.

## <a name="members"></a>Üyeler

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[weak_ptr](#weak_ptr)|Oluşturur bir `weak_ptr`.|

### <a name="methods"></a>Yöntemler

|||
|-|-|
|[element_type](#element_type)|Öğe türü.|
|[Süresi doldu](#expired)|Test sahipliği süresi doldu.|
|[lock](#lock)|Özel bir kaynağın sahipliğini alır.|
|[owner_before](#owner_before)|Döndürür **true** bu `weak_ptr` önceyse (veya küçüktür) sağlanan işaretçi.|
|[Sıfırlama](#reset)|Yayınları kaynak sahibi.|
|[değiştirme](#swap)|İki değiştirir `weak_ptr` nesneleri.|
|[use_count](#use_count)|Sayıları sayısı belirtilen `shared_ptr` nesneleri.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[operator=](#op_eq)|Sahip olunan kaynağın yerini alır.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<bellek >

**Namespace:** std

## <a name="element_type"></a>  ELEMENT_TYPE

Öğe türü.

```cpp
typedef Ty element_type;
```

### <a name="remarks"></a>Açıklamalar

Şablon parametresi için bir eşanlamlı türüdür `Ty`.

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

## <a name="expired"></a>  Süresi doldu

Test sahipliği süresi doldu.

```cpp
bool expired() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevinin döndürdüğü **true** varsa `*this` , aksi takdirde doldu **false**.

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

## <a name="lock"></a>  Kilit

Özel bir kaynağın sahipliğini alır.

```cpp
shared_ptr<Ty> lock() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi boş shared_ptr nesneyi döndürür `*this` sona erdi; Aksi halde döndürür bir [shared_ptr sınıfı](../standard-library/shared-ptr-class.md)\<Ty > kaynağa sahip olan nesne `*this` işaret eder.

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

Sahip olunan kaynağın yerini alır.

```cpp
weak_ptr& operator=(const weak_ptr& wp);

template <class Other>
weak_ptr& operator=(const weak_ptr<Other>& wp);

template <class Other>
weak_ptr& operator=(const shared_ptr<Other>& sp);
```

### <a name="parameters"></a>Parametreler

*Diğer*<br/>
Bağımsız değişken paylaşılan zayıf işaretçiyle kontrol edilen tür.

*WP*<br/>
Kopyalamak için zayıf işaretçi.

*SP*<br/>
Kopyalamak için paylaşılan işaretçi.

### <a name="remarks"></a>Açıklamalar

Kaynak şu anda işaret ettiği tüm işleçleri yayın `*this` ve işlenen dizinin tarafından adlı kaynağın sahipliğini Ata `*this`. İsteğe bağlı olarak bir işleç leaves başarısız olursa `*this` değişmez.

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

Döndürür **true** bu `weak_ptr` önceyse (veya küçüktür) sağlanan işaretçi.

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

Şablon üye işlevinin döndürdüğü **true** varsa `*this` olduğu `ordered before` `ptr`.

## <a name="reset"></a>  Sıfırlama

Yayınları kaynak sahibi.

```cpp
void reset();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi tarafından işaret kaynak sürümleri `*this` ve dönüştüren `*this` boş weak_ptr nesneye.

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

## <a name="swap"></a>  değiştirme

İki değiştirir `weak_ptr` nesneleri.

```cpp
void swap(weak_ptr& wp);
```

### <a name="parameters"></a>Parametreler

*WP*<br/>
İle takas için zayıf işaretçi.

### <a name="remarks"></a>Açıklamalar

İlk olarak işaret ettiği kaynak üye işlevi bırakır `*this` sonradan işaret ettiği *wp*ve ilk olarak işaret ettiği kaynak *wp* sonradan tarafındanişaretedilen`*this`. İşlev iki kaynaklar için başvuru sayılarını değiştirmez ve özel durumlar oluşturmaz.

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

Sayıları sayısı belirtilen `shared_ptr` nesneleri.

```cpp
long use_count() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi döndürür `shared_ptr` kaynağa sahip nesneler tarafından işaret edilen `*this`.

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

Oluşturur bir `weak_ptr`.

```cpp
weak_ptr();

weak_ptr(const weak_ptr& wp);

template <class Other>
weak_ptr(const weak_ptr<Other>& wp);

template <class Other>
weak_ptr(const shared_ptr<Other>& sp);
```

### <a name="parameters"></a>Parametreler

*Diğer*<br/>
Bağımsız değişken paylaşılan zayıf işaretçiyle kontrol edilen tür.

*WP*<br/>
Kopyalamak için zayıf işaretçi.

*SP*<br/>
Kopyalamak için paylaşılan işaretçi.

### <a name="remarks"></a>Açıklamalar

Her oluşturucular tarafından işlenen dizisi adlı kaynağı işaret eden bir nesne oluşturur.

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
