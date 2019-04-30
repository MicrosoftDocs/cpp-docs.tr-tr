---
title: Derleyici Hatası C2473
ms.date: 11/04/2016
f1_keywords:
- C2473
helpviewer_keywords:
- C2473
ms.assetid: 6bb7dbf5-b198-490f-860e-fd64d0c2a284
ms.openlocfilehash: 232f89a714d70c6914b73a370c5f658ff4283ab4
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64345636"
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