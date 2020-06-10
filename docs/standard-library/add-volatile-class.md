---
title: add_volatile Sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::add_volatile
helpviewer_keywords:
- add_volatile class
- add_volatile
ms.assetid: cde57277-d764-402d-841e-97611ebaab14
ms.openlocfilehash: 1a4ad8a86b88cdfa98f043bb49ba6eeff8b090c9
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84619212"
---
# <a name="add_volatile-class"></a>add_volatile Sınıfı

Belirtilen türden **geçici** bir tür yapar.

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

Bir örneğinin bir `add_volatile<T>` **typedef** `type` başvuru, bir işlev veya geçici nitelenmiş bir *T* tür, aksi durumda **geçici** *T*bir tür olması halinde *t* olan bir üye typedef öğesi vardır. Diğer ad, `add_volatile_t` **typedef** üyesine erişmek için bir kısayoldur `type` .

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
