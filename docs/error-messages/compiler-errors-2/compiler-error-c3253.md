---
title: Derleyici Hatası C3253
ms.date: 11/04/2016
f1_keywords:
- C3253
helpviewer_keywords:
- C3253
ms.assetid: da40be26-0f78-4730-8727-ad11cddf8869
ms.openlocfilehash: 997d23fa5736e31b3824459f928a58eddde56e15
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50605097"
---
# <a name="compiler-error-c3253"></a>Derleyici Hatası C3253

'function': açıkça geçersiz kılma hatası

Açık bir geçersiz kılma yanlış olarak belirtildi. Örneğin, bir uygulama da saf olarak belirttiğiniz bir geçersiz kılma için belirtilemez. Daha fazla bilgi için [açık geçersiz kılmalar](../../windows/explicit-overrides-cpp-component-extensions.md).

Aşağıdaki örnek, C3253 oluşturur:

```
// C3253.cpp
// compile with: /clr
public interface struct I {
   void a();
   void b();
   void c();
};

public ref struct R : I {
   virtual void a() = 0, I::a {}   // C3253
   virtual void b() = I::a {}   // OK
   virtual void c() = 0;   // OK
};
```