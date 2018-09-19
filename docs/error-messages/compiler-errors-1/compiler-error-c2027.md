---
title: Derleyici Hatası C2027 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2027
dev_langs:
- C++
helpviewer_keywords:
- C2027
ms.assetid: a39150c0-ec04-45ec-934c-a838bfe76627
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 69aae289fbab56cd77e544118909b2d7ef72ae0c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46032048"
---
# <a name="compiler-error-c2027"></a>Derleyici Hatası C2027

Tanımsız türü 'type' kullanın

Bir tür tanımlandıktan kadar kullanılamaz. Hatayı gidermek için türü başvurmadan önce tam olarak tanımlanmış emin olun.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C2027 oluşturur.

```
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

Bir işaretçi bildirimli ancak tanımlanmamış bir türü bildirmek mümkündür.  Ancak Visual C++ tanımlanmamış bir türe başvuru izin vermez.

Aşağıdaki örnek, C2027 oluşturur.

```
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