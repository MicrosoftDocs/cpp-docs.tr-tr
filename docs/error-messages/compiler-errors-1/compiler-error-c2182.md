---
title: Derleyici hatası C2182
ms.date: 11/04/2016
f1_keywords:
- C2182
helpviewer_keywords:
- C2182
ms.assetid: dfd8d47d-9606-496e-bd96-4bf41ba1f857
ms.openlocfilehash: da702087ad4d445d7fd4abe1956040a45b4414b6
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74737146"
---
# <a name="compiler-error-c2182"></a>Derleyici hatası C2182

' tanımlayıcı ': ' void ' türünün geçersiz kullanımı

Değişken `void`olarak bildirilmiştir.

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
