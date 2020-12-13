---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2553'
title: Derleyici hatası C2553
ms.date: 11/04/2016
f1_keywords:
- C2553
helpviewer_keywords:
- C2553
ms.assetid: 64bc1e9a-627f-4ce9-b7bc-dc911bdb9180
ms.openlocfilehash: 5f5e3eb9d94935aa8e6974f72517e7193ba07db3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97134504"
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
