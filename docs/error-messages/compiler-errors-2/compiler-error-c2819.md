---
title: Derleyici Hatası C2819 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2819
dev_langs:
- C++
helpviewer_keywords:
- C2819
ms.assetid: fcc7762d-cb82-4bb1-a715-0d82da832edf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e535b47828a70a7a2e52606bc5c9de6ceb62ee48
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46095460"
---
# <a name="compiler-error-c2819"></a>Derleyici Hatası C2819

türü 'type', '-> bir aşırı yüklü üye işleci' yok.

Tanımlamanız gereken `operator->()` Bu işaretçi işlemi kullanılacak.

Aşağıdaki örnek, C2819 oluşturur:

```
// C2819.cpp
// compile with: /c
class A {
   public:
      int i;
};

class B {};

void C(B j) {
   j->i;   // C2819
}

class D {
   A* pA;

   public:
      A* operator->() {
         return pA;
      }
};

void F(D j) {
   j->i;
}
```

C2819 kullanırken da gerçekleşebilir [başvuru türleri için C++ yığın anlamları](../../dotnet/cpp-stack-semantics-for-reference-types.md). Aşağıdaki örnek, C2819 oluşturur:

```
// C2819_b.cpp
// compile with: /clr
ref struct R {
   void Test() {}
};

int main() {
   R r;
   r->Test();   // C2819
   r.Test();   // OK
}
```