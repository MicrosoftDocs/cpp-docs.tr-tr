---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3671'
title: Derleyici hatası C3671
ms.date: 11/04/2016
f1_keywords:
- C3671
helpviewer_keywords:
- C3671
ms.assetid: d684e4ae-87e2-4424-80bb-6f346652c831
ms.openlocfilehash: a8fba0ccec84789b7fe5e45cd72b18abc3fe63b9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97228878"
---
# <a name="compiler-error-c3671"></a>Derleyici hatası C3671

' function_1 ': işlev ' function_2 ' öğesini geçersiz kılmıyor

Açık geçersiz kılma söz dizimi kullanılırken, bir işlev geçersiz kılınmamışsa derleyici bir hata oluşturur.  Daha fazla bilgi için bkz. [Açık geçersiz kılmalar](../../extensions/explicit-overrides-cpp-component-extensions.md) .

## <a name="example"></a>Örnek

Aşağıdaki örnek C3671 oluşturur.

```cpp
// C3671.cpp
// compile with: /clr /c
ref struct S {
   virtual void f();
};

ref struct S1 : S {
   virtual void f(int) new sealed = S::f;   // C3671
   virtual void f() new sealed = S::f;
};
```
