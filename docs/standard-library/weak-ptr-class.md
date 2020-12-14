---
description: 'Hakkında daha fazla bilgi edinin: weak_ptr sınıfı'
title: weak_ptr Sınıfı
ms.date: 07/29/2019
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
ms.openlocfilehash: a0434c57a70c40fc1fa1ae6b39837fd6112ba696
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97187812"
---
# <a name="weak_ptr-class"></a>weak_ptr Sınıfı

Zayıf bağlantılı bir işaretçi sarar.

## <a name="syntax"></a>Sözdizimi

```cpp
template<class T> class weak_ptr;
```

### <a name="parameters"></a>Parametreler

*Şı*\
Zayıf işaretçi tarafından denetlenen tür.

## <a name="remarks"></a>Açıklamalar

Sınıf şablonu, bir veya daha fazla [shared_ptr](shared-ptr-class.md) nesnesi tarafından yönetilen bir kaynağı işaret eden bir nesneyi tanımlar. `weak_ptr`Bir kaynağa işaret eden nesneler kaynağın başvuru sayısını etkilemez. Bu kaynağı yöneten son nesne yok edildiğinde, kaynağı `shared_ptr` işaret eden nesneler olsa bile kaynak serbest bırakılır `weak_ptr` . Bu davranış, veri yapılarında döngüleri önlemeye yönelik olarak gereklidir.

Bir nesne, kaynağı işaret eden bir nesneden oluşturulmuşsa, bu kaynağı `weak_ptr` `shared_ptr` işaret eden bir nesneden oluşturulduysa `weak_ptr` veya bu kaynağa [işleç =](#op_eq)ile atanmışsa bir kaynağı işaret eder. Bir `weak_ptr` nesne, işaret ettiği kaynağa doğrudan erişim sağlamaz. Kaynağı kullanması gereken kod `shared_ptr` , bu kaynağı, üye işlev [kilidi](#lock)çağırarak oluşturulan kaynağa sahip bir nesne aracılığıyla yapar. `weak_ptr`Kaynak sahibi olan tüm nesneler yok edildiğinden, bir nesnenin, gösterdiği kaynak serbest bırakıldığında süresi doldu `shared_ptr` . `lock` `weak_ptr` Süresi sona ermeyen bir nesneyi çağırmak boş bir shared_ptr nesnesi oluşturur.

Boş bir weak_ptr nesnesi herhangi bir kaynağa işaret etmez ve denetim bloğu yoktur. Üye işlevi `lock` boş bir shared_ptr nesnesi döndürüyor.

Nesneler tarafından denetlenen iki veya daha fazla kaynak, `shared_ptr` karşılıklı olarak başvurulan nesneleri tutan zaman bir döngüden oluşur `shared_ptr` . Örneğin, üç öğesi olan bir döngüsel bağlantılı listede bir baş düğüm bulunur; bu düğüm bir sonraki düğüme sahip bir nesne barındırır; bu düğüm bir sonraki düğüme sahip bir nesne barındırır; bu `N0` `shared_ptr` düğüm, `N1` `shared_ptr` `N2` sırasıyla `shared_ptr` baş düğüme sahip olan bir nesneyi tutar ve `N0` döngüyü kapatıyor. Bu durumda, başvuru sayıları hiçbir şekilde sıfır olmaz ve döngüdeki düğümler hiçbir şekilde serbest bırakılmaz. Döngüyü ortadan kaldırmak için, son düğüm `N2` `weak_ptr` bir nesne yerine üzerine işaret eden bir nesneyi tutmalıdır `N0` `shared_ptr` . `weak_ptr`Nesne sahip `N0` olmadığı için `N0` başvuru sayısını etkilemez ve programın baş düğüme en son başvurusu yok edildiğinde, listedeki düğümler de yok edilir.

## <a name="members"></a>Üyeler

|Ad|Açıklama|
|-|-|
| **Oluşturucular** | |
|[weak_ptr](#weak_ptr)|Bir oluşturur `weak_ptr` .|
| **Yıkıcılar** | |
|[~ weak_ptr](#tilde-weak_ptr)|Bir oluşturur `weak_ptr` .|
| **Tür tanımları** | |
|[element_type](#element_type)|Öğenin türü.|
| **Üye işlevleri** | |
|[aşıldığı](#expired)|Sahiplik süresi dolmuşsa sınar.|
|[ine](#lock)|Bir kaynağın özel sahipliğini edinir.|
|[owner_before](#owner_before)|**`true`** Bu, `weak_ptr` belirtilen işaretçiden önce (veya ondan küçük) sıralanmış ise döndürür.|
|[döndürmek](#reset)|Sahip olunan kaynak.|
|[Kur](#swap)|İki `weak_ptr` nesneyi değiştirir.|
|[use_count](#use_count)|Nesne sayısını sayar `shared_ptr` .|
| **İşleçler** | |
|[işleç =](#op_eq)|Sahip olunan kaynağı değiştirir.|

## <a name="element_type"></a><a name="element_type"></a> element_type

Öğenin türü.

```cpp
typedef T element_type; // through C++17
using element_type = remove_extent_t<T>; // C++20
```

### <a name="remarks"></a>Açıklamalar

Tür, şablon parametresi için bir eş anlamlı `T` .

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

## <a name="expired"></a><a name="expired"></a> aşıldığı

Sahipliğin süresi dolmuşsa, yani başvurulan nesnenin silindiğini sınar.

```cpp
bool expired() const noexcept;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, **`true`** **`*this`** süresi dolmuşsa döndürür, aksi takdirde **`false`** .

### <a name="example"></a>Örnek

```cpp
// std__memory__weak_ptr_expired.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

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

## <a name="lock"></a><a name="lock"></a> ine

Bir `shared_ptr` kaynağın sahipliğini paylaşan bir alır.

```cpp
shared_ptr<T> lock() const noexcept;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, süresi dolmuşsa boş bir [shared_ptr](shared-ptr-class.md) nesnesi döndürür **`*this`** ; Aksi takdirde `shared_ptr<T>` , işaret eden kaynağa sahip bir nesne döndürür **`*this`** . Öğesinin atomik yürütülmesine denk bir değer döndürür `expired() ? shared_ptr<T>() : shared_ptr<T>(*this)` .

### <a name="example"></a>Örnek

```cpp
// std__memory__weak_ptr_lock.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

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

## <a name="operator"></a><a name="op_eq"></a> işleç =

Sahip olunan kaynağı değiştirir.

```cpp
weak_ptr& operator=(const weak_ptr& ptr) noexcept;

template <class Other>
weak_ptr& operator=(const weak_ptr<Other>& ptr) noexcept;

template <class Other>
weak_ptr& operator=(const shared_ptr<Other>& ptr) noexcept;
```

### <a name="parameters"></a>Parametreler

*Farklı*\
Paylaşılan veya zayıf işaretçi tarafından denetlenen tür.

*kaydetmeye*\
Kopyalanacak zayıf işaretçi veya paylaşılan işaretçi.

### <a name="remarks"></a>Açıklamalar

İşleçler, ' ın şu anda gösterdiği kaynağı serbest bırakın **`*this`** ve *PTR* tarafından adlandırılan kaynağın sahipliğini öğesine atar **`*this`** . Bir operatör başarısız olursa, **`*this`** değiştirilmez. Her işlecin öğesine eşdeğer bir etkisi vardır `weak_ptr(ptr).swap(*this)` .

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

## <a name="owner_before"></a><a name="owner_before"></a> owner_before

**`true`** Bu, `weak_ptr` belirtilen işaretçiden önce (veya ondan küçük) sıralanmış ise döndürür.

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

Şablon üye işlevi, **`true`** **`*this`** *PTR*'den önce Sıralansa, döndürür.

## <a name="reset"></a><a name="reset"></a> döndürmek

Sahip olunan kaynağı serbest bırakır.

```cpp
void reset() noexcept;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi tarafından işaret edilen kaynağı serbest bırakır **`*this`** ve **`*this`** boş bir `weak_ptr` nesneye dönüştürür.

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

## <a name="swap"></a><a name="swap"></a> Kur

İki `weak_ptr` nesneyi değiştirir.

```cpp
void swap(weak_ptr& wp) noexcept;
```

Özelleştirmeyi de içerir:

```cpp
template<class T>
void swap(weak_ptr<T>& a, weak_ptr<T>& b) noexcept;
```

### <a name="parameters"></a>Parametreler

*WB*\
İle takas edilecek zayıf işaretçi.

### <a name="remarks"></a>Açıklamalar

Bir sonrasında `swap` , tarafından tarafından işaret edilen kaynak **`*this`** *WP* tarafından işaret edilir ve başlangıçta *WP* tarafından işaret edilen kaynak tarafından işaret edilir **`*this`** . İşlev, iki kaynağın başvuru sayısını değiştirmez ve hiçbir özel durum oluşturmaz. Şablon özelleşmenin etkisi, ' nin eşdeğeridir `a.swap(b)` .

### <a name="example"></a>Örnek

```cpp
// std__memory__weak_ptr_swap.cpp
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

## <a name="use_count"></a><a name="use_count"></a> use_count

`shared_ptr`Paylaşılan kaynağa sahip olan nesne sayısını sayar.

```cpp
long use_count() const noexcept;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi `shared_ptr` tarafından işaret edilen kaynağın sahip olduğu nesne sayısını döndürür **`*this`** .

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

## <a name="weak_ptr"></a><a name="weak_ptr"></a> weak_ptr

Bir oluşturur `weak_ptr` .

```cpp
constexpr weak_ptr() noexcept;

weak_ptr(const weak_ptr& wp) noexcept;

weak_ptr(weak_ptr&& wp) noexcept;

template <class Other>
weak_ptr(const weak_ptr<Other>& wp) noexcept;

template <class Other>
weak_ptr(weak_ptr<Other>&& sp) noexcept;

template <class Other>
weak_ptr(const shared_ptr<Other>& sp) noexcept;
```

### <a name="parameters"></a>Parametreler

*Farklı*\
Paylaşılan/zayıf işaretçi tarafından denetlenen tür. _Diğeri \*_ ile uyumlu olmadığı takdirde bu oluşturucular aşırı yükleme çözümüne katılmaz `element_type*` .

*WB*\
Kopyalanacak zayıf işaretçi.

*SP2*\
Kopyalanacak paylaşılan işaretçi.

### <a name="remarks"></a>Açıklamalar

Varsayılan Oluşturucu boş bir nesne oluşturur `weak_ptr` . Bağımsız değişken işaretçisi boş ise bağımsız değişken alan oluşturucuların her biri boş bir `weak_ptr` nesne oluşturur. Aksi takdirde, `weak_ptr` bağımsız değişken tarafından adlandırılan kaynağı işaret eden bir nesne oluşturur. Paylaşılan nesnenin başvuru sayısı değiştirilmez.

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

## <a name="weak_ptr"></a><a name="tilde-weak_ptr"></a> ~ weak_ptr

Yok eder `weak_ptr` .

```cpp
~weak_ptr();
```

### <a name="remarks"></a>Açıklamalar

Yok edicisi bunu yok eder, `weak_ptr` ancak nesnenin saklı işaretçi noktalarının başvuru sayısı üzerinde hiçbir etkisi yoktur.

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](cpp-standard-library-header-files.md)\
[\<memory>](memory.md)\
[shared_ptr sınıfı](shared-ptr-class.md)
