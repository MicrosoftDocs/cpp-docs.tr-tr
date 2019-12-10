---
title: Derleyici Uyarısı (düzey 4) C4913
ms.date: 11/04/2016
f1_keywords:
- C4913
helpviewer_keywords:
- C4913
ms.assetid: b94aa52e-6029-4170-9134-017714931546
ms.openlocfilehash: 8858f116b34451e5c7509d9aff9bb99f438c3b36
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/10/2019
ms.locfileid: "74989010"
---
# <a name="compiler-warning-level-4-c4913"></a>Derleyici Uyarısı (düzey 4) C4913

**Kullanıcı tanımlı ', ' ikili işleci var, ancak hiçbir aşırı yükleme tüm işlenenleri dönüştüremiyor, varsayılan yerleşik ikili işleç ', ' kullanıldı**

Yerleşik virgül işlecine yapılan bir çağrı, aşırı yüklenmiş bir virgül işlecine sahip olan bir programda oluştu; oluşmuş olabilecek bir dönüştürme gerçekleşmedi.

Aşağıdaki kod örneği C4913 oluşturur:

```cpp
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
