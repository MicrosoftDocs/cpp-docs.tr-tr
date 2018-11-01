---
title: Derleyici Hatası C2798
ms.date: 11/04/2016
f1_keywords:
- C2798
helpviewer_keywords:
- C2798
ms.assetid: fb0cd861-b228-4f81-8090-e28344a727e0
ms.openlocfilehash: f3e8f0ac260e49866d1c654f89d34bf57a8ffbc1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50463068"
---
# <a name="compiler-error-c2798"></a>Derleyici Hatası C2798

'super::member' belirsiz

İle başvurulan üyesi birden fazla devralınan yapıları içeren [Süper](../../cpp/super.md). Hatayı düzeltin ya da:

- B1 veya B2 D. devralma listesinden kaldırılıyor

- B1 B2 de veri üyesinin adı değiştiriliyor.

Aşağıdaki örnek, C2798 oluşturur:

```
// C2798.cpp
struct B1 {
   int i;
};

struct B2 {
   int i;
};

struct D : B1, B2 {
   void g() {
      __super::i = 4; // C2798
   }
};
```