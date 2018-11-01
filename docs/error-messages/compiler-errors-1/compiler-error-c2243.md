---
title: Derleyici Hatası C2243
ms.date: 11/04/2016
f1_keywords:
- C2243
helpviewer_keywords:
- C2243
ms.assetid: b90065bb-d251-4ba9-8b4c-280ee13fa9c0
ms.openlocfilehash: ded5a3d459e4b5d1412998aadbaa385864f505a6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50445558"
---
# <a name="compiler-error-c2243"></a>Derleyici Hatası C2243

'type1' öğesinden 'type2' 'dönüştürme türünü' dönüştürme var, ancak erişilebilir değil

Erişim Koruması (`protected` veya `private`) taban sınıfı işaretçisini bir türetilmiş sınıf işaretçisine dönüştürme engelledi.

Aşağıdaki örnek C2243 oluşturur:

```
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

Temel sınıflar ile `protected` veya `private` erişim türetilen sınıfın istemcilere erişilebilir değildir. Bu düzeyde erişim denetimi, temel sınıf istemcilere görünmez olması gereken bir uygulama ayrıntısı olduğunu belirtmek için kullanılır. Taban sınıfı işaretçisini bir türetilmiş sınıf işaretçisine örtük dönüştürme erişimi istemcilerin türetilen sınıfın istiyorsanız ortak türetme kullanın.