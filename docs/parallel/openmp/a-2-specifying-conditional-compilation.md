---
title: A.2 koşullu derlemeyi belirtme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: de4a21b9-f987-4738-9f13-c4795f6f2dff
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2d8b0f3df67313dbf03d40077a551fe64930199d
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46393704"
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