---
title: remove_const Sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::remove_const
helpviewer_keywords:
- remove_const class
- remove_const
ms.assetid: feb76fb3-9228-41d6-80f6-2fbb04daec43
ms.openlocfilehash: 04f7c6475d88f843ef381563f80559529e6b59e4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50477187"
---
# <a name="removeconst-class"></a>remove_const Sınıfı

Türden sabit olmayan bir tür yapar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class T>
struct remove_const;
```

```cpp
template <class T>
using remove_const_t = typename remove_const<T>::type;
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Değiştirilecek tür.

## <a name="remarks"></a>Açıklamalar

Örneği `remove_const<T>` bir değişiklik-tür tutar `T1` olduğunda *T* biçimindedir `const T1`, aksi takdirde *T*.

## <a name="example"></a>Örnek

```cpp
#include <type_traits>
#include <iostream>

int main()
    {
    int *p = (std::remove_const_t<const int>*)0;

    p = p;  // to quiet "unused" warning
    std::cout << "remove_const_t<const int> == "
        << typeid(*p).name() << std::endl;

    return (0);
    }
```

```Output
remove_const_t<const int> == int
```

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<type_traits >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)<br/>
[add_const Sınıfı](../standard-library/add-const-class.md)<br/>
[remove_cv Sınıfı](../standard-library/remove-cv-class.md)<br/>
