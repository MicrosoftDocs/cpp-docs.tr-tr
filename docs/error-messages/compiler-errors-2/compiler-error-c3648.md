---
title: Derleyici hatası C3648
ms.date: 11/04/2016
f1_keywords:
- C3648
helpviewer_keywords:
- C3648
ms.assetid: 5d042989-41cb-4cd0-aa50-976b70146aaf
ms.openlocfilehash: 3b26be9890bbbdf6276c61023e6867160528e236
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74751839"
---
# <a name="compiler-error-c3648"></a>Derleyici hatası C3648

Bu açık geçersiz kılma söz dizimi/clr: oldSyntax gerektirir

En son yönetilen sözdizimi için derlerken, derleyici artık desteklenmeyen önceki sürümler için açık bir geçersiz kılma sözdizimi buldu.

Daha fazla bilgi için bkz. [Açık geçersiz kılmalar](../../extensions/explicit-overrides-cpp-component-extensions.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek C3648 oluşturur:

```cpp
// C3648.cpp
// compile with: /clr
public interface struct I {
   void f();
};

public ref struct R : I {
   virtual void I::f() {}   // C3648
   // try the following line instead
   // virtual void f() = I::f{}
};
```
