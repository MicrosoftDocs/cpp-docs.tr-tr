---
title: Derleyici hatası C2903
ms.date: 11/04/2016
f1_keywords:
- C2903
helpviewer_keywords:
- C2903
ms.assetid: bf6b223f-4921-48c7-82b9-ff318b42c801
ms.openlocfilehash: df097cf38fea47702b639b44fd2f2ac3341df2ba
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74735911"
---
# <a name="compiler-error-c2903"></a>Derleyici hatası C2903

' tanımlayıcı ': simge, bir sınıf şablonu veya bir işlev şablonu değil

Kod, şablon olmayan bir şeyin açıkça örneklemesi yapmayı dener.

Aşağıdaki örnek C2903 oluşturur:

```cpp
// C2903.cpp
// compile with: /c
namespace N {
   template<class T> class X {};
   class Y {};
}
void g() {
   N::template Y y;   // C2903
   N::X<N::Y> y;   // OK
}
```

C2903, genel türler kullanılırken de oluşabilir:

```cpp
// C2903b.cpp
// compile with: /clr /c
namespace N {
   class Y {};
   generic<class T> ref class Z {};
}

void f() {
   N::generic Y y;   // C2903
   N:: generic Z<int>^ z;   // OK
}
```
