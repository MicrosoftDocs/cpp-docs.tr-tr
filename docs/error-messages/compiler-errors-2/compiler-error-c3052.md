---
title: Derleyici hatası C3052
ms.date: 11/04/2016
f1_keywords:
- C3052
helpviewer_keywords:
- C3052
ms.assetid: 87480c42-1ceb-4775-8d20-88c54a7bb6a6
ms.openlocfilehash: 40857432e07baffea69d8201cc3e0241698c93da
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2020
ms.locfileid: "91506203"
---
# <a name="compiler-error-c3052"></a>Derleyici hatası C3052

' var ': değişken bir default (None) yan tümcesi altında bir veri paylaşımı yan tümcesinde görünmüyor

[Varsayılan (hiçbiri)](../../parallel/openmp/reference/openmp-clauses.md#default-openmp) kullanılırsa, Structured bloğunda kullanılan herhangi bir değişken doğrudan [paylaşılan](../../parallel/openmp/reference/openmp-clauses.md#shared-openmp) veya [özel](../../parallel/openmp/reference/openmp-clauses.md#private-openmp)olarak belirtilmelidir.

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
