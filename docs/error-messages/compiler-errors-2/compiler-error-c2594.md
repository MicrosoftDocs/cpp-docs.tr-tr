---
title: Derleyici Hatası C2594
ms.date: 11/04/2016
f1_keywords:
- C2594
helpviewer_keywords:
- C2594
ms.assetid: 68cd708f-266e-44b0-a211-3e3ab63b11bf
ms.openlocfilehash: 75e3b438dd69f8879fdc2273a8f0357229941340
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50428291"
---
# <a name="compiler-error-c2594"></a>Derleyici Hatası C2594

'operator': 'type1' öğesinden 'type2' belirsiz dönüştürme

Hiçbir dönüştürme *type1* için *type2* diğerinden daha doğrudan oluştu. Dönüştürme için iki olası çözümü öneririz *type1* için *type2*. İlk seçenek doğrudan dönüştürme tanımlamaktır *type1* için *type2*, ve Dönüştürmelere sırasını belirlemek için ikinci seçenek ise *type1* için  *type2*.

Aşağıdaki örnek, C2594 oluşturur. Önerilen çözüm hata dönüştürmeler dizisidir:

```
// C2594.cpp
// compile with: /c
struct A{};
struct I1 : A {};
struct I2 : A {};
struct D : I1, I2 {};

A *f (D *p) {
   return (A*) (p);    // C2594

// try the following line instead
// return static_cast<A *>(static_cast<I1 *>(p));
}
```