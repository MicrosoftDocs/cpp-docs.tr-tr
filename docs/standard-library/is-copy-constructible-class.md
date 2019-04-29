---
title: is_copy_constructible sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_copy_constructible
helpviewer_keywords:
- is_copy_constructible
ms.assetid: d8db9d4c-21ed-4884-bead-0b0b562de007
ms.openlocfilehash: c85d036efda2509885a079cf59a130a63c0389bc
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62336637"
---
# <a name="iscopyconstructible-class"></a>is_copy_constructible sınıfı

Kopya Oluşturucu türüne sahip olmadığını sınar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Ty>
struct is_copy_constructible;
```

### <a name="parameters"></a>Parametreler

*Ty*<br/>
Sorgulanacak tür.

## <a name="remarks"></a>Açıklamalar

Karşılaştırmasının bir örneği true tutan türü *Ty* tuttuğu yanlış bir kopya Oluşturucu, aksi takdirde sahip bir sınıftır.

## <a name="example"></a>Örnek

```cpp
#include <type_traits>
#include <iostream>

struct Copyable
{
    int val;
};

struct NotCopyable
{
   NotCopyable(const NotCopyable&) = delete;
   int val;

};

int main()
{
    std::cout << "is_copy_constructible<Copyable> == " << std::boolalpha
        << std::is_copy_constructible<Copyable>::value << std::endl;
    std::cout << "is_copy_constructible<NotCopyable> == " << std::boolalpha
        << std::is_copy_constructible<NotCopyable>::value << std::endl;

    return (0);
}
```

```Output
is_copy_constructible<Copyable> == true
is_copy_constructible<NotCopyable > == false
```

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<type_traits >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)<br/>
