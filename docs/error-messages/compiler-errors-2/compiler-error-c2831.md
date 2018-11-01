---
title: Derleyici Hatası C2831
ms.date: 11/04/2016
f1_keywords:
- C2831
helpviewer_keywords:
- C2831
ms.assetid: c8c04288-0889-4265-a077-17f94cbcdcc9
ms.openlocfilehash: b0708a7c45f33e30280666cf9bc903723d6a9c26
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50628339"
---
# <a name="compiler-error-c2831"></a>Derleyici Hatası C2831

'operator işleci' varsayılan parametrelere sahip olamaz

Varsayılan parametreleri yalnızca üç işleçleri olabilir:

- [new](../../cpp/new-operator-cpp.md)

- Atama =

- Sol parantez)

Aşağıdaki örnek, C2831 oluşturur:

```
// C2831.cpp
// compile with: /c
#define BINOP <=
class A {
public:
   int i;
   int operator BINOP(int x = 1) {   // C2831
   // try the following line instead
   // int operator BINOP(int x) {
      return i+x;
   }
};
```