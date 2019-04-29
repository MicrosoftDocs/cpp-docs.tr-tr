---
title: remove_all_extents Sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::remove_all_extents
helpviewer_keywords:
- remove_all_extents class
- remove_all_extents
ms.assetid: 548dc536-82e7-423a-b8c1-443d66d9632e
ms.openlocfilehash: 1c8972889272a4621d6357758cde6d174bb2abd7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62368961"
---
# <a name="removeallextents-class"></a>remove_all_extents Sınıfı

Dizi türünden dizi olmayan tür yapar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class T>
struct remove_all_extents;

template <class T>
using remove_all_extents_t = typename remove_all_extents<T>::type;
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Değiştirilecek tür.

## <a name="remarks"></a>Açıklamalar

Örneği `remove_all_extents<T>` bir değiştirilen dizi türünün öğe türü olan türü tutar *T* tüm dizi boyutları kaldırılmış olan veya *T* varsa *T* bir dizi türü değil.

## <a name="example"></a>Örnek

```cpp
#include <type_traits>
#include <iostream>

int main()
    {
    std::cout << "remove_all_extents<int> == "
        << typeid(std::remove_all_extents_t<int>).name()
        << std::endl;
    std::cout << "remove_all_extents_t<int[5]> == "
        << typeid(std::remove_all_extents_t<int[5]>).name()
        << std::endl;
    std::cout << "remove_all_extents_t<int[5][10]> == "
        << typeid(std::remove_all_extents_t<int[5][10]>).name()
        << std::endl;

    return (0);
    }
```

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<type_traits >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)<br/>
[remove_extent Sınıfı](../standard-library/remove-extent-class.md)<br/>
