---
title: Derleyici hatası C3899
ms.date: 11/04/2016
f1_keywords:
- C3899
helpviewer_keywords:
- C3899
ms.assetid: 14e07e4a-f7a7-4309-baaa-649d69e12e23
ms.openlocfilehash: 022bc1a37f7d9cfdb2c206592dd303a9c3c95080
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74749119"
---
# <a name="compiler-error-c3899"></a>Derleyici hatası C3899

' var ': initonly veri üyesinin lvalue kullanımına doğrudan ' class ' sınıfındaki bir paralel bölgenin içinde izin verilmez

Bir [initonly (C++/CLI)](../../dotnet/initonly-cpp-cli.md) veri üyesi, bir [paralel](../../parallel/openmp/reference/parallel.md) bölgedeki oluşturucunun bu bölümü içinde başlatılamaz.  Bunun nedeni, derleyicinin bu kodun dahili bir konum değiştirme işlemi yaptığı, yani artık oluşturucunun bir parçası olmadığı için.

Çözümlemek için, oluşturucuda initonly veri üyesini, ancak paralel bölgenin dışına başlatın.

## <a name="example"></a>Örnek

Aşağıdaki örnek C3899 oluşturur.

```cpp
// C3899.cpp
// compile with: /clr /openmp
#include <omp.h>

public ref struct R {
   initonly int x;
   R() {
      x = omp_get_thread_num() + 1000;   // OK
      #pragma omp parallel num_threads(5)
      {
         // cannot assign to 'x' here
         x = omp_get_thread_num() + 1000;   // C3899
         System::Console::WriteLine("thread {0}", omp_get_thread_num());
      }
      x = omp_get_thread_num() + 1000;   // OK
   }
};

int main() {
   R^ r = gcnew R;
   System::Console::WriteLine(r->x);
}
```
