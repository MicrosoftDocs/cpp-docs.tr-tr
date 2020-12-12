---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2052'
title: Derleyici hatası C2052
ms.date: 11/04/2016
f1_keywords:
- C2052
helpviewer_keywords:
- C2052
ms.assetid: 922ca43b-b64b-4ef7-9611-c7313be3fd79
ms.openlocfilehash: 3274b601fc54368fd2c27f3faa1cc1092f5d88b2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97174968"
---
# <a name="compiler-error-c2052"></a>Derleyici hatası C2052

' Type ': case ifadesi için geçersiz tür

Case ifadeleri tamsayı sabitleri olmalıdır.

Aşağıdaki örnek C2052 oluşturur:

```cpp
// C2052.cpp
int main() {
   int index = 0;
   switch (index) {
      case 1:
         return 24;
      case 1.0:   // C2052
      // try the following line instead
      // case 2:
         return 23;
   }
}
```
