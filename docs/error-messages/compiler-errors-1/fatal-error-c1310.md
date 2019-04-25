---
title: Önemli hata C1310
ms.date: 11/04/2016
f1_keywords:
- C1310
helpviewer_keywords:
- C1310
ms.assetid: ac48aa51-8023-42fe-b844-3f8bf228fbef
ms.openlocfilehash: 1b0fca9a5e453fd354a4efc6960a54386795ccf6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62266434"
---
# <a name="fatal-error-c1310"></a>Önemli hata C1310

Profil temelli en iyileştirmeler OpenMP ile kullanılamaz

İle bağlamak mümkün olmayacaktır [/LTCG:PGI](../../build/reference/ltcg-link-time-code-generation.md) ile derlenmiş modüllerde [/GL](../../build/reference/gl-whole-program-optimization.md).

Aşağıdaki örnek, C1310 oluşturur:

```
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