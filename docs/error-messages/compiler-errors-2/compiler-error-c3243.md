---
title: Derleyici Hatası C3243
ms.date: 11/04/2016
f1_keywords:
- C3243
helpviewer_keywords:
- C3243
ms.assetid: 35d8ad1a-377d-47df-be9d-c55eea23340f
ms.openlocfilehash: 1fd0cdf44cb820882cdcda3728b664321f730d5c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62173528"
---
# <a name="compiler-error-c3243"></a>Derleyici Hatası C3243

aşırı yükleme işlevlerinin Hiçbiri 'interface' tarafından sunulan

Çalıştığınız [açıkça geçersiz kılma](../../cpp/explicit-overrides-cpp.md) belirtilen arabiriminde var olmayan üye.

Aşağıdaki örnek, C3243 oluşturur:

```
// C3243.cpp
#pragma warning(disable:4199)
__interface IX14A {
   void g();
};

__interface IX14B {
   void f();
   void f(int);
};

class CX14 : public IX14A, public IX14B {
public:
   void IX14A::g();
   void IX14B::f();
   void IX14B::f(int);
};

void CX14::IX14A::f()   // C3243 occurs here
{
}
```