---
title: 'Nasıl yapılır: C++ birlikte çalışmayı kullanarak geri çağrıları ve temsilcileri sıralama'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- data marshaling [C++], callbacks and delegates
- C++ Interop, callbacks and delegates
- interop [C++], callbacks and delegates
- delegates [C++], marshaling
- marshaling [C++], callbacks and delegates
- callbacks [C++], marshaling
ms.assetid: 2313e9eb-5df9-4367-be0f-14b4712d8d2d
ms.openlocfilehash: f8088bf90162fd2177599c252b0eee6332d61289
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58766943"
---
# <a name="how-to-marshal-callbacks-and-delegates-by-using-c-interop"></a>Nasıl yapılır: C++ birlikte çalışmayı kullanarak geri çağrıları ve temsilcileri sıralama

Bu konu geri çağırmaları sıralanabileceği gösterilmektedir ve (bir geri çağırma yönetilen sürümü) Visual C++ kullanarak yönetilen ve yönetilmeyen kod arasında atar.

Aşağıdaki kod örnekleri kullan [yönetilen, yönetilmeyen](../preprocessor/managed-unmanaged.md) #pragma yönergeleri uygulamak için yönetilen ve yönetilmeyen işlevleri aynı dosyada, ancak işlevlerini ayrı dosyalarında de tanımlanabilir. Yalnızca yönetilmeyen işlevleri içeren dosyalar ile derlenmesine gerek yoktur [/CLR (ortak dil çalışma zamanı derlemesi)](../build/reference/clr-common-language-runtime-compilation.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, yönetilen bir temsilci tetiklemek için yönetilmeyen bir API'nin gösterilmiştir. Yönetilen bir temsilci oluşturulur ve birlikte çalışma yöntemi <xref:System.Runtime.InteropServices.Marshal.GetFunctionPointerForDelegate%2A>, temel alınan giriş noktası için temsilci almak için kullanılır. Bu adres, daha sonra yönetilen bir işlev uygulanır olgu olanağıyla ile çağrı yönetilmeyen işleve geçirilir.

Olası, ancak gerekli PIN kullanarak temsilci dikkat [pin_ptr (C++/CLI)](../extensions/pin-ptr-cpp-cli.md) yeniden bulunan veya çöp toplayıcısı tarafından elden önlemek için. Erken çöp toplama korumadan gereklidir, ancak sabitleme koleksiyon engeller ancak aynı zamanda yeniden konumlandırma engeller gerekli olandan daha fazla koruma sağlar.

Bir temsilci bir çöp toplama tarafından yeniden bulunuyorsa, yerleştirildiyse geri çağırma böylece etkilemez <xref:System.Runtime.InteropServices.GCHandle.Alloc%2A> temsilci temsilcinin izin vererek, ancak elden engelleyen bir başvuru eklemek için kullanılır. GCHandle yerine pin_ptr kullanarak yönetilen yığının parçalanma olasılığını azaltır.

```
// MarshalDelegate1.cpp
// compile with: /clr
#include <iostream>

using namespace System;
using namespace System::Runtime::InteropServices;

#pragma unmanaged

// Declare an unmanaged function type that takes two int arguments
// Note the use of __stdcall for compatibility with managed code
typedef int (__stdcall *ANSWERCB)(int, int);

int TakesCallback(ANSWERCB fp, int n, int m) {
   printf_s("[unmanaged] got callback address, calling it...\n");
   return fp(n, m);
}

#pragma managed

public delegate int GetTheAnswerDelegate(int, int);

int GetNumber(int n, int m) {
   Console::WriteLine("[managed] callback!");
   return n + m;
}

int main() {
   GetTheAnswerDelegate^ fp = gcnew GetTheAnswerDelegate(GetNumber);
   GCHandle gch = GCHandle::Alloc(fp);
   IntPtr ip = Marshal::GetFunctionPointerForDelegate(fp);
   ANSWERCB cb = static_cast<ANSWERCB>(ip.ToPointer());
   Console::WriteLine("[managed] sending delegate as callback...");

// force garbage collection cycle to prove
// that the delegate doesn't get disposed
   GC::Collect();

   int answer = TakesCallback(cb, 243, 257);

// release reference to delegate
   gch.Free();
}
```

## <a name="example"></a>Örnek

Aşağıdaki örnek önceki örneğe benzer, ancak bu durumda, herhangi bir zamanda çöp toplama rastgele bir süre atlanması gerektiren etkinleştirilebilir böylece yönetilmeyen API'si tarafından sağlanan işlev işaretçisi depolanır. Sonuç olarak, aşağıdaki örnek, genel bir örneğini kullanır <xref:System.Runtime.InteropServices.GCHandle> temsilciyi yeniden konumlandırılmasını işlev kapsamından bağımsız olarak önlemek için. İlk örnekte açıklandığı gibi pin_ptr kullanarak bu örnekler için gerekli değildir, ancak bir pin_ptr kapsamı tek bir işleve sınırlı olduğu gibi bu durumda yine de çalışmaz.

```
// MarshalDelegate2.cpp
// compile with: /clr
#include <iostream>

using namespace System;
using namespace System::Runtime::InteropServices;

#pragma unmanaged

// Declare an unmanaged function type that takes two int arguments
// Note the use of __stdcall for compatibility with managed code
typedef int (__stdcall *ANSWERCB)(int, int);
static ANSWERCB cb;

int TakesCallback(ANSWERCB fp, int n, int m) {
   cb = fp;
   if (cb) {
      printf_s("[unmanaged] got callback address (%d), calling it...\n", cb);
      return cb(n, m);
   }
   printf_s("[unmanaged] unregistering callback");
   return 0;
}

#pragma managed

public delegate int GetTheAnswerDelegate(int, int);

int GetNumber(int n, int m) {
   Console::WriteLine("[managed] callback!");
   static int x = 0;
   ++x;

   return n + m + x;
}

static GCHandle gch;

int main() {
   GetTheAnswerDelegate^ fp = gcnew GetTheAnswerDelegate(GetNumber);

   gch = GCHandle::Alloc(fp);

   IntPtr ip = Marshal::GetFunctionPointerForDelegate(fp);
   ANSWERCB cb = static_cast<ANSWERCB>(ip.ToPointer());
   Console::WriteLine("[managed] sending delegate as callback...");

   int answer = TakesCallback(cb, 243, 257);

   // possibly much later (in another function)...

   Console::WriteLine("[managed] releasing callback mechanisms...");
   TakesCallback(0, 243, 257);
   gch.Free();
}
```

## <a name="see-also"></a>Ayrıca bkz.

[C++ Birlikte Çalışabilirliği Kullanma (Örtük PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)
