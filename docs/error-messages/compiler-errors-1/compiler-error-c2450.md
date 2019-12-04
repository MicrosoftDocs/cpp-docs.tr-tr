---
title: Derleyici hatası C2450
ms.date: 11/04/2016
f1_keywords:
- C2450
helpviewer_keywords:
- C2450
ms.assetid: 929f1c06-8774-468b-be2a-f428757875a2
ms.openlocfilehash: 2d015bd165986467a82f33a2ae0dda08c6f6d248
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74744153"
---
# <a name="compiler-error-c2450"></a>Derleyici hatası C2450

' Type ' türündeki switch ifadesi geçersizdir

`switch` ifadesi geçersiz bir tür olarak değerlendirilir. Bir tamsayı türüne veya bir tamsayı türüne belirsiz dönüştürmeye sahip bir sınıf türüne göre değerlendirilmelidir. Kullanıcı tanımlı bir tür olarak değerlendirilirse, bir dönüştürme işleci sağlamanız gerekir.

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
