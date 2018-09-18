---
title: Derleyici Hatası C2660 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2660
dev_langs:
- C++
helpviewer_keywords:
- C2660
ms.assetid: 2e01a1db-4f00-4df6-a04d-cb6f70a6922b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 389e56c778a626572d0254324791af17a3108622
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46042471"
---
# <a name="compiler-error-c2660"></a>Derleyici Hatası C2660

'function': işlev numarası parametreler almaz

İşlev, yanlış sayıda parametre ile çağrılır.

Aynı ada sahip bir MFC üye işlevi yerine Windows API işlevi yanlışlıkla çağırırsanız C2660 ortaya çıkabilir. Bu sorunu çözmek için:

- Üye işlev çağrısı biçimine uygun olması için işlev çağrısı yapın.

- Kapsam çözümleme işlecini kullanın (`::`) işlev adı genel ad alanında aranacak derleyici söylemek için.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C2660 oluşturur.

```
// C2660.cpp
void func( int, int ) {}

int main() {
   func( 1 );   // C2660 func( int ) not declared
   func( 1, 0 );   // OK
}
```

## <a name="example"></a>Örnek

Yönetilen bir tür olan Dispose yöntemini doğrudan çağırmak çalışırsanız C2660 da meydana gelebilir. Daha fazla bilgi için [yok ediciler ve sonlandırıcılar](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers). Aşağıdaki örnek, C2660 oluşturur.

```
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

Türetilmiş bir sınıf bir işlev gizliyor C2660 meydana gelir.

```
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

Dizini oluşturulmuş özelliğe yanlış çağırma C2660 oluşabilir.

```
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

Dizini oluşturulmuş özelliğe yanlış çağırma C2660 oluşabilir.

```
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

New işleci bir şablon sınıfı tanımlarsanız ancak yeni işleç kapsayan türdeki dışında türü olan bir nesne oluşturur, C2660 ortaya çıkabilir.

```
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