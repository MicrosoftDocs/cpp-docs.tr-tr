---
description: 'Hakkında daha fazla bilgi edinin: add_pointer sınıfı'
title: add_pointer Sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::add_pointer
helpviewer_keywords:
- add_pointer class
- add_pointer
ms.assetid: d8095cb0-6578-4143-b78f-87f82485298c
ms.openlocfilehash: 36f262c68c17dbcaca603c2a78e2450f0de64aa6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97319901"
---
# <a name="add_pointer-class"></a>add_pointer Sınıfı

Belirtilen türden bir işaretçi türü sağlar.

## <a name="syntax"></a>Sözdizimi

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

Üye **`typedef`** `type` adı aynı türde `remove_reference<T>::type*` . Diğer ad, `add_pointer_t` üyeye erişmek için bir kısayoldur **`typedef`** `type` .

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
