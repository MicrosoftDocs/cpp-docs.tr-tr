---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2250'
title: Derleyici hatası C2250
ms.date: 11/04/2016
f1_keywords:
- C2250
helpviewer_keywords:
- C2250
ms.assetid: f990986f-5c7d-4af4-a25c-b35540f1e217
ms.openlocfilehash: 5d018a01899ac74f148b2f0467feff9d7cecc025
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97134847"
---
# <a name="compiler-error-c2250"></a>Derleyici hatası C2250

' tanımlayıcı ': ' class:: Member ' öğesinin belirsiz devralınması

Türetilmiş sınıf, sanal bir temel sınıfın sanal işlevinin birden fazla geçersiz kılmasını devralır. Bu geçersiz kılmalar türetilmiş sınıfta belirsizdir.

Aşağıdaki örnek C2286 oluşturur:

```cpp
// C2250.cpp
// compile with: /c
// C2250 expected
struct V {
   virtual void vf();
};

struct A : virtual V {
   void vf();
};

struct B : virtual V {
   void vf();
};

struct D : A, B {
   // Uncomment the following line to resolve.
   // void vf();
};
```
