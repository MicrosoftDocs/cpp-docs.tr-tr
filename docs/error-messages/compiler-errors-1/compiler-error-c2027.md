---
title: Derleyici hatası C2027
ms.date: 11/04/2016
f1_keywords:
- C2027
helpviewer_keywords:
- C2027
ms.assetid: a39150c0-ec04-45ec-934c-a838bfe76627
ms.openlocfilehash: 62cf208d9d0025afba06d32a15b9a1e50777c473
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74751007"
---
# <a name="compiler-error-c2027"></a>Derleyici hatası C2027

tanımsız ' Type ' türü kullanımı

Bir tür, tanımlanana kadar kullanılamaz. Hatayı gidermek için, türün kendisine başvurulmadan önce tam olarak tanımlandığından emin olun.

## <a name="example"></a>Örnek

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

## <a name="example"></a>Örnek

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
