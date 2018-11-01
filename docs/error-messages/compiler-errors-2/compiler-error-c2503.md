---
title: Derleyici Hatası C2503
ms.date: 11/04/2016
f1_keywords:
- C2503
helpviewer_keywords:
- C2503
ms.assetid: da86cc89-fd04-400b-aa8d-a5ffaf7e3918
ms.openlocfilehash: c481a27f19a92f47a19f0cfaa7b59cd509bb3c15
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50660817"
---
# <a name="compiler-error-c2503"></a>Derleyici Hatası C2503

'class': taban sınıflar sıfır boyutlu diziler içeremez

Bir temel sınıf veya yapı bir sıfır boyutlu dizi içeriyor. Bir sınıftaki bir dizi en az bir öğe olmalıdır.

Aşağıdaki örnek, C2503 oluşturur:

```
// C2503.cpp
// compile with: /c
class A {
   public:
   int array [];
};

class B : A {};    // C2503

class C {
public:
   int array [10];
};

class D : C {};
```