---
title: Derleyici Hatası C3653
ms.date: 11/04/2016
f1_keywords:
- C3653
helpviewer_keywords:
- C3653
ms.assetid: 316549d7-f7ef-4578-a2ba-57adc8aac527
ms.openlocfilehash: d7936303dab4fbb273a01f98def5b9af99f89dac
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50477629"
---
# <a name="compiler-error-c3653"></a>Derleyici Hatası C3653

'function': adlandırılmış bir geçersiz kılma olarak kullanılamaz: bulunamadı; kılınan bir işlev kullanarak işlevi açıkça adlandırmayı unuttunuz bir:: işleci?

Açık bir geçersiz kılma herhangi bir arabirimde bulunamadı bir işlev belirtildi. Daha fazla bilgi için [açık geçersiz kılmalar](../../windows/explicit-overrides-cpp-component-extensions.md).

Aşağıdaki örnek, C3653 oluşturur:

```
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