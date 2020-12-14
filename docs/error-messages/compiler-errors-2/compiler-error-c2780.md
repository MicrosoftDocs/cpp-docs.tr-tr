---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2780'
title: Derleyici hatası C2780
ms.date: 11/04/2016
f1_keywords:
- C2780
helpviewer_keywords:
- C2780
ms.assetid: 423793d8-a3b2-4f35-85f8-ae1d043e2b69
ms.openlocfilehash: 00b1117bdcae2559b7ec7c374f7b5ca403aa783c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97298038"
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
