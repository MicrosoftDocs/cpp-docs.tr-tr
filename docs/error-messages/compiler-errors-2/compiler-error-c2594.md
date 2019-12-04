---
title: Derleyici hatası C2594
ms.date: 11/04/2016
f1_keywords:
- C2594
helpviewer_keywords:
- C2594
ms.assetid: 68cd708f-266e-44b0-a211-3e3ab63b11bf
ms.openlocfilehash: ade657f9ada2a2249d2f96b7caada7b9719195d1
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74759340"
---
# <a name="compiler-error-c2594"></a>Derleyici hatası C2594

' operator ': ' type1 ' öğesinden ' type2 ' öğesine belirsiz dönüşümler

*Type1* 'den *type2* 'e dönüştürme işlemi bundan daha doğrudan. *Type1* 'den *type2*'e dönüştürmek için iki olası çözüm öneririz. İlk seçenek, *Type1* ' den *type2*' ye doğrudan dönüştürme tanımlamak ve ikinci seçenek *Type1* ile *type2*arasında bir dönüştürme sırası belirtmektir.

Aşağıdaki örnek C2594 oluşturur. Hataya önerilen çözüm bir dönüştürme dizisidir:

```cpp
// C2594.cpp
// compile with: /c
struct A{};
struct I1 : A {};
struct I2 : A {};
struct D : I1, I2 {};

A *f (D *p) {
   return (A*) (p);    // C2594

// try the following line instead
// return static_cast<A *>(static_cast<I1 *>(p));
}
```
