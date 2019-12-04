---
title: Derleyici hatası C2694
ms.date: 11/04/2016
f1_keywords:
- C2694
helpviewer_keywords:
- C2694
ms.assetid: 8dc2cec2-67ae-4e16-8c0c-374425aca8bc
ms.openlocfilehash: ca378c3e0ce88b454cb89fc08470a277a7be6f47
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74755232"
---
# <a name="compiler-error-c2694"></a>Derleyici hatası C2694

' override ': geçersiz kılan sanal işlev, temel sınıf sanal üye işlevi olan ' Base ' öğesinden daha az kısıtlayıcı özel durum belirtimine sahiptir

Bir sanal işlev geçersiz kılındı, ancak [/za](../../build/reference/za-ze-disable-language-extensions.md)altında geçersiz kılan işlevin daha az kısıtlayıcı bir [özel durum belirtimi](../../cpp/exception-specifications-throw-cpp.md)vardı.

Aşağıdaki örnek C2694 oluşturur:

```cpp
// C2694.cpp
// compile with: /Za /c
class MyBase {
public:
   virtual void f(void) throw(int) {
   }
};

class Derived : public MyBase {
public:
   void f(void) throw(...) {}   // C2694
   void f2(void) throw(int) {}   // OK
};
```
