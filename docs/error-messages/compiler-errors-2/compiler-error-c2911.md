---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2911'
title: Derleyici hatası C2911
ms.date: 11/04/2016
f1_keywords:
- C2911
helpviewer_keywords:
- C2911
ms.assetid: 83c7c01a-ab6a-4179-9fb0-289a9ec8d44e
ms.openlocfilehash: c3890a6017e96b4b5f2f9dc7b5711fd98f29b947
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97270549"
---
# <a name="compiler-error-c2911"></a>Derleyici hatası C2911

' Member ': geçerli kapsamda bildirilemez veya tanımlanamaz

Bir ad alanı, sınıf veya işlev içinde, yalnızca aynı ad alanı, sınıf veya işlevin veya aynı ad alanı, sınıf veya işlev tarafından alınmış bir üyenin bir üyesini tanımlayabilirsiniz.

Aşağıdaki örnek C2911 oluşturur:

```cpp
// C2911.cpp
struct A;

namespace M {
   struct D;
}

namespace N {
   struct C;

   namespace O {
      struct B;
   }

   // in N
   struct ::A {};   // C2911  A is member of global NS
   struct O::B{};   // OK B is in O, O is inside of N
   struct C {};     // OK C is member of N
   struct M::D {};  // C2911 D is member of M, M not enclosed by N
}
```
