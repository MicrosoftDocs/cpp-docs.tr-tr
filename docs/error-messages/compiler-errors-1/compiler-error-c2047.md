---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2047'
title: Derleyici hatası C2047
ms.date: 11/04/2016
f1_keywords:
- C2047
helpviewer_keywords:
- C2047
ms.assetid: 686a5a81-3857-4753-84a0-5c2e7149cbee
ms.openlocfilehash: 40df340017b134a3d2abe092478658f92142298d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97175124"
---
# <a name="compiler-error-c2047"></a>Derleyici hatası C2047

Geçersiz varsayılan

Anahtar sözcüğü **`default`** yalnızca bir **`switch`** ifadede görünebilir.

Aşağıdaki örnek C2047 oluşturur:

```cpp
// C2047.cpp
int main() {
   int i = 0;
   default:   // C2047
   switch(i) {
      case 0:
      break;
   }
}
```

Olası çözüm:

```cpp
// C2047b.cpp
int main() {
   int i = 0;
   switch(i) {
      case 0:
      break;
      default:
      break;
   }
}
```
