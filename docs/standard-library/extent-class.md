---
title: extent Sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::extent
helpviewer_keywords:
- extent class
- extent
ms.assetid: 6d16263d-90b2-4330-9ec7-b59ed898792d
ms.openlocfilehash: 0cd53ba8537e706a68ffdcf08df998108266ad20
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68457787"
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

*KAYDEDEMİYORUM*\
Sorguya bağlantılı dizi.

## <a name="remarks"></a>Açıklamalar

*Ty* , en az *ı* boyutlu bir dizi türüdür, tür sorgusu *i*tarafından belirtilen boyuttaki öğelerin sayısını tutar. *Ty* bir dizi türü değilse veya derecesi *i*'den küçükse ya da *sıfır ise ve* *Ty* , "bilinmeyen sınırının `U`dizisi" ise tür sorgusu 0 değerini tutar.

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

**Üst bilgi:** \<type_traits >

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[< type_traits >](../standard-library/type-traits.md)\
[remove_all_extents sınıfı](../standard-library/remove-all-extents-class.md)\
[remove_extent Sınıfı](../standard-library/remove-extent-class.md)
