---
title: Derleyici Hatası C2227
ms.date: 11/04/2016
f1_keywords:
- C2227
helpviewer_keywords:
- C2227
ms.assetid: d470e8b8-7e15-468b-84fa-37d1a0132271
ms.openlocfilehash: 8f9fc435682eb400574eea61a6f90392fa679233
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50452747"
---
# <a name="compiler-error-c2227"></a>Derleyici Hatası C2227

Sol 'üye ->', sınıf/yapı/birleşim/genel türe işaret etmelidir

İşlenen solundaki `->` bir sınıf, yapı veya birleşim işaretçisi değil.

Aşağıdaki örnek, C2227 oluşturur:

```
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