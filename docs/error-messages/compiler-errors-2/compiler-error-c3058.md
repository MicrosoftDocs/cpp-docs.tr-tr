---
title: Derleyici hatası C3058
ms.date: 11/04/2016
f1_keywords:
- C3058
helpviewer_keywords:
- C3058
ms.assetid: 669d08c8-0b58-4351-88aa-c6e6e1af481c
ms.openlocfilehash: 618c9bd127a4e8a11cd858ab9642a5c52eee8d30
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74761134"
---
# <a name="compiler-error-c3058"></a>Derleyici hatası C3058

' symbol ': simge ' copyin ' yan tümcesinde kullanılmadan önce ' threadprivate ' olarak bildirilmemiş

Bir simgenin bir [copyin](../../parallel/openmp/reference/copyin.md) yan tümcesinde kullanılabilmesi için önce [threadprivate](../../parallel/openmp/reference/threadprivate.md) olarak bildirilmelidir.

Aşağıdaki örnek C3058 oluşturur:

```cpp
// C3058.cpp
// compile with: /openmp
int x, y, z;
#pragma omp threadprivate(x, z)

void test() {
   #pragma omp parallel copyin(x, y)   // C3058
   {
   }
}
```

Olası çözüm:

```cpp
// C3058b.cpp
// compile with: /openmp /LD
int x, y, z;
#pragma omp threadprivate(x, y)

void test() {
   #pragma omp parallel copyin(x, y)
   {
   }
}
```
