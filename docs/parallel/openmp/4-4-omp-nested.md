---
title: 4.4 OMP_NESTED
ms.date: 11/04/2016
ms.assetid: fd17b6f4-84e8-44c0-a96a-3a9e5ba33688
ms.openlocfilehash: e45b8901c56923ab37ca387a5f057c5b41af21f3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50453631"
---
# <a name="44-ompnested"></a>4.4 OMP_NESTED

`OMP_NESTED` Ortam değişkeni etkinleştirir veya iç içe geçmiş paralellik etkin veya devre dışı çağırarak sürece iç içe geçmiş paralellik devre dışı bırakır `o` **mp_set_nested** yordamı. Varsa kümesine **TRUE**, iç içe geçmiş paralellik etkindir; Bu ayarlanırsa **FALSE**, iç içe geçmiş paralellik devre dışı bırakıldı. Varsayılan değer **FALSE**.

Örnek:

```
setenv OMP_NESTED TRUE
```

## <a name="cross-reference"></a>Başvuru çapraz:

- `omp_set_nested` işlev, bkz: [bölümü 3.1.9](../../parallel/openmp/3-1-9-omp-set-nested-function.md) 40 sayfasında.