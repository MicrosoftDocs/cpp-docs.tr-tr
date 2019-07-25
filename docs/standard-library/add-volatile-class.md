---
title: add_volatile Sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::add_volatile
helpviewer_keywords:
- add_volatile class
- add_volatile
ms.assetid: cde57277-d764-402d-841e-97611ebaab14
ms.openlocfilehash: becea4ff52342a79d0b87ffe0022e2cf84c47949
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68456526"
---
# <a name="addvolatile-class"></a>add_volatile Sınıfı

Belirtilen türden **geçici** bir tür yapar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Ty>
struct add_volatile;

template <class T>
using add_volatile_t = typename add_volatile<T>::type;
```

### <a name="parameters"></a>Parametreler

*ŞI*\
Değiştirilecek tür.

## <a name="remarks"></a>Açıklamalar

Bir örneğinin `add_volatile<T>` bir başvuru, bir işlev veya geçici nitelenmiş bir tür, aksi durumda **geçici** bir tür *olması halinde* *t* olan bir üye **typedef** `type` öğesi *vardır.* Diğer ad `add_volatile_t` , **typedef** `type`üyesine erişmek için bir kısayoldur.

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

**Üst bilgi:** \<type_traits >

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[< type_traits >](../standard-library/type-traits.md)\
[remove_volatile Sınıfı](../standard-library/remove-volatile-class.md)
