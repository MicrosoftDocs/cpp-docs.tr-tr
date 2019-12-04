---
title: Derleyici hatası C3054
ms.date: 11/04/2016
f1_keywords:
- C3054
helpviewer_keywords:
- C3054
ms.assetid: 6f4b7ac5-0d12-474b-b611-76ff26ee41ac
ms.openlocfilehash: 7a35f72be07799f61587c77b511395223ae72939
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74761195"
---
# <a name="compiler-error-c3054"></a>Derleyici hatası C3054

' #pragma omp Parallel ' Şu anda genel bir sınıfta veya işlevde desteklenmiyor

Daha fazla bilgi için bkz. [Genel türler](../../extensions/generics-cpp-component-extensions.md) ve [OpenMP](../../parallel/openmp/openmp-in-visual-cpp.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek C3054 oluşturur.

```cpp
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
