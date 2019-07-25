---
title: is_default_constructible sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_default_constructible
helpviewer_keywords:
- is_default_constructible
ms.assetid: dd8f1c44-dae5-4258-891f-c5e048d94092
ms.openlocfilehash: 451f43435132876fcfbbabe37c613d3c9efef30e
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68452782"
---
# <a name="isdefaultconstructible-class"></a>is_default_constructible sınıfı

Bir türün varsayılan Oluşturucusu olup olmadığını sınar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Ty>
struct is_default_constructible;
```

### <a name="parameters"></a>Parametreler

*ŞI*\
Sorgulanacak tür.

## <a name="remarks"></a>Açıklamalar

Tür *T* türü, varsayılan oluşturucuya sahip bir sınıf türü ise true, aksi takdirde false barındırır. Bu koşul `is_constructible<T>`ile eşdeğerdir. Tür *T* , tamamen bir tür, **void**veya bilinmeyen bir bağlantılı dizi olmalıdır.

## <a name="example"></a>Örnek

```cpp
#include <type_traits>
#include <iostream>

struct Simple
{
    Simple() : val(0) {}
    int val;
};

struct Simple2
{
    Simple2(int v) : val(v) {}
    int val;
};

int main()
{
    std::cout << "is_default_constructible<Simple> == " << std::boolalpha
        << std::is_default_constructible<Simple>::value << std::endl;
    std::cout << "is_default_constructible<Simple2> == " << std::boolalpha
        << std::is_default_constructible<Simple2>::value << std::endl;

    return (0);
}
```

```Output
is_default_constructible<Simple> == true
is_default_constructible<Simple2> == false
```

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<type_traits >

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)
