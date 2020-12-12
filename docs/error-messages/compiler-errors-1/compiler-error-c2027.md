---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2027'
title: Derleyici hatası C2027
ms.date: 11/04/2016
f1_keywords:
- C2027
helpviewer_keywords:
- C2027
ms.assetid: a39150c0-ec04-45ec-934c-a838bfe76627
ms.openlocfilehash: 131362f2caa8da80865a9601d87cfe3a5e7ab3b9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97175553"
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
