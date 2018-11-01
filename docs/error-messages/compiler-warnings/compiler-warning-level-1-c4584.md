---
title: Derleyici Uyarısı (düzey 1) c4584 arasındaki
ms.date: 11/04/2016
f1_keywords:
- C4584
helpviewer_keywords:
- C4584
ms.assetid: ad86582f-cb8c-4d21-8c4c-a6c800059e25
ms.openlocfilehash: 3c60575e766ea3490a40711fe26c3e402c41fbdd
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50552743"
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