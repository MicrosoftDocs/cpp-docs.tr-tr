---
title: Derleyici Hatası C2550
ms.date: 11/04/2016
f1_keywords:
- C2550
helpviewer_keywords:
- C2550
ms.assetid: 3293f53e-ee66-4035-920d-34e115c3a24c
ms.openlocfilehash: 2df6ae70be31bc519e6cfd826646073becf1ad61
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50462679"
---
# <a name="compiler-error-c2550"></a>Derleyici Hatası C2550

'identifier': oluşturucu başlatıcı listelerine yalnızca Oluşturucu tanımlarında izin verilir

Bir temel sınıf başlatıcı listesi bir oluşturucusu olmayan bir işlev tanımı üzerinde kullanılır.

Aşağıdaki örnek, C2550 oluşturur:

```
// C2550.cpp
// compile with: /c
class C {
public:
   C();
};

class D : public C {
public:
   D();
   void func();
};

void D::func() : C() {}  // C2550
D::D() : C() {}   // OK
```