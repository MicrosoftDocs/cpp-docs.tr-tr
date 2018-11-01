---
title: 'Nasıl yapılır: C++ Birlikte Çalışması Kullanarak Yapıları Sıralama'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- C++ Interop, structures
- structures [C++], marshaling
- data marshaling [C++], structures
- interop [C++], structures
- marshaling [C++], structures
ms.assetid: c2080200-f983-4d6e-a557-cd870f060a54
ms.openlocfilehash: c44b23bf0f73191b86b4970c57313d9bc38c8b7a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50521339"
---
# <a name="how-to-marshal-structures-using-c-interop"></a>Nasıl yapılır: C++ Birlikte Çalışması Kullanarak Yapıları Sıralama

Bu konuda, Visual C++ birlikte çalışabilirliği bir modeli gösterilmektedir. Daha fazla bilgi için [C++ Çalışabilirliği kullanma (örtük PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md).

Aşağıdaki kod örnekleri kullan [yönetilen, yönetilmeyen](../preprocessor/managed-unmanaged.md) #pragma yönergeleri uygulamak için yönetilen ve yönetilmeyen işlevleri aynı dosyada, ancak bu işlevler ayrı dosyalarında tanımlandıysa aynı şekilde birlikte çalışır. Yalnızca yönetilmeyen işlevleri içeren dosyalar ile derlenmesine gerek yoktur [/CLR (ortak dil çalışma zamanı derlemesi)](../build/reference/clr-common-language-runtime-compilation.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, bir yapı yönetilen bir işlevden yönetilmeyen bir işleve, hem değere göre ve başvuruya göre geçirme gösterir. Bu örnekte yapısı yalnızca basit, iç veri türleri içerdiğinden (bkz [blok halinde kopyalanabilir ve örnekteki](/dotnet/framework/interop/blittable-and-non-blittable-types)), herhangi bir özel sıralama gereklidir. Gibi işaretçiler içeren bu blittable olmayan yapılar hazırlamak için bkz. [nasıl yapılır: hazırlama katıştırılmış işaretçiler kullanarak C++ birlikte çalışması](../dotnet/how-to-marshal-embedded-pointers-using-cpp-interop.md).

```
// PassStruct1.cpp
// compile with: /clr

#include <stdio.h>
#include <math.h>

using namespace System;
using namespace System::Runtime::InteropServices;

#pragma unmanaged

struct Location {
   int x;
   int y;
};

double GetDistance(Location loc1, Location loc2) {
   printf_s("[unmanaged] loc1(%d,%d)", loc1.x, loc1.y);
   printf_s(" loc2(%d,%d)\n", loc2.x, loc2.y);

   double h = loc1.x - loc2.x;
   double v = loc1.y = loc2.y;
   double dist = sqrt( pow(h,2) + pow(v,2) );

   return dist;
}

void InitLocation(Location* lp) {
   printf_s("[unmanaged] Initializing location...\n");
   lp->x = 50;
   lp->y = 50;
}

#pragma managed

int main() {
   Location loc1;
   loc1.x = 0;
   loc1.y = 0;

   Location loc2;
   loc2.x = 100;
   loc2.y = 100;

   double dist = GetDistance(loc1, loc2);
   Console::WriteLine("[managed] distance = {0}", dist);

   Location loc3;
   InitLocation(&loc3);
   Console::WriteLine("[managed] x={0} y={1}", loc3.x, loc3.y);
}
```

## <a name="example"></a>Örnek

Aşağıdaki örnek, bir yapının bir yönetilmeyen disklerden yönetilen bir işleve hem değere göre ve başvuruya göre geçirme gösterir. Bu örnekte yapısı yalnızca basit, iç veri türleri içerdiğinden (bkz [blok halinde kopyalanabilir ve örnekteki](/dotnet/framework/interop/blittable-and-non-blittable-types)), hiçbir özel dizimi gereklidir. Gibi işaretçiler içeren bu blittable olmayan yapılar hazırlamak için bkz. [nasıl yapılır: hazırlama katıştırılmış işaretçiler kullanarak C++ birlikte çalışması](../dotnet/how-to-marshal-embedded-pointers-using-cpp-interop.md).

```
// PassStruct2.cpp
// compile with: /clr
#include <stdio.h>
#include <math.h>
using namespace System;

// native structure definition
struct Location {
   int x;
   int y;
};

#pragma managed

double GetDistance(Location loc1, Location loc2) {
   Console::Write("[managed] got loc1({0},{1})", loc1.x, loc1.y);
   Console::WriteLine(" loc2({0},{1})", loc2.x, loc2.y);

   double h = loc1.x - loc2.x;
   double v = loc1.y = loc2.y;
   double dist = sqrt( pow(h,2) + pow(v,2) );

   return dist;
}

void InitLocation(Location* lp) {
   Console::WriteLine("[managed] Initializing location...");
   lp->x = 50;
   lp->y = 50;
}

#pragma unmanaged

int UnmanagedFunc() {
   Location loc1;
   loc1.x = 0;
   loc1.y = 0;

   Location loc2;
   loc2.x = 100;
   loc2.y = 100;

   printf_s("(unmanaged) loc1=(%d,%d)", loc1.x, loc1.y);
   printf_s(" loc2=(%d,%d)\n", loc2.x, loc2.y);

   double dist = GetDistance(loc1, loc2);
   printf_s("[unmanaged] distance = %f\n", dist);

   Location loc3;
   InitLocation(&loc3);
   printf_s("[unmanaged] got x=%d y=%d\n", loc3.x, loc3.y);

    return 0;
}

#pragma managed

int main() {
   UnmanagedFunc();
}
```

## <a name="see-also"></a>Ayrıca Bkz.

[C++ Birlikte Çalışabilirliği Kullanma (Örtük PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)