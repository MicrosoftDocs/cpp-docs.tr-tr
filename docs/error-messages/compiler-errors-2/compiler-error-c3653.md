---
title: Derleyici Hatası C3653
ms.date: 11/04/2016
f1_keywords:
- C3653
helpviewer_keywords:
- C3653
ms.assetid: 316549d7-f7ef-4578-a2ba-57adc8aac527
ms.openlocfilehash: 75e2c061190b24019491db7a625ecafb5ac82b6b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62227519"
---
# <a name="compiler-error-c3653"></a>Derleyici Hatası C3653

'function': adlandırılmış bir geçersiz kılma olarak kullanılamaz: bulunamadı; kılınan bir işlev kullanarak işlevi açıkça adlandırmayı unuttunuz bir:: işleci?

Açık bir geçersiz kılma herhangi bir arabirimde bulunamadı bir işlev belirtildi. Daha fazla bilgi için [açık geçersiz kılmalar](../../extensions/explicit-overrides-cpp-component-extensions.md).

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