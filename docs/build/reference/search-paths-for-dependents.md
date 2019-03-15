---
title: Bağımlılıklar için Yollar Ara
ms.date: 11/04/2016
helpviewer_keywords:
- NMAKE program, dependents
- dependents, NMAKE
ms.assetid: bf998e47-da74-48b5-891d-d3d8ce57264b
ms.openlocfilehash: bc2c430c43f408065234c9df50977003eafd3cb1
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57823574"
---
# <a name="search-paths-for-dependents"></a>Bağımlılıklar için Yollar Ara

Her bağlı gibi belirtilen bir isteğe bağlı arama yolu vardır:

## <a name="syntax"></a>Sözdizimi

```
{directory[;directory...]}dependent
```

## <a name="remarks"></a>Açıklamalar

NMAKE bağımlı bir geçerli dizin ilk olarak ve belirtilen sırada dizinde arar. Makro bölümünü veya tümünü bir arama yolu belirtebilirsiniz. Dizin adları ({}); küme ayraçları içine alın. birden çok dizin, noktalı virgül (;) ayırın. Boşluk veya sekme izin verilir.

## <a name="see-also"></a>Ayrıca bkz.

[Bağımlılıklar](dependents.md)