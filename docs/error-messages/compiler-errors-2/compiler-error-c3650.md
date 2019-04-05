---
title: Derleyici Hatası C3650
ms.date: 11/04/2016
f1_keywords:
- C3650
helpviewer_keywords:
- C3650
ms.assetid: ca4d8de4-b027-4d13-9b9f-03ca62905c33
ms.openlocfilehash: 54543225144ed0187f6c1e68e7236d886c026860
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "58777122"
---
# <a name="compiler-error-c3650"></a>Derleyici Hatası C3650

'interface_method': açık bir geçersiz kılma kullanılamaz, bir taban sınıfı sanal üye işlevi olmalıdır

Açık bir geçersiz kılma, sanal olmayan bir üyesinde gerçekleştirmek için girişimde bulunuldu.

Daha fazla bilgi için [açık geçersiz kılmalar](../../extensions/explicit-overrides-cpp-component-extensions.md).

Aşağıdaki örnek, C3650 oluşturur:

```
// C3650.cpp
// compile with: /clr
public interface struct I {
   void a();
};

public ref class S {
public:
   static int f() { return 0; }
   static int g() { return 0; }
};

public ref struct T1 : public S, I {
   virtual int f() new sealed = S::f;   // C3650
   virtual int g() { return 0; }   // OK does not override S::g
   virtual void a() new sealed = I::a {}   // OK
};
```