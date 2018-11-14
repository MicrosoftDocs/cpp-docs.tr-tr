---
title: Derleyici Hatası C2064
ms.date: 11/04/2016
f1_keywords:
- C2064
helpviewer_keywords:
- C2064
ms.assetid: 6cda05da-f437-4f50-9813-ae69538713a3
ms.openlocfilehash: 8af20c5172cddd0194ed018c13960bbed7859674
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/10/2018
ms.locfileid: "51520445"
---
# <a name="compiler-error-c2064"></a>Derleyici Hatası C2064

Terim N bağımsız değişken alan bir işlev olarak değerlendirilmiyor

Bir ifade ile bir işleve bir çağrı yapılır. Belirtilen sayıda bağımsız değişken alan bir işlev işaretçisine ifadeyi değerlendirmez.

Bu örnekte, kod arama işlevleri olmayan işlevler olarak çalışır. Aşağıdaki örnek, C2064 oluşturur:

```
// C2064.cpp
int i, j;
char* p;
void func() {
   j = i();    // C2064, i is not a function
   p();        // C2064, p doesn't point to a function
}
```

Statik olmayan üye işlevleri için bir nesne örneği bağlamında işaretçileri çağırmalıdır. Aşağıdaki örnek, C2064 oluşturur ve bu sorunun nasıl gösterir:

```
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

Bir sınıf içinde üye işlev işaretçileri arama nesne bağlamı da belirtmeniz gerekir. Aşağıdaki örnek, C2064 oluşturur ve bu sorunun nasıl gösterir:

```
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