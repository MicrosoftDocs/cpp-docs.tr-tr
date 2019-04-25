---
title: Derleyici Hatası C3671
ms.date: 11/04/2016
f1_keywords:
- C3671
helpviewer_keywords:
- C3671
ms.assetid: d684e4ae-87e2-4424-80bb-6f346652c831
ms.openlocfilehash: c4534b11f3aedf638f69337fb6a7af778e086bb4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62215023"
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