---
title: Derleyici Uyarısı (Düzey 3) C4102
ms.date: 11/04/2016
f1_keywords:
- C4102
helpviewer_keywords:
- C4102
ms.assetid: 349f308a-daf3-48c6-bd53-6c38b73f8880
ms.openlocfilehash: 9e5b4850c82083e19a0fe859b1021b5beecf1a1d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50666585"
---
# <a name="compiler-warning-level-3-c4102"></a>Derleyici Uyarısı (Düzey 3) C4102

'etiketi': Etiket başvurusu kaldırıldı

Etiket tanımlandı ancak nikdy neodkazovalo. Derleyici, etiket yok sayar.

Aşağıdaki örnek, C4102 oluşturur:

```
// C4102.cpp
// compile with: /W3
int main() {
   int a;

   test:   // C4102, remove the unreferenced label to resolve

   a = 1;
}
```