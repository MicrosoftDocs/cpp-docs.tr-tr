---
title: add_const Sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::add_const
helpviewer_keywords:
- add_const class
- add_const
ms.assetid: 1262a1eb-8c9c-4dd6-9f43-88ba280182f1
ms.openlocfilehash: dc457fd4efba538e96200f7f42f84a73fc1b5228
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50438656"
---
# <a name="addconst-class"></a>add_const Sınıfı

Const tür yapar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Ty>
struct add_const;
```

### <a name="parameters"></a>Parametreler

*Ty*<br/>
Değiştirilecek tür.

## <a name="remarks"></a>Açıklamalar

Tür değiştiricinin bir örneği bir değişiklik-tür tutar *Ty* varsa *Ty* bir başvuru, bir işlev veya bir const nitelenmiş türde olduğundan, aksi takdirde `const Ty`.

## <a name="example"></a>Örnek

```cpp
// std__type_traits__add_const.cpp
// compile with: /EHsc
#include <type_traits>
#include <iostream>

int main()
{
    std::add_const<int>::type *p = (const int *)0;

    p = p;  // to quiet "unused" warning
    std::cout << "add_const<int> == "
        << typeid(*p).name() << std::endl;

    return (0);
}
```

```Output
add_const<int> == int
```

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<type_traits >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)<br/>
[remove_const Sınıfı](../standard-library/remove-const-class.md)<br/>
