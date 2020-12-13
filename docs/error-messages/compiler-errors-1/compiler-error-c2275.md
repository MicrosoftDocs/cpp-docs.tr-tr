---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2275'
title: Derleyici hatası C2275
ms.date: 11/04/2016
f1_keywords:
- C2275
helpviewer_keywords:
- C2275
ms.assetid: c1eafa71-48de-46e0-82f3-b575538ef205
ms.openlocfilehash: c6bc03c630a859c2f0913fd482f463071a21758c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97134556"
---
# <a name="compiler-error-c2275"></a>Derleyici hatası C2275

' tanımlayıcı ': Bu tür geçersiz bir ifade olarak kullanım

Bir ifade `->` işleci bir tanımlayıcı ile kullanır **`typedef`** .

Aşağıdaki örnek C2275 oluşturur:

```cpp
// C2275.cpp
typedef struct S {
    int mem;
} *S_t;
void func1( int *parm );
void func2() {
    func1( &S_t->mem );   // C2275, S_t is a typedef
}
```
