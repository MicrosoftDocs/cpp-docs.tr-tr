---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2046'
title: Derleyici hatası C2046
ms.date: 11/04/2016
f1_keywords:
- C2046
helpviewer_keywords:
- C2046
ms.assetid: f0c8f9dd-dbd7-4c4a-8838-fde54208ec71
ms.openlocfilehash: 7d1735c4f27c80f2830b7f36a9f3533033119535
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97175163"
---
# <a name="compiler-error-c2046"></a>Derleyici hatası C2046

geçersiz durum

Anahtar sözcüğü `case` yalnızca bir **`switch`** ifadede görünebilir.

Aşağıdaki örnek C2046 oluşturur:

```cpp
// C2046.cpp
int main() {
   case 0:   // C2046
}
```

Olası çözüm:

```cpp
// C2046b.cpp
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
