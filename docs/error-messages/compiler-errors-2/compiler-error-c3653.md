---
title: Derleyici hatası C3653
ms.date: 11/04/2016
f1_keywords:
- C3653
helpviewer_keywords:
- C3653
ms.assetid: 316549d7-f7ef-4578-a2ba-57adc8aac527
ms.openlocfilehash: 69fc6fa9303b2256172dd079028050823f053246
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74756344"
---
# <a name="compiler-error-c3653"></a>Derleyici hatası C3653

' function ': adlandırılmış geçersiz kılma olarak kullanılamaz: geçersiz kılınan bir işlev bulunamadı; bir:: işleci kullanarak işlevi açıkça adı belirtmeyi unuttunuz mu?

Açık bir geçersiz kılma, hiçbir arabirimde bulunmayan bir işlevi belirtti. Daha fazla bilgi için bkz. [Açık geçersiz kılmalar](../../extensions/explicit-overrides-cpp-component-extensions.md).

Aşağıdaki örnek C3653 oluşturur:

```cpp
// C3653.cpp
// compile with: /clr
public interface struct I {
   void h();
};

public ref struct X : public I {
   virtual void f() new sealed = J {};   // C3653 no J in scope
   virtual void g() {}   // OK
   virtual void h() new sealed = I::h {};   // OK
};
```
