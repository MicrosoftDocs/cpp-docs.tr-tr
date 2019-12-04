---
title: Derleyici hatası C2371
ms.date: 11/04/2016
f1_keywords:
- C2371
helpviewer_keywords:
- C2371
ms.assetid: d383993d-05ef-4e35-8129-3b58a6f7b7b7
ms.openlocfilehash: 4b488ff1c43f6d8d95e79ec9754cdecc17198ad4
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74745648"
---
# <a name="compiler-error-c2371"></a>Derleyici hatası C2371

' tanımlayıcı ': yeniden tanımlama; farklı temel türler

Tanımlayıcı zaten tanımlanmış.

Aşağıdaki örnek C2371 oluşturur:

```cpp
// C2371.cpp
int main() {
   int i;
   float i;   // C2371, redefinition
   float f;   // OK
}
```
