---
title: Bağımlılıklar için Yollar Ara
ms.date: 11/04/2016
helpviewer_keywords:
- NMAKE program, dependents
- dependents, NMAKE
ms.assetid: bf998e47-da74-48b5-891d-d3d8ce57264b
ms.openlocfilehash: 8856d845d51072d205c84278978c7fbb447aed9b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50448808"
---
# <a name="search-paths-for-dependents"></a>Bağımlılıklar için Yollar Ara

Her bağlı gibi belirtilen bir isteğe bağlı arama yolu vardır:

## <a name="syntax"></a>Sözdizimi

```
{directory[;directory...]}dependent
```

## <a name="remarks"></a>Açıklamalar

NMAKE bağımlı bir geçerli dizin ilk olarak ve belirtilen sırada dizinde arar. Makro bölümünü veya tümünü bir arama yolu belirtebilirsiniz. Dizin adları ({}); küme ayraçları içine alın. birden çok dizin, noktalı virgül (;) ayırın. Boşluk veya sekme izin verilir.

## <a name="see-also"></a>Ayrıca Bkz.

[Bağımlılıklar](../build/dependents.md)