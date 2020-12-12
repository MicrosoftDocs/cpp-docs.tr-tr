---
description: 'Daha fazla bilgi edinin: kapsam sınıfı'
title: extent Sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::extent
helpviewer_keywords:
- extent class
- extent
ms.assetid: 6d16263d-90b2-4330-9ec7-b59ed898792d
ms.openlocfilehash: d3db49db99d2cb7a241ca3b69c48fa6bcf2cb490
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97324392"
---
# <a name="extent-class"></a>extent Sınıfı

Bir dizi boyutu alır.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Ty, unsigned I = 0>
struct extent;
```

### <a name="parameters"></a>Parametreler

*Kalite*\
Sorgulanacak tür.

*Kaydedemiyorum*\
Sorguya bağlantılı dizi.

## <a name="remarks"></a>Açıklamalar

*Ty* , en az *ı* boyutlu bir dizi türüdür, tür sorgusu *i* tarafından belirtilen boyuttaki öğelerin sayısını tutar. *Ty* bir dizi türü değilse veya derecesi *i*'den küçükse ya da sıfır ise ve *Ty* , *"* bilinmeyen sınırının dizisi `U` " ise tür sorgusu 0 değerini tutar.

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

**Üst bilgi:**\<type_traits>

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)\
[remove_all_extents sınıfı](../standard-library/remove-all-extents-class.md)\
[remove_extent sınıfı](../standard-library/remove-extent-class.md)
