---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3648'
title: Derleyici hatası C3648
ms.date: 11/04/2016
f1_keywords:
- C3648
helpviewer_keywords:
- C3648
ms.assetid: 5d042989-41cb-4cd0-aa50-976b70146aaf
ms.openlocfilehash: 532c65896ae5c3707c86735c661a095698417288
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97203750"
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
