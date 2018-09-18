---
title: Derleyici Hatası C2553 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2553
dev_langs:
- C++
helpviewer_keywords:
- C2553
ms.assetid: 64bc1e9a-627f-4ce9-b7bc-dc911bdb9180
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 38fb61b7281dd0371c546fd7b7bc960232cf2e00
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46043995"
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