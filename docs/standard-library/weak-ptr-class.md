---
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
ms.openlocfilehash: d4ba30f737bc570a4ee700b3a317b5feebe8a50a
ms.sourcegitcommit: 725e86dabe2901175ecc63261c3bf05802dddff4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/31/2019
ms.locfileid: "68682417"
---
# <a name="weakptr-class"></a>weak_ptr Sınıfı

Zayıf bağlantılı bir işaretçi sarar.

## <a name="syntax"></a>Sözdizimi

```cpp
template<class T> class weak_ptr;
```

### <a name="parameters"></a>Parametreler

*ŞI*\
Zayıf işaretçi tarafından denetlenen tür.

## <a name="remarks"></a>Açıklamalar

Şablon sınıfı, bir veya daha fazla [shared_ptr](shared-ptr-class.md) nesnesi tarafından yönetilen bir kaynağı işaret eden bir nesneyi tanımlar. Bir kaynağa işaret eden nesnelerkaynağınbaşvurusayısınıetkilemez.`weak_ptr` Bu kaynağı yöneten `shared_ptr` son nesne yok edildiğinde, kaynağı işaret eden `weak_ptr` nesneler olsa bile kaynak serbest bırakılır. Bu davranış, veri yapılarında döngüleri önlemeye yönelik olarak gereklidir.

Bir `weak_ptr` nesne, kaynağı işaret eden bir nesneden oluşturulmuşsa, bu kaynağı `shared_ptr` işaret eden bir `weak_ptr` nesneden oluşturulduysa veya bu kaynağa [işleç =](#op_eq)ile atanmışsa bir kaynağı işaret eder. Bir `weak_ptr` nesne, işaret ettiği kaynağa doğrudan erişim sağlamaz. Kaynağı kullanması gereken kod, bu kaynağı, üye işlev `shared_ptr` [kilidi](#lock)çağırarak oluşturulan kaynağa sahip bir nesne aracılığıyla yapar. Kaynak `weak_ptr` sahibi olan tüm `shared_ptr` nesneler yok edildiğinden, bir nesnenin, gösterdiği kaynak serbest bırakıldığında süresi doldu. Süresi `lock` sona ermeyen bir `weak_ptr` nesneyi çağırmak boş bir shared_ptr nesnesi oluşturur.

Boş bir weak_ptr nesnesi herhangi bir kaynağa işaret etmez ve denetim bloğu içermez. Üye işlevi `lock` boş bir shared_ptr nesnesi döndürür.

Nesneler tarafından denetlenen iki veya daha fazla kaynak, karşılıklı `shared_ptr` olarak başvurulan `shared_ptr` nesneleri tutan zaman bir döngüden oluşur. Örneğin, üç öğesi olan bir döngüsel bağlantılı listede bir `N0`baş düğüm bulunur; bu düğüm bir sonraki düğüme `shared_ptr` `N1`sahip bir nesne barındırır; bu düğüm bir sonraki düğüme sahip `N2`bir `shared_ptr` nesne barındırır; bu düğüm, içindeki öğesini açın, baş `shared_ptr` `N0`düğümün sahibi olan bir nesneyi tutar, bu da döngüyü kapatıyor. Bu durumda, başvuru sayıları hiçbir şekilde sıfır olmaz ve döngüdeki düğümler hiçbir şekilde serbest bırakılmaz. Döngüyü ortadan kaldırmak için, `N2` son düğüm bir `shared_ptr` nesne `N0` yerine üzerine `weak_ptr` işaret eden bir nesneyi tutmalıdır. Nesne sahip `weak_ptr` `N0` olmadığı için başvuru sayısını etkilemez `N0`ve programın baş düğüme en son başvurusu yok edildiğinde, listedeki düğümler de yok edilir.

## <a name="members"></a>Üyeler

|||
|-|-|
| **Oluşturucular** | |
|[weak_ptr](#weak_ptr)|Bir `weak_ptr`oluşturur.|
| **Yıkıcılar** | |
|[~ weak_ptr](#tilde-weak_ptr)|Bir `weak_ptr`oluşturur.|
| **Tür tanımları** | |
|[element_type](#element_type)|Öğenin türü.|
| **Üye işlevleri** | |
|[aşıldığı](#expired)|Sahiplik süresi dolmuşsa sınar.|
|[lock](#lock)|Bir kaynağın özel sahipliğini edinir.|
|[owner_before](#owner_before)|Bu`weak_ptr` , belirtilen işaretçiden önce (veya ondan küçük) daha önce sipariş alıyorsa **true** değerini döndürür.|
|[döndürmek](#reset)|Sahip olunan kaynak.|
|[Kur](#swap)|İki `weak_ptr` nesneyi değiştirir.|
|[use_count](#use_count)|`shared_ptr` Nesne sayısını sayar.|
| **İşleçler** | |
|[operator=](#op_eq)|Sahip olunan kaynağı değiştirir.|

## <a name="element_type"></a>element_type

Öğenin türü.

```cpp
typedef T element_type; // through C++17
using element_type = remove_extent_t<T>; // C++20
```

### <a name="remarks"></a>Açıklamalar

Tür, şablon parametresi `T`için bir eş anlamlı.

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

## <a name="expired"></a>aşıldığı

Sahipliğin süresi dolmuşsa, yani başvurulan nesnenin silindiğini sınar.

```cpp
bool expired() const noexcept;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, süresi dolmuşsa true `*this` , değilse **false**döndürür.

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

## <a name="lock"></a>ine

Bir kaynağın `shared_ptr` sahipliğini paylaşan bir alır.

```cpp
shared_ptr<T> lock() const noexcept;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, süresi dolmuşsa boş bir [shared_ptr](shared-ptr-class.md) nesnesi `*this` döndürür; Aksi takdirde, işaret eden `shared_ptr<T>` `*this` kaynağa sahip bir nesne döndürür. Öğesinin `expired() ? shared_ptr<T>() : shared_ptr<T>(*this)`atomik yürütülmesine denk bir değer döndürür.

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

## <a name="op_eq"></a>işleç =

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

İşleçler, `*this` ' ın şu anda gösterdiği kaynağı serbest bırakın ve *PTR* tarafından adlandırılan kaynağın sahipliğini öğesine `*this`atar. Bir operatör başarısız olursa, `*this` değiştirilmez. Her işlecin öğesine `weak_ptr(ptr).swap(*this)`eşdeğer bir etkisi vardır.

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

## <a name="owner_before"></a>owner_before

Bu`weak_ptr` , belirtilen işaretçiden önce (veya ondan küçük) daha önce sipariş alıyorsa **true** değerini döndürür.

```cpp
template <class Other>
bool owner_before(const shared_ptr<Other>& ptr) const noexcept;

template <class Other>
bool owner_before(const weak_ptr<Other>& ptr) const noexcept;
```

### <a name="parameters"></a>Parametreler

*kaydetmeye*\
`shared_ptr` Bir`weak_ptr`veya öğesine lvalue başvurusu.

### <a name="remarks"></a>Açıklamalar

Şablon üye işlevi, *PTR*'den önce `*this` sıralandıysanız **true** değerini döndürür.

## <a name="reset"></a>döndürmek

Sahip olunan kaynağı serbest bırakır.

```cpp
void reset() noexcept;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi tarafından `*this` işaret edilen kaynağı serbest bırakır ve boş `weak_ptr` bir `*this` nesneye dönüştürür.

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

## <a name="swap"></a>Kur

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

Bir `swap`sonrasında, tarafından tarafından `*this` işaret edilen kaynak *WP*tarafından işaret edilir ve başlangıçta *WP* tarafından işaret edilen kaynak tarafından `*this`işaret edilir. İşlev, iki kaynağın başvuru sayısını değiştirmez ve hiçbir özel durum oluşturmaz. Şablon özelleşmenin etkisi, ' nin `a.swap(b)`eşdeğeridir.

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

## <a name="use_count"></a>use_count

Paylaşılan kaynağa sahip olan `shared_ptr` nesne sayısını sayar.

```cpp
long use_count() const noexcept;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi tarafından `*this`işaret edilen kaynağın sahip `shared_ptr` olduğu nesne sayısını döndürür.

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

## <a name="weak_ptr"></a>weak_ptr

Bir `weak_ptr`oluşturur.

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
Paylaşılan/zayıf işaretçi tarafından denetlenen tür. _Diğeri\*_  ile`element_type*`uyumlu olmadığı takdirde bu oluşturucular aşırı yükleme çözümüne katılmaz.

*WB*\
Kopyalanacak zayıf işaretçi.

*SP2*\
Kopyalanacak paylaşılan işaretçi.

### <a name="remarks"></a>Açıklamalar

Varsayılan Oluşturucu boş `weak_ptr` bir nesne oluşturur. Bağımsız değişken işaretçisi boş ise bağımsız değişken alan oluşturucuların her `weak_ptr` biri boş bir nesne oluşturur. Aksi takdirde, bağımsız değişken `weak_ptr` tarafından adlandırılan kaynağı işaret eden bir nesne oluşturur. Paylaşılan nesnenin başvuru sayısı değiştirilmez.

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

## <a name="tilde-weak_ptr"></a>~ weak_ptr

Yok eder `weak_ptr`.

```cpp
~weak_ptr();
```

### <a name="remarks"></a>Açıklamalar

Yok edicisi bunu `weak_ptr` yok eder, ancak nesnenin saklı işaretçi noktalarının başvuru sayısı üzerinde hiçbir etkisi yoktur.

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](cpp-standard-library-header-files.md)\
[\<bellek >](memory.md)\
[shared_ptr Sınıfı](shared-ptr-class.md)
