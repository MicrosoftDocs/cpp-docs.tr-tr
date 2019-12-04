---
title: Derleyici hatası C3060
ms.date: 11/04/2016
f1_keywords:
- C3060
helpviewer_keywords:
- C3060
ms.assetid: 6282bb92-0546-4b59-9435-d3840bf93bdb
ms.openlocfilehash: 6eba6264caf3e9f443e1b614a62b53708688ab95
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74749561"
---
# <a name="compiler-error-c3060"></a>Derleyici hatası C3060

' üye ': bir arkadaş işlev tam ad kullanılarak bir sınıf içinde tanımlanamaz (yalnızca tanımlanmış olabilir)

Bir Friend işlevi, izin verilmeyen bir tam ad kullanılarak tanımlandı.

Aşağıdaki örnek C3060 oluşturur:

```cpp
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
