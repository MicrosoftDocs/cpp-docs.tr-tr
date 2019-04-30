---
title: Derleyici Hatası C3020
ms.date: 11/04/2016
f1_keywords:
- C3020
helpviewer_keywords:
- C3020
ms.assetid: f625c7a3-afaa-4bd8-9c1b-51891b832f36
ms.openlocfilehash: 0e2d8e70dcc9b23c56a321487cd4b933a1086387
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62386687"
---
# <a name="compiler-error-c3020"></a>Derleyici Hatası C3020

'var': OpenMP 'for' döngüsünün dizin değişkeni döngü gövdesi içinde değiştirilemez

Bir OpenMP `for` döngü gövdesi, dizin (döngü sayacı) değiştiremez `for` döngü.

Aşağıdaki örnek, C3020 oluşturur:

```
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

Bildirilen bir değişken [lastprivate](../../parallel/openmp/reference/lastprivate.md) paralel döngü içinde dizin olarak kullanılamaz.

Aşağıdaki örnek bu lastprivate bir for döngüsü içinde en dıştaki idx_a yazma tetikleyecek çünkü C3020 için ikinci lastprivate sağlayacaktır. Bir for döngüsü (teknik olarak en son yineleme sonuna) dışında en dıştaki idx_a yazma bu lastprivate Tetikleyiciler olduğundan ilk lastprivate hata vermez. Aşağıdaki örnek, C3020 oluşturur.

```
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

Aşağıdaki örnek, olası çözümü göstermektedir:

```
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