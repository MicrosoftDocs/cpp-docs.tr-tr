---
title: Derleyici hatası C3228
ms.date: 11/04/2016
f1_keywords:
- C3228
helpviewer_keywords:
- C3228
ms.assetid: 9015adf9-17b0-4312-b4a7-c1f33e4126f4
ms.openlocfilehash: 81ced2765ab1ac7d0d138209ee33e163d7451041
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74743438"
---
# <a name="compiler-error-c3228"></a>Derleyici hatası C3228

' function ': ' param ' için genel tür bağımsız değişkeni ' Type ' olamaz, bu bir ValueType veya tanıtıcı türü olmalıdır

Genel tür bağımsız değişkeni olarak yanlış tür geçirildi.

Aşağıdaki örnek C3228 oluşturur:

```cpp
// C3228.cpp
// compile with: /clr
class A {};

value class B {};

generic <class T>
void Test() {}

ref class C {
public:
   generic <class T>
   static void f() {}
};

int main() {
   C::f<A>();   // C3228
   C::f<B>();   // OK

   Test<C>();   // C3228
   Test<C ^>();   // OK
}
```
