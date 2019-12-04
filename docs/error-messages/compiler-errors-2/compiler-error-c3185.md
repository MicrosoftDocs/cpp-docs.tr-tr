---
title: Derleyici hatası C3185
ms.date: 11/04/2016
f1_keywords:
- C3185
helpviewer_keywords:
- C3185
ms.assetid: 5bf96279-043c-4981-9d02-b4550071b192
ms.openlocfilehash: 36f350287a1cfaf937ee739800042aaf99f31769
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74761640"
---
# <a name="compiler-error-c3185"></a>Derleyici hatası C3185

' Type ' yönetilen veya WinRT türü üzerinde ' TypeId ' kullanıldı, bunun yerine ' operator ' kullanın

[TypeId](../../cpp/typeid-operator.md) işlecini yönetilen veya WinRT türüne uygulayamazsınız; Bunun yerine [TypeId](../../extensions/typeid-cpp-component-extensions.md) kullanın.

Aşağıdaki örnek C3185 oluşturur ve nasıl düzeltileceğini gösterir:

```cpp
// C3185a.cpp
// compile with: /clr
ref class Base {};
ref class Derived : public Base {};

int main() {
   Derived ^ pd = gcnew Derived;
   Base ^pb = pd;
   const type_info & t1 = typeid(pb);   // C3185
   System::Type ^ MyType = Base::typeid;   // OK
};
```
