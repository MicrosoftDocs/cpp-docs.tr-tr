---
title: Derleyici hatası C2250
ms.date: 11/04/2016
f1_keywords:
- C2250
helpviewer_keywords:
- C2250
ms.assetid: f990986f-5c7d-4af4-a25c-b35540f1e217
ms.openlocfilehash: 472aabf00fecd000f274d97b5753ed8460ff867f
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74758872"
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
