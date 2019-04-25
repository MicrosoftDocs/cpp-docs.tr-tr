---
title: Derleyici Hatası C3044
ms.date: 11/04/2016
f1_keywords:
- C3044
helpviewer_keywords:
- C3044
ms.assetid: 9f3e25b2-4676-49ab-97bf-6c88cd0fa377
ms.openlocfilehash: 0fb63d63ce9bdf0979382887164056dcdb288bd2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62187583"
---
# <a name="compiler-error-c3044"></a>Derleyici Hatası C3044

'bölüm': yalnızca bir OpenMP 'sections' yönergesinin altında doğrudan iç içe

Derleyicinin bulunan bir `section` yönergesi yanlış kullanıldı. Daha fazla bilgi için [bölümleri](../../parallel/openmp/reference/sections-openmp.md).

Aşağıdaki örnek, C3044 oluşturur:

```
// C3044.cpp
// compile with: /openmp /c
#include "omp.h"
int main() {
   int n2 = 2, n3 = 3;

   #pragma omp parallel
   {
      ++n2;

      #pragma omp sections
      {
         ++n2;
      }

      #pragma omp section   // C3044
      {
         ++n3;
      }
   }

   #pragma omp parallel
   {
      ++n2;

      #pragma omp sections
      {
         #pragma omp section   // OK
         {
            ++n3;
         }
      }
   }
}
```