---
title: Derleyici Hatası C2100
ms.date: 11/04/2016
f1_keywords:
- C2100
helpviewer_keywords:
- C2100
ms.assetid: 9ed5ea11-9d55-4ddf-8b1a-162c74f3c390
ms.openlocfilehash: 89273d5ef9c3b011a7b08a160431dcbc17fc065e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50677545"
---
# <a name="compiler-error-c2100"></a>Derleyici Hatası C2100

Geçersiz yöneltme

Yöneltme işleci ( `*` ) nonpointer değerine uygulanır.

Aşağıdaki örnek, C2100 oluşturur:

```
// C2100.cpp
int main() {
   int r = 0, *s = 0;
   s = &r;
   *r = 200;   // C2100
   *s = 200;   // OK
}
```