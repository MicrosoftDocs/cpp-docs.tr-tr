---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2450'
title: Derleyici hatası C2450
ms.date: 11/04/2016
f1_keywords:
- C2450
helpviewer_keywords:
- C2450
ms.assetid: 929f1c06-8774-468b-be2a-f428757875a2
ms.openlocfilehash: 5e2d838ea03ca8d42b2addb2e52d4cf29deabfa1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97332406"
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
