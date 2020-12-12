---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3017'
title: Derleyici hatası C3017
ms.date: 11/04/2016
f1_keywords:
- C3017
helpviewer_keywords:
- C3017
ms.assetid: 12ab2c2a-d0d2-4900-9cbf-39be0af590dd
ms.openlocfilehash: bbfffbb9d9f9b0c34dbf0dab57c28d7fd6892fd9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97285844"
---
# <a name="compiler-error-c3017"></a>Derleyici hatası C3017

OpenMP ' for ' deyimindeki sonlandırma testi yanlış biçimde

**`for`** Bir OpenMP deyimindeki bir döngü tam olarak ve açıkça belirtilmelidir.

Aşağıdaki örnek C3017 oluşturur:

```cpp
// C3017.cpp
// compile with: /openmp
int main()
{
   int i = 0, j = 10;

   #pragma omp parallel
   {
      #pragma omp for
      for (i = 0; i; ++i)   // C3017
      // Try the following line instead:
      // for (i = 0; i < 10; ++i)
         ;
   }
}
```
