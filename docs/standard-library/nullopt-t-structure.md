---
title: nullopt_t yapısı
ms.date: 08/04/2019
f1_keywords:
- optional/std::nullopt_t
- optional/std::nullopt
ms.openlocfilehash: 1f453a5d75de3f6dedb133d55c094a4f4274e08f
ms.sourcegitcommit: 16c0392fc8d96e814c3a40b0c5346d7389aeb525
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/12/2019
ms.locfileid: "68957053"
---
# <a name="nullopt_t-struct"></a>nullopt_t yapısı

Tür, isteğe bağlı bir nesnenin bir değer içermediğini belirtmek için kullanılan benzersiz, boş bir tür. [](optional-class.md) `nullopt_t`

Türünün `nullopt` `optional` sabiti, bir türün başlatılmamış bir duruma sahip olduğunu gösterir. `nullopt_t` Bu, bir `optional` nesneyi başlatmak veya bir ile karşılaştırmak için kullanılabilir.

## <a name="syntax"></a>Sözdizimi

```cpp
struct nullopt_t;
inline constexpr nullopt_t nullopt{ /*implementation-defined*/ };
```

## <a name="see-also"></a>Ayrıca bkz.

[\<isteğe bağlı >](optional.md)\
[isteğe bağlı sınıf](optional-class.md)
