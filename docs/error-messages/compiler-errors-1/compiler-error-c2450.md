---
title: Derleyici hatası C2450
ms.date: 11/04/2016
f1_keywords:
- C2450
helpviewer_keywords:
- C2450
ms.assetid: 929f1c06-8774-468b-be2a-f428757875a2
ms.openlocfilehash: 55c7f7ba8708e1475404a474f85df7dbe37fcec0
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87220359"
---
# <a name="compiler-error-c2450"></a>Derleyici hatası C2450

' Type ' türündeki switch ifadesi geçersizdir

**`switch`** İfade geçersiz bir tür olarak değerlendirilir. Bir tamsayı türüne veya bir tamsayı türüne belirsiz dönüştürmeye sahip bir sınıf türüne göre değerlendirilmelidir. Kullanıcı tanımlı bir tür olarak değerlendirilirse, bir dönüştürme işleci sağlamanız gerekir.

Aşağıdaki örnek C2450 oluşturur:

```cpp
// C2450.cpp
class X {
public:
   int i;
} x;

class Y {
public:
   int i;
   operator int() { return i; }   // conversion operator
} y;

int main() {
   int j = 1;
   switch ( x ) {   // C2450, x is not type int
   // try the following line instead
   // switch ( y ) {
      default:  ;
   }
}
```
