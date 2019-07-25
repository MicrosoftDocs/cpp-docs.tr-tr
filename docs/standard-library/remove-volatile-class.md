---
title: remove_volatile Sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::remove_volatile
helpviewer_keywords:
- remove_volatile class
- remove_volatile
ms.assetid: 8b87e2c2-a581-4eb3-8691-c5603910d61d
ms.openlocfilehash: 19514d1839fa6e0afcecb690dcb12657a85f3c2e
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68451258"
---
# <a name="removevolatile-class"></a>remove_volatile Sınıfı

Türden geçici olmayan tür yapar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class T>
struct remove_volatile;

template <class T>
using remove_volatile_t = typename remove_volatile<T>::type;
```

### <a name="parameters"></a>Parametreler

*ŞI*\
Değiştirilecek tür.

## <a name="remarks"></a>Açıklamalar

`remove_volatile<T>` Bir örneği, *t* formu `T1` `volatile T1`olduğunda, yoksa *t*olarak değiştirilmiş bir türü tutar.

## <a name="example"></a>Örnek

```cpp
#include <type_traits>
#include <iostream>

int main()
    {
    int *p = (std::remove_volatile_t<volatile int> *)0;

    p = p;  // to quiet "unused" warning
    std::cout << " remove_volatile_t<volatile int> == "
        << typeid(*p).name() << std::endl;

    return (0);
    }
```

```Output
remove_volatile_t<volatile int> == int
```

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<type_traits >

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[< type_traits >](../standard-library/type-traits.md)\
[add_volatile Sınıfı](../standard-library/add-volatile-class.md)
