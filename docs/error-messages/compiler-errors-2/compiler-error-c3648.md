---
title: Derleyici Hatası C3648
ms.date: 11/04/2016
f1_keywords:
- C3648
helpviewer_keywords:
- C3648
ms.assetid: 5d042989-41cb-4cd0-aa50-976b70146aaf
ms.openlocfilehash: f3ef949b2651631f30a9c614a0d21b2668b7239f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50653771"
---
# <a name="compiler-error-c3648"></a>Derleyici Hatası C3648

Bu açık geçersiz kılma sözdiziminin /clr:oldSyntax gerektirir

En son yönetilen sözdizimi derlenirken açık bulunan derleyici artık desteklenmeyen söz dizimi önceki sürümler için geçersiz kılın.

Daha fazla bilgi için [açık geçersiz kılmalar](../../windows/explicit-overrides-cpp-component-extensions.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3648 oluşturur:

```
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