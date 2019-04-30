---
title: Derleyici Hatası C2254
ms.date: 11/04/2016
f1_keywords:
- C2254
helpviewer_keywords:
- C2254
ms.assetid: 49bb3d7e-3bdf-4af6-937c-fa627be412a9
ms.openlocfilehash: da89741811bbb9055f3f6793d115a357d80ab79a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62397542"
---
# <a name="compiler-error-c2254"></a>Derleyici Hatası C2254

'function': Saf belirtici veya soyut geçersiz kılma belirticisi arkadaş işlev üzerinde kullanılamaz

A `friend` işlevi olarak saf belirtilen `virtual`.

Aşağıdaki örnek, C2254 oluşturur:

```
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