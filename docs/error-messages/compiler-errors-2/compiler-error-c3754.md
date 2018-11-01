---
title: Derleyici Hatası C3754
ms.date: 11/04/2016
f1_keywords:
- C3754
helpviewer_keywords:
- C3754
ms.assetid: 14b877bc-9277-40ec-af1c-196a58b45f10
ms.openlocfilehash: e03ac39213429fbbb9f289be3514718985c04b4b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50582123"
---
# <a name="compiler-error-c3754"></a>Derleyici Hatası C3754

temsilci oluşturucusu: 'function' üye işlevi, 'type' türünün bir örneği üzerinde çağrılamaz

İşlev içermeyen bir türü bir işaretçi ile bir işleve bir çağrı yapıldı.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3754 oluşturur:

```
// C3754a.cpp
// compile with: /clr
using namespace System;

delegate void MyDel();

interface class MyInterface {};

ref struct MyClass : MyInterface {
   void f() {}
};

int main() {
   MyInterface^ p = gcnew MyClass;
   MyDel^ q = gcnew MyDel(p, &MyClass::f);   // C3754
   // try the following line instead
//   MyDel^ q = gcnew MyDel(safe_cast<MyClass^>(p), &MyClass::f);
}
```
