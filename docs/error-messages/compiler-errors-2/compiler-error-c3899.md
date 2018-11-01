---
title: Derleyici Hatası C3899
ms.date: 11/04/2016
f1_keywords:
- C3899
helpviewer_keywords:
- C3899
ms.assetid: 14e07e4a-f7a7-4309-baaa-649d69e12e23
ms.openlocfilehash: 26860ba0e8fd92f491ee389147605ba82cecf25c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50598399"
---
# <a name="compiler-error-c3899"></a>Derleyici Hatası C3899

'var': initonly veri üyesinin lvalue kullanımına doğrudan 'class' sınıfındaki bir paralel bölgenin içinde izin verilmez

Bir [initonly (C + +/ CLI)](../../dotnet/initonly-cpp-cli.md) veri üyesi içinde bir parçası olan bir oluşturucu başlatılamıyor bir [paralel](../../parallel/openmp/reference/parallel.md) bölge.  Derleyici bu kod, dahili bir yeniden konumlandırma gerçekleştirdiğinden etkili bir şekilde artık Oluşturucusu bir parçası olduğu gibi budur.

Çözümlenecek, initonly veri üyesi Oluşturucu, ancak bir paralel bölgenin dışında başlatın.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3899 oluşturur.

```
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