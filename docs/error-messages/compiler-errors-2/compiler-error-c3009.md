---
title: Derleyici Hatası C3009
ms.date: 11/04/2016
f1_keywords:
- C3009
helpviewer_keywords:
- C3009
ms.assetid: aded5985-f5fd-4c3e-a157-16be55ec1313
ms.openlocfilehash: a1f4a20396e97c6b868a5678958970813b638499
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50597203"
---
# <a name="compiler-error-c3009"></a>Derleyici Hatası C3009

'etiketi': OpenMP yapısal bloğunun izin içine atlamaya

Kod içine veya bir OpenMP bloğunun dışına atlama olamaz.

Aşağıdaki örnek, C3009 oluşturur:

```
// C3009.c
// compile with: /openmp
int main() {
   #pragma omp parallel
   {
   lbl2:;
   }
   goto lbl2;   // C3009
}
```