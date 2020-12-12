---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2903'
title: Derleyici hatası C2903
ms.date: 11/04/2016
f1_keywords:
- C2903
helpviewer_keywords:
- C2903
ms.assetid: bf6b223f-4921-48c7-82b9-ff318b42c801
ms.openlocfilehash: 0013be28857ac8e138a78cb7a4e3502cdc04536b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97270738"
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
