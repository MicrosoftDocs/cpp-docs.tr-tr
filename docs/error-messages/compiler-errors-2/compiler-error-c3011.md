---
title: Derleyici Hatası C3011
ms.date: 11/04/2016
f1_keywords:
- C3011
helpviewer_keywords:
- C3011
ms.assetid: 24c3a917-ebff-4deb-9155-23adf6468531
ms.openlocfilehash: 453af6be844b1a3aa4f0e9c80f6b5733952c1557
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50515784"
---
# <a name="compiler-error-c3011"></a>Derleyici Hatası C3011

Satır içi derleme doğrudan bir paralel bölgenin içinde izin verilmiyor

Bir `omp` paralel bölgenin, satır içi derleme yönergeleri içeremez.

Aşağıdaki örnek, C3011 oluşturur:

```
// C3011.cpp
// compile with: /openmp
// processor: /x86
int main() {
   int   n = 0;

   #pragma omp parallel
   {
      _asm mov eax, n   // Delete this line to resolve this error.
   }   // C3011
}
```