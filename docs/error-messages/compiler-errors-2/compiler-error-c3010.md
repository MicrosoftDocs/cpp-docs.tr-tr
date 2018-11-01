---
title: Derleyici Hatası C3010
ms.date: 11/04/2016
f1_keywords:
- C3010
helpviewer_keywords:
- C3010
ms.assetid: e959d038-bba6-432a-9c0a-0470474de7d9
ms.openlocfilehash: c5f0d33632cb155b8365c8de421fa5eaf91421c6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50455503"
---
# <a name="compiler-error-c3010"></a>Derleyici Hatası C3010

'etiketi': OpenMP yapısal bloğunun izin dışına atlamaya

Kod içine veya bir OpenMP bloğunun dışına atlama olamaz.

Aşağıdaki örnek, C3010 oluşturur:

```
// C3010.c
// compile with: /openmp
int main() {
   #pragma omp parallel
   {
      #pragma omp parallel
      {
         goto lbl3;
      }
   }
   lbl3:;   // C3010
}
```