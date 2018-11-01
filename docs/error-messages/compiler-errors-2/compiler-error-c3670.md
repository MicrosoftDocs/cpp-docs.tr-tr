---
title: Derleyici Hatası C3670
ms.date: 11/04/2016
f1_keywords:
- C3670
helpviewer_keywords:
- C3670
ms.assetid: d0fa9c6e-8f90-48c7-9066-31b4fa5942eb
ms.openlocfilehash: d3acfd9d4d09c53fac0b2c5a2462c56dfd54e6d8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50598558"
---
# <a name="compiler-error-c3670"></a>Derleyici Hatası C3670

'override': 'method' erişilemez taban sınıfı yöntemi geçersiz kılınamıyor

Bir geçersiz kılma yalnızca türetilmiş bir tür içinde kullanılabilir getirir, erişim düzeyi bir işlev üzerinde gerçekleştirilebilir. Daha fazla bilgi için [açık geçersiz kılmalar](../../windows/explicit-overrides-cpp-component-extensions.md).

Aşağıdaki örnek, C3670 oluşturur:

```
// C3670.cpp
// compile with: /clr /c
public ref class C {
// Uncomment the following line to resolve.
// public:
   virtual void g() { }
};

public ref class D : public C {
public:
   virtual void f() new sealed = C::g {};   // C3670
};
```