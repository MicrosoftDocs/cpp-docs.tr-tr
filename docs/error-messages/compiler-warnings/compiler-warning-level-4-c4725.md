---
title: Derleyici Uyarısı (düzey 4) C4725
ms.date: 11/04/2016
f1_keywords:
- C4725
helpviewer_keywords:
- C4725
ms.assetid: effa0335-71c3-4b3b-8618-da4b9b46a95d
ms.openlocfilehash: c86d1a5351adf5ba29752613f2301a11fb1b93ce
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/10/2019
ms.locfileid: "74989514"
---
# <a name="compiler-warning-level-4-c4725"></a>Derleyici Uyarısı (düzey 4) C4725

yönerge bazı bilgisayarlarda yanlış olabilir

Kodunuz, bazı Pentium mikro işlemcilerde doğru sonuçlar üretmeyen bir satır içi derleme yönergesi içeriyor.

Aşağıdaki örnek C4725 oluşturur:

```cpp
// C4725.cpp
// compile with: /W4
// processor: x86
double m32fp = 2.0003e-17;

void f() {
   __asm
   {
      FDIV m32fp   // C4725
   }
}

int main() {
}
```
