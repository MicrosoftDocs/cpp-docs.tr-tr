---
title: add_volatile Sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::add_volatile
helpviewer_keywords:
- add_volatile class
- add_volatile
ms.assetid: cde57277-d764-402d-841e-97611ebaab14
ms.openlocfilehash: e8c213a116ff7a7d4218179f0e944ac4f84a75e5
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87230278"
---
# <a name="add_volatile-class"></a>add_volatile Sınıfı

**`volatile`** Belirtilen türden bir tür yapar.

## <a name="syntax"></a>Söz dizimi

```cpp
template <class Ty>
struct add_volatile;

template <class T>
using add_volatile_t = typename add_volatile<T>::type;
```

### <a name="parameters"></a>Parametreler

*Şı*\
Değiştirilecek tür.

## <a name="remarks"></a>Açıklamalar

Öğesinin bir örneği `add_volatile<T>` **`typedef`** `type` bir başvuru, bir işlev veya geçici *T* nitelenmiş bir tür *ise t* olan bir üyeye sahiptir, aksi halde **`volatile`** *t*. Diğer ad, `add_volatile_t` üyeye erişmek için bir kısayoldur **`typedef`** `type` .

## <a name="example"></a>Örnek

```cpp
#include <type_traits>
#include <iostream>

int main()
{
    std::add_volatile_t<int> *p = (volatile int *)0;

    p = p;  // to quiet "unused" warning
    std::cout << "add_volatile<int> == "
        << typeid(*p).name() << std::endl;

    return (0);
}
```

```Output
add_volatile<int> == int
```

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<type_traits>

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](type-traits.md)\
[remove_volatile sınıfı](remove-volatile-class.md)
