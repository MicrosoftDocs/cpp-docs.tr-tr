---
title: Derleyici hatası C2182
ms.date: 11/04/2016
f1_keywords:
- C2182
helpviewer_keywords:
- C2182
ms.assetid: dfd8d47d-9606-496e-bd96-4bf41ba1f857
ms.openlocfilehash: 0312a1144b3afec52b2041cc25374b691ed97d0c
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87209883"
---
# <a name="compiler-error-c2182"></a>Derleyici hatası C2182

' tanımlayıcı ': ' void ' türünün geçersiz kullanımı

Değişken, tür olarak bildirilmiştir **`void`** .

Aşağıdaki örnek C2182 oluşturur:

```cpp
// C2182.cpp
// compile with: /c
int main() {
   int i = 10;
   void &ir = i;   // C2182 cannot have a reference to type void
   int &ir = i;   // OK
}
```
