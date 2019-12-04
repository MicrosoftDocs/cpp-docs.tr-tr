---
title: Derleyici hatası C2875
ms.date: 11/04/2016
f1_keywords:
- C2875
helpviewer_keywords:
- C2875
ms.assetid: d589fc0c-08b2-4a79-bc0e-dca5eb80bdd5
ms.openlocfilehash: cefb2c0b138c0a6a6061e990e6bb79ce9b93f6b5
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74736340"
---
# <a name="compiler-error-c2875"></a>Derleyici hatası C2875

using bildirimi, ' class:: Identifier ' öğesinin birden çok bildirimine neden oluyor

Bildirim aynı öğenin iki kez tanımlanmasını sağlar.

Aşağıdaki örnek C2875 oluşturur:

```cpp
// C2875.cpp
struct A {
   void f(int*);
};

struct B {
   void f(double*);
};

struct AB : A, B {
   using A::f;
   using A::f;   // C2875
   using B::f;
};
```
