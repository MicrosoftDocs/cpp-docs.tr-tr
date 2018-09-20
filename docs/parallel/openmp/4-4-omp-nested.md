---
title: 4.4 OMP_NESTED | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: fd17b6f4-84e8-44c0-a96a-3a9e5ba33688
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1083269f31ebc710da24430635ff8381e3f2147a
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46419522"
---
# <a name="44-ompnested"></a>4.4 OMP_NESTED

`OMP_NESTED` Ortam değişkeni etkinleştirir veya iç içe geçmiş paralellik etkin veya devre dışı çağırarak sürece iç içe geçmiş paralellik devre dışı bırakır `o` **mp_set_nested** yordamı. Varsa kümesine **TRUE**, iç içe geçmiş paralellik etkindir; Bu ayarlanırsa **FALSE**, iç içe geçmiş paralellik devre dışı bırakıldı. Varsayılan değer **FALSE**.

Örnek:

```
setenv OMP_NESTED TRUE
```

## <a name="cross-reference"></a>Başvuru çapraz:

- `omp_set_nested` işlev, bkz: [bölümü 3.1.9](../../parallel/openmp/3-1-9-omp-set-nested-function.md) 40 sayfasında.