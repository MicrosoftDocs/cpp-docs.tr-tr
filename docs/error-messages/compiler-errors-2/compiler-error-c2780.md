---
title: Derleyici hatası C2780
ms.date: 11/04/2016
f1_keywords:
- C2780
helpviewer_keywords:
- C2780
ms.assetid: 423793d8-a3b2-4f35-85f8-ae1d043e2b69
ms.openlocfilehash: cf327852da325940b1090e4f6199ac10c83ea09b
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74739967"
---
# <a name="compiler-error-c2780"></a>Derleyici hatası C2780

' declaration ': N bağımsız değişken bekliyor-s bekleniyor

Bir işlev şablonunda çok az veya çok fazla bağımsız değişken var.

Aşağıdaki örnek C2780 oluşturur ve nasıl düzeltileceğini gösterir:

```cpp
// C2780.cpp
template<typename T>
void f(T, T){}

int main() {
   f(1);  // C2780
   // try the following line instead
   // f(1,2);
}
```
