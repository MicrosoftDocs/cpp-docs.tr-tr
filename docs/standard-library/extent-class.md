---
title: extent Sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::extent
helpviewer_keywords:
- extent class
- extent
ms.assetid: 6d16263d-90b2-4330-9ec7-b59ed898792d
ms.openlocfilehash: 716f4fcd90e97eaeb3f56c8429379590d176e1c8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50428151"
---
# <a name="extent-class"></a>extent Sınıfı

Bir dizi boyutu alır.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Ty, unsigned I = 0>
struct extent;
```

### <a name="parameters"></a>Parametreler

*Ty*<br/>
Sorgulanacak tür.

*I*<br/>
Dizi sorgu bağlanır.

## <a name="remarks"></a>Açıklamalar

Varsa *Ty* en az bir dizi türü *miyim* boyutları türü sorgu tutan öğelerin sayısı tarafından belirtilen boyutta *miyim*. Varsa *Ty* sıralamasını bir dizi türü değilse veya küçüktür *miyim*, veya *miyim* sıfırdır ve *Ty* türü "Bilinmeyen bir dizi sınırı `U` ", 0 değeri türü sorgu tutar.

## <a name="example"></a>Örnek

```cpp
// std__type_traits__extent.cpp
// compile with: /EHsc
#include <type_traits>
#include <iostream>

int main()
    {
    std::cout << "extent 0 == "
        << std::extent<int[5][10]>::value << std::endl;
    std::cout << "extent 1 == "
        << std::extent<int[5][10], 1>::value << std::endl;

    return (0);
    }

```

```Output
extent 0 == 5
extent 1 == 10
```

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<type_traits >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)<br/>
[remove_all_extents Sınıfı](../standard-library/remove-all-extents-class.md)<br/>
[remove_extent Sınıfı](../standard-library/remove-extent-class.md)<br/>
