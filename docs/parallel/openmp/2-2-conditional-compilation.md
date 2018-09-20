---
title: 2.2 koşullu derleme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 8f9c914d-736c-48cf-899d-c8029dbe1e32
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 25b52ce624777efe85e27b8ce5e7941bc2f5dcba
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46440387"
---
# <a name="22-conditional-compilation"></a>2.2 Koşullu Derleme

_**OPENMP** makro adı ondalık sabit olarak OpenMP uyumlu uygulamaları tarafından tanımlanan *yyyymm*, yıl ve ay onaylı belirtiminin olacak. Bu makro konu olmalıdır bir **#define** veya **#undef** ön işleme yönergesi.

```
#ifdef _OPENMP
iam = omp_get_thread_num() + index;
#endif
```

Satıcılar için OpenMP uzantıları tanımlarsanız, bunlar ek önceden tanımlı makrolar belirtebilirsiniz.