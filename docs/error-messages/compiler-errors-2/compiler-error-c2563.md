---
title: Derleyici hatası C2563
ms.date: 11/04/2016
f1_keywords:
- C2563
helpviewer_keywords:
- C2563
ms.assetid: 54abba68-6458-4ca5-894d-3babdb7b3552
ms.openlocfilehash: 983788f041651fcd313c0707a4a7c64cc6e33c5a
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74755544"
---
# <a name="compiler-error-c2563"></a>Derleyici hatası C2563

biçimsel parametre listesinde uyuşmazlık

Bir işlevin (veya bir işlev işaretçisinin) biçimsel parametre listesi, başka bir işlevden (veya bir üye işlev işaretçisinden) eşleşmiyor. Sonuç olarak, işlev veya işaretçilerin atanması yapılamaz.

Aşağıdaki örnek C2563 oluşturur:

```cpp
// C2563.cpp
void func( int );
void func( int, int );
int main() {
   void *fp();
   fp = func;   // C2563
}
```
