---
title: Derleyici Hatası C3244
ms.date: 11/04/2016
f1_keywords:
- C3244
helpviewer_keywords:
- C3244
ms.assetid: dae6c49b-5212-4206-8f61-d4010c0b9969
ms.openlocfilehash: fe17ac0f20c5644fd5bb81094242403b244bd1d5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62174932"
---
# <a name="compiler-error-c3244"></a>Derleyici Hatası C3244

'method': Bu yöntem 'interface' tarafından 'interface' tarafından kullanılmaya başlandı

Çalıştığınız [açıkça geçersiz kılma](../../cpp/explicit-overrides-cpp.md) belirtilen arabiriminde yok, ancak başka bir temel sınıfta mevcut bir üyesi.

Aşağıdaki örnek, C3244 oluşturur:

```
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