---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3244'
title: Derleyici hatası C3244
ms.date: 11/04/2016
f1_keywords:
- C3244
helpviewer_keywords:
- C3244
ms.assetid: dae6c49b-5212-4206-8f61-d4010c0b9969
ms.openlocfilehash: 2c74efd321d87d6451d7949c72f1f50ebb6dface
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97307229"
---
# <a name="compiler-error-c3244"></a>Derleyici hatası C3244

' Method ': Bu yöntem ' interface ' tarafından değil ' Interface ' tarafından tanıtılmıştı

Belirtilen arabirimde mevcut olmayan ancak başka bir temel sınıfta bulunan bir üyeyi [açıkça geçersiz kılmayı](../../cpp/explicit-overrides-cpp.md) denediniz.

Aşağıdaki örnek C3244 oluşturur:

```cpp
// C3244.cpp
#pragma warning(disable:4199)

__interface IX15A {
   void f();
};

__interface IX15B {
   void g();
};

class CX15 : public IX15A, public IX15B {
public:
   void IX15A::f();
   void IX15B::g();
};

void CX15::IX15A::g()   // C3244 occurs here
{
}
```
