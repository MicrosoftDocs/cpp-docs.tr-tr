---
title: 2.2 Koşullu Derleme
ms.date: 11/04/2016
ms.assetid: 8f9c914d-736c-48cf-899d-c8029dbe1e32
ms.openlocfilehash: 9dc107ee9e5328df205d4b6f826f71c23abfb3ba
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50658555"
---
# <a name="22-conditional-compilation"></a>2.2 Koşullu Derleme

_**OPENMP** makro adı ondalık sabit olarak OpenMP uyumlu uygulamaları tarafından tanımlanan *yyyymm*, yıl ve ay onaylı belirtiminin olacak. Bu makro konu olmalıdır bir **#define** veya **#undef** ön işleme yönergesi.

```
#ifdef _OPENMP
iam = omp_get_thread_num() + index;
#endif
```

Satıcılar için OpenMP uzantıları tanımlarsanız, bunlar ek önceden tanımlı makrolar belirtebilirsiniz.