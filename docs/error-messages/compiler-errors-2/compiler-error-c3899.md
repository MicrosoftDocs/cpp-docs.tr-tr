---
title: Derleyici Hatası C3899 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3899
dev_langs:
- C++
helpviewer_keywords:
- C3899
ms.assetid: 14e07e4a-f7a7-4309-baaa-649d69e12e23
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b154941051e1c6887e8e05756befd6a18c62ed72
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46091789"
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