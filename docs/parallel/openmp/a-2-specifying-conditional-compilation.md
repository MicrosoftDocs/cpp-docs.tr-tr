---
title: A.2   Koşullu Derlemeyi Belirtme
ms.date: 11/04/2016
ms.assetid: de4a21b9-f987-4738-9f13-c4795f6f2dff
ms.openlocfilehash: 92ae22ffac1b1a1c3fc45a9a7a883203ff6d251e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50491227"
---
# <a name="a2---specifying-conditional-compilation"></a>A.2   Koşullu Derlemeyi Belirtme

Aşağıdaki örnekler OpenMP makrosu kullanarak koşullu derleme kullanımını gösterir `_OPENMP` ([bölümü 2.2](../../parallel/openmp/2-2-conditional-compilation.md) sayfasında 8). OpenMP derleme ile `_OPENMP` olur Makro tanımlı.

```
# ifdef _OPENMP
    printf_s("Compiled by an OpenMP-compliant implementation.\n");
# endif
```

Tek bir yönergesinde test edilecek birden fazla Makro tanımlı önişlemci işleci sağlar.

```
# if defined(_OPENMP) && defined(VERBOSE)
    printf_s("Compiled by an OpenMP-compliant implementation.\n");
# endif
```