---
title: Derleyici hatası C2156
ms.date: 11/04/2016
f1_keywords:
- C2156
helpviewer_keywords:
- C2156
ms.assetid: 136f9c67-2c27-4f61-b7e6-ccd202eca697
ms.openlocfilehash: da8a5a9bcdeb33a9b308e24b129fded0595449a3
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74755908"
---
# <a name="compiler-error-c2156"></a>Derleyici hatası C2156

pragma işlevin dışında olmalıdır

Genel düzeyde (bir işlev gövdesi dışında) belirtilmesi gereken bir pragma, bir işlev içinde.

Aşağıdaki örnek C2156 oluşturur:

```cpp
// C2156.cpp
#pragma optimize( "l", on )   // OK
int main() {
   #pragma optimize( "l", on )   // C2156
}
```
