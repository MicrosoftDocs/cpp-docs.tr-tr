---
title: remove_cv Sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::remove_cv
helpviewer_keywords:
- remove_cv class
- remove_cv
ms.assetid: 8502602a-1c80-479c-84e0-33bd1d6496d6
ms.openlocfilehash: dcabf9b4687d473898dea98f1001647299a40b76
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50660687"
---
# <a name="removecv-class"></a>remove_cv Sınıfı

Türden sabit/geçici olmayan tür yapar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class T>
struct remove_cv;

template <class T>
using remove_cv_t = typename remove_cv<T>::type;
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Değiştirilecek tür.

## <a name="remarks"></a>Açıklamalar

Örneği `remove_cv<T>` bir değişiklik-tür tutar `T1` olduğunda *T* biçimindedir `const T1`, `volatile T1`, veya `const volatile T1`, aksi takdirde *T*.

## <a name="example"></a>Örnek

```cpp
#include <type_traits>
#include <iostream>

int main()
    {
    int *p = (std::remove_cv_t<const volatile int> *)0;

    p = p;  // to quiet "unused" warning
    std::cout << "remove_cv_t<const volatile int> == "
        << typeid(*p).name() << std::endl;

    return (0);
    }
```

```Output
remove_cv_t<const volatile int> == int
```

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<type_traits >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)<br/>
[remove_const Sınıfı](../standard-library/remove-const-class.md)<br/>
[remove_volatile Sınıfı](../standard-library/remove-volatile-class.md)<br/>
