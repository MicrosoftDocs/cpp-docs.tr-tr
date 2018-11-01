---
title: Derleyici Hatası C2758
ms.date: 11/04/2016
f1_keywords:
- C2758
helpviewer_keywords:
- C2758
ms.assetid: 1d273034-194c-4926-9869-142d1b219cbe
ms.openlocfilehash: c3a86b8b8c7f122929a52221d4f01a17c50395be
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50618042"
---
# <a name="compiler-error-c2758"></a>Derleyici Hatası C2758

'member': başvuru türünün bir üyesi başlatılmalıdır

Oluşturucu başlatıcı listesinde bir başvuru türünün üyesi Başlatmıyor oluşan derleyici hatası C2758 neden olur. Derleyici, üye tanımsız bırakır. Başvuru üyesi değişkenleri gerekir ne zaman başlatılır bildirildi veya oluşturucu başlatma listesinde bir değer verilmesi.

Aşağıdaki örnek, C2758 oluşturur:

```
// C2758.cpp
// Compile by using: cl /W3 /c C2758.cpp
struct A {
   const int i;

   A(int n) { };   // C2758
   // try the following line instead
   // A(int n) : i{n} {};
};
```