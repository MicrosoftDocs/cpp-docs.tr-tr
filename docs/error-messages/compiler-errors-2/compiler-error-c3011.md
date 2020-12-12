---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3011'
title: Derleyici hatası C3011
ms.date: 11/04/2016
f1_keywords:
- C3011
helpviewer_keywords:
- C3011
ms.assetid: 24c3a917-ebff-4deb-9155-23adf6468531
ms.openlocfilehash: 3a8591ad528c68bb5d072049e2b85567699fc5c8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97286039"
---
# <a name="compiler-error-c3011"></a>Derleyici hatası C3011

doğrudan bir paralel bölgenin içinde satır içi derlemeye izin verilmiyor

`omp`Paralel bölge satır içi derleme yönergeleri içeremez.

Aşağıdaki örnek C3011 oluşturur:

```cpp
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
