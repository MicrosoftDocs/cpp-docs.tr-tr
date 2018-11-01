---
title: Derleyici Hatası C3060
ms.date: 11/04/2016
f1_keywords:
- C3060
helpviewer_keywords:
- C3060
ms.assetid: 6282bb92-0546-4b59-9435-d3840bf93bdb
ms.openlocfilehash: c77af7fa1220aa5211d480cddf3bf0979c642ade
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50515408"
---
# <a name="compiler-error-c3060"></a>Derleyici Hatası C3060

'member': bir arkadaş işlev tam adı (Bu yalnızca bildirilebilir) kullanarak bir sınıf içinde tanımlanamaz

İzin bir tam ad kullanılarak bir arkadaş işlev tanımlandı.

Aşağıdaki örnek, C3060 oluşturur:

```
// C3060.cpp
class A {
public:
   void func();
};

class C {
public:
   friend void A::func() { }   // C3060
   // Try the following line and the out of class definition:
   // friend void A::func();
};

// void A::func(){}
```