---
title: Derleyici Hatası C2835
ms.date: 11/04/2016
f1_keywords:
- C2835
helpviewer_keywords:
- C2835
ms.assetid: 41c70630-983f-4da2-8342-513cf48b0519
ms.openlocfilehash: 069514d1a5d2b16e1175bbc1ce0c796bee64110a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50637976"
---
# <a name="compiler-error-c2835"></a>Derleyici Hatası C2835

Kullanıcı tanımlı dönüştürme 'type' hiçbir biçimsel parametre almıyor

Kullanıcı tanımlı tür dönüştürmeler, biçimsel parametre alamaz.

Aşağıdaki örnek, C2835 oluşturur:

```
// C2835.cpp
class A {
public:
   char v_char;

   A() {
      v_char = 'A';
   };
   operator char(char a) {   // C2835
   // try the following line instead
   // operator char() {
      return v_char + 1;
   };
};

int main() {
   A a;
}
```