---
title: Derleyici hatası C3052
ms.date: 11/04/2016
f1_keywords:
- C3052
helpviewer_keywords:
- C3052
ms.assetid: 87480c42-1ceb-4775-8d20-88c54a7bb6a6
ms.openlocfilehash: 618fac69078987b0322739733c403e5b2cd36486
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74761224"
---
# <a name="compiler-error-c3052"></a>Derleyici hatası C3052

' var ': değişken bir default (None) yan tümcesi altında bir veri paylaşımı yan tümcesinde görünmüyor

[Varsayılan (hiçbiri)](../../parallel/openmp/reference/default-openmp.md) kullanılırsa, Structured bloğunda kullanılan herhangi bir değişken doğrudan [paylaşılan](../../parallel/openmp/reference/shared-openmp.md) veya [özel](../../parallel/openmp/reference/private-openmp.md)olarak belirtilmelidir.

Aşağıdaki örnek C3052 oluşturur:

```cpp
// C3052.cpp
// compile with: /openmp /c
int main() {
   int n1 = 1;

   #pragma omp parallel default(none) // shared(n1) private(n1)
   {
      n1 = 0;   // C3052 use either a shared or private clause
   }
}
```
