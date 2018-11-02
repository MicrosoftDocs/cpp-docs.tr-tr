---
title: Derleyici Hatası C3049
ms.date: 11/04/2016
f1_keywords:
- C3049
helpviewer_keywords:
- C3049
ms.assetid: 6ddf54f6-2c30-4d04-b637-98c6c922c533
ms.openlocfilehash: ca8481eb06a7ec679b27a446bf738f2ad018f79d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50526366"
---
# <a name="compiler-error-c3049"></a>Derleyici Hatası C3049

'değişken': OpenMP 'default' yan tümcesinde geçersiz bağımsız değişken

Yanlış bir değer geçildi bir [varsayılan](../../parallel/openmp/reference/default-openmp.md) yan tümcesi.

Aşağıdaki örnek, C3049 oluşturur:

```
// C3049.cpp
// compile with: /openmp /c
int main() {
   int n1 = 1;

   #pragma omp parallel default(private)   // C3049
   // try the following line instead
   // #pragma omp parallel default(shared)
   {
      ++n1;
   }
}
```