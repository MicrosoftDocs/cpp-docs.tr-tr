---
description: 'Daha fazla bilgi edinin: önemli hata C1310'
title: Önemli hata C1310
ms.date: 11/04/2016
f1_keywords:
- C1310
helpviewer_keywords:
- C1310
ms.assetid: ac48aa51-8023-42fe-b844-3f8bf228fbef
ms.openlocfilehash: edd4cb75c77ec272ddd3f985b4bfefac93e04e83
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97177763"
---
# <a name="fatal-error-c1310"></a>Önemli hata C1310

Profil temelli iyileştirmeler OpenMP ile kullanılamaz

[/GL](../../build/reference/gl-whole-program-optimization.md)ile derlenen [/LTCG: PGi](../../build/reference/ltcg-link-time-code-generation.md) any modülle bağlantı oluşturabileceksiniz.

Aşağıdaki örnek C1310 oluşturur:

```cpp
// C1310.cpp
// compile with: /openmp /GL /link /LTCG:PGI
// C1310 expected
int main()
{
   int i = 0, j = 10;

   #pragma omp parallel
   {
      #pragma omp for
      for (i = 0; i < 0; i++)
         --j;
   }
}
```
