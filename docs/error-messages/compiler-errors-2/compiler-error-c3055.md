---
title: Derleyici hatası C3055
ms.date: 11/04/2016
f1_keywords:
- C3055
helpviewer_keywords:
- C3055
ms.assetid: 60446ee0-18dd-48fc-9059-f0a14229dce8
ms.openlocfilehash: 0bfd045079a7f0fbbd078d3d859d5687e96338dd
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74761178"
---
# <a name="compiler-error-c3055"></a>Derleyici hatası C3055

' symbol ': simgeye ' threadprivate ' yönergesinde kullanılmadan önce simgeye başvurulamaz

Bir simgeye başvuruldu ve bu izin verilmeyen bir [threadprivate](../../parallel/openmp/reference/threadprivate.md) yan tümcesinde kullanılmıştı.

Aşağıdaki örnek C3055 oluşturur:

```cpp
// C3055.cpp
// compile with: /openmp
int x, y;
int z = x;
#pragma omp threadprivate(x, y)   // C3055

void test() {
   #pragma omp parallel copyin(x, y)
   {
      x = y;
   }
}
```

Olası çözüm:

```cpp
// C3055b.cpp
// compile with: /openmp /LD
int x, y, z;
#pragma omp threadprivate(x, y)

void test() {
   #pragma omp parallel copyin(x, y)
   {
      x = y;
   }
}
```
