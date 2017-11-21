---
title: "Nasıl yapılır: sıralama geri aramalar ve temsilciler C++ birlikte çalışması kullanarak | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: get-started-article
dev_langs: C++
helpviewer_keywords:
- data marshaling [C++], callbacks and delegates
- C++ Interop, callbacks and delegates
- interop [C++], callbacks and delegates
- delegates [C++], marshaling
- marshaling [C++], callbacks and delegates
- callbacks [C++], marshaling
ms.assetid: 2313e9eb-5df9-4367-be0f-14b4712d8d2d
caps.latest.revision: "23"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 2a835dbdbce23f7f92f13fabd038d6e294345981
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="how-to-marshal-callbacks-and-delegates-by-using-c-interop"></a>Nasıl yapılır: C++ Birlikte Çalışmayı Kullanarak Geri Çağrıları ve Temsilcileri Sıralama
Bu konu geri çağrılar sıralanabileceği gösterilmektedir ve (bir geri çağırma yönetilen sürümü) kullanarak Visual C++ yönetilen ve yönetilmeyen kodu arasında atar.  
  
 Aşağıdaki kod örnekleri kullan [yönetilen, yönetilmeyen](../preprocessor/managed-unmanaged.md) uygulamak için #pragma yönergeleri yönetilen ve yönetilmeyen işlevleri aynı dosyada, ancak işlevler ayrı dosyalarda de tanımlanabilir. Yalnızca yönetilmeyen işlevleri içeren dosyalar ile derlenmesi gerekmez [/CLR (ortak dil çalışma zamanı derlemesi)](../build/reference/clr-common-language-runtime-compilation.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, yönetilen bir temsilci tetiklemek için yönetilmeyen bir API'nin gösterilmiştir. Yönetilen bir temsilci oluşturulur ve birlikte çalışma yöntemlerden birini <xref:System.Runtime.InteropServices.Marshal.GetFunctionPointerForDelegate%2A>, temel alınan giriş noktası için temsilci almak için kullanılır. Bu adres, daha sonra yönetilen bir işlevi olarak uygulandığını olgu olanağıyla ile çağırır yönetilmeyen işlevi geçirilir.  
  
 Olası, ancak gerekli PIN kullanarak temsilci dikkat [pin_ptr (C + +/ CLI)](../windows/pin-ptr-cpp-cli.md) yeniden bulunan veya çöp toplayıcı tarafından elden önlemek için. Erken atık toplama korumadan gereklidir, ancak sabitleme, koleksiyon engeller, ancak aynı zamanda yeniden konumlandırma engeller gibi gerekli olandan daha fazla koruma sağlar.  
  
 Temsilci bir atık toplama tarafından yeniden bulunuyorsa, yerleştirildiyse geri çağırma şekilde etkilemez <xref:System.Runtime.InteropServices.GCHandle.Alloc%2A> temsilci konumlandırmasını izin vererek, ancak elden önleme temsilci başvuru eklemek için kullanılır. Pin_ptr yerine GCHandle kullanarak yönetilen yığın parçalanma olasılığı azaltır.  
  
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
 Aşağıdaki örnek önceki örneğe benzer, ancak herhangi bir zamanda bu çağrılabilir atık toplama rasgele bir süre atlanması gerektiren bu durumda sağlanan işlev işaretçisi yönetilmeyen API tarafından depolanır, böylece. Sonuç olarak, aşağıdaki örnek, genel bir örneğini kullanır <xref:System.Runtime.InteropServices.GCHandle> yeniden konumlandırılmasını işlevinin kapsam bağımsız temsilci önlemek için. Pin_ptr kullanarak ilk örnekte açıklandığı gibi bu örnekler için gerekli değildir ancak bir pin_ptr kapsamı tek bir işlev için sınırlı olduğu gibi bu durumda yine de çalışmayacaktır.  
  
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
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ birlikte çalışması (örtük PInvoke) kullanarak](../dotnet/using-cpp-interop-implicit-pinvoke.md)