---
title: Derleyici Hatası C3890
ms.date: 11/04/2016
f1_keywords:
- C3890
helpviewer_keywords:
- C3890
ms.assetid: 2f22c2fd-c14e-45e1-b936-b739ffc0b135
ms.openlocfilehash: 2354be5ac7299fc0361e1b3ad50554e9949f8c1d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50599491"
---
# <a name="compiler-error-c3890"></a>Derleyici Hatası C3890

'var': sabit değerli bir veri üyesinin adresini alamazsınız

Sabit değerli veri üyesi üzerinde atık olarak toplanmış yığınla var.  Atık olarak toplanmış yığındaki bir nesne taşınabilir, bu nedenle adresini almak kullanışlı değildir.

Aşağıdaki örnek, C3890 oluşturur:

```
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