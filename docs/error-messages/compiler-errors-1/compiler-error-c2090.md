---
title: Derleyici hatası C2090
ms.date: 11/04/2016
f1_keywords:
- C2090
helpviewer_keywords:
- C2090
ms.assetid: e8176e55-382b-453d-aa27-6597f0274afd
ms.openlocfilehash: 3c87bc75e984c544646a28a663302acd5733ac25
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74755947"
---
# <a name="compiler-error-c2090"></a>Derleyici hatası C2090

işlev dizi döndürüyor

Bir işlev bir dizi döndüremez. Bunun yerine diziye bir işaretçi döndürün.

Aşağıdaki örnek C2090 oluşturur:

```cpp
// C2090.cpp
int func1(void)[] {}   // C2090
```

Olası çözüm:

```cpp
// C2090b.cpp
// compile with: /c
int* func2(int * i) {
   return i;
}
```
