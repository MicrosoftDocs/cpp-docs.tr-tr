---
title: Derleyici Hatası C3038
ms.date: 11/04/2016
f1_keywords:
- C3038
helpviewer_keywords:
- C3038
ms.assetid: 140ada3e-5636-43ef-a4ee-22a9f66a771f
ms.openlocfilehash: 0baceeec9911181d9b21c53edf55b73686801316
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62350159"
---
# <a name="compiler-error-c3038"></a>Derleyici Hatası C3038

'var': 'private' yan tümcesindeki değişken kapsayan bağlamda bir azaltma değişkeni olamaz

Görünen değişkenleri [azaltma](../../parallel/openmp/reference/reduction.md) paralel bir yönerge yan tümcesi belirtilemez bir [özel](../../parallel/openmp/reference/private-openmp.md) iş paylaşım için paralel yapı bağlayan bir yönerge yan tümcesi.

Aşağıdaki örnek, C3038 oluşturur:

```
// C3038.cpp
// compile with: /openmp /c
int g_i, g_i2;

int main() {
   int i;

   #pragma omp parallel reduction(+: g_i)
   {
      #pragma omp for private(g_i)   // C3038
      // try the following line instead
      // #pragma omp for private(g_i2)
      for (i = 0; i < 10; ++i)
         g_i += i;
   }
}
```