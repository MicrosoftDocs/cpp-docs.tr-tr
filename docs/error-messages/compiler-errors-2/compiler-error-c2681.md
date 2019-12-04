---
title: Derleyici hatası C2681
ms.date: 11/04/2016
f1_keywords:
- C2681
helpviewer_keywords:
- C2681
ms.assetid: eb42da6d-8d2c-43fd-986b-e73e2b004885
ms.openlocfilehash: d7cf39e89f70f27471fb3a251aac12793f1fb33b
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74760302"
---
# <a name="compiler-error-c2681"></a>Derleyici hatası C2681

' Type ': ad için geçersiz ifade türü

Atama işleci geçersiz bir türden dönüştürmeye çalıştı. Örneğin, bir ifadeyi işaretçi türüne dönüştürmek için [dynamic_cast](../../cpp/dynamic-cast-operator.md) işlecini kullanırsanız, kaynak ifade bir işaretçi olmalıdır.

Aşağıdaki örnek C2681 oluşturur:

```cpp
// C2681.cpp
class A { virtual void f(); };

void g(int i) {
    A* pa;
    pa = dynamic_cast<A*>(i);  // C2681
}
```
