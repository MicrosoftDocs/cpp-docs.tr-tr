---
title: Derleyici Hatası C3045
ms.date: 11/04/2016
f1_keywords:
- C3045
helpviewer_keywords:
- C3045
ms.assetid: 9351ba3e-3d3f-455f-ac90-a810fa9fd947
ms.openlocfilehash: 9beae880d840f1cd1ac73f51ebeac8883882dd92
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64345551"
---
# <a name="compiler-error-c3045"></a>Derleyici Hatası C3045

Bir bileşik deyim bekleniyordu OpenMP 'sections' yönergesinden sonra. Eksik ' {'

Ayraç içinde virgülle ayrılmış bir kod bloğu izlemeniz gereken bir [bölümleri](../../parallel/openmp/reference/sections-openmp.md) yönergesi.

Aşağıdaki örnek, C3045 oluşturur:

```
// C3045.cpp
// compile with: /openmp /c
#include "omp.h"

int main() {
   int n2 = 2, n3 = 3;

   #pragma omp parallel
   {
      ++n2;

      #pragma omp sections
         ++n2;   // C3045

      #pragma omp sections   // OK
      {
         ++n3;
      }
   }
}
```