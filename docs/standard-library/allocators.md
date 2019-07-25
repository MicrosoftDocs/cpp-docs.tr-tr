---
title: Ayırıcılar
ms.date: 11/04/2016
helpviewer_keywords:
- allocators
- C++ Standard Library, allocators
ms.assetid: ac95023b-9e7d-49f5-861a-bf7a9a340746
ms.openlocfilehash: cb1b0e0d1466d4af5ba255bdf3d00b11cd921fd6
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68457542"
---
# <a name="allocators"></a>Ayırıcılar

Ayrıcılar, kapsayıcılarda depolanan C++ öğelerin ayrılmasını ve ayırmayı işlemek Için standart kitaplık tarafından kullanılır. STD C++ :: Array hariç tüm standart kitaplık kapsayıcıları türünde `allocator<Type>`bir şablon parametresine sahiptir; burada `Type` kapsayıcı öğesinin türü temsil eder. Örneğin, vektör sınıfı şu şekilde bildirilmiştir:

```cpp
template <
    class Type,
    class Allocator = allocator<Type>
>
class vector
```

Standart C++ kitaplık, ayırıcı için varsayılan bir uygulama sağlar. C++ 11 ve sonrasında varsayılan ayırıcı, daha küçük bir arabirim sunmak üzere güncelleştirilir; Yeni ayırıcı *en az ayırıcı*olarak adlandırılır. Özellikle, en küçük ayırıcı `construct()` üyesi, performansı önemli ölçüde iyileştirebilecek taşıma semantiğini destekler. Çoğu durumda, bu varsayılan ayırıcı yeterli olmalıdır. C++ 11 ' de, `std::function` `shared_ptr, allocate_shared()`bir ayırıcı türü parametresi alan standart kitaplık türleri ve işlevleri,, ve `basic_string`dahil olmak üzere minimum ayırıcı arabirimini destekler.  Varsayılan ayırıcı hakkında daha fazla bilgi için bkz. [ayırıcı sınıfı](../standard-library/allocator-class.md).

## <a name="writing-your-own-allocator-c11"></a>Kendi ayırıcıyı yazma (C++ 11)

Varsayılan ayırıcı, belleği ayırmak ve serbest bırakmak için **New** ve **Delete** kullanır. Paylaşılan bellek kullanma gibi farklı bir bellek ayırma yöntemi kullanmak istiyorsanız, kendi ayırıcıyı oluşturmanız gerekir. C++ 11 ' i hedefliyorsanız ve yeni bir özel ayırıcı yazmanız gerekiyorsa, mümkünse bunu minimum ayırıcı yapın. Eski stil ayırıcı uygulamış olsanız bile, sizin için otomatik olarak sağlanacak daha verimli `construct()` bir yöntemden faydalanmak için onu *en az ayırıcı* olacak şekilde değiştirmeyi göz önünde bulundurun.

Minimum ayırıcı çok daha az ortak gerektirir ve tüm işleri oluşturan `allocate` ve `deallocate` üye işlevlerine odaklanabilmenizi sağlar. Minimum ayırıcı oluştururken, aşağıdaki örnekte gösterilenler dışında hiçbir üye uygulamayın:

1. bir kopya Oluşturucusu dönüştürülüyor (bkz. örnek)

1. operator==

1. operator!=

1. allocate

1. kaldırmak

Sizin için sağlanacak olan `construct()` c++ 11 varsayılan üyesi, mükemmel bir iletme ve taşıma semantiğini sağlar; eski sürümden çok sayıda durumda çok daha etkilidir.

> [!WARNING]
> Derleme zamanında C++ standart kitaplık, açıkça hangi üyelerin sağlandığını saptamak için allocator_traits sınıfını kullanır ve mevcut olmayan tüm Üyeler için varsayılan bir uygulama sağlar. Ayırıcılarınız için allocator_traits özelleştirmesi sunarak bu mekanizmayı engellemez!

Aşağıdaki örnek, ve `malloc` `free`kullanan bir ayırıcının en az bir uygulamasını gösterir. Dizi boyutu sıfırdan küçükse veya izin verilen en `std::bad_array_new_length` büyük boyuttan daha büyükse oluşturulan yeni özel durum türünün kullanımını aklınızda yapın.

```cpp
#pragma once
#include <stdlib.h> //size_t, malloc, free
#include <new> // bad_alloc, bad_array_new_length
#include <memory>
template <class T>
struct Mallocator
{
    typedef T value_type;
    Mallocator() noexcept {} //default ctor not required by C++ Standard Library

    // A converting copy constructor:
    template<class U> Mallocator(const Mallocator<U>&) noexcept {}
    template<class U> bool operator==(const Mallocator<U>&) const noexcept
    {
        return true;
    }
    template<class U> bool operator!=(const Mallocator<U>&) const noexcept
    {
        return false;
    }
    T* allocate(const size_t n) const;
    void deallocate(T* const p, size_t) const noexcept;
};

template <class T>
T* Mallocator<T>::allocate(const size_t n) const
{
    if (n == 0)
    {
        return nullptr;
    }
    if (n > static_cast<size_t>(-1) / sizeof(T))
    {
        throw std::bad_array_new_length();
    }
    void* const pv = malloc(n * sizeof(T));
    if (!pv) { throw std::bad_alloc(); }
    return static_cast<T*>(pv);
}

template<class T>
void Mallocator<T>::deallocate(T * const p, size_t) const noexcept
{
    free(p);
}
```

## <a name="writing-your-own-allocator-c03"></a>Kendi ayırıcıyı yazma (C++ 03)

C++ 03 ' de, standart kitaplık kapsayıcılarıyla C++ kullanılan herhangi bir ayırıcı aşağıdaki tür tanımlarını gerçekleştirmelidir:

|||
|-|-|
|`const_pointer`|`rebind`|
|`const_reference`|`reference`|
|`difference_type`|`size_type`|
|`pointer`|`value_type`|

Ayrıca, standart kitaplık kapsayıcılarıyla C++ kullanılan herhangi bir ayırıcı aşağıdaki yöntemleri gerçekleştirmelidir:

|||
|-|-|
|Oluşturucu|`deallocate`|
|Kopya oluşturucu|`destroy`|
|Yok edici|`max_size`|
|`address`|`operator==`|
|`allocate`|`operator!=`|
|`construct`||

Bu tür tanımları ve yöntemleri hakkında daha fazla bilgi için bkz. [ayırıcı sınıfı](../standard-library/allocator-class.md).

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)
