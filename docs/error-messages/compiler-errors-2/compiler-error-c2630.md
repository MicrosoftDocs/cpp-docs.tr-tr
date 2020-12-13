---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2630'
title: Derleyici hatası C2630
ms.date: 11/04/2016
f1_keywords:
- C2630
helpviewer_keywords:
- C2630
ms.assetid: 7a655a9c-bab4-495b-97a3-a3f34cf5369a
ms.openlocfilehash: 67bd0687afcd4668e89335fbe6f79e46d8237c16
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97341184"
---
# <a name="compiler-error-c2630"></a>Derleyici hatası C2630

' symbol ', virgülle ayrılmış bir liste olarak bulundu

Simge, virgül gerektiren bir bağlamda görünür.

Aşağıdaki örnek C2630 oluşturur:

```cpp
// C2630.cpp
// compile with: /c
struct D {
   D(int);
};

struct E {
   E(int);
};

class C : public D, public E {
   C();
};

C::C() : D(0) ; E(0) { }   // C2630
C::C() : D(0), E(0) {}   // OK
```
