---
title: Extent sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::extent
dev_langs:
- C++
helpviewer_keywords:
- extent class
- extent
ms.assetid: 6d16263d-90b2-4330-9ec7-b59ed898792d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2e6df4526eea3b0b8b4e91fa4f3e6a89cdd8adb7
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38964316"
---
# <a name="extent-class"></a>extent Sınıfı

Bir dizi boyutu alır.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Ty, unsigned I = 0>
struct extent;
```

### <a name="parameters"></a>Parametreler

*Ty* Sorgulanacak tür.

*Ben* dizi ilişkili sorgu.

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
