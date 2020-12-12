---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2063'
title: Derleyici hatası C2063
ms.date: 11/04/2016
f1_keywords:
- C2063
helpviewer_keywords:
- C2063
ms.assetid: 0a90c18f-4029-416a-9128-e8713b53e6f1
ms.openlocfilehash: 18b2cd6bf68144245b85d744923404f4a27d63f0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97328619"
---
# <a name="compiler-error-c2063"></a>Derleyici hatası C2063

' tanımlayıcı ': bir işlev değil

Tanımlayıcı bir işlev olarak kullanılır ancak işlev olarak bildirilmez.

Aşağıdaki örnek C2063 oluşturur:

```c
// C2063.c
int main() {
   int i, j;
   j = i();    // C2063, i is not a function
}
```

Olası çözüm:

```c
// C2063b.c
int i() { return 0;}
int main() {
   int j;
   j = i();
}
```
