---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2048'
title: Derleyici hatası C2048
ms.date: 11/04/2016
f1_keywords:
- C2048
helpviewer_keywords:
- C2048
ms.assetid: 44704726-85fc-42f0-afb9-194df8c4ca7c
ms.openlocfilehash: cc87d0ca1670daa4cb137f4c3053030d188884e4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97175085"
---
# <a name="compiler-error-c2048"></a>Derleyici hatası C2048

birden çok varsayılan

Bir **`switch`** ifade birden çok **`default`** etiket içerir. **`default`** Hatayı çözümlemek için etiketlerden birini silin.

Aşağıdaki örnek C2048 oluşturur:

```cpp
// C2048.cpp
int main() {
   int a = 1;
   switch (a) {
      case 1:
         a = 0;
      default:
         a = 2;
      default:   // C2048
         a = 3;
   }
}
```

Olası çözüm:

```cpp
// C2048b.cpp
int main() {
   int a = 1;
   switch (a) {
      case 1:
         a = 0;
      default:
         a = 2;
   }
}
```
