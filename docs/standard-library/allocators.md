---
title: Allocators | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- allocators
- C++ Standard Library, allocators
ms.assetid: ac95023b-9e7d-49f5-861a-bf7a9a340746
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 05f774b6cc243223d396d7c18648a2451bf8dd18
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="allocators"></a>Ayırıcılar
Allocators C++ Standart Kitaplığı tarafından ayırma ve ayırmayı kaldırma kapsayıcılarında depolanan öğelerin işlemek için kullanılır. Bir şablon parametresi türü std::array dışındaki tüm C++ Standart Kitaplığı kapsayıcıları sahip `allocator<Type>`, burada `Type` kapsayıcı öğe türünü temsil eder. Örneğin, vector sınıfı şu şekilde bildirilmiş:  
  
```  
template <  
    class Type,  
    class Allocator = allocator<Type>  
>  
class vector  
```  
  
 C++ Standart Kitaplığı için bir ayırıcı varsayılan uygulamasını sağlar. C ++ 11 ve sonraki sürümlerinde, varsayılan ayırıcısı daha küçük bir arabirimi kullanıma sunmak için güncelleştirilir; Yeni ayırıcısı olarak adlandırılan bir *en az ayırıcısı*. Özellikle, en az ayırıcısı 's `construct()` üye performansı önemli ölçüde artırabilir taşıma semantiği destekler. Çoğu durumda bu varsayılan ayırıcısı yeterli olacaktır. C ++ 11 tüm standart kitaplığı türleri ve bu işlev bir ayırıcı tür parametre desteği en az ayırıcısı arabirimi ele dahil olmak üzere `std::function`, `shared_ptr, allocate_shared()`, ve `basic_string`.  Varsayılan ayırıcısı hakkında daha fazla bilgi için bkz: [allocator sınıfı](../standard-library/allocator-class.md).  
  
## <a name="writing-your-own-allocator-c11"></a>Kendi ayırıcısı (C ++ 11) yazma  
 Varsayılan ayırıcısı kullanan `new` ve `delete` ayırmak ve bellek ayırması için. Bellek ayırma, paylaşılan bellek kullanma gibi farklı bir yöntem kullanmak istiyorsanız, kendi ayırıcısı oluşturmanız gerekir. C ++ 11 hedeflediğiniz ve yeni bir özel ayırıcısı yazmak ihtiyacınız varsa, mümkünse en az bir ayırıcı olun. Eski Tarz ayırıcısı zaten uyguladıysanız olsa bile olmasını değiştirmeyi düşünebilirsiniz bir *en az ayırıcısı* daha verimli şekilde yararlanmak için `construct()` sizin için otomatik olarak sağlanacak yöntemi.  
  
 En az bir ayırıcı çok daha az Demirbaş gerektirir ve odağı etkinleştirmek `allocate` ve `deallocate` iş tümünü üye işlevleri. En az bir ayırıcı oluştururken, aşağıdaki örnekte gösterildiği olanlar dışında herhangi bir üye kullanılmaz:  
  
1.  dönüştürme kopya Oluşturucu (örneğe bakın)  
  
2.  operator==  
  
3.  operator!=  
  
4.  allocate  
  
5.  Serbest bırakma  
  
 C ++ 11 varsayılan `construct()` sizin için sağlanan üye kusursuz iletme ve etkinleştirir taşıma semantiği; sürümünden daha eski birçok durumda çok daha verimli olur.  
  
> [!WARNING]
>  Derleme zamanında C++ Standart Kitaplığı allocator_traits sınıfı açıkça sağladığınız üyeleri algılamak için kullanır ve mevcut olmayan tüm üyeleri için varsayılan uygulamasını sağlar. Bu mekanizma ile ayırıcı için allocator_traits uzmanlaşması sağlayarak karışmaması!  
  
 Aşağıdaki örnek kullanan bir ayırıcı en az bir uyarlamasını gösterir `malloc` ve `free`. Yeni özel durum türü kullanımına dikkat edin `std::bad_array_new_length` sıfırdan küçük veya izin verilen en yüksek boyuttan büyük dizi boyutu olması durumunda oluşur.  
  
```  
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
  
## <a name="writing-your-own-allocator-c03"></a>Kendi ayırıcısı (C ++ 03) yazma  
 C ++ 03, C++ Standart Kitaplığı kapsayıcılarını ile kullanılan ayırıcısı aşağıdaki tür tanımları uygulamanız gerekir:  
  
|||  
|-|-|  
|`const_pointer`|`rebind`|  
|`const_reference`|`reference`|  
|`difference_type`|`size_type`|  
|`pointer`|`value_type`|  
  
 Ayrıca, C++ Standart Kitaplığı kapsayıcılarını ile kullanılan ayırıcısı aşağıdaki yöntemlerden uygulamanız gerekir:  
  
|||  
|-|-|  
|Oluşturucu|`deallocate`|  
|Kopya oluşturucu|`destroy`|  
|Yok edici|`max_size`|  
|`address`|`operator==`|  
|`allocate`|`operator!=`|  
|`construct`||  
  
 Bu tür tanımları ve yöntemleri hakkında daha fazla bilgi için bkz: [allocator sınıfı](../standard-library/allocator-class.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)




