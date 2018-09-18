---
title: Derleyici Uyarısı (düzey 4) C4913 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4913
dev_langs:
- C++
helpviewer_keywords:
- C4913
ms.assetid: b94aa52e-6029-4170-9134-017714931546
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2567659b4fee80a7e620bfbe29a4fba78c3aad44
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46041915"
---
# <a name="compiler-warning-level-4-c4913"></a>Derleyici Uyarısı (düzey 4) C4913

**Kullanıcı tanımlı ikili işleç ',' var ancak hiçbir aşırı yüklemesi dönüştüremedi tüm işlenenler, varsayılan yerleşik ikili operatör ',' kullanılan**

Yerleşik virgül işlecinin çağrısı bir aşırı yüklenmiş bir virgül işleci olan bir programda oluştu; bir düşünce oluşmuş olabilecek bir dönüştürme belirtmiyor.

Aşağıdaki kod örneği C4913 oluşturur:

```
// C4913.cpp
// compile with: /W4
struct A
{
};

struct S
{
};

struct B
{
   // B() { }
   // B(S &s) { s; }
};

B operator , (A a, B b)
{
   a;
   return b;
}

int main()
{
   A a;
   B b;
   S s;

   a, b;   // OK calls user defined operator
   a, s;   // C4913 uses builtin comma operator
           // uncomment the conversion code in B to resolve.
}
```