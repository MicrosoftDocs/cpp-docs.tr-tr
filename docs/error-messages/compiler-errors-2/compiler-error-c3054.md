---
title: Derleyici Hatası C3054
ms.date: 11/04/2016
f1_keywords:
- C3054
helpviewer_keywords:
- C3054
ms.assetid: 6f4b7ac5-0d12-474b-b611-76ff26ee41ac
ms.openlocfilehash: 1dd6450d661700d9b2f7f94e625abd9ecc64ed08
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "58773001"
---
# <a name="compiler-error-c3054"></a>Derleyici Hatası C3054

'#pragma omp parallel' şu anda bir genel sınıfta veya işlevde desteklenmiyor

Daha fazla bilgi için [genel türler](../../extensions/generics-cpp-component-extensions.md) ve [OpenMP](../../parallel/openmp/openmp-in-visual-cpp.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3054 oluşturur.

```
// C3054.cpp
// compile with: /openmp /clr /c
#include <omp.h>

ref struct MyBaseClass {
   // Delete the following 7 lines to resolve.
   generic <class ItemType>
   void Test(ItemType i) {   // C3054
      #pragma omp parallel num_threads(4)
      {
         int i = omp_get_thread_num();
      }
   }

   // OK
   void Test2() {
      #pragma omp parallel num_threads(4)
      {
         int i = omp_get_thread_num();
      }
   }
};
```