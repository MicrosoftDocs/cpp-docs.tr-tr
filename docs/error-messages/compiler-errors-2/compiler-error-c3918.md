---
title: Derleyici Hatası C3918 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3918
dev_langs:
- C++
helpviewer_keywords:
- C3918
ms.assetid: a8b3a90a-3fe1-4244-a5ff-a31cdae97d98
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8d7111c2c34b4fb367af906156cc1e8b6dd496bb
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46019113"
---
# <a name="compiler-error-c3918"></a>Derleyici Hatası C3918

Kullanım 'member' veri üyesi olmasını gerektirir.

C3918 olayları ile ilgili çeşitli nedenlerle ortaya çıkabilir.

## <a name="example"></a>Örnek

Geçerli bağlamda bir sınıf üyesi olması gerektiğinden C3918 ortaya çıkabilir. Aşağıdaki örnek, C3918 oluşturur.

```
// C3918.cpp
// compile with: /clr /c
public ref class C {
public:
   System::Object ^ o;
   delegate void Del();

   event Del^ MyEvent {
      void add(Del^ev) {
         if ( MyEvent != nullptr) {}   // C3918
         if ( o != nullptr) {}   // OK
   }
   void remove(Del^){}
   }
};
```

## <a name="example"></a>Örnek

Önemsiz bir olay (olay adı artık doğrudan erişim için yedekleme deposu temsilcisini olayı için sağlayacak olan) NULL iade etmeye çalışırsanız C3918 de oluşabilir.

Aşağıdaki örnek, C3918 oluşturur.

```
// C3918_2.cpp
// compile with: /clr /c
using namespace System;
public delegate int MyDel(int);

interface struct IEFace {
   event MyDel ^ E;
};

ref struct EventSource : public IEFace {
   virtual event MyDel ^ E;
   void Fire_E(int i) {
      if (E)   // C3918
         E(i);
   }
};
```

## <a name="example"></a>Örnek

Yanlış bir olaya abone olursanız C3918 da meydana gelebilir. Aşağıdaki örnek, C3918 oluşturur.

```
// C3918_3.cpp
// compile with: /clr /c
using namespace System;

public delegate void del();

public ref class A {
public:
   event del^ e {
      void add(del ^handler ) {
         d += handler;
      }

      void remove(del ^handler) {
         d -= handler;
      }

      void raise() {
         d();
      }
   }

   del^ d;
   void f() {}

   A() {
      e = gcnew del(this, &A::f);   // C3918
      // try the following line instead
      // e += gcnew del(this, &A::f);
      e();
   }
};

int main() {
   A a;
}
```