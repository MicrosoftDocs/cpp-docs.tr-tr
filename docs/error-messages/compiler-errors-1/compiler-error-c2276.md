---
title: Derleyici Hatası C2276 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2276
dev_langs:
- C++
helpviewer_keywords:
- C2276
ms.assetid: 62005ad9-6cb9-4b1f-965d-b875adaf695e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5a39c006acc3b5e3e74a738ba89c8ea6f56b889d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46114182"
---
# <a name="compiler-error-c2276"></a>Derleyici Hatası C2276

'operator': bağlı üye işlev ifadesinde geçersiz işlem

Derleyici, bir işaretçi-üye oluşturmak için söz dizimi ile ilgili bir sorun bulundu.

Aşağıdaki örnek, C2276 oluşturur:

```
// C2276.cpp
class A {
public:
   int func(){return 0;}
} a;

int (*pf)() = &a.func;   // C2276
// try the following line instead
// int (A::*pf3)() = &A::func;

class B {
public:
   void mf() {
      &this -> mf;   // C2276
      // try the following line instead
      // &B::mf;
   }
};

int main() {
   A a;
   &a.func;   // C2276
   // try the following line instead
   // &A::func;
}
```