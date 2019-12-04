---
title: Derleyici hatası C3039
ms.date: 11/04/2016
f1_keywords:
- C3039
helpviewer_keywords:
- C3039
ms.assetid: 02776f16-f57a-4ffd-b7f7-9c696b633e08
ms.openlocfilehash: 344fd32e66881c2529ddb1f9185c25752f0a736c
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74754985"
---
# <a name="compiler-error-c3039"></a>Derleyici hatası C3039

' var ': OpenMP ' for ' deyimindeki dizin değişkeni bir azaltma değişkeni olamaz

Dizin değişkeni örtük olarak özeldir, bu nedenle değişken kapsayan [paralel](../../parallel/openmp/reference/parallel.md) yönergedeki bir [azaltma](../../parallel/openmp/reference/reduction.md) yan tümcesinde kullanılamaz.

## <a name="example"></a>Örnek

Aşağıdaki örnek C3039 oluşturur:

```cpp
// C3039.cpp
// compile with: /openmp /c
int g_i;

int main() {
   int i;

   #pragma omp parallel reduction(+: i)
   {
      #pragma omp for
      for (i = 0; i < 10; ++i)   // C3039
         g_i += i;
   }
}
```
