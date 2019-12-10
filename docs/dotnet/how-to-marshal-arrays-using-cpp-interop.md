---
title: 'Nasıl yapılır: C++ Birlikte Çalışması Kullanarak Dizileri Sıralama'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- arrays [C++], marshaling
- marshaling [C++], arrays
- interop [C++], arrays
- C++ Interop, arrays
- data marshaling [C++], arrays
ms.assetid: c2b37ab1-8acf-4855-ad3c-7d2864826b14
ms.openlocfilehash: fddb8b4fa645d6fee3597d098fc67a3006603b9f
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/10/2019
ms.locfileid: "74988194"
---
# <a name="how-to-marshal-arrays-using-c-interop"></a>Nasıl yapılır: C++ Birlikte Çalışması Kullanarak Dizileri Sıralama

Bu konuda, Visual C++ birlikte çalışabilirlik 'nin bir modeli gösterilmektedir. Daha fazla bilgi için bkz [. C++ birlikte çalışabilirliği kullanma (örtük PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md).

Aşağıdaki kod örnekleri, yönetilen ve yönetilmeyen işlevleri aynı dosyada uygulamak için [yönetilen, yönetilmeyen](../preprocessor/managed-unmanaged.md) #pragma yönergelerini kullanır, ancak bu işlevler ayrı dosyalarda tanımlanmışsa aynı şekilde çalışır. Yalnızca yönetilmeyen işlevleri içeren dosyaların [/clr (ortak dil çalışma zamanı derlemesi)](../build/reference/clr-common-language-runtime-compilation.md)ile derlenmesi gerekmez.

## <a name="example"></a>Örnek

Aşağıdaki örnek, yönetilen bir dizinin yönetilmeyen bir işleve nasıl geçirileceğini gösterir. Yönetilen işlev, yönetilmeyen işlevi çağırmadan önce dizi için çöp toplamayı bastırmak üzere [pin_ptr (C++/CLI)](../extensions/pin-ptr-cpp-cli.md) kullanır. GC yığınına sabitlenmiş bir işaretçi ile yönetilmeyen işlev sağlayarak dizinin bir kopyasını oluşturma yükü kaçınılabilir. Yönetilmeyen işlevin GC yığın belleğine eriştiğini göstermek için, dizinin içeriğini değiştirir ve yönetilen işlev denetimi sürdürüyorsa değişiklikler yansıtılır.

```cpp
// PassArray1.cpp
// compile with: /clr
#ifndef _CRT_RAND_S
#define _CRT_RAND_S
#endif

#include <iostream>
#include <stdlib.h>
using namespace std;

using namespace System;

#pragma unmanaged

void TakesAnArray(int* a, int c) {
   cout << "(unmanaged) array received:\n";
   for (int i=0; i<c; i++)
      cout << "a[" << i << "] = " << a[i] << "\n";

   unsigned int number;
   errno_t err;

   cout << "(unmanaged) modifying array contents...\n";
   for (int i=0; i<c; i++) {
      err = rand_s( &number );
      if ( err == 0 )
         a[i] = number % 100;
   }
}

#pragma managed

int main() {
   array<int>^ nums = gcnew array<int>(5);

   nums[0] = 0;
   nums[1] = 1;
   nums[2] = 2;
   nums[3] = 3;
   nums[4] = 4;

   Console::WriteLine("(managed) array created:");
   for (int i=0; i<5; i++)
      Console::WriteLine("a[{0}] = {1}", i, nums[i]);

   pin_ptr<int> pp = &nums[0];
   TakesAnArray(pp, 5);

   Console::WriteLine("(managed) contents:");
   for (int i=0; i<5; i++)
      Console::WriteLine("a[{0}] = {1}", i, nums[i]);
}
```

## <a name="example"></a>Örnek

Aşağıdaki örnek, yönetilmeyen bir dizinin yönetilen bir işleve geçirilmesini gösterir. Yönetilen işlev, dizi belleğine doğrudan erişir (yönetilen bir diziyi oluşturma ve dizi içeriğini kopyalama aksine), yönetilen işlev tarafından yapılan değişikliklerin, bir denetim sırasında yönetilmeyen işlevde yansıtılmasına olanak tanır.

```cpp
// PassArray2.cpp
// compile with: /clr
#include <iostream>
using namespace std;

using namespace System;

#pragma managed

void ManagedTakesAnArray(int* a, int c) {
   Console::WriteLine("(managed) array received:");
   for (int i=0; i<c; i++)
      Console::WriteLine("a[{0}] = {1}", i, a[i]);

   cout << "(managed) modifying array contents...\n";
   Random^ r = gcnew Random(DateTime::Now.Second);
   for (int i=0; i<c; i++)
      a[i] = r->Next(100);
}

#pragma unmanaged

void NativeFunc() {
   int nums[5] = { 0, 1, 2, 3, 4 };

   printf_s("(unmanaged) array created:\n");
   for (int i=0; i<5; i++)
      printf_s("a[%d] = %d\n", i, nums[i]);

   ManagedTakesAnArray(nums, 5);

   printf_s("(ummanaged) contents:\n");
   for (int i=0; i<5; i++)
      printf_s("a[%d] = %d\n", i, nums[i]);
}

#pragma managed

int main() {
   NativeFunc();
}
```

## <a name="see-also"></a>Ayrıca bkz.

[C++ Birlikte Çalışabilirliği Kullanma (Örtük PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)
