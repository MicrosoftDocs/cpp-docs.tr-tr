---
title: Derleyici hatası C2243
ms.date: 11/04/2016
f1_keywords:
- C2243
helpviewer_keywords:
- C2243
ms.assetid: b90065bb-d251-4ba9-8b4c-280ee13fa9c0
ms.openlocfilehash: ab0dbe8c5595c18a01f78c22056803dce91a3f31
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87212845"
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
