---
title: Derleyici hatası C3252
ms.date: 11/04/2016
f1_keywords:
- C3252
helpviewer_keywords:
- C3252
ms.assetid: aa9ad096-e9ac-41c7-8ad9-b966751c7c75
ms.openlocfilehash: fbfe3ffaca66cad4922b5771ee8c9003acba7571
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74754335"
---
# <a name="compiler-error-c3252"></a>Derleyici hatası C3252

' Method ': yönetilen veya WinRT türündeki bir sanal metodun erişilebilirliği azaltılamaz

Bir taban sınıftan veya bir arabirimden herhangi bir yöntemden sanal bir yöntemi uygulayan bir sınıf, bu yöntemin erişimini azaltamaz.

Bir arabirimdeki tüm yöntemlerin genel olduğunu unutmayın.

Aşağıdaki örnek C3252 oluşturur ve nasıl düzeltileceğini gösterir:

```cpp
// C3252.cpp
// compile with: /clr /c
ref class A {
public:
   virtual void f1() {}
};

ref class B : public A {
// To fix, uncomment the following line:
// public:
   virtual void f1() override sealed {}   // C3252, make this method public
};
```
