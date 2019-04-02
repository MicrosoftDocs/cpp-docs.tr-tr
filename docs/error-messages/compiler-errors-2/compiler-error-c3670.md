---
title: Derleyici Hatası C3670
ms.date: 11/04/2016
f1_keywords:
- C3670
helpviewer_keywords:
- C3670
ms.assetid: d0fa9c6e-8f90-48c7-9066-31b4fa5942eb
ms.openlocfilehash: a9fe72501152891d3f82567f09922dda9a9b711a
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58775484"
---
# <a name="compiler-error-c3670"></a>Derleyici Hatası C3670

'override': 'method' erişilemez taban sınıfı yöntemi geçersiz kılınamıyor

Bir geçersiz kılma yalnızca türetilmiş bir tür içinde kullanılabilir getirir, erişim düzeyi bir işlev üzerinde gerçekleştirilebilir. Daha fazla bilgi için [açık geçersiz kılmalar](../../extensions/explicit-overrides-cpp-component-extensions.md).

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