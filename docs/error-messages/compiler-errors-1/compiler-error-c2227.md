---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2227'
title: Derleyici hatası C2227
ms.date: 11/04/2016
f1_keywords:
- C2227
helpviewer_keywords:
- C2227
ms.assetid: d470e8b8-7e15-468b-84fa-37d1a0132271
ms.openlocfilehash: 75cab2269a254bc485a33396fb128aaa955651d2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97195079"
---
# <a name="compiler-error-c2227"></a>Derleyici hatası C2227

'->Member ' sol tarafı sınıf/yapı/birleşim/genel türüne işaret etmelidir

Solundaki işlenen, bir `->` sınıfa, yapıya veya birleşime yönelik bir işaretçi değildir.

Aşağıdaki örnek C2227 oluşturur:

```cpp
// C2227.cpp
int *pInt;
struct S {
public:
    int member;
} s, *pS = &s;

int main() {
   pInt->member = 0;   // C2227 pInt points to an int
   pS->member = 0;   // OK
}
```
