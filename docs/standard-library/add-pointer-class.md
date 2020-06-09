---
title: add_pointer Sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::add_pointer
helpviewer_keywords:
- add_pointer class
- add_pointer
ms.assetid: d8095cb0-6578-4143-b78f-87f82485298c
ms.openlocfilehash: 8adeffd0352d04fe844b286ea7456c66e907a0a7
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84619258"
---
# <a name="add_pointer-class"></a>add_pointer Sınıfı

Belirtilen türden bir işaretçi türü sağlar.

## <a name="syntax"></a>Söz dizimi

```cpp
template <class T>
struct add_pointer;

template <class T>
using add_pointer_t = typename add_pointer<T>::type;
```

### <a name="parameters"></a>Parametreler

*Şı*\
Değiştirilecek tür.

## <a name="remarks"></a>Açıklamalar

TypeDef öğesi **typedef** `type` , ile aynı türü adlandırır `remove_reference<T>::type*` . Diğer ad, `add_pointer_t` **typedef** üyesine erişmek için bir kısayoldur `type` .

Bir başvurudan işaretçi yapmak için geçersiz olduğundan, `add_pointer` türü bir işaretçi yapmadan önce belirtilen türden bir başvuruyu kaldırır. Sonuç olarak, türün `add_pointer` bir başvuru olup olmadığı konusunda endişe duymadan bir türü kullanabilirsiniz.

## <a name="example"></a>Örnek

Aşağıdaki örnek, `add_pointer` bir türün bu türe yönelik işaretçiyle aynı olduğunu gösterir.

```cpp
#include <type_traits>
#include <iostream>

int main()
{
    std::add_pointer_t<int> *p = (int **)0;

    p = p;  // to quiet "unused" warning
    std::cout << "add_pointer_t<int> == "
        << typeid(*p).name() << std::endl;

    return (0);
}
```

```Output
add_pointer_t<int> == int *
```

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<type_traits>

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](type-traits.md)\
[remove_pointer sınıfı](remove-pointer-class.md)
