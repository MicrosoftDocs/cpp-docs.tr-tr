---
description: 'Hakkında daha fazla bilgi edinin: nullopt_t struct'
title: nullopt_t yapısı
ms.date: 08/04/2019
f1_keywords:
- optional/std::nullopt_t
- optional/std::nullopt
ms.openlocfilehash: 7a597dcc5f15843f125dc7572dc4c5694320f0bb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97338116"
---
# <a name="nullopt_t-struct"></a>nullopt_t yapısı

`nullopt_t`Tür, [isteğe bağlı](optional-class.md) bir nesnenin bir değer içermediğini belirtmek için kullanılan benzersiz, boş bir tür.

Türünün sabiti, `nullopt` `nullopt_t` bir `optional` türün başlatılmamış bir duruma sahip olduğunu gösterir. Bu, bir `optional` nesneyi başlatmak veya bir ile karşılaştırmak için kullanılabilir.

## <a name="syntax"></a>Syntax

```cpp
struct nullopt_t;
inline constexpr nullopt_t nullopt{ /*implementation-defined*/ };
```

## <a name="see-also"></a>Ayrıca bkz.

[\<optional>](optional.md)\
[isteğe bağlı sınıf](optional-class.md)
