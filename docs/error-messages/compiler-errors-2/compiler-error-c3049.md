---
title: Derleyici hatası C3049
ms.date: 11/04/2016
f1_keywords:
- C3049
helpviewer_keywords:
- C3049
ms.assetid: 6ddf54f6-2c30-4d04-b637-98c6c922c533
ms.openlocfilehash: 994940b8d8b8cf7905ec635aef95c7d8069592d2
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74761305"
---
# <a name="compiler-error-c3049"></a>Derleyici hatası C3049

' arg ': OpenMP ' default ' yan tümcesinde geçersiz bağımsız değişken

[Varsayılan](../../parallel/openmp/reference/default-openmp.md) bir yan tümcesine yanlış bir değer geçirildi.

Aşağıdaki örnek C3049 oluşturur:

```cpp
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
