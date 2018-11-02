---
title: Ayırıcılar
ms.date: 11/04/2016
helpviewer_keywords:
- allocators
- C++ Standard Library, allocators
ms.assetid: ac95023b-9e7d-49f5-861a-bf7a9a340746
ms.openlocfilehash: 1f11d1b007a728b32d27afd733df271f361864e7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50493879"
---
# <a name="allocators"></a>Ayırıcılar

Ayırıcılar C++ Standart Kitaplığı tarafından ayırmayı ve ayırmayı kaldırma kapsayıcılarda depolanan öğeleri işlemek için kullanılır. Bir şablon parametresi türü std::array dışındaki tüm C++ Standart Kitaplığı kapsayıcıları sahip `allocator<Type>`burada `Type` kapsayıcı öğe türünü temsil eder. Örneğin, vector sınıfı şu şekilde bildirilir:

```cpp
template <
    class Type,
    class Allocator = allocator<Type>
>
class vector
```

C++ Standart Kitaplığı için bir ayırıcısı bir varsayılan uygulamasını sağlar. C ++ 11 ve sonraki sürümlerinde, varsayılan ayırıcı daha küçük bir arabirimi kullanıma sunmak için güncelleştirilir; Yeni ayırıcı olarak adlandırılan bir *minimal ayırıcılar*. Özellikle, minimal ayırıcılar 's `construct()` üye performansı önemli ölçüde iyileştirebilen taşıma semantiklerini destekler. Çoğu durumda, bu varsayılan ayırıcı yeterli olur. C ++ 11'de tüm standart kitaplık türleri ve işlevleri, bir ayırıcıyı tür parametresi desteği minimal ayırıcılar arabiriminin olması da dahil olmak üzere `std::function`, `shared_ptr, allocate_shared()`, ve `basic_string`.  Varsayılan ayırıcı hakkında daha fazla bilgi için bkz. [allocator sınıfı](../standard-library/allocator-class.md).

## <a name="writing-your-own-allocator-c11"></a>Kendi ayırıcınızı (C ++ 11) yazma

Varsayılan ayırıcı kullanır **yeni** ve **Sil** ayırma ve bellek serbest bırakın. Bellek ayırma, paylaşılan bellek kullanma gibi farklı bir yöntem kullanmak istiyorsanız kendi ayırıcınızı oluşturmanız gerekir. C ++ 11'i hedeflediğiniz ve yeni bir özel bellek ayırıcısı yazmanız gereken, mümkünse bir minimal ayırıcılar olun. Eski stil ayırıcı zaten uygulanmış olsa bile olmasını değiştirme göz önünde bir *minimal ayırıcılar* daha verimli avantajlarından yararlanmak için `construct()` sizin için otomatik olarak sağlanacak yöntemi.

Minimal ayırıcılar çok daha az ortak gerektirir ve odağı etkinleştirmeden `allocate` ve `deallocate` tüm işleri bunu üye işlevleri. Minimal ayırıcılar oluştururken, aşağıdaki örnekte gösterilenlerin dışında herhangi bir üye kullanılmaz:

1. dönüştürme bir kopya Oluşturucu (örneğe bakın)

1. operator==

1. operator!=

1. allocate

1. Serbest Bırak

C ++ 11 varsayılan `construct()` sizin için sağlanan üye kusursuz iletme ve taşıma semantiği sağlar; sürümünden daha eski çoğu durumda çok daha verimli olur.

> [!WARNING]
> Derleme zamanında, C++ Standart Kitaplığı allocator_traits sınıfı açıkça sağladığınız hangi üyelerin algılamak için kullanır ve mevcut olmayan herhangi bir üye için bir varsayılan uygulamasını sağlar. Bu mekanizma ile allocator_traits özelleştirmesi için ayırıcı sağlayarak müdahale etmez!

Aşağıdaki örnek, kullanan bir ayırıcı'nın en az bir uygulamasını gösterir. `malloc` ve `free`. Yeni özel durum türü kullanımına dikkat edin `std::bad_array_new_length` sıfırdan küçük veya izin verilen en yüksek boyuttan büyük dizi boyutu ise oluşturulur.

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

## <a name="writing-your-own-allocator-c03"></a>Kendi ayırıcınızı (C ++ 03) yazma

C ++ 03, C++ Standart Kitaplığı kapsayıcıları ile kullanılan herhangi bir ayırıcı aşağıdaki tür tanımlarını uygulamanız gerekir:

|||
|-|-|
|`const_pointer`|`rebind`|
|`const_reference`|`reference`|
|`difference_type`|`size_type`|
|`pointer`|`value_type`|

Ayrıca, C++ Standart Kitaplığı kapsayıcıları ile kullanılan herhangi bir ayırıcı aşağıdaki yöntemleri uygulamanız gerekir:

|||
|-|-|
|Oluşturucu|`deallocate`|
|Kopya oluşturucu|`destroy`|
|Yok edici|`max_size`|
|`address`|`operator==`|
|`allocate`|`operator!=`|
|`construct`||

Bu tür tanımlarını ve yöntemleri hakkında daha fazla bilgi için bkz. [allocator sınıfı](../standard-library/allocator-class.md).

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)<br/>
