---
description: 'Hakkında daha fazla bilgi edinin: add_const sınıfı'
title: add_const Sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::add_const
helpviewer_keywords:
- add_const class
- add_const
ms.assetid: 1262a1eb-8c9c-4dd6-9f43-88ba280182f1
ms.openlocfilehash: ce1dd895a5968234feca7905d3b9f8d571336053
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97319950"
---
# <a name="add_const-class"></a>add_const Sınıfı

Türünden const türü yapar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Ty>
struct add_const;
```

### <a name="parameters"></a>Parametreler

*Kalite*\
Değiştirilecek tür.

## <a name="remarks"></a>Açıklamalar

Tür değiştiricisinin bir örneği, *Ty* bir başvuru, bir işlev veya const nitelikli bir *tür ise,* Aksi durumda bir değiştirilmiş türü tutar `const Ty` .

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

**Üst bilgi:**\<type_traits>

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](type-traits.md)\
[remove_const sınıfı](remove-const-class.md)
