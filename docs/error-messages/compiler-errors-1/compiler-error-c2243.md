---
title: Derleyici hatası C2243
ms.date: 11/04/2016
f1_keywords:
- C2243
helpviewer_keywords:
- C2243
ms.assetid: b90065bb-d251-4ba9-8b4c-280ee13fa9c0
ms.openlocfilehash: f5a62b1c12b94735d0383697bf7a92d12d64b21f
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74757806"
---
# <a name="compiler-error-c2243"></a>Derleyici hatası C2243

' type1 ' öğesinden ' type2 ' öğesine ' dönüştürme türü ' dönüştürmesi var, ancak erişilebilir değil

Erişim Koruması (`protected` veya `private`), bir işaretçiden türetilmiş bir sınıfa, taban sınıfına olan işaretçiye dönüştürmeyi engelledi.

Aşağıdaki örnek C2243 oluşturur:

```cpp
// C2243.cpp
// compile with: /c
class B {};
class D : private B {};
class E : public B {};

D d;
B *p = &d;   // C2243

E e;
B *p2 = &e;
```

`protected` veya `private` erişimi olan temel sınıflara türetilmiş sınıfın istemcileri erişemez. Bu erişim denetimi düzeyleri, temel sınıfın istemciler için görünmezlik bir uygulama ayrıntısı olduğunu göstermek için kullanılır. Türetilmiş sınıfın istemcilerinin, bir türetilmiş sınıf işaretçisinin temel sınıfa yönelik bir işaretçiye örtük dönüştürülmesine erişmesini istiyorsanız ortak türetme kullanın.
