---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2783'
title: Derleyici hatası C2783
ms.date: 11/04/2016
f1_keywords:
- C2783
helpviewer_keywords:
- C2783
ms.assetid: 1ce94a11-bb8b-4be3-a222-f1f105da74b3
ms.openlocfilehash: 671a1974f94ca9e31b83861c3e1b503762ca58d1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97297973"
---
# <a name="compiler-error-c2783"></a>Derleyici hatası C2783

' declaration ': ' Identifier ' için şablon bağımsız değişkeni anlaşılamadı

Derleyici bir şablon bağımsız değişkenini belirleyemiyor. Varsayılan bağımsız değişkenler bir şablon bağımsız değişkenini bırakmak için kullanılamaz.

Aşağıdaki örnek C2783 oluşturur:

```cpp
// C2783.cpp
template<typename T1, typename T2>
T1 f(T2) {
   return 248;
}

int main() {
   f(1);   // C2783
   // try the following line instead
   int i = f<int>(1);
}
```

C2783, genel türler kullanılırken de oluşabilir:

```cpp
// C2783b.cpp
// compile with: /clr
using namespace System;
generic<typename T1, typename T2>
T1 gf(T2) {
   T1 t1 = safe_cast<T1>( Activator::CreateInstance(T1::typeid));
   return t1;
}

ref class MyClass{};

int main() {
   int i;
   i = gf(9);   // C2783

   // OK
   i = gf<int>(9);
}
```
