---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3652'
title: Derleyici hatası C3652
ms.date: 11/04/2016
f1_keywords:
- C3652
helpviewer_keywords:
- C3652
ms.assetid: 15d68737-177e-41f1-80e0-7c3e2afdf0fc
ms.openlocfilehash: d7ef611f58a62cd7a209ee680390c147759c9b64
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97203672"
---
# <a name="compiler-error-c3652"></a>Derleyici hatası C3652

' override ': açıkça geçersiz kılan bir işlev sanal olmalıdır

Açık bir geçersiz kılma yapan bir işlev sanal olmalıdır. Daha fazla bilgi için bkz. [Açık geçersiz kılmalar](../../extensions/explicit-overrides-cpp-component-extensions.md).

Aşağıdaki örnek C3652 oluşturur:

```cpp
// C3652.cpp
// compile with: /clr /c
public interface class I {
   void f();
};

public ref struct R : I {
   void f() = I::f {}   // C3652
   // try the following line instead
   // virtual void f() = I::f {}
};
```
