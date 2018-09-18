---
title: Derleyici Uyarısı (düzey 1) c4584 arasındaki | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4584
dev_langs:
- C++
helpviewer_keywords:
- C4584
ms.assetid: ad86582f-cb8c-4d21-8c4c-a6c800059e25
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9db97bf35034f7ca628f860924bfb9a1fccc942f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46036260"
---
# <a name="compiler-warning-level-1-c4584"></a>Derleyici Uyarısı (düzey 1) c4584 arasındaki

'class1': taban sınıfı 'class2' temel sınıfı 'Ders3 alanları' nın bulunmakta

İki sınıflardan biri diğerinden devralan tanımladığınız sınıf devralır. Örneğin:

```
// C4584.cpp
// compile with: /W1 /LD
class A {
};

class B : public A {
};

class C : public A, public B { // C4584
};
```

Hem sınıf A ve B, a sınıfından devralan sınıf devraldığından bu durumda, bir uyarı sınıfı C verilmesi Bu uyarı, tam olarak bu temel sınıfların üyelerinden kullanımını nitelemeniz gerekir veya bir derleyici hatası hangi sınıf üyesi için başvuru belirsizlik nedeniyle oluşturulacak bir anımsatıcı olarak görev yapar.