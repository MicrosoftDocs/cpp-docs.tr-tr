---
title: Derleyici hatası C2462
ms.date: 11/04/2016
f1_keywords:
- C2462
helpviewer_keywords:
- C2462
ms.assetid: a8601bf8-f5ce-41de-9117-e2632bd4996b
ms.openlocfilehash: 8db79bf9813d9701b45d9a0427f68cfbecc3eba4
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87214678"
---
# <a name="compiler-error-c2462"></a>Derleyici hatası C2462

' tanımlayıcı ': ' New-Expression ' içinde tür tanımlanamaz

İşlecin işlenen alanında bir tür tanımlayamazsınız **`new`** . Tür tanımını ayrı bir deyime koyun.

Aşağıdaki örnek C2462 oluşturur:

```cpp
// C2462.cpp
int main() {
   new struct S { int i; };   // C2462
}
```
