---
title: remove_reference Sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::remove_reference
helpviewer_keywords:
- remove_reference class
- remove_reference
ms.assetid: 294e1965-3ae3-46ee-bc42-4fdf60c24717
ms.openlocfilehash: f185994f943b2419a67fe86ce957751dc4031cbe
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68451281"
---
# <a name="removereference-class"></a>remove_reference Sınıfı

Türden başvuru türü yapar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class T>
struct remove_reference;

template <class T>
using remove_reference_t = typename remove_reference<T>::type;
```

### <a name="parameters"></a>Parametreler

*ŞI*\
Değiştirilecek tür.

## <a name="remarks"></a>Açıklamalar

`remove_reference<T>` Bir örneği, *t* formu `T1` `T1&`olduğunda, yoksa *t*olarak değiştirilmiş bir türü tutar.

## <a name="example"></a>Örnek

```cpp
#include <type_traits>
#include <iostream>

int main()
    {
    int *p = (std::remove_reference_t<int&> *)0;

    p = p;  // to quiet "unused" warning
    std::cout << "remove_reference_t<int&> == "
        << typeid(*p).name() << std::endl;

    return (0);
    }
```

```Output
remove_reference_t<int&> == int
```

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<type_traits >

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[< type_traits >](../standard-library/type-traits.md)\
[add_lvalue_reference Sınıfı](../standard-library/add-lvalue-reference-class.md)
