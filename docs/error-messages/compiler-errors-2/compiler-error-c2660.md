---
title: Derleyici hatası C2660
ms.date: 11/04/2016
f1_keywords:
- C2660
helpviewer_keywords:
- C2660
ms.assetid: 2e01a1db-4f00-4df6-a04d-cb6f70a6922b
ms.openlocfilehash: febeb75cbde6738bd9079b7bd86f88c521c29e40
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74756064"
---
# <a name="compiler-error-c2660"></a>Derleyici hatası C2660

' function ': işlev sayı parametresi almaz

İşlev yanlış sayıda parametre ile çağırılır.

C2660, aynı ada sahip bir MFC üye işlevi yerine yanlışlıkla bir Windows API işlevini çağırırsanız oluşabilir. Bu sorunu çözmek için:

- İşlev çağrısını üye işlev çağrısının biçimiyle uyumlu olacak şekilde ayarlayın.

- Derleyiciye, genel ad alanında işlev adını arayacaklarını söylemek için kapsam çözümleme işlecini (`::`) kullanın.

## <a name="example"></a>Örnek

Aşağıdaki örnek C2660 oluşturur.

```cpp
// C2660.cpp
void func( int, int ) {}

int main() {
   func( 1 );   // C2660 func( int ) not declared
   func( 1, 0 );   // OK
}
```

## <a name="example"></a>Örnek

C2660, yönetilen bir türün Dispose yöntemini doğrudan çağırmayı denerseniz da oluşabilir. Daha fazla bilgi için bkz. yok [ediciler ve sonlandırıcılar](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers). Aşağıdaki örnek C2660 oluşturur.

```cpp
// C2660_a.cpp
// compile with: /clr
using namespace System;
using namespace System::Threading;

void CheckStatus( Object^ stateInfo ) {}

int main() {
   ManualResetEvent^ event = gcnew ManualResetEvent( false );
   TimerCallback^ timerDelegate = gcnew TimerCallback( &CheckStatus );
   Timer^ stateTimer = gcnew Timer( timerDelegate, event, 1000, 250 );

   stateTimer->Dispose();   // C2660
   stateTimer->~Timer();   // OK
}
```

## <a name="example"></a>Örnek

Türetilmiş bir sınıf bir işlevi gizlediğini C2660 olur.

```cpp
// C2660b.cpp
// C2660 expected
#include <stdio.h>

class f {
public:
   void bar() {
      printf_s("in f::bar\n");
    }
};

class f2 : public f {
public:
   void bar(int i){printf("in f2::bar\n");}
   // Uncomment the following line to resolve.
   // using f::bar;   // - using declaration added
   // or
   // void bar(){__super::bar();}
};

int main() {
   f2 fObject;
   fObject.bar();
}
```

## <a name="example"></a>Örnek

Dizinli bir özelliği yanlış çağırırsanız, C2660 oluşabilir.

```cpp
// C2660c.cpp
// compile with: /clr
ref class X {
   double d;
public:
   X() : d(1.9) {}
   property double MyProp[] {
      double get(int i) {
         return d;
      }
   }   // end MyProp definition
};

int main() {
   X ^ MyX = gcnew X();
   System::Console::WriteLine(MyX->MyProp(1));   // C2660
   System::Console::WriteLine(MyX->MyProp[1]);   // OK
}
```

## <a name="example"></a>Örnek

Dizinli bir özelliği yanlış çağırırsanız, C2660 oluşabilir.

```cpp
// C2660d.cpp
// compile with: /clr
ref class A{
public:
   property int default[int,int] {
      int get(int a, int b) {
         return a + b;
      }
   }
};

int main() {
   A^ a = gcnew A;
   int x = a[3][5];   // C2660
   int x2 = a[3,5];   // OK
}
```

## <a name="example"></a>Örnek

Bir şablon sınıfında yeni bir işleç tanımlarsanız, ancak New işlecinin türü kapsayan türden farklı olan bir nesne oluşturduğunda, C2660 meydana gelebilir.

```cpp
// C2660e.cpp
// compile with: /c
#include <malloc.h>

template <class T> class CA {
private:
    static T** line;
   void* operator new (size_t, int i) {
      return 0;
   }
   void operator delete(void* pMem, int i) {
      free(pMem);
   }

public:
   CA () { new (1) T(); }   // C2660
   // try the following line instead
   // CA () { new (1) CA<int>(); }
};

typedef CA <int> int_CA;

void AAA() {
   int_CA  list;
}
```
