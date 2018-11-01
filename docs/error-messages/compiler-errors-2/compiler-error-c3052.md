---
title: Derleyici Hatası C3052
ms.date: 11/04/2016
f1_keywords:
- C3052
helpviewer_keywords:
- C3052
ms.assetid: 87480c42-1ceb-4775-8d20-88c54a7bb6a6
ms.openlocfilehash: ed9c27e1602f9372cb9137615ef66932a8df960c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50441840"
---
# <a name="compiler-error-c3052"></a>Derleyici Hatası C3052

'var': değişken bir default(none) yan tümcesi altında bir veri paylaşımı yan tümcesinde görünmüyor

Varsa [default(none)](../../parallel/openmp/reference/default-openmp.md) olan kullanıldığında, yapılandırılmış bloğunda kullanılan herhangi bir değişken açıkça olarak belirtilmelidir [paylaşılan](../../parallel/openmp/reference/shared-openmp.md) veya [özel](../../parallel/openmp/reference/private-openmp.md).

Aşağıdaki örnek, C3052 oluşturur:

```
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