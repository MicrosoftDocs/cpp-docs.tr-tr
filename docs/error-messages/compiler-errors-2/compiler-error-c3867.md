---
title: Derleyici Hatası C3867 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3867
dev_langs:
- C++
helpviewer_keywords:
- C3867
ms.assetid: bc5de03f-e01a-4407-88c3-2c63f0016a1e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 55545c0353b6d7442bcf3c4721053a60dd2bb6a5
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46019324"
---
# <a name="compiler-error-c3867"></a>Derleyici Hatası C3867

'İşlev': işlev çağrısı; bağımsız değişken listesi eksik Kullan ' & func' bir üyeye işaretçi oluşturmak için

Üye işlevi, sınıf adını ve address-of işlecini nitelemeden bir üye işlevin adresini almak çalıştı.

Bu hata için Visual C++ 2005 yapıldığı derleyici uyumluluğu iş sonucu olarak da oluşturulabilir: Gelişmiş işaretçi-üye uyumluluğu. Visual C++ 2005'ten önce derlenmiş kod artık C3867 oluşturur.

## <a name="example"></a>Örnek

C3867 yanıltıcı bir önerilen çözüm derleyicisinden verilebilir. Mümkün olduğunda, en çok türetilen sınıfı kullanın.

Aşağıdaki örnek, C3867 oluşturur ve bu sorunun nasıl gösterir.

```
// C3867_1.cpp
// compile with: /c
struct Base {
protected:
   void Test() {}
};

class Derived : public Base {
   virtual void Bar();
};

void Derived::Bar() {
   void (Base::*p1)() = Test;   // C3867
   &Derived::Test;   // OK
}
```

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3867 oluşturur ve bu sorunun nasıl gösterir.

```
// C3867_2.cpp
#include<stdio.h>

struct S {
   char *func() {
      return "message";
   }
};

class X {
public:
   void f() {}
};

int main() {
   X::f;   // C3867

   // OK
   X * myX = new X;
   myX->f();

   S s;
   printf_s("test %s", s.func);   // C3867
   printf_s("test %s", s.func());   // OK
}
```

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3867 oluşturur ve bu sorunun nasıl gösterir.

```
// C3867_3.cpp
class X {
public:
   void mf(){}
};

int main() {
   void (X::*pmf)() = X::mf;   // C3867

   // try the following line instead
   void (X::*pmf2)() = &X::mf;
}
```

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3867 oluşturur.

```
// C3867_4.cpp
// compile with: /c
class A {
public:
   void f(int) {}

   typedef void (A::*TAmtd)(int);

   struct B {
      TAmtd p;
   };

   void g() {
      B b1;
      b1.p = f;   // C3867
   }
};
```

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3867 oluşturur.

```
// C3867_5.cpp
// compile with: /EHsc
#include <iostream>

class Testpm {
public:
   void m_func1() {
      std::cout << m_num << "\tm_func1\n";
    }

   int m_num;
   typedef void (Testpm::*pmfn1)();
   void func(Testpm* p);
};

void Testpm::func(Testpm* p) {
   pmfn1 s = m_func1;   // C3867
   pmfn1 s2 = &Testpm::m_func1;   // OK
   (p->*s2)();
}

int main() {
   Testpm *pTestpm = new Testpm;
   pTestpm->m_num = 10;

   pTestpm->func(pTestpm);
}
```