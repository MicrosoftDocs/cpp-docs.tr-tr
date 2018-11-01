---
title: Derleyici Hatası C3217
ms.date: 11/04/2016
f1_keywords:
- C3217
helpviewer_keywords:
- C3217
ms.assetid: 99070417-c23a-4d82-bdd2-04be1a07adea
ms.openlocfilehash: bcb63c7025f0addda546379947e2e1f5c3afc545
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50600365"
---
# <a name="compiler-error-c3217"></a>Derleyici Hatası C3217

'param': Bu bildirimde genel parametre kısıtlanamaz

Kısıtlama olgu biçimlendirildi; genel parametre kısıtlama ile genel bir sınıf şablonu parametre kabul etmesi gerekir.

Aşağıdaki örnek, C3217 oluşturur:

```
// C3217.cpp
// compile with: /clr
interface struct A {};

generic <class T>
ref class C {
   generic <class T1>
   where T : A   // C3217
   void f();
};
```

Aşağıdaki örnek, olası çözümü göstermektedir:

```
// C3217b.cpp
// compile with: /clr /c
interface struct A {};

generic <class T>
ref class C {
   generic <class T1>
   where T1 : A
   void f();
};
```