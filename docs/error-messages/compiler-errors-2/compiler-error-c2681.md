---
title: Derleyici Hatası C2681
ms.date: 11/04/2016
f1_keywords:
- C2681
helpviewer_keywords:
- C2681
ms.assetid: eb42da6d-8d2c-43fd-986b-e73e2b004885
ms.openlocfilehash: 8b311052d3a3525090d954c0dc8cee20e985b1b4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50632706"
---
# <a name="compiler-error-c2681"></a>Derleyici Hatası C2681

'type': geçersiz ifade türü adı

Geçersiz bir türden dönüştürmek bir atama işleci çalıştı. Örneğin, kullanırsanız [dynamic_cast](../../cpp/dynamic-cast-operator.md) işleci bir ifade kaynak ifadesi bir işaretçi türüne dönüştürmek için bir işaretçi olması gerekir.

Aşağıdaki örnek, C2681 oluşturur:

```
// C2681.cpp
class A { virtual void f(); };

void g(int i) {
    A* pa;
    pa = dynamic_cast<A*>(i);  // C2681
}
```