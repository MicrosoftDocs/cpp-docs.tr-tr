---
title: Derleyici hatası C2877
ms.date: 11/04/2016
f1_keywords:
- C2877
helpviewer_keywords:
- C2877
ms.assetid: 0b54837e-fcae-4d90-9658-623250435e24
ms.openlocfilehash: b28a301b757e41e6ba238f361520bc89e0744eba
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74736327"
---
# <a name="compiler-error-c2877"></a>Derleyici hatası C2877

' symbol ', ' class ' öğesinden erişilebilir değil

Temel sınıftan türetilmiş tüm üyelere türetilmiş sınıfta erişilebilir olması gerekir.

Aşağıdaki örnek C2877 oluşturur:

```cpp
// C2877.cpp
// compile with: /c
class A {
private:
   int a;
};

class B : public A {
   using A::a;   // C2877
};
```
