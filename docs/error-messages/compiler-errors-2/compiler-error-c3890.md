---
title: Derleyici Hatası C3890 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3890
dev_langs:
- C++
helpviewer_keywords:
- C3890
ms.assetid: 2f22c2fd-c14e-45e1-b936-b739ffc0b135
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e599150c1e8d62d751f9dca67cffc99fb079bd32
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46104930"
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