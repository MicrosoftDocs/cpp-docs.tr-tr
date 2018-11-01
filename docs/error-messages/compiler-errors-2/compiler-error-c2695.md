---
title: Derleyici Hatası C2695
ms.date: 11/04/2016
f1_keywords:
- C2695
helpviewer_keywords:
- C2695
ms.assetid: 3f6f2091-c38b-40ea-ab6c-f1846f5702d7
ms.openlocfilehash: 08f74bf635324ed9a05c13ecf532862d58e4f0b1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50429425"
---
# <a name="compiler-error-c2695"></a>Derleyici Hatası C2695

'function1': geçersiz kılan sanal işlev farklı 'function2' yalnızca çağırma kuralı

Türetilen bir sınıfta bir işlev imzası, temel sınıf içinde bir işlevi geçersiz kılma ve çağırma kuralı değiştirin.

Aşağıdaki örnek, C2695 oluşturur:

```
// C2695.cpp
class C {
   virtual void __fastcall func();
};

class D : public C {
   virtual void __clrcall func();   // C2695
};
```