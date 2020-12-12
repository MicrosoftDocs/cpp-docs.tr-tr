---
description: 'Hakkında daha fazla bilgi edinin: add_volatile sınıfı'
title: add_volatile Sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::add_volatile
helpviewer_keywords:
- add_volatile class
- add_volatile
ms.assetid: cde57277-d764-402d-841e-97611ebaab14
ms.openlocfilehash: 6f138c9009d127efe2d640124d9af1e114eb0732
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97319875"
---
# <a name="add_volatile-class"></a>add_volatile Sınıfı

**`volatile`** Belirtilen türden bir tür yapar.

## <a name="syntax"></a>Sözdizimi

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

Öğesinin bir örneği `add_volatile<T>` **`typedef`** `type` bir başvuru, bir işlev veya geçici  nitelenmiş bir tür *ise t* olan bir üyeye sahiptir, aksi halde **`volatile`** *t*. Diğer ad, `add_volatile_t` üyeye erişmek için bir kısayoldur **`typedef`** `type` .

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
