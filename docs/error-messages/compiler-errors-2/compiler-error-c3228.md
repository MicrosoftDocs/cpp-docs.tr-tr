---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3228'
title: Derleyici hatası C3228
ms.date: 11/04/2016
f1_keywords:
- C3228
helpviewer_keywords:
- C3228
ms.assetid: 9015adf9-17b0-4312-b4a7-c1f33e4126f4
ms.openlocfilehash: f245555674d7ce9dcd48697d7ff1fd3016750f40
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97304135"
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
