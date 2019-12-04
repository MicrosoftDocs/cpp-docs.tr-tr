---
title: Derleyici hatası C2254
ms.date: 11/04/2016
f1_keywords:
- C2254
helpviewer_keywords:
- C2254
ms.assetid: 49bb3d7e-3bdf-4af6-937c-fa627be412a9
ms.openlocfilehash: 38220575a48720a9df0e232ef74c8743e7e056c7
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74758846"
---
# <a name="compiler-error-c2254"></a>Derleyici hatası C2254

' function ': saf belirtici veya soyut geçersiz kılma tanımlayıcısına arkadaş işlevinde izin verilmiyor

`friend` işlevi saf `virtual`olarak belirtilir.

Aşağıdaki örnek C2254 oluşturur:

```cpp
// C2254.cpp
// compile with: /c
class A {
public:
   friend void func1() = 0;   // C2254, func1 is friend
   void virtual func2() = 0;   // OK, pure virtual
   friend void func3();   // OK, friend not virtual nor pure
};

void func1() {};
void func3() {};
```
