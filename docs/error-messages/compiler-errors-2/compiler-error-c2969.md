---
title: Derleyici Hatası C2969
ms.date: 11/04/2016
f1_keywords:
- C2969
helpviewer_keywords:
- C2969
ms.assetid: e4ea3d66-b937-4b2c-b42a-96e03fb11579
ms.openlocfilehash: 1330babe92266a6bc410084b4a46ef75f83f0b7c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50455529"
---
# <a name="compiler-error-c2969"></a>Derleyici Hatası C2969

sözdizimi hatası: 'symbol': üye işlev tanımının'ile bitmesi bekleniyor '}'

Şablon üye işlev tanımı bir eşleşmeyen kapanış ayracı sahiptir.

Aşağıdaki örnek, C2969 oluşturur:

```
// C2969.cpp
// compile with: /c
class A {
   int i;
public:
   A(int i) {}
};

A anA(1);

class B {
   A a;
   B() : a(anA);   // C2969
   // try the following line instead
   // B() : a(anA) {}
};
```