---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3731'
title: Derleyici hatası C3731
ms.date: 11/04/2016
f1_keywords:
- C3731
helpviewer_keywords:
- C3731
ms.assetid: 45f89fcd-464c-4bc8-8a42-edcb5416d26c
ms.openlocfilehash: 8a7ad836083a8c103df7becd7605a0dfd0efeea7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97245089"
---
# <a name="compiler-error-c3731"></a>Derleyici hatası C3731

uyumsuz olay ' işlev1 ' ve işleyici ' function2 '; Olay kaynağı ve olay işleyicisi aynı türde olmalıdır

Olay kaynağı ve olay alıcısı aynı türde (örneğin, `native` vs. `com` Types) olmalıdır. Bu hatayı düzeltirecek şekilde olay kaynağı ve olay işleyici türlerini eşleştirin.

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
