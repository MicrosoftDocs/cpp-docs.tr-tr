---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3375'
title: Derleyici hatası C3375
ms.date: 11/04/2016
f1_keywords:
- C3375
helpviewer_keywords:
- C3375
ms.assetid: f1df78c6-e6ca-48f3-8b29-4e1710002bf3
ms.openlocfilehash: d2a9e9904185877e730096d08cb1f7c23c35c0d2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97335002"
---
# <a name="compiler-error-c3375"></a>Derleyici hatası C3375

' function ': belirsiz temsilci işlevi

Bir temsilci örnekleme, bir statik üye işlevine veya bir örnek işlevine ilişkisiz bir temsilci olarak olabilir, bu nedenle derleyici bu hatayı verdi.

Daha fazla bilgi için bkz. [Temsilci (C++ Bileşen Uzantıları)](../../extensions/delegate-cpp-component-extensions.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek C3375 oluşturur.

```cpp
// C3375.cpp
// compile with: /clr
ref struct R {
   static void f(R^) {}
   void f() {}
};

delegate void Del(R^);

int main() {
   Del ^ a = gcnew Del(&R::f);   // C3375
}
```
