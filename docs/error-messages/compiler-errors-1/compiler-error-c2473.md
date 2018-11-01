---
title: Derleyici Hatası C2473
ms.date: 11/04/2016
f1_keywords:
- C2473
helpviewer_keywords:
- C2473
ms.assetid: 6bb7dbf5-b198-490f-860e-fd64d0c2a284
ms.openlocfilehash: 232f89a714d70c6914b73a370c5f658ff4283ab4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50631796"
---
# <a name="compiler-error-c2473"></a>Derleyici Hatası C2473

'identifier': işlev tanımı gibi görünüyor, ancak hiçbir parametre listesi yoktur.

Derleyici, parametre listesi olmayan bir işlev göründüğüne algıladı.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C2473 oluşturur.

```
// C2473.cpp
// compile with: /clr /c
class A {
   int i {}   // C2473
};

class B {
   int i() {}   // OK
};
```