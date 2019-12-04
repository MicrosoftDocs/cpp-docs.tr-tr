---
title: Derleyici hatası C2553
ms.date: 11/04/2016
f1_keywords:
- C2553
helpviewer_keywords:
- C2553
ms.assetid: 64bc1e9a-627f-4ce9-b7bc-dc911bdb9180
ms.openlocfilehash: aa3e97d576e994878ab5b080363c4c09b79f42ed
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74756792"
---
# <a name="compiler-error-c2553"></a>Derleyici hatası C2553

' base_function ': geçersiz kılan sanal işlev dönüş türü ' override_function ' öğesinden farklı

Türetilmiş sınıftaki bir işlev, temel sınıftaki bir sanal işlevi geçersiz kılmaya çalıştı, ancak türetilmiş sınıf işlevi taban sınıf işleviyle aynı dönüş türüne sahip değil.  Geçersiz kılma işlevi imzasının geçersiz kılınan işlevin imzasıyla eşleşmesi gerekir.

Aşağıdaki örnek C2553 oluşturur:

```cpp
// C2553.cpp
// compile with: /clr /c
ref struct C {
   virtual void f();
};

ref struct D : C {
   virtual int f() override ;   // C2553

   // try the following line instead
   // virtual void f() override;
};
```
