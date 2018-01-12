---
title: "Derleyici Hatası C2039 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2039
dev_langs: C++
helpviewer_keywords: C2039
ms.assetid: f9dfd521-9b36-4454-a69c-d63f45b606bb
caps.latest.revision: "19"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 753ba66cfbc20e19bab5351ff67d9e6f8cc3a392
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2039"></a>Derleyici Hatası C2039
'identifier1': 'identifier2' üyesi değil  
  
 Kodu yanlış çağıran veya yapısı, sınıf veya birleşim üyesine başvuruyor.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C2039 oluşturur.  
  
```  
// C2039.cpp  
struct S {  
   int mem0;  
} s, *pS = &s;  
  
int main() {  
   pS->mem1 = 0;   // C2039 mem1 is not a member  
   pS->mem0 = 0;   // OK  
}  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C2039 oluşturur.  
  
```  
// C2039_b.cpp  
// compile with: /clr  
using namespace System;  
int main() {  
   Console::WriteLine( "{0}", DateTime::get_Now());   // C2039  
   Console::WriteLine( "{0}", DateTime::Now);   // OK  
   Console::WriteLine( "{0}", DateTime::Now::get());   // OK  
}  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C2039 oluşturur.  
  
```  
// C2039_c.cpp  
// compile with: /clr /c  
ref struct S {  
   property int Count {  
     int get();  
     void set(int i){}  
   };  
};  
  
int S::get_Count() { return 0; }   // C2039  
int S::Count::get() { return 0; }   // OK  
```  
  
## <a name="example"></a>Örnek  
 Varsayılan dizin oluşturucu yanlış erişme girişimi C2039 de ortaya çıkabilir. Aşağıdaki örnek, C# dilinde yazılmış bir bileşen tanımlar.  
  
```  
// C2039_d.cs  
// compile with: /target:library  
// a C# program  
[System.Reflection.DefaultMember("Item")]  
public class B {  
   public int Item {  
      get { return 13; }  
      set {}  
   }  
};  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C2039 oluşturur.  
  
```  
// C2039_e.cpp  
// compile with: /clr  
using namespace System;  
#using "c2039_d.dll"  
  
int main() {  
   B ^ b = gcnew B;  
   int n = b->default;   // C2039  
   // try the following line instead  
   // int n = b->Item;  
   Console::WriteLine(n);  
}  
```  
  
## <a name="example"></a>Örnek  
 Genel türler kullanırsanız C2039 da oluşabilir. Aşağıdaki örnek C2039 oluşturur.  
  
```  
// C2039_f.cpp  
// compile with: /clr  
interface class I {};  
  
ref struct R : public I {  
   virtual void f3() {}  
};  
  
generic <typename T>  
where T : I  
void f(T t) {  
   t->f3();   // C2039  
   safe_cast<R^>(t)->f3();   // OK  
}  
  
int main() {  
   f(gcnew R());  
}  
```  
  
## <a name="example"></a>Örnek  
 Yönetilen veya yönetilmeyen kaynakları serbest bırakmak çalıştığınızda C2039 ortaya çıkabilir. Daha fazla bilgi için bkz: [yok ediciler ve sonlandırıcılar](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers).  
  
 Aşağıdaki örnek C2039 oluşturur.  
  
```  
// C2039_g.cpp  
// compile with: /clr  
using namespace System;  
using namespace System::Threading;  
  
void CheckStatus( Object^ stateInfo ) {}  
  
int main() {  
   ManualResetEvent^ event = gcnew ManualResetEvent( false );     
   TimerCallback^ timerDelegate = gcnew TimerCallback( &CheckStatus );  
   Timer^ stateTimer = gcnew Timer( timerDelegate, event, 1000, 250 );  
  
   ((IDisposable ^)stateTimer)->Dispose();   // C2039  
  
   stateTimer->~Timer();   // OK  
}  
```