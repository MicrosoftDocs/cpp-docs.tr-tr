---
title: Derleyici Hatası C3671
ms.date: 11/04/2016
f1_keywords:
- C3671
helpviewer_keywords:
- C3671
ms.assetid: d684e4ae-87e2-4424-80bb-6f346652c831
ms.openlocfilehash: c4534b11f3aedf638f69337fb6a7af778e086bb4
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59778039"
---
# <a name="compiler-error-c3671"></a>Derleyici Hatası C3671

'function_1': işlev 'function_2' Kılmıyor

Bir işlev değil kılınırsa açık geçersiz kılma sözdizimi kullanıldığında, derleyici bir hata oluşturur.  Bkz: [açık geçersiz kılmalar](../../extensions/explicit-overrides-cpp-component-extensions.md) daha fazla bilgi için.

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