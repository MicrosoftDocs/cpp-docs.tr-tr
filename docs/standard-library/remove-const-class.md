---
title: remove_const Sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::remove_const
helpviewer_keywords:
- remove_const class
- remove_const
ms.assetid: feb76fb3-9228-41d6-80f6-2fbb04daec43
ms.openlocfilehash: 0091c77d33e1fcd2be5b361680c9422210866be2
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68451352"
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

*ŞI*\
Değiştirilecek tür.

## <a name="remarks"></a>Açıklamalar

`remove_const<T>` Bir örneği, *t* formu `T1` `const T1`olduğunda, yoksa *t*olarak değiştirilmiş bir türü tutar.

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

**Üst bilgi:** \<type_traits >

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[< type_traits >](../standard-library/type-traits.md)\
[add_const sınıfı](../standard-library/add-const-class.md)\
[remove_cv Sınıfı](../standard-library/remove-cv-class.md)
