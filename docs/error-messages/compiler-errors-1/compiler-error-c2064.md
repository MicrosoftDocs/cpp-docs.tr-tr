---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2064'
title: Derleyici hatası C2064
ms.date: 11/04/2016
f1_keywords:
- C2064
helpviewer_keywords:
- C2064
ms.assetid: 6cda05da-f437-4f50-9813-ae69538713a3
ms.openlocfilehash: dd9f0386267a81d4f92d6dd0474cd9a3292e7345
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97328562"
---
# <a name="compiler-error-c2064"></a>Derleyici hatası C2064

terim N bağımsız değişken alan bir işlev olarak değerlendirilmiyor

Bir işleve bir ifade aracılığıyla çağrı yapılır. İfade, belirtilen sayıda bağımsız değişken alan bir işlev işaretçisi olarak değerlendirilmiyor.

Bu örnekte, kod işlevleri işlev olarak çağırmaya çalışır. Aşağıdaki örnek C2064 oluşturur:

```cpp
// C2064.cpp
int i, j;
char* p;
void func() {
   j = i();    // C2064, i is not a function
   p();        // C2064, p doesn't point to a function
}
```

Bir nesne örneği bağlamından statik olmayan üye işlevlerine işaretçiler çağırmanız gerekir. Aşağıdaki örnek C2064 oluşturur ve nasıl düzeltileceğini gösterir:

```cpp
// C2064b.cpp
struct C {
   void func1(){}
   void func2(){}
};

typedef void (C::*pFunc)();

int main() {
   C c;
   pFunc funcArray[2] = {&C::func1, &C::func2};
   (funcArray[0])();    // C2064
   (c.*funcArray[0])(); // OK - function called in instance context
}
```

Bir sınıf içinde, üye işlev işaretçileri de çağıran nesne bağlamını göstermelidir. Aşağıdaki örnek C2064 oluşturur ve nasıl düzeltileceğini gösterir:

```cpp
// C2064d.cpp
// Compile by using: cl /c /W4 C2064d.cpp
struct C {
   typedef void (C::*pFunc)();
   pFunc funcArray[2];
   void func1(){}
   void func2(){}
   C() {
      funcArray[0] = &C::func1;
      funcArray[1] = &C::func2;
   }
   void func3() {
      (funcArray[0])();   // C2064
      (this->*funcArray[0])(); // OK - called in this instance context
   }
};
```
