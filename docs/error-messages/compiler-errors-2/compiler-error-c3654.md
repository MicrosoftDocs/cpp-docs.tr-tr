---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3654'
title: Derleyici hatası C3654
ms.date: 11/04/2016
f1_keywords:
- C3654
helpviewer_keywords:
- C3654
ms.assetid: 57d96e3f-6bbb-4eaa-934b-26c23b4ceb2e
ms.openlocfilehash: e3f5aee0031e398493b97e403159da64e891d2b9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97198290"
---
# <a name="compiler-error-c3654"></a>Derleyici hatası C3654

' text ': açık geçersiz kılma içinde sözdizimi hatası

Açık bir geçersiz kılmada beklenmeyen bir dize vardı. Daha fazla bilgi için bkz. [Açık geçersiz kılmalar](../../extensions/explicit-overrides-cpp-component-extensions.md).

Aşağıdaki örnek C3654 oluşturur:

```cpp
// C3654.cpp
// compile with: /clr /c
public ref struct B {
   virtual void f() = 0;
   virtual void g() = 0;
   virtual void h() = 0;
};

public ref struct Q : B {
   virtual void f() = B::f, 3 {}   // C3654
   // try the following line instead
   // virtual void g() = B::g, B::h {}
};
```
