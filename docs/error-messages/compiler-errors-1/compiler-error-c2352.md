---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2352'
title: Derleyici hatası C2352
ms.date: 11/04/2016
f1_keywords:
- C2352
helpviewer_keywords:
- C2352
ms.assetid: 0efad8cb-659f-4b3e-8f6f-9f8ec44d345c
ms.openlocfilehash: f8094261c4a0ad23b5603d1e16bbaa4f34e0038e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97298311"
---
# <a name="compiler-error-c2352"></a>Derleyici hatası C2352

' class:: Function ': statik olmayan üye işlev için geçersiz çağrı

**`static`** Statik olmayan üye işlevi adlı bir üye işlev. Veya statik olmayan bir üye işlevi, sınıfın dışından statik bir işlev olarak çağırılır.

Aşağıdaki örnek C2352 oluşturur ve nasıl düzeltileceğini gösterir:

```cpp
// C2352.cpp
// compile with: /c
class CMyClass {
public:
   static void func1();
   void func2();
   static void func3() {
      func2();   // C2352 calls nonstatic func2
      func1();   // OK calls static func1
   }
};
```

Aşağıdaki örnek C2352 oluşturur ve nasıl düzeltileceğini gösterir:

```cpp
// C2352b.cpp
class MyClass {
public:
   void MyFunc() {}
   static void MyFunc2() {}
};

int main() {
   MyClass::MyFunc();   // C2352
   MyClass::MyFunc2();   // OK
}
```
