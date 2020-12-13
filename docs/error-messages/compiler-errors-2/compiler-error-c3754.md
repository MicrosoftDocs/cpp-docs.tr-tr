---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3754'
title: Derleyici hatası C3754
ms.date: 11/04/2016
f1_keywords:
- C3754
helpviewer_keywords:
- C3754
ms.assetid: 14b877bc-9277-40ec-af1c-196a58b45f10
ms.openlocfilehash: 1f6c32a94caf6b2045f177480f76aa0c7fc2a7fd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97340144"
---
# <a name="compiler-error-c3754"></a>Derleyici hatası C3754

temsilci Oluşturucu: ' function ' üye işlevi ' Type ' türündeki bir örnekte çağrılamaz

İşlevi içermeyen bir türe işaretçi aracılığıyla bir işleve bir çağrı yapıldı.

## <a name="example"></a>Örnek

Aşağıdaki örnek C3754 oluşturur:

```cpp
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
