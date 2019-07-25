---
title: add_pointer Sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::add_pointer
helpviewer_keywords:
- add_pointer class
- add_pointer
ms.assetid: d8095cb0-6578-4143-b78f-87f82485298c
ms.openlocfilehash: 759867a542aa128755ba31e090984eb5b3fe6963
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68456552"
---
# <a name="addpointer-class"></a>add_pointer Sınıfı

Belirtilen türden bir işaretçi türü sağlar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class T>
struct add_pointer;

template <class T>
using add_pointer_t = typename add_pointer<T>::type;
```

### <a name="parameters"></a>Parametreler

*ŞI*\
Değiştirilecek tür.

## <a name="remarks"></a>Açıklamalar

`remove_reference<T>::type*`  Typedef`type` öğesi, ile aynı türü adlandırır. Diğer ad `add_pointer_t` , **typedef** `type`üyesine erişmek için bir kısayoldur.

Bir başvurudan `add_pointer` işaretçi yapmak için geçersiz olduğundan, türü bir işaretçi yapmadan önce belirtilen türden bir başvuruyu kaldırır. Sonuç olarak, türün bir başvuru olup olmadığı `add_pointer` konusunda endişe duymadan bir türü kullanabilirsiniz.

## <a name="example"></a>Örnek

Aşağıdaki örnek, bir türün `add_pointer` bu türe yönelik işaretçiyle aynı olduğunu gösterir.

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

**Üst bilgi:** \<type_traits >

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[< type_traits >](../standard-library/type-traits.md)\
[remove_pointer Sınıfı](../standard-library/remove-pointer-class.md)
