---
title: Derleyici Hatası C2243 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2243
dev_langs:
- C++
helpviewer_keywords:
- C2243
ms.assetid: b90065bb-d251-4ba9-8b4c-280ee13fa9c0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ef5d3a6c20ff147ac2a4b765c7779cec9f19627e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46102235"
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