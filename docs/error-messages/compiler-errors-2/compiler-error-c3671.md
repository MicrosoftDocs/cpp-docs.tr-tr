---
title: Derleyici Hatası C3671
ms.date: 11/04/2016
f1_keywords:
- C3671
helpviewer_keywords:
- C3671
ms.assetid: d684e4ae-87e2-4424-80bb-6f346652c831
ms.openlocfilehash: 4b99578ed40b4ff70f3606840198b7062083ca83
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50667056"
---
# <a name="compiler-error-c3671"></a>Derleyici Hatası C3671

'function_1': işlev 'function_2' Kılmıyor

Bir işlev değil kılınırsa açık geçersiz kılma sözdizimi kullanıldığında, derleyici bir hata oluşturur.  Bkz: [açık geçersiz kılmalar](../../windows/explicit-overrides-cpp-component-extensions.md) daha fazla bilgi için.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3671 oluşturur.

```
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