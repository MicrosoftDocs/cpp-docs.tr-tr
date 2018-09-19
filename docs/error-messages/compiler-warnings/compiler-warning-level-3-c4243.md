---
title: Derleyici Uyarısı (Düzey 3) C4243 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4243
dev_langs:
- C++
helpviewer_keywords:
- C4243
ms.assetid: ca72f9ad-ce0b-43a9-a68c-106e1f8b90ef
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b407939b58d1025698f7c3d82bbe1921b33f90a5
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46025691"
---
# <a name="compiler-warning-level-3-c4243"></a>Derleyici Uyarısı (Düzey 3) C4243

'dönüştürme türünü' dönüştürme 'type1' 'type2' var, ancak erişilebilir değil

Bir taban sınıfı işaretçisini bir türetilmiş sınıf işaretçisine dönüştürülür, ancak türetilen sınıfın temel sınıf özel veya korumalı erişimle devralır.

Aşağıdaki örnek, C4243 oluşturur:

```
// C4243.cpp
// compile with: /W3
// C4243 expected
struct B {
   int f() {
      return 0;
   };
};

struct D : private B {};
struct E : public B {};

int main() {
   // Delete the following 2 lines to resolve.
   int (D::* d)() = (int(D::*)()) &B::f;
   d;

   int (E::* e)() = (int(E::*)()) &B::f; // OK
   e;
}
```