---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3890'
title: Derleyici hatası C3890
ms.date: 11/04/2016
f1_keywords:
- C3890
helpviewer_keywords:
- C3890
ms.assetid: 2f22c2fd-c14e-45e1-b936-b739ffc0b135
ms.openlocfilehash: 1eddf71c5b380f97cd9910649f64fc67045b76a7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97274300"
---
# <a name="compiler-error-c3890"></a>Derleyici hatası C3890

' var ': sabit değerli bir veri üyesinin adresini alamaz

Atık toplanmış yığında sabit değerli bir veri üyesi var.  Atık olarak toplanan yığında bir nesne taşınabilir, bu nedenle adres alınması yararlı değildir.

Aşağıdaki örnek C3890 oluşturur:

```cpp
// C3890.cpp
// compile with: /clr
ref struct Y1 {
   literal int staticConst = 9;
};

int main() {
   int p = &Y1::staticConst;   // C3890
   int p2 = Y1::staticConst;   // OK
}
```
