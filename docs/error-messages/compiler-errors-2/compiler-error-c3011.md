---
title: Derleyici Hatası C3011
ms.date: 11/04/2016
f1_keywords:
- C3011
helpviewer_keywords:
- C3011
ms.assetid: 24c3a917-ebff-4deb-9155-23adf6468531
ms.openlocfilehash: 453af6be844b1a3aa4f0e9c80f6b5733952c1557
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62350315"
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