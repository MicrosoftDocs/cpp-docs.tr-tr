---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2135'
title: Derleyici hatası C2135
ms.date: 11/04/2016
f1_keywords:
- C2135
helpviewer_keywords:
- C2135
ms.assetid: aa360d22-4f79-4de1-b384-93cadd10975f
ms.openlocfilehash: 85b8dce9bd735ec7e4e17ce86cd8a03c1a2778c3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97323122"
---
# <a name="compiler-error-c2135"></a>Derleyici hatası C2135

' bit işleci ': geçersiz bit alanı işlemi

Address-of işleci ( `&` ) bir bit alanına uygulanamaz.

Aşağıdaki örnek C2135 oluşturur:

```cpp
// C2135.cpp
struct S {
   int i : 1;
};

struct T {
   int j;
};
int main() {
   &S::i;   // C2135 address of a bit field
   &T::j;   // OK
}
```
