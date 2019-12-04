---
title: Derleyici hatası C3731
ms.date: 11/04/2016
f1_keywords:
- C3731
helpviewer_keywords:
- C3731
ms.assetid: 45f89fcd-464c-4bc8-8a42-edcb5416d26c
ms.openlocfilehash: 9acf80eec0d36db64fa070d691533e7085754ac0
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74752957"
---
# <a name="compiler-error-c3731"></a>Derleyici hatası C3731

uyumsuz olay ' işlev1 ' ve işleyici ' function2 '; Olay kaynağı ve olay işleyicisi aynı türde olmalıdır

Olay kaynağı ve olay alıcısı aynı türde olmalıdır (örneğin `native` vs. `com` türleri). Bu hatayı düzeltirecek şekilde olay kaynağı ve olay işleyici türlerini eşleştirin.

Aşağıdaki örnek C3731 oluşturur:

```cpp
// C3731.cpp
// compile with: /clr
#using <mscorlib.dll>
[event_source(native)]
struct A {
   __event void MyEvent();
};

[event_receiver(managed)]
// try the following line instead
// [event_receiver(native)]
struct B {
   void func();
   B(A a) {
      __hook(&A::MyEvent, &a, &B::func);   // C3731
   }
};

int main() {
}
```
