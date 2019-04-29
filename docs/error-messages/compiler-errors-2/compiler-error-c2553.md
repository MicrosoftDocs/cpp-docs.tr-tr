---
title: Derleyici Hatası C2553
ms.date: 11/04/2016
f1_keywords:
- C2553
helpviewer_keywords:
- C2553
ms.assetid: 64bc1e9a-627f-4ce9-b7bc-dc911bdb9180
ms.openlocfilehash: 11cb2b83d958f0c59d05034a716a022f00b326ec
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62353206"
---
# <a name="compiler-error-c2553"></a>Derleyici Hatası C2553

'base_function': geçersiz kılan sanal işlev dönüş türü 'override_function'

Türetilen bir sınıfta bir işlev bir temel sınıf sanal işlevi geçersiz kılma çalışıldı, ancak türetilmiş sınıf işlev temel sınıf işlevi aynı dönüş türüne sahip değil.  Bir geçersiz kılma işlev imzası geçersiz kılınmasını işlev imzası eşleşmesi gerekir.

Aşağıdaki örnek, C2553 oluşturur:

```
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