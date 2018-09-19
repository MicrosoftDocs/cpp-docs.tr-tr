---
title: Derleyici Hatası C2039 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2039
dev_langs:
- C++
helpviewer_keywords:
- C2039
ms.assetid: f9dfd521-9b36-4454-a69c-d63f45b606bb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2896a6d98b49802676b1b5a8966a8e0d130a24fe
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46091237"
---
# <a name="compiler-error-c2039"></a>Derleyici Hatası C2039

'ıdentifier1': 'identifier2' üyesi değil

Yanlış kod çağırır veya yapısı, sınıf veya birleşim üyesi için ifade eder.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C2039 oluşturur.

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

Aşağıdaki örnek, C2039 oluşturur.

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

Aşağıdaki örnek, C2039 oluşturur.

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

Varsayılan dizin oluşturucu yanlış erişmeye çalışırsanız C2039 da meydana gelebilir. Aşağıdaki örnek, C# dilinde yazılmış bir bileşeni tanımlar.

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

Aşağıdaki örnek, C2039 oluşturur.

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

Genel türler kullanırsanız C2039 da meydana gelebilir. Aşağıdaki örnek, C2039 oluşturur.

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

Yönetilen veya yönetilmeyen kaynaklar serbest bırakılacaksa çalıştığınızda C2039 ortaya çıkabilir. Daha fazla bilgi için [yok ediciler ve sonlandırıcılar](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers).

Aşağıdaki örnek, C2039 oluşturur.

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