---
title: 'Nasıl yapılır: C++ Birlikte Çalışmayı Kullanarak Geri Çağrıları ve Temsilcileri Sıralama'
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
ms.openlocfilehash: 592eae0ff59baddb79b810d46669b78ecc801155
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/10/2019
ms.locfileid: "74988191"
---
# <a name="how-to-marshal-callbacks-and-delegates-by-using-c-interop"></a>Nasıl yapılır: C++ Birlikte Çalışmayı Kullanarak Geri Çağrıları ve Temsilcileri Sıralama

Bu konu, Visual C++kullanılarak yönetilen ve yönetilmeyen kod arasında geri çağırmaların ve temsilcilerin (bir geri aramanın yönetilen sürümü) sıralanmasını gösterir.

Aşağıdaki kod örnekleri, yönetilen ve yönetilmeyen işlevleri aynı dosyada uygulamak için [yönetilen, yönetilmeyen](../preprocessor/managed-unmanaged.md) #pragma yönergelerini kullanır, ancak işlevler ayrı dosyalarda de tanımlanabilir. Yalnızca yönetilmeyen işlevleri içeren dosyaların [/clr (ortak dil çalışma zamanı derlemesi)](../build/reference/clr-common-language-runtime-compilation.md)ile derlenmesi gerekmez.

## <a name="example"></a>Örnek

Aşağıdaki örnek, yönetilmeyen bir API 'nin yönetilen bir temsilciyi tetiklemek için nasıl yapılandırılacağını gösterir. Yönetilen bir temsilci oluşturulur ve temsilci için temel alınan giriş noktasını almak için <xref:System.Runtime.InteropServices.Marshal.GetFunctionPointerForDelegate%2A>birlikte çalışma yöntemlerinden biri kullanılır. Bu adres daha sonra yönetilmeyen işleve geçirilir ve bu, yönetilen bir işlev olarak uygulanan olguyla ilgili hiçbir bilgi olmadan onu çağırır.

[Pin_ptr (C++/CLI)](../extensions/pin-ptr-cpp-cli.md) kullanarak temsilciyi, atık toplayıcı tarafından yeniden konumlandırılmasını veya elden çıkarmasını engellemek için, bu mümkün değildir, ancak gerekli değildir. Zamanından önce çöp toplamadan koruma gerekir, ancak sabitleme, koleksiyonu engelliyor, ancak aynı zamanda yeniden konumlandırma işlemini yaptığı için gerekenden daha fazla koruma sağlar.

Bir temsilci bir çöp toplama işlemi tarafından yeniden konumlandırıldığında, yönetilen geri çağırma işlemini etkilemez, bu nedenle <xref:System.Runtime.InteropServices.GCHandle.Alloc%2A> temsilciye bir başvuru eklemek ve temsilcinin yeniden konumlandırılmasını sağlamak için kullanılır. Pin_ptr yerine GCHandle kullanmak, yönetilen yığının parçalanma potansiyelini azaltır.

```cpp
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

Aşağıdaki örnek, önceki örneğe benzerdir, ancak bu durumda, belirtilen işlev işaretçisi yönetilmeyen API tarafından depolanır, bu nedenle herhangi bir zamanda çağrılabilir ve bu da çöp toplamanın rastgele bir süre boyunca bastırılmasını gerektirir. Sonuç olarak, aşağıdaki örnek bir <xref:System.Runtime.InteropServices.GCHandle> genel örneğini kullanır, bu da temsilcinin işlev kapsamından bağımsız olarak yeniden konumlandırılmasını önler. İlk örnekte açıklandığı gibi, bu örneklerde pin_ptr kullanılması gereksizdir, ancak bu durumda, bir pin_ptr kapsamı tek bir işlevle sınırlı olduğu için yine de çalışmaz.

```cpp
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
