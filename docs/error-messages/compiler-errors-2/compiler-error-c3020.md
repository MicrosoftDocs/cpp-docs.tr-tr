---
title: Derleyici hatası C3020
ms.date: 11/04/2016
f1_keywords:
- C3020
helpviewer_keywords:
- C3020
ms.assetid: f625c7a3-afaa-4bd8-9c1b-51891b832f36
ms.openlocfilehash: 89b28ae396322859596b99ba56a28375e9c9d6d5
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87232033"
---
# <a name="compiler-error-c3020"></a>Derleyici hatası C3020

' var ': OpenMP ' for ' döngüsünün dizin değişkeni döngü gövdesinde değiştirilemez

Bir OpenMP **`for`** döngüsü, döngünün gövdesinde dizini (döngü sayacı) değiştiremeyebilir **`for`** .

Aşağıdaki örnek C3020 oluşturur:

```cpp
// C3020.cpp
// compile with: /openmp
int main() {
   int i = 0, n = 3;

   #pragma omp parallel
   {
      #pragma omp for
      for (i = 0; i < 10; i += n)
         i *= 2;   // C3020
         // try the following line instead
         // n++;
   }
}
```

[Lastprivate](../../parallel/openmp/reference/lastprivate.md) ile belirtilen bir değişken, paralelleştirilmiş bir döngü içinde dizin olarak kullanılamaz.

Bu lastprivate, en dıştaki for döngüsünde idx_a bir yazma tetikleyeceği için aşağıdaki örnek ikinci lastprivate için C3020 verecektir. Lastprivate, en dıştaki for döngüsünün dışına idx_a bir yazma tetiklediği için ilk lastprivate bir hata vermez (Teknik olarak son yinelemenin çok sonunda). Aşağıdaki örnek C3020 oluşturur.

```cpp
// C3020b.cpp
// compile with: /openmp /c
float a[100][100];
int idx_a, idx_b;
void test(int first, int last)
{
   #pragma omp parallel for lastprivate(idx_a)
   for (idx_a = first; idx_a <= last; ++idx_a) {
      #pragma omp parallel for lastprivate(idx_a)   // C3020
      for (idx_b = first; idx_b <= last; ++idx_b) {
         a[idx_a][idx_b] += 1.0f;
      }
   }
}
```

Aşağıdaki örnekte olası bir çözüm gösterilmektedir:

```cpp
// C3020c.cpp
// compile with: /openmp /c
float a[100][100];
int idx_a, idx_b;
void test(int first, int last)
{
   #pragma omp parallel for lastprivate(idx_a)
   for (idx_a = first; idx_a <= last; ++idx_a) {
      #pragma omp parallel for lastprivate(idx_b)
      for (idx_b = first; idx_b <= last; ++idx_b) {
         a[idx_a][idx_b] += 1.0f;
      }
   }
}
```
