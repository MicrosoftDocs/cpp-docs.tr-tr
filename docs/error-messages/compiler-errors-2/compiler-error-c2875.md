---
title: Derleyici Hatası C2875
ms.date: 11/04/2016
f1_keywords:
- C2875
helpviewer_keywords:
- C2875
ms.assetid: d589fc0c-08b2-4a79-bc0e-dca5eb80bdd5
ms.openlocfilehash: 59df226e2740dbda3a67e0c3c49d688a3e564fee
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62266029"
---
# <a name="compiler-error-c2875"></a>Derleyici Hatası C2875

bildirim kullanımı birden çok 'class::identifier' bildirimi neden olur.

Bildirimi, aynı öğesini iki kez tanımlanmış olması neden olur.

Aşağıdaki örnek, C2875 oluşturur:

```
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