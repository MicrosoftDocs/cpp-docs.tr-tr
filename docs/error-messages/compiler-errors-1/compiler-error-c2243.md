---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2243'
title: Derleyici hatası C2243
ms.date: 11/04/2016
f1_keywords:
- C2243
helpviewer_keywords:
- C2243
ms.assetid: b90065bb-d251-4ba9-8b4c-280ee13fa9c0
ms.openlocfilehash: 48947ee39e61b2db1a64023f730b89d8be8d1907
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97302211"
---
# <a name="compiler-error-c2243"></a>Derleyici hatası C2243

' type1 ' öğesinden ' type2 ' öğesine ' dönüştürme türü ' dönüştürmesi var, ancak erişilebilir değil

Erişim Koruması ( **`protected`** veya **`private`** ), bir işaretçiden türetilmiş bir sınıfa, taban sınıfına olan işaretçiye dönüştürmeyi engelledi.

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

Veya erişimi olan temel sınıflara **`protected`** **`private`** türetilmiş sınıfın istemcileri erişemez. Bu erişim denetimi düzeyleri, temel sınıfın istemciler için görünmezlik bir uygulama ayrıntısı olduğunu göstermek için kullanılır. Türetilmiş sınıfın istemcilerinin, bir türetilmiş sınıf işaretçisinin temel sınıfa yönelik bir işaretçiye örtük dönüştürülmesine erişmesini istiyorsanız ortak türetme kullanın.
