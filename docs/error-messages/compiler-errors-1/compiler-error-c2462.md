---
title: Derleyici hatası C2462
ms.date: 11/04/2016
f1_keywords:
- C2462
helpviewer_keywords:
- C2462
ms.assetid: a8601bf8-f5ce-41de-9117-e2632bd4996b
ms.openlocfilehash: 4eb50ddac51ea78ab3a28d7703384f02eb026ecb
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74743932"
---
# <a name="compiler-error-c2462"></a>Derleyici hatası C2462

' tanımlayıcı ': ' New-Expression ' içinde tür tanımlanamaz

`new` işlecinin işlenen alanında bir tür tanımlayamazsınız. Tür tanımını ayrı bir deyime koyun.

Aşağıdaki örnek C2462 oluşturur:

```cpp
// C2462.cpp
int main() {
   new struct S { int i; };   // C2462
}
```
