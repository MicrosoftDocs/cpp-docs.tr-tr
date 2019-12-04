---
title: Derleyici hatası C2229
ms.date: 11/04/2016
f1_keywords:
- C2229
helpviewer_keywords:
- C2229
ms.assetid: 933c7cf2-a463-4e74-b0b4-59dedad987fb
ms.openlocfilehash: 2d974c4f0630a592daad956448bf21cea21efb7c
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74759275"
---
# <a name="compiler-error-c2229"></a>Derleyici hatası C2229

' Identifier ' türünde geçersiz bir sıfır boyutlu dizi vardır

Bir yapının veya bit alanının üyesi, son üye olmayan sıfır boyutlu bir dizi içerir.

Yapının son üyesi olarak sıfır boyutlu bir diziye sahip olabilirsiniz, yapısını ayırdığınızda boyutunu belirtmeniz gerekir.

Sıfır boyutlu dizi yapının son üyesi değilse, derleyici kalan alanların sapmasını hesaplayamaz.

Aşağıdaki örnek C2229 oluşturur:

```cpp
// C2229.cpp
struct S {
   int a[0];  // C2229  zero-sized array
   int b[1];
};

struct S2 {
   int a;
   int b[0];
};

int main() {
   // allocate 7 elements for b field
   S2* s2 = (S2*)new int[sizeof(S2) + 7*sizeof(int)];
   s2->b[6] = 100;
}
```
