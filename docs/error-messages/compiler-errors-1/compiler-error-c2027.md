---
title: Derleyici hatası C2027
ms.date: 11/04/2016
f1_keywords:
- C2027
helpviewer_keywords:
- C2027
ms.assetid: a39150c0-ec04-45ec-934c-a838bfe76627
ms.openlocfilehash: 59d0e5d5a5f0957f2d73cdb863ccee9a2dd2a026
ms.sourcegitcommit: 72161bcd21d1ad9cc3f12261aa84a5b026884afa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2020
ms.locfileid: "90743262"
---
# <a name="compiler-error-c2027"></a>Derleyici hatası C2027

tanımsız ' Type ' türü kullanımı

Bir tür, tanımlanana kadar kullanılamaz. Hatayı gidermek için, türün kendisine başvurulmadan önce tam olarak tanımlandığından emin olun.

## <a name="examples"></a>Örnekler

Aşağıdaki örnek C2027 oluşturur.

```cpp
// C2027.cpp
class C;
class D {
public:
   void func() {
   }
};

int main() {
   C *pC;
   pC->func();   // C2027

   D *pD;
   pD->func();
}
```

Tanımlanan ancak tanımlanmamış bir tür için bir işaretçi bildirmek mümkündür. Ancak C++ tanımsız bir türe başvuruya izin vermez.

Aşağıdaki örnek C2027 oluşturur.

```cpp
// C2027_b.cpp
class A;
A& CreateA();

class B;
B* CreateB();

int main() {
   CreateA();   // C2027
   CreateB();   // OK
}
```
