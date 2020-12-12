---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2473'
title: Derleyici hatası C2473
ms.date: 11/04/2016
f1_keywords:
- C2473
helpviewer_keywords:
- C2473
ms.assetid: 6bb7dbf5-b198-490f-860e-fd64d0c2a284
ms.openlocfilehash: c81e1329e17c03b3bd8f857d2f8ceddcc1a9f264
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97164464"
---
# <a name="compiler-error-c2473"></a>Derleyici hatası C2473

' tanımlayıcı ': işlev tanımı gibi görünüyor ancak hiçbir parametre listesi yok.

Derleyici, parametre listesi olmadan işlevi beğendiklerinizi algıladı.

## <a name="example"></a>Örnek

Aşağıdaki örnek C2473 oluşturur.

```cpp
// C2473.cpp
// compile with: /clr /c
class A {
   int i {}   // C2473
};

class B {
   int i() {}   // OK
};
```
